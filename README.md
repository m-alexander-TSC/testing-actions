# testing-actions

## Action testing releasing semantic versions
- A GitHub action creates a new semver version tag and release.  
- To advance the version, put `#patch`, `#minor`, or `#major` in a commit message.  Which ever is the highest increment will be applied (major/minor/patch)

### Want tagging to work like this [ecalidraw link](https://excalidraw.com/#json=69fKwjcotDyda3cG_igb6,IJSVoDb-0pxZfC2UPZglIg)
 
## Referencing templates in build & deploy yaml pipelines
As a consumer of this repo, you get two choices for how to do versioning:
- by git branch (`ref: refs/heads/<branch name>`)
```
resources:
  repositories:
    - repository: templates
      type: github
      name: m-alexander-TSC/testing-actions
      ref: refs/heads/<branch name>
      endpoint: TechSmith
```
- by git tag (`ref: refs/tags/<tag name>`)
```
resources:
  repositories:
    - repository: templates
      type: github
      name: m-alexander-TSC/testing-actions
      ref: refs/tags/<tag name>
      endpoint: TechSmith
```

### Semver tags
Tags are created and maintained to point at major and minor versions.  For each relase there will be a full version tag, `vX.Y.Z`.  Minor and major tags, `vX` and `vX.Y`, are created or updated depending on the release.  

- For a specific version:
```
      ref: refs/tags/vX.Y.Z
```
- For a minor version and all its patch releases
```
      ref: refs/tags/vX.Y
```
- For a major release and all minor and patch releases
```
      ref: refs/tags/vX
```

## References
Tagging task: https://github.com/anothrNick/github-tag-action
