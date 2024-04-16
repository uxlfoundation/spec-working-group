===========================================
Moving to uxlfoundation GitHub Organization
===========================================

Move repo to https://github.com/uxlfoundation/oneapi-spec

Background
==========

Repo is currently location in https://github.com/oneapi-src organization. The
repo is being moved to uxlfoundation organization because oneapi-src is owned by
Intel and contains projects that are not part of UXL.

How it will happen
==================

The repo will be moved to the new org, including PR's, issues, etc. The
following teams will be created in the uxlfoundation org with the same
membership:

* oneapi-spec-maintainers
* oneapi-spec-owners

Documentation that is hosted in GitHub pages will move. Redirects will be setup
for the top level:

* https://oneapi-src.github.io/oneAPI-spec/spec/
* https://oneapi-src.github.io/oneAPI-spec/spec/oneAPI-spec.pdf


GitHub automatically forwards traffic to the old URL to the new URL, so links
and git remotes will continue to work.

Auto-completion of names, e.g. ``@rscohn2`` only works for org members so that
may no longer work. Feel free to request that names be added to uxlfoundation
org.

When: 4/22/2024
