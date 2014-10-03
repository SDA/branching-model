# How to use Git effectively

A simple, yet effective, git branching model.

Arguably, a solid text editor is all a good programmer needs although some
would argue that, aside from a debugger, a good version control system may
come in a close second spot. After all, no one wants their shiny new source
code to be accidentally overwritten by another team member.

A successful git branching model ...

## The trunk

This simple model works with just one required branch, `master`, which acts
as the trunk for the project.

It is perfectly okay to make all commits directly onto the `master` branch.
This is important so let's say it again: It is not necessary to create any
branches other than the `master` branch.

## Releases

As you get ready to release a new version of your product, you may want your
version control system to help you to:

1. Recover the exact version of all files that form part of the product release
2. Hot-fix bugs directly against the released version of files
3. Merge any hot-fixes onto the main trunk (ie. the `master` branch) so that future
   product releases will also benefit from the same fixes

Tag the release as `v1.0.0`. Leave it like that until and unless a hot fix is
needed. Then create a branch out of the tag, titled `r1.0.0`. Make your hot fix
directly on the new branch. Once done, merge the branch into `master`.

Follow semantic versioning (TBD provide link to definition)

## Stable environment while working

Disruptive changes are changes that could potentially prevent other team members
from being able to work effectively until you're done. For example, this could
be a feature that takes a long time to implement (well, more than a few minutes).
It's desirable to have everyone on the team working at capacity.

A simple way to accomplish this is to have developers create temporary local
branches for development work, where their changes could last long enough to
prevent other developers from working effectively.

Work locally on the master branch. So long as you don't need to pull, you will
have a stable environment. If you need to put your work aside in order to make
some other fixes in parallel, move your work to a temporary local branch. If
you only need to make a very quick fix, you can also stash your changes (then
unstash them after finishing the simple change you needed to do).

Don't push your temporary local branch to the shared repository, unless you are
looking to continue development on a different computer and this is the most
convenient, or only, option. Delete your temporary branch from the shared repo
as soon as you can. Leaving these temporary branches in the shared repository
doesn't provide any benefit and only clutters the repository.

