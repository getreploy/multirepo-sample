# Reploy multirepo-sample

- _Important_ when adding a multi repo project on reploy, you must add permission to access all the individual repos when installing reploy on github. You can always click 'install reploy' again to add repos you missed.

  - If you miss this step, Reploy will fail to do a recursive clone. You'll see an error on the cache -> retrieval step for cloning.

- This is an example project showing one approach to multi-repo staging environments across different branches.
- This top-level git repo has a `reploy.yml` to spin up all the services.
- different repos are set up as submodules. Reploy automatically does a recursive submodule clone, to pull all submodules.

- When setting up submodules, You should use a relative path, and I recommend tracking the default branch. eg: `git submodule add -b main ../[repo].git;`
  - a relative path is required to let Reploy clone it either via https or via ssh, depending on the git host and how it's configured on Reploy.
- you can run `git submodule update --remote --recursive` to update all the submodules.

# How to test specific branches in staging

- check out the submodules to the branches that you wish to test. or, you can leave them on the default branch.
