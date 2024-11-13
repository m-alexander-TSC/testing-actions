# testing-actions

## Action testing releasing semantic versions
- A GitHub action creates a new semver version tag and release on merge to main.  
  - This is set to default to a patch release.
  - To advance a minor or major version, put `#minor`, or `#major` in a commit message.  Which ever is the highest increment will be applied (major/minor/patch).

## Referencing templates in build & deploy yaml pipelines
As a consumer of this repo there are two ways to do determine whihch version is used:
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
Tags are created and maintained to point at major and minor versions.  For each relase there will be a new full version tag, `vX.Y.Z`, created.  Minor and major tags, `vX` and `vX.Y`, are created or updated 

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

### `latest` tag
Additionally, there is a latest tag which will always point to the latest release
```
      ref: refs/tags/latest
```

## References
### Actions
- Version & tag: https://github.com/anothrNick/github-tag-action
- Create or replace tag: https://github.com/EndBug/latest-tag

v91