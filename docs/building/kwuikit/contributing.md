# KW UI Kit - Contributing

If you see that a component can be improved or a component is missing all together, feel free to contribute to the UI Kit!

### Guidelines

- Utilize the GitFlow branching model
- Update supporting documentation
- Create a pull request off of the `develop` branch for contributions

### Testing

Use Test-Driven Development and tests are added, updated or removed respective to your modifications

This library utilizes [Jest](https://facebook.github.io/jest/) as the test runner and assertion library and [Enzyme](http://airbnb.io/enzyme/) for utilities and renderer. There are several different test commands available:

| Command                 | Result / Description                                  |
| :---------------------- | :---------------------------------------------------- |
| `npm run test`          | Runs all available tests in the library a single time |
| `npm run test:watch`    | Runs all available tests in the library in watch mode |
| `npm run test:coverage` | Generates a testing coverage report for the library   |
