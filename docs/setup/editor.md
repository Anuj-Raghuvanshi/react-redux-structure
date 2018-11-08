# Local Development Setup - Editor Configuration

The following plugins/extensions should be added to your code editor (or addressed in some fashion) in order to maintain clean code. Their configuration should not be modified unless discussed by the team. The rules these tools enfore will be cross-refrenced when reviewing code.

### [CSSComb](http://csscomb.com/)

- [Sublime](https://github.com/csscomb/sublime-csscomb)
- [VS Code](https://github.com/mrmlnc/vscode-csscomb)
- [Atom](https://atom.io/packages/atom-css-comb)

The CSS Comb allows us to format and priotize the CSS properties we define to keep the order consistent.

We use a slightly modified version of the [yandex](https://github.com/csscomb/csscomb.js/blob/master/config/yandex.json) comb for our CSS/SASS.

You can check out the CSS Comb config [here](../../.csscomb.json).

### [ESLint](https://eslint.org/)

- [Sublime](https://github.com/SublimeLinter/SublimeLinter-eslint)
- [VS Code](https://github.com/Microsoft/vscode-eslint)
- [Atom](https://atom.io/packages/linter-eslint)

The primary purpose for using a linter is to help prevent errors in the code by flagging syntax errors or potential issues.

We use the same linting configuration as `create-react-app` with a few modifications around prop types. You can read more about it [here](https://www.npmjs.com/package/eslint-config-react-app).

### [Prettier](https://prettier.io/)

- [Sublime](https://github.com/danreeves/sublime-prettier)
- [VS Code](https://github.com/prettier/prettier-vscode)
- [Atom](https://github.com/prettier/prettier-atom)

We use prettier to automatically format our code to the defined standard.

You can check out our Prettier config [here](../../.prettierrc).

### [Editorconfig](https://editorconfig.org/)

- [Sublime](https://github.com/sindresorhus/editorconfig-sublime)
- [VS Code](https://github.com/editorconfig/editorconfig-vscode)
- [Atom](https://github.com/sindresorhus/atom-editorconfig)

EditorConfig helps developers define and maintain consistent coding styles between different editors and IDEs.

You can check out our editorconfig [here](../../.editorconfig).
