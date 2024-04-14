==========================
001: Removing SYCL Chapter
==========================

Remove the SYCL chapter from the oneAPI specification.

See also:

* `WG discussion`_

.. _`WG discussion`: https://github.com/uxlfoundation/spec-working-group/blob/main/meetings/notes.rst#notes

Background
==========

The SYCL chapter no longer serves a useful purpose and is causing some confusion
about UXL's role in SYCL. The original motivation for the chapter was that DPC++
was considered part of oneapi specification, and the chapter specifies the API
that DPC++ supports, which is SYCL 2020 + extensions. With the adoption of SYCL
2020, the need for extensions is reduced. DPC++ is not part of UXL. The hope is
that the SYCL support in DPC++ will be upstreamed in LLVM, and that would be the
home for specification of extensions, not the oneAPI specification.

After the initial WG discussion, I followed up with Alexey & Greg.

There are several issues:

1. Policy/Documentation about use of SYCL vendor extensions in interfaces that
   are part of oneapi spec
2. Policy/Documentation about use of SYCL vendor extensions in UXL open source
   projects.
3. Documentation of use of ``std::`` from SYCL kernels

Use of SYCL vendor extensions in interfaces
===========================================

I searched the header files by cloning all the UXL projects and the sources of
the spec::

    grep -n -r --include=\*.{h,hpp,rst} -E 'sycl::ext|ext_intel|ext_oneapi' .

After review, I don't believe that extensions are currently part of the API. The
closest to that is when a type defined in sycl::ext is made available in a
library namespace::

    namespace oneapi {
    namespace mkl {

    #ifndef __HIPSYCL__
    using bfloat16 = sycl::ext::oneapi::bfloat16;
    #endif


I believe this was done to make ``oneapi::mkl::bfloat16`` available.

Recommendation
    Oneapi spec components should not use vendor extensions in interfaces. Some
    alternatives are:
    
    * Wrap the type (example above)
    * Work with SYCL WG to make it part of the specification or a KHR extension.
      KHR extensions are Khronos extensions which have been approved in the SYCL
      WG and are more likely to be provided in more than one SYCL implementation.

    If using a vendor extension is the only way to achieve the desired behavior,
    then it should be documented in the specification.


Use of SYCL vendor extensions in implementations
================================================

Implementations need to use vendor extensions for best performance and
functionality. It would be useful if a project had a reference implementation
designed for maximum portability. This would be a good topic for the open source
WG and individual projects.

Recommendation
    Discuss reference implementations in the open source WG.

Documentation of use of ``std::`` from SYCL kernels
===================================================

SYCL specification does not support the use of ``std::`` in kernels and does not
provide replacements. oneDPL wants to support standard C++ where ``std::`` would
be used in code called from a kernel. DPL documents a list of ``std::``
functions that are supported. It would be better if the SYCL specification or
SYCL implementation documentation defined what can be used. This documentation
would be useful for other projects. It has been discussed in the SYCL WG.

Recommendation
    Raise it as a topic in the SYCL WG and DPC++ project.
