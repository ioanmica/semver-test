# semver-test
Test semantic versioning process with a python project

(https://blog.guilatrova.dev/semantic-release-to-automate-versioning-and-publishing-to-pypi-with-github-actions/)

## Version display

```yaml
rev: v0.1.1
```

## Steps

* protect main branch and allow PRs only (Settings -> Branches -> add new rule for main) + test it
* test main branch protection -> git push origin main
* add/invite a colaborator in order to review the PRs (Settings -> manage access)

Init poetry project

* Since this will be a python project ensure Petry is installed (poetry --version)
* Poetry is a Dependency Manager for Pyton (poetry uses pyproject.toml)
* use 'poetry init' for an existing project or 'poetry new <proj_name>' for a new project (it will create/update the pyproject.toml file)

Init Semantic-release

* poetry add -D python-semantic-release
* define all the places where I want the version updated

``` toml
[tool.semantic_release]
version_variable = [
    "src/__main__.py:__version__"
]
version_toml = [
    "pyproject.toml:tool.poetry.version"
]
version_pattern = [
    "README.md:rev: v{version}" 
]
branch = "main"      # release from main branch
major_on_zero = true # until release become stable
# build_command="pip <something>"  # generate the final package
```