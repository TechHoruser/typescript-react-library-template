<p align="center">
  <a href="https://github.com/TechHoruser">
    <img src="https://avatars.githubusercontent.com/u/14580756" alt="TechHoruser logo"/>
  </a>
</p>

<h1 align="center">
  <⚡⚛️> Vite React Library Template
</h1>

<p align="center">
    <a href="https://github.com/TechHoruser/typescript-react-library-template/actions/workflows/ci.yml"><img src="https://github.com/TechHoruser/typescript-react-library-template/actions/workflows/ci.yml/badge.svg" alt="Build status"/></a>
</p>

## ⚡ Using this Vite template

1. Create your project based on this template:
   - a) If you want to create a GitHub repository, we would recommend to use the GitHub "Use this template" button and clone your newly created repository
   - b) If you prefer to just create a local project, you can use [degit](https://github.com/Rich-Harris/degit):
     ```bash
     npx degit TechHoruser/typescript-react-library-template#main my-app
     ```
2. Update your project meta-information:
   - [ ] Update the [`package.json`](https://github.com/TechHoruser/typescript-react-library-template/blob/main/package.json):
     - [ ] Specify proper values for the `name`, `author` and `license` properties
     - [ ] Specify the file name for the `main` and `module` properties
     - [ ] If you wish to expose multiple entry points, follow this structure:
     ```
      {
        "name": "my-component",
        "type": "module",
        "files": ["dist"],
        "main": "./dist/my-component.cjs",
        "module": "./dist/my-component.js",
        "exports": {
          ".": {
            "import": "./dist/my-component.js",
            "require": "./dist/my-component.cjs"
          },
          "./secondary": {
            "import": "./dist/secondary.js",
            "require": "./dist/secondary.cjs"
          }
        }
      }
      ```
   - [ ] Change the `name` and `fileName` in [`vite.config.ts`](https://github.com/TechHoruser/typescript-react-library-template/blob/main/vite.config.ts) to match the file name specified in the `package.json`
   - [ ] Change the author in [`LICENSE`](https://github.com/TechHoruser/typescript-react-library-template/blob/main/LICENSE)
   - [ ] If you want to create a private component, you need to change `access: public` into `publish.yml` file and `"private": false,` into `package.json` file
   - [ ] Clean up this [`README.md`](https://github.com/TechHoruser/typescript-react-library-template/blob/main/README.md)
3. Set up your GitHub Actions workflow:
   - [ ] If you do **not** wish to publish to npm, you can delete the `.github/workflows/publish.yml`
   - [ ] If you do wish to publish to npm, you can delete the `.github/workflows/CI.yml` and set up your token following [the instructions below](#-ci-and-publishing).
4. Run your library:
   2. `npm install`: Install all the project dependencies
   3. `npm run cy:open`: Start cypress
   3. `npm run docs`: Start the Storybook dev mode on [localhost:6006](http://localhost:6006)

## 📚 Documentation

- `npm run docs`: Run Storybook documentation in dev mode
- `npm run build:docs`: Build Storybook documentation

## ✅ Testing

This template comes with both Jest and Cypress component testing. Since this is a template for a component library, we feel it doesn't make sense to use the `e2e` Cypress option, but feel free to change it to your needs.

### Unit tests

`npm run test`: Run unit tests with Jest and React Testing Library
`npm run test:watch`: Run unit tests on watch mode

### Component tests

```
  npm run cy:open: Open Cypress in dev mode
  npm run cy:run: Execute Cypress in CLI
```

## 🔦 Linting

- `npm run lint`: Run linter
- `npm run lint:fix`: Fix lint issues

## 🚀 CI and Publishing

This template comes with a GitHub Actions workflow to automatically publish on any push to `main` when the `package.json` version number differs from the latest on npm. Please note that you need to create the package on NPM first.

For it to work you will need to add an `NPM_TOKEN` secret to your repo:

1. Create an automation token in NPM
   - [Documentation on npm tokens](https://docs.npmjs.com/about-access-tokens) and how to create them
2. Go to your GitHub Repository Settings / Secrets / Actions
3. Click on the "New repository secret" button
4. Fill in the form:
   - Name: `NPM_TOKEN`
   - Secret: the NPM token value

Read the [full documentation on the npm-publish action](https://github.com/JS-DevTools/npm-publish).

## 🌈 Tech Stack

- [TypeScript](https://www.typescriptlang.org)
- [Storybook](https://storybook.js.org/)
- [ESLint](https://eslint.org) and [Prettier](https://prettier.io)
- [Jest](https://jestjs.io) with [React Testing Library](https://testing-library.com/docs/react-testing-library/intro) for the unit tests
- [Cypress](https://www.cypress.io/) with [Testing Library](https://testing-library.com/docs/cypress-testing-library) for acceptance/component tests
- [GitHub Action Workflows](https://github.com/features/actions) set up to run tests and linting on push
- [Makefile](https://github.com/TechHoruser/typescript-react-library-template/blob/main/Makefile) for standardize how to run projects
- [Sass](https://sass-lang.com) to supercharge CSS with nested classes and more fun
- [.editorconfig](https://editorconfig.org) for sharing the IDE config

## 🤔 FAQ

### 👻 Why not adding `.vscode` or `.idea` to the `.gitignore` template

These are folders created due to personal environment preferences. We should ignore these personal development environment preferences to be ignored using your global `.gitignore` file and leave the project `.gitignore` file as clean as possible, that is, only containing the project specific rules.

You can create a `.gitignore_global` file with rules that will apply to all your repositories with:

```bash
touch ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```

## 🔀 Related information

This application was generated using the [<⚡⚛️> TypeScript React Library Template](https://github.com/TechHoruser/typescript-react-library-template). Feel free to check it out and star the repo! 🌟😊🙌
