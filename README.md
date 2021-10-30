# semver-test
Test semantic versioning process with a python project


## Steps

* protect main branch and allow PRs only (Settings -> Branches -> add new rule for main) + test it
* test main branch protection -> git push origin main
* add/invite a colaborator in order to review the PRs (Settings -> manage access)

Init poetry project

* Since this will be a python project ensure Petry is installed (poetry --version)
* Poetry is a Dependency Manager for Pyton (poetry uses pyproject.toml)
* use 'poetry init' for an existing project or 'poetry new <proj_name>' for a new project (it will create/update the pyproject.toml file)

Init Semantic-release

* 