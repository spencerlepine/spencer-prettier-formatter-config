# Spencer's Prettier Formatter Config

Shared [Prettier](https://github.com/prettier/prettier) configuration to enforce standard code formatting, along with [Husky](https://github.com/typicode/husky) + [Lint-Staged](https://github.com/lint-staged/lint-staged) (for a pre-commit hook)

## Setup

1. Install the package:

```sh
npm install @spencerlepine/prettier-formatter-config --save-dev
npm install husky@4.3.8 lint-staged@10.5.4 prettier@2.8.8 --save-dev
```

2. Update your `package.json`:

```json
{
  "name": "@org/example-package",
  // ...
  "scripts": {
    "format": "prettier --write ."
  },
  "prettier": "@spencerlepine/prettier-formatter-config",
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "**/*.(js|jsx|ts|tsx|json|css|md)": [
      "prettier --write"
    ]
  }
}
```

3. (optional) One-time cleanup to format the entire codebase

```sh
npx prettier --write .
```
