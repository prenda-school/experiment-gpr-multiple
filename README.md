# experiment-gpr-multiple
Experimenting with GitHub Packages.

This is a repository for publishing multiple packages to the GitHub Packages npm registry from a single repository.

### Guide (specific to our organization)
1. Follow "Guide" for publishing a single package, [here](https://github.com/prenda-school/experiment-gpr-single#guide-specific-to-our-organization)
  - Where appropriate, substitute mentions of "project/repository" with "package root within your project/repository"
2. In the `package.json` file for a given package within your repository, specify the `"directory"` field of the `"repository"` field with the location of your package root, relative to the repository root.
```bash
  "repository": {
    "type": "git",
    "url": "git+https://github.com/prenda-school/experiment-gpr-multiple.git",
    "directory": "packages/experiment-gpr-multiple-first"
  },
```
3. In your release workflow file, add the directory name of your package to your publish command
```yml
run: npm publish packages/experiment-gpr-multiple-first
```

#### Sources
- Reference: https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#publishing-multiple-packages-to-the-same-repository

#### See more
- [repository publishing a single package](https://github.com/prenda-school/experiment-gpr-single)
- [repository publishing consuming packages](https://github.com/prenda-school/experiment-gpr-consumer)
