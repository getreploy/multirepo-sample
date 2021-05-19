# Reploy multirepo-sample

- This is an example project showing one approach to multi-repo staging environments across different branches.
- This top-level git repo has a `reploy.yml` to spin up all the services.
- different repos are set up as submodules. Reploy automatically does a recursive submodule clone, to pull all submodules.

- When setting up submodules, I recommend tracking the default branch. eg: `git submodule add -b main git@github.com:[owner]/[repo].git;`
- you can run `git submodule update --remote --recursive` to update all the submodules.

# How to test specific branches in staging

- TODO proper docs
  - basically, make a PR on this top level repo with the submodules checked out on the branches you want to test (or just leave them on the default branch to not change anything)
