# testing-actions

## Action testing release version
- A GitHub action creates a new semver version tag and release.  
- A `latest` tag is recreated for the latest release.
- The versioning defaults to patch.  
- To advance the version, put `#patch`, `#minor`, or `#major ` in a commit message.  Which ever is the highest increment will be applied (major/minor/patch)
 
## Referencing templates in build & deploy yaml pipelines
```
resources:
  repositories:
    - repository: templates
      type: github
      name: m-alexander-TSC/testing-actions
      ref: refs/tags/latest
      endpoint: TechSmith
```
As a consumer of this repo, you get two choices for how to do versioning:
- by git branch (`ref: refs/heads/<branch name>`)
- by git tag (`ref: refs/tags/<tag name>`)

## References
Tagging task: https://github.com/anothrNick/github-tag-action
