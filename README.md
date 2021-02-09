# TypeScript template

A template for creating TypeScript projects. It is preconfigured all the basics you'd want when using TypeScript.

- TypeScript support
- ESLint configuration
- Jest setup
- CI/CD pipeline with Github actions
- Almost zero config npm publishing

## Installation

This is a template repository. So follow [GitHub's instructions for creating a new repository based on this template](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template).

All dependencies should be up-to-date, so just run `npm i` to install the dependencies.

## Build

To build your scripts:

```bash
npm run build
```

## ESLint

If you use VS Code, everything will be linted and formatted on every save.

Alternatively, you can run:

```bash
npm run lint
```

## Jest

Jest is already setup. Any `*.test.ts` files will be run when testing. For organization, this template includes a `__tests__` folder for you to put all your tests into.

To run the tests:

```bash
npm run test # or
npm run test:watch
```

## CI/CD

### Dependabot

Dependabot update your dependencies automatically. This includes both your npm dependencies and the GitHub Actions dependencies.

By default, this is done every day. However, you can choose to update dependencies weekly. In `.github/dependabot.yml`, just change `daily` to `weekly`.

Before merging, every update will be tested and linted. That ensures that these updates don't produce breaking changes so long as you have decent test coverage.

### Continuous integration

All pull requests and pushes to GitHub will automatically lint, test, and build the entire repository.

See these GitHub Actions:

- `.github/workflows/main.yml`
- `.github/workflows/test-pull-requests.yml`

### Continuous deployment

If you're creating an npm package, this template can automatically deploy your package to npm on Mondays and Fridays. That way, the npm package can always be up-to-date (including with updated dependencies) even without any maintenance by you.

To do so, just uncomment the entire `.github/workflows/deploy.yml` file.

## Publish to npm

Just change the `name` in the `package.json` and run `npm publish`.

Version bumps and publishing will run lint, test, and build the package, so you can be confident that you're never publishing broken code to npm.
