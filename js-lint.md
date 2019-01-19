# Js Lint #

- Install globally as well locally for project `eslint` using npm.
    - For local `npm install eslint --save-dev`.
    - For global `npm install -g eslint`.
- Install related plugin for `eslint` in project directory.
    ```
        - npm i eslint-config-airbnb-base,
        - npm i eslint-plugin-import,
        - npm i eslint-plugin-vue,
        - npm i stylelint,
        - npm i stylelint-config-idiomatic-order
    ```
- Update `package.json` with lint.
    ```
    "scripts": {
        "lint": "eslint --fix resources/  webpack.mix.js --ext .js,.vue && stylelint resources/sass/**/*.scss resources/sass/*.scss --fix",
        "lint:ci": "eslint resources/ webpack.mix.js --ext .js,.vue && stylelint resources/sass/**/*.scss resources/sass/*.scss",
        "lint:js": "eslint --fix resources/ webpack.mix.js --ext .js,.vue",
        "lint:styles": "stylelint resources/sass/**/*.scss resources/sass/*.scss --fix",
    }
    ```
- Now make file in root directory of project with name of `eslintrc.js`.
- Add below content in this file.
    ```
        module.exports = {
        "env": {
            "browser": true,
            "node": true,
            "jasmine": true,
            "jest": true,
            "jquery": true,
        },
        "globals": {
            "_": true,
            "afterEach": true,
            "axios": true,
            "beforeEach": true,
            "config": true,
            "describe": true,
            "expect": true,
            "google": true,
            "it": true,
            "jest": true,
            "mockFn": true,
            "pit": true,
            "require": true,
            "runs": true,
            "test": true,
            "waitsFor": true,
            "xdescribe": true,
            "xit": true,
        },
        "extends": [
            "airbnb-base",
            "plugin:vue/recommended",
        ],
        "plugins": [
            "vue",
        ],
        // We use the Airbnb base template. These rules are override preferences
        // that we have that aren't covered in their template.
        "rules": {
            "array-bracket-spacing": ["error", "always"],
            "arrow-parens": ["error", "as-needed"],
            "comma-dangle": ["error", "always-multiline"],
            "import/prefer-default-export": "off",
            "indent": ["error", 4],
            "max-len": ["error", 120],
            "no-console": ["error", {"allow": ["warn", "error"]}],
            "no-param-reassign": [2, {"props": false}],
            "prefer-destructuring": ["error", {
                "array": false,
                "object": true,
            }],
            "semi": 0,
            "space-before-function-paren": ["error", "never"],
            // eslint-plugin-vue specific rules
            "vue/html-indent": ["error", 4],
            "vue/script-indent": ["error", 4],
            "vue/html-self-closing": ["error", {
                "html": {
                    "component": "never"
                }
            }]
        },
    }
    ```
- Now make another file stylelint with name of `stylelintrc.json`.
    ```
    {
        "extends": "stylelint-config-idiomatic-order",
        "rules": {
            "at-rule-no-unknown": null,
            "indentation": 4
        }
    }
    ```
- run `npm run lint`.    
