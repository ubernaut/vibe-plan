SEPARATION OF CONCERNS! 

create separate components with clean interfaces that can be easily tested, swapped out, etc. 

use the the LTS (best supported release version) of libraries wherever possible. 

use dependencies that are still supported

unless specified use more popular battle tested dependencies where possible. 

when making changes consider how these changes fit in with the overall architecture.

don't take shortcuts to add functionality. 

application design should be fractal. where common patterns and style are repeated throughout the entire codebase

performance is important.  choose algorithms and a concurrency model that leverages the hardware available.  for example, when writing GPU code leverage the vast concurrency available insted of sequential loops. 

## Branch-scoped development history

Maintain one detailed development log per Git branch under `plan/log/detail/`.
Replace `/` in the full branch name with `--` for the filename so parallel
branches do not edit the same log. Each branch updates only its own log; keep
the shared summary concise and retain branch logs after merge as history.


