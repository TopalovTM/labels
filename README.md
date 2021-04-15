# labels
Repo to push a standard set of labels to the other repos we use so that we have consistent labeling

## LICENSE

[Mozilla Public License Version 2.0](https://www.mozilla.org/en-US/MPL/2.0/) see [FAQ](https://www.mozilla.org/en-US/MPL/2.0/FAQ/) for more detail

## Automation

There's a GitHub Action `Sync` configured in this repo that runs `unify.py` to apply the labels from `github-labels.yaml` to the repos listed in `atsign-foundation.yaml`.
The action runs every time a change is pushed to this repo (such as an additon to the labels file).

There's also a `Newlabel` Action that adds runs when new labels are added to this repo, running `dump_github_labels.py` to create a new `github-labels.yaml`
and then `unify.py` to sync like above.

## Python scripts:

### clear_github_labels.py

Used to remove existing labels from a repo:  
`./clear_github_labels.py user/org_name repo_name`

### dump_github_labels.py

Dump the labels in an existing repo to a file:  
`./dump_github_labels.py github-labels.yaml user/org_name repo_name`

### list_org_repos.py

List the repos in an org to a file:  
`./list_org_repos.py myorg-repos.yaml org_name`

### push_github_labels.py

Push a set of labels from a file to a repo:  
`./push_github_labels.py github-labels.yaml user/org_name repo_name`

### unify_labels.py

Push a set of labels from a file to a list of repos within an org:  
`./unify_labels.py github-labels.yaml myorg-repos.yaml org_name`

## Lists:

### atsign-foundation-repos.yaml

Repos in the atsign-foundation org

### github-labels.yaml

Labels used across atsign orgs

### people-labels.yaml

Test set with additional label

### testrun.yaml

Smaller set of repos in atsign-foundation for testing

## Acknowledgement

Thanks to the [DXC Online DevOps Dojo](https://github.com/dxc-technology/online-devops-dojo) team for the [github-labels.py](https://github.com/dxc-technology/online-devops-dojo/blob/master/online-devops-dojo/welcome/assets/github-labels.py) script that's used in the Welcome module.
