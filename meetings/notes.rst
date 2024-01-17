===============
 Meeting Notes
===============

1/17/2024
=========

Attendees:
----------

Will Damon
Robert Cohn
Penporn Koanantakool
Alexey Kukanov
Maria Garzaran
Greg Lueck
Maria Kraynyuk
Rod Burns
Mehdi Goli
Timmie Smith
Ravindra Babu Ganapathi


Agenda:
-------

* Introductions
* Opens
* SYCL specification
* Review Operational Procedures
* Expanding participation beyond Intel
* Retrospective
* Publishing Infrastructure

Notes
-----

* Introductions
* Opens

  * Participation

    * Robert invited members of spec working group mailing list. Next
      time invite steering committee so they can invite their
      organizations.
    * Some difficulties connecting to zoom. Are mailing list and zoom
      login the same? Do people know guest registration is available?
    
* SYCL specification

  * Problem: oneAPI spec includes chapter defining required SYCL
    extensions. Not clear why we need it. Some members of Khronos SYCL
    working group feel that it is a competing specification
  * Robert proposed removing standalone chapter and components are
    free to list SYCL requirements in their spec.
  * Alexey wants important extensions with no line of sight to SYCL
    spec to be documented somewhere.
  * As an example, Alexey pointed out that DPL needs to document which
    std API can be used. This is mostly determined by SYCL support for
    use of std in kernels. He would rather SYCL/dpc++ document
    it. Greg said SYCL current spec does not require that any API, but
    SYCL working group acknowledges that a list is needed. There is a
    documented extension that lists API. oneAPI spec refers to that
    extension.
  * Not clear how to resolve this. Robert to follow up with Alexey,
    Greg, and other interested parties.

* Review Operational Procedures

  * Operational procedures are being finalized now so it would be good
    to understand their impact on how we develop spec and propose
    changes if necessary.
  * Documents: `UXLF Operational procedures`_ and `Robert's markup`_
  * We reviewed the highlighted sections. Most of the discussion was
    about how to interpret the document.
  * Robert called out the 7/14 day waiting period for accepting
    substantial changes. 3 required approvers. No one raised a strong
    objection at the meeting, team members will discuss it with their
    teams and provide feedback if there are issues. Rod proposed
    documenting the list of approvers.
    
* Expanding participation beyond Intel

  * There needs to be a clear path for new people to participate in
    specification development. A steering committee member said that
    onemkl was clear, but it was harder to find for oneDNN. This is
    odd because oneDNN has a lot of non Intel participation. Rod and
    Alison suggested projects pro-actively looking for reasons for
    connections with other projects. Robert will look at project
    documentation for how to get involved in specification if you are
    not already a member of the project.
    
* Retrospective

  * Now is a good time to make changes to the way we develop and
    publish specifications, so everyone is invited to raise issues and
    make proposals.
   
* Publishing Infrastructure

  * Robert wants to stop using Akamai/AWS to publish specs and move to
    GitHub pages. Akamai/AWS was managed by Intel IT and would not
    work well for non-Intel employees.

.. _`UXLF Operational procedures`: https://github.com/uxlfoundation/uxl_operational_procedures
.. _`Robert's markup` : presentations/operational_procedures_markup.pdf
