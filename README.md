# testing-actions

Action testing release version
- Action creates a new semver version
- Defaults to patch
- To advance the version, put `#patch`, `#minor`, or `#major ` in a commit message.  Which ever is the highest increment will be applied (major/minor/patch)
- reference templates with 'refs/latest'

## Testing
- To create a test release, set `PRERELEASE: true` in the 'bump-version.yml`

test33