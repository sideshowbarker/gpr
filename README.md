This script is intended to make it easier for project maintainers to check
out GitHub PR branches—including ones from external contributor forks—so
the maintainers can push changes to the branches and thus back to the PRs.

It takes as its sole argument either a GitHub PR URL or just a PR number,
then into the clone where it’s run, checks out the corresponding branch
from the PR contributor’s fork.

Fed just a PR number, it assumes you have an `upstream` or `origin` remote,
and uses that remote's URL to infer which repo the PR was submitted to.

If the remote has a GitHub SSH URL, then it uses an SSH URL for the fork,
which assumes you have write access to the contributor's branch.

### Checking out a PR branch

If your current directory is in a clone of the GitHub `whatwg/html` repo,
to check out the branch for PR #1871:

#### Example using just a PR number
```bash
gpr 1871
```

#### Example using a PR URL
```bash
gpr https://github.com/whatwg/html/pull/1871
```

You should see output similar to this:

```
Getting data for whatwg/html PR #1871...

Author: estark37 (Emily Stark)
Title:  Honor srcdoc document referrer policies when set

Preparing for checkout into 'estark37-srcdoc-meta-referrer-policy' local branch.
Adding new remote 'estark37'.
Fetching 'srcdoc-meta-referrer-policy' branch from remote 'estark37'.
Checking out into 'estark37-srcdoc-meta-referrer-policy' local branch.
Switched to a new branch 'estark37-srcdoc-meta-referrer-policy'
Branch estark37-srcdoc-meta-referrer-policy set up to track remote branch srcdoc-meta-referrer-policy from estark37.
```
