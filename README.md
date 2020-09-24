<p align="center">
  <a href="https://github.com/DanailMinchev/gatsby-starter-testing/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Project is released under the MIT license." />
  </a>
  <a href="https://github.com/DanailMinchev/gatsby-starter-testing/actions">
    <img src="https://github.com/DanailMinchev/gatsby-starter-testing/workflows/CI/badge.svg?branch=master" alt="GitHub Actions status" />
  </a>
  <a href="https://codecov.io/gh/DanailMinchev/gatsby-starter-testing">
    <img src="https://codecov.io/gh/DanailMinchev/gatsby-starter-testing/branch/master/graph/badge.svg" alt="Codecov status" />
  </a>
</p>

<p align="center">
  <a href="https://www.gatsbyjs.org">
    <img alt="Gatsby" src="https://www.gatsbyjs.com/Gatsby-Monogram.svg" width="64" />
  </a>
</p>
<h1 align="center">
  Gatsby Testing Starter
</h1>

Kick off your project with this default boilerplate. This starter ships with configured testing frameworks and tools for each layer of the Test Pyramid and more.

- Unit Testing: [Jest](https://jestjs.io/) with [React Testing Library](https://testing-library.com/docs/react-testing-library/intro)

- Structural Testing: [Jest Snapshot Testing](https://jestjs.io/docs/en/snapshot-testing)

- End-to-End Testing: [Cypress](https://www.cypress.io/) with [Cypress Testing Library](https://testing-library.com/docs/cypress-testing-library/intro)

- Accessibility Testing: [axe](https://www.deque.com/axe/) with [cypress-axe](https://github.com/avanslaars/cypress-axe)

- Automated Visual Testing:
  - [Storybook](https://storybook.js.org/) with [jest-puppeteer](https://github.com/smooth-code/jest-puppeteer) and [jest-image-snapshot](https://github.com/americanexpress/jest-image-snapshot)
  - [Cypress](https://www.cypress.io/) with [Cypress Image Snapshot](https://github.com/palmerhq/cypress-image-snapshot)

## 🚀 Quick start

1.  **Create a Gatsby site.**

    Use the Gatsby CLI to create a new site, specifying the starter.

    ```shell
    # create a new Gatsby site using the testing starter
    gatsby new my-testing-starter https://github.com/DanailMinchev/gatsby-starter-testing
    ```

2.  **Install dependencies.**

    Navigate into your new site's directory and install dependencies.

    ```shell
    cd my-testing-starter/
    npm ci
    ```

3.  **Run unit and structural tests.**

    After installing dependencies using `npm ci`, you can run the unit and structural tests in your site's directory.

    ```shell
    npm run test
    ```

    or you can run them in "watch" mode:

    ```shell
    npm run test:watch
    ```

    and you can update the Jest snapshots:

    ```shell
    npm run test:update
    ```

4.  **Run e2e (end-to-end), accessibility and visual tests using Cypress.**

    After installing dependencies using `npm ci`, you need to build the project to run e2e tests in `ci` mode.

    ```shell
    npm run build
    ```

    Then, you can run the tests using `test:e2e` which will run in `dev` or `ci` mode depending on machine type:

    ```shell
    npm run test:e2e
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    npm run test:e2e:update
    ```

    You can run e2e tests explicitly in `dev` mode with hot reloading:

    ```shell
    npm run test:e2e:dev
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    npm run test:e2e:dev:update
    ```

    You can run e2e tests explicitly in `ci` mode, the same way as it runs on your Continuous Integration (CI) platform:

    ```shell
    npm run test:e2e:ci
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    npm run test:e2e:ci:update
    ```

5.  **Run e2e (end-to-end), accessibility and visual tests using Cypress running in Docker.**

    You should have `XQuartz` installed and configured as described in [Running GUI applications using Docker for Mac](https://sourabhbajaj.com/blog/2017/02/07/gui-applications-docker-mac/)
    in case you would like to use `Cypress Test Runner` running in Docker on `macOS`.

    To run Cypress in Docker you can use similar commands as in point 4, but append `:docker` in the end.

    You can run the tests using `test:e2e:docker` which will run in `dev` or `ci` mode depending on machine type.

    The `test:e2e:docker` command is working only on macOS and before running it you should run `. docker/setupXQuartz.sh`:

    ```shell
    . docker/setupXQuartz.sh
    npm run test:e2e:docker
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    . docker/setupXQuartz.sh
    npm run test:e2e:docker:update
    ```

    You can run e2e tests explicitly in `dev` mode with hot reloading.

    The `test:e2e:dev:docker` command is working only on macOS and before running it you should run `. docker/setupXQuartz.sh`:

    ```shell
    . docker/setupXQuartz.sh
    npm run test:e2e:dev:docker
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    . docker/setupXQuartz.sh
    npm run test:e2e:dev:docker:update
    ```

    You can run e2e tests explicitly in `ci` mode, the same way as it runs on your Continuous Integration (CI) platform:

    ```shell
    npm run test:e2e:ci:docker
    ```

    Corresponding option to update image snapshots in this mode:

    ```shell
    npm run test:e2e:ci:docker:update
    ```

6.  **Run automated visual tests.**

    After installing dependencies using `npm ci`, you need to build the project to run Storybook and visual tests.

    ```shell
    npm run build
    ```

    Then, you can run the tests using `test:visual` which will start [Storybook](https://storybook.js.org/) and [Puppeteer](https://github.com/puppeteer/puppeteer):

    ```shell
    npm run test:visual
    ```

    and you can update the Jest image snapshots:

    ```shell
    npm run test:visual:update
    ```

7.  **Run automated visual tests in Docker.**

    To run automated visual tests in Docker you can use similar commands as in point 6, but append `:docker` in the end.

    You can run the tests using `test:visual:docker` which will start [Storybook](https://storybook.js.org/) and [Puppeteer](https://github.com/puppeteer/puppeteer) in Docker:

    ```shell
    npm run test:visual:docker
    ```

    and you can update the Jest image snapshots:

    ```shell
    npm run test:visual:docker:update
    ```

8.  **Start developing.**

    Navigate into your new site's directory and start the app using `develop` or `start` script,
    or if you prefer you can start it together with e2e tests in watch mode:

    ```shell
    cd my-testing-starter/
    npm run test:e2e
    ```

    and you can start unit tests in watch mode in another terminal:

    ```shell
    npm run test:watch
    ```

9.  **Open the source code and start editing!**

    Your site is now running at [http://localhost:8000/](http://localhost:8000/)!

    Open the `my-testing-starter` directory in your code editor of choice and edit `src/pages/index.js`.
    Save your changes and the browser will update in real time.
    The unit tests will re-run automatically and Cypress will reload the app so that you can re-trigger the Cypress tests.

10. **Commit your changes.**

    This project is using pre-commit hook to format your code with [Prettier](https://prettier.io/).
    [Husky](https://github.com/typicode/husky) with [lint-staged](https://github.com/okonet/lint-staged) are configured,
    so that when new files are staged and committed they will be formatted same way as `npm run format` command.

## ✅ Writing tests

There are few conventions when writing tests.

1.  **Automated Visual Testing and Storybook.**

    You can write your Storybook stories in `/stories/` directory and later you can write visual tests in `__visual_tests__/` directories.
    More information can be found [here](https://storybook.js.org/docs/testing/automated-visual-testing/#example-using-puppeteer-and-jest).

## ✅ Automated Visual Testing

There are two options for Automated Visual Testing:

- [Storybook](https://storybook.js.org/) with [jest-puppeteer](https://github.com/smooth-code/jest-puppeteer) and [jest-image-snapshot](https://github.com/americanexpress/jest-image-snapshot)
- [Cypress](https://www.cypress.io/) with [Cypress Image Snapshot](https://github.com/palmerhq/cypress-image-snapshot)

When creating the screenshots (image snapshots) there might be differences in font size or other platform specific rendering in the browser when running locally and on [CI](https://github.com/features/actions).

That is why it is better to run the visual tests inside [Docker](https://www.docker.com/), so that the same platform and browser is used locally and on CI.

For macOS users there is an option to run [Cypress Test Runner](https://docs.cypress.io/guides/core-concepts/test-runner.html#Overview) inside Docker as well.

Please see following articles:

- [Running GUI applications using Docker for Mac](https://sourabhbajaj.com/blog/2017/02/07/gui-applications-docker-mac/)
- [Run Cypress with a single Docker command](https://www.cypress.io/blog/2019/05/02/run-cypress-with-a-single-docker-command/)

## 🧐 What's inside?

A quick look at the top-level files and directories you'll see in a Gatsby project.

    .
    ├── .cache
    ├── .circleci
    ├── .github
    ├── .storybook
    ├── __mocks__
    ├── coverage
    ├── cypress
    ├── docker
    ├── node_modules
    ├── public
    ├── src
    ├── static
    ├── stories
    ├── storybook-static
    ├── .dockerignore
    ├── .gitattributes
    ├── .gitignore
    ├── .nvmrc
    ├── .prettierignore
    ├── .prettierrc
    ├── app.Dockerfile
    ├── CODE_OF_CONDUCT.md
    ├── CONTRIBUTING.md
    ├── cypress.json
    ├── gatsby-browser.js
    ├── gatsby-config.js
    ├── gatsby-node.js
    ├── gatsby-ssr.js
    ├── jest.config.js
    ├── jest.setup.js
    ├── jest.visual.config.js
    ├── jest-loadershim.js
    ├── jest-preprocess.js
    ├── jest-puppeteer.config.js
    ├── LICENSE
    ├── package.json
    ├── package-lock.json
    ├── README.md
    └── test.Dockerfile

1. **`.cache`**: This directory is autogenerated. This directory is internal to Gatsby used for caching.

2. **`.circleci`**: This directory is used by [CircleCI](https://circleci.com/) to build and test the project. The pipeline is defined in [.circleci/config.yml](.circleci/config.yml) file.

3. **`.github`**: This directory is used by [GitHub](https://github.com/). Currently, it has [Dependabot](.github/dependabot.yml) and [GitHub Actions](.github/workflows/ci.yml) files.

4. **`.storybook`**: This directory is used by [Storybook](https://storybook.js.org/) to store the configuration and setup as described [here](https://storybook.js.org/docs/configurations/overview/).

5. **`__mocks__`**: This directory is used by [Jest](https://jestjs.io/) to store various mocks as described [here](https://jestjs.io/docs/en/manual-mocks).

6. **`coverage`**: This directory is autogenerated. This directory is generated by [Jest](https://jestjs.io/) when running the tests and has test coverage reports.

7. **`cypress`**: This directory is used by [Cypress](https://www.cypress.io/) to store Cypress tests, fixtures, plugins and test artifacts (Cypress screenshots and videos) as described [here](https://docs.cypress.io/guides/core-concepts/writing-and-organizing-tests.html). The Cypress tests are located in `/cypress/e2e` directory.

8. **`docker`**: This directory is used by [Docker Compose](https://docs.docker.com/compose/) to run Docker containers used mainly for `Automated Visual Testing`.

9. **`node_modules`**: This directory is autogenerated when you run `npm run ci`. This directory contains all of the modules of code that your project depends on (npm packages) are automatically installed.

10. **`public`**: This directory is autogenerated when you run `npm run build`. This directory contains all of your application code and assets which can be deployed to production.

11. **`src`**: This directory will contain the source code of your application.

12. **`static`**: This directory will contain various assets which will be added to `public/` directory automatically when build the project. More information can be found [here](https://www.gatsbyjs.org/docs/static-folder/).

13. **`stories`**: This directory will contain various [stories](https://storybook.js.org/docs/basics/writing-stories/) for your application used by [Storybook](https://storybook.js.org/) as well as used for `Automated Visual Testing`.

14. **`storybook-static`**: This directory is autogenerated when you run `npm run build-storybook`. This directory will contain [Storybook](https://storybook.js.org/) application shipped with various [stories](https://storybook.js.org/docs/basics/writing-stories/). The directory can be shared or deployed within the team.

15. **`.dockerignore`**: This file tells [Docker](https://docs.docker.com/engine/reference/builder/#dockerignore-file) which files it should not send to Docker daemon when building the Docker images.

16. **`.gitattributes`**: This file is used by [Git](https://git-scm.com/) to define attributes to pathnames.

17. **`.gitignore`**: This file tells [Git](https://git-scm.com/) which files it should not track / not maintain a version history for.

18. **`.nvmrc`**: This file is used by [nvm](https://github.com/nvm-sh/nvm) to use the correct Node.js version for this application.

19. **`.prettierignore`**: This file tells [Prettier](https://prettier.io/) which files it should not format.

20. **`.prettierrc`**: This is a configuration file for [Prettier](https://prettier.io/). Prettier is a tool to help keep the formatting of your code consistent.

21. **`app.Dockerfile`**: This file is used by [Docker](https://docs.docker.com/engine/reference/builder/) and defines the Docker image for the app.

22. **`CODE_OF_CONDUCT.md`**: "Contributor Code of Conduct" document.

23. **`CONTRIBUTING.md`**: "Contributing" document.

24. **`cypress.json`**: This is a configuration file for [Cypress](https://www.cypress.io/). More information can be found [here](https://docs.cypress.io/guides/references/configuration.html).

25. **`gatsby-browser.js`**: This file is where Gatsby expects to find any usage of the [Gatsby browser APIs](https://www.gatsbyjs.org/docs/browser-apis/) (if any). These allow customization/extension of default Gatsby settings affecting the browser.

26. **`gatsby-config.js`**: This is the main configuration file for a Gatsby site. This is where you can specify information about your site (metadata) like the site title and description, which Gatsby plugins you'd like to include, etc. (Check out the [config docs](https://www.gatsbyjs.org/docs/gatsby-config/) for more detail).

27. **`gatsby-node.js`**: This file is where Gatsby expects to find any usage of the [Gatsby Node APIs](https://www.gatsbyjs.org/docs/node-apis/) (if any). These allow customization/extension of default Gatsby settings affecting pieces of the site build process.

28. **`gatsby-ssr.js`**: This file is where Gatsby expects to find any usage of the [Gatsby server-side rendering APIs](https://www.gatsbyjs.org/docs/ssr-apis/) (if any). These allow customization of default Gatsby settings affecting server-side rendering.

29. **`jest.config.js`**: This is a configuration file for [Jest](https://jestjs.io/) and it is used when you run `npm run test` for `Unit Testing` and `Structural Testing`. More information can be found [here](https://www.gatsbyjs.org/docs/unit-testing/) and [here](https://jestjs.io/docs/en/configuration).

30. **`jest.setup.js`**: This is a setup file for [Jest](https://jestjs.io/) that runs some code to configure or set up the testing framework before each test file in the suite while it is executed. More information can be found [here](https://jestjs.io/docs/en/configuration#setupfilesafterenv-array).

31. **`jest.visual.config.js`**: This is a configuration file for [Jest](https://jestjs.io/) and it is used when you run `npm run test:visual` for `Automated Visual Testing`. More information can be found [here](https://www.gatsbyjs.org/docs/unit-testing/) and [here](https://jestjs.io/docs/en/configuration).

32. **`jest-loadershim.js`**: This is a setup file for [Jest](https://jestjs.io/) and it is used to configure or set up the testing environment. More information can be found [here](https://jestjs.io/docs/en/configuration#setupfiles-array).

33. **`jest-preprocess.js`**: This is a setup file for [Jest](https://jestjs.io/) that defines transformers. More information can be found [here](https://jestjs.io/docs/en/configuration#transform-objectstring-pathtotransformer--pathtotransformer-object).

34. **`jest-puppeteer.config.js`**: This is a configuration file for [jest-puppeteer](https://github.com/smooth-code/jest-puppeteer) and it is used when you run `npm run test:visual` for `Automated Visual Testing`. More information can be found [here](https://storybook.js.org/docs/testing/automated-visual-testing/#example-using-puppeteer-and-jest).

35. **`LICENSE`**: Gatsby is licensed under the MIT license.

36. **`package.json`**: A manifest file for Node.js projects, which includes things like metadata (the project's name, author, etc). This manifest is how npm knows which packages to install for your project.

37. **`package-lock.json`** (See `package.json` above, first). This is an automatically generated file based on the exact versions of your npm dependencies that were installed for your project. **(You won't change this file directly).**

38. **`README.md`**: A text file containing useful reference information about your project.

39. **`test.Dockerfile`**: This file is used by [Docker](https://docs.docker.com/engine/reference/builder/) and defines the Docker image for `Automated Visual Testing`.
