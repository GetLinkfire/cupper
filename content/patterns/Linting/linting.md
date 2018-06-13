+++
title = "Linting"
tags = ["linting", "ember"]
+++

## General JavaScript Linting
eslint is used for JavaScript linting: [https://eslint.org/](https://eslint.org/)

Required plugins are as follows:
    [eslint-plugin-unicorn](https://github.com/sindresorhus/eslint-plugin-unicorn)
    [eslint-plugin-const-case](https://github.com/k03mad/eslint-plugin-const-case)

.eslintrc.js
```js
module.exports = {
  plugins: [
    'const-case',
    'unicorn'
  ],
  extends: [
    'eslint:recommended',
    'plugin:unicorn/recommended'
  ],
  rules: {
    'operator-linebreak': ['error', 'after'],
    'no-useless-escape': 'off',
    'const-case/uppercase': 'error',

    'capitalized-comments': ['error', 'always'],
    'no-inline-comments': 'error',

    'no-lonely-if': 'error',
    'no-mixed-operators': 'error',
    'no-mixed-spaces-and-tabs': 'error',
    'no-tabs': 'error',
    'no-multiple-empty-lines': ['error', { max: 1 }],
    'no-nested-ternary': 'error',
    'no-negated-condition': 'error',
    'no-unneeded-ternary': 'error',
    'no-whitespace-before-property': 'error',

    'nonblock-statement-body-position': ['error', 'beside'],
    'key-spacing': ['error', { 'mode': 'strict' }],
    'implicit-arrow-linebreak': ['error', 'beside'],
    'newline-per-chained-call': ['error', { 'ignoreChainWithDepth': 2 }],
    'padded-blocks': ['error', 'never'],
    'lines-between-class-members': [
      'error',
      'always',
      { 'exceptAfterSingleLine': true }
    ],
    'padding-line-between-statements': [
      'error',
      { 'blankLine': 'always', 'prev': 'multiline-block-like', 'next': '*' },
      { 'blankLine': 'always', 'prev': 'multiline-expression', 'next': '*' },
      { 'blankLine': 'always', 'prev': 'let', 'next': '*' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'let' },
      { 'blankLine': 'never', 'prev': 'let', 'next': 'let' },

      { 'blankLine': 'always', 'prev': '*', 'next': 'if' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'for' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'while' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'do' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'switch' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'try' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'throw' },
      { 'blankLine': 'always', 'prev': '*', 'next': 'return' }
    ],
    'array-bracket-newline': [
      'error',
      'consistent'
    ],
    'object-curly-newline': [
      'error',
      {
        'ObjectExpression': { 'minProperties': 3, 'consistent': true },
        'ObjectPattern': { 'minProperties': 3 },
        'ImportDeclaration': { 'minProperties': 3 },
        'ExportDeclaration': { 'minProperties': 3 }
      }
    ]
  }
};
```

## Ember Linting
Required plugins are as follows:

    [eslint-plugin-ember](https://github.com/ember-cli/eslint-plugin-ember)
    [eslint-plugin-ember-best-practices](https://github.com/ember-best-practices/eslint-plugin-ember-best-practices)
    [eslint-plugin-ember-suave](https://github.com/DockYard/eslint-plugin-ember-suave)

.eslintrc

```js
module.exports = {
  plugins: [
    'ember',
  ],
  extends: [
    'plugin:ember-suave/recommended',
    'plugin:ember-best-practices/recommended'
  ],
  rules: {
    'ember-best-practices/no-attrs-snapshot': 'error',
    'ember-best-practices/no-attrs': 'error',
    'ember-best-practices/no-broken-super-chain': 'error',
    'ember-best-practices/no-lifecycle-events': 'error',
    'ember-best-practices/no-global-jquery': 'off', // Will be covered in `eslint-plugin-ember` below
    'ember-best-practices/no-observers': 'error',
    'ember-best-practices/no-send-action': 'error',
    'ember-best-practices/no-side-effect-cp': 'error',
    'ember-best-practices/require-dependent-keys': 'error',

    'ember/alias-model-in-controller': 'error',
    'ember/new-module-imports': 'error',
    'ember/no-capital-letters-in-routes': 'error',
    'ember/no-duplicate-dependent-keys': 'error',
    'ember/no-empty-attrs': 'off',
    'ember/no-global-jquery': 'error',
    'ember/no-old-shims': 'error',
    'ember/no-side-effects': 'off',
    'ember/order-in-components': 'error',
    'ember/order-in-controllers': 'error',
    'ember/order-in-models': 'error',
    'ember/order-in-routes': 'error',
    'ember/routes-segments-snake-case': 'error',
    'ember/use-brace-expansion': 'error',
    'ember/use-ember-get-and-set': 'error'
  }
};
```

## Handlebars
Linter

ember-template-lint is used for Handlebars linting: [https://github.com/ember-template-lint/ember-template-lint](https://github.com/ember-template-lint/ember-template-lint)

Please also install ember-cli-template-lint as described in the readme for ember-template-lint.

.template-lintrc.js
```js

/* eslint-env node */
'use strict';

module.exports = {
  extends: 'recommended',

  rules: {
    'attribute-indentation': { 'open-invocation-max-len': 100 },
    'no-bare-strings': true,
    'inline-link-to': true,
    'no-inline-styles': true,
    'no-duplicate-attributes': true,
    'no-input-block': true,
    'no-input-tagname': true,
    'no-outlet-outside-routes': true,
    'no-partial': true,
    'no-trailing-spaces': true,
    'no-unbound': true,
    'quotes': 'single',
    'table-groups': true,
    'template-length': { max: 200, min: 1 }
  }
};
```

## CSS
Linter

stylelint is used for CSS linting: https://stylelint.io/

Required plugins are as follows:

    [stylelint-selector-bem-pattern](https://github.com/simonsmith/stylelint-selector-bem-pattern)

.stylelintrc

```js
{
  'plugins': [
    'stylelint-selector-bem-pattern'
  ],
  'rules': {
    'plugin/selector-bem-pattern': {
      'componentName': '[A-Z]+',
      'componentSelectors': {
        'initial': '^\\.{componentName}(?:-[a-z]+)?$',
        'combined': '^\\.combined-{componentName}-[a-z]+$'
      },
      'utilitySelectors': '^\\.util-[a-z]+$',
      'implicitComponents': true
    },
    'number-leading-zero': 'always',
    'indentation': 2,
    'string-quotes': 'single',
    'color-no-hex': true,

    'declaration-block-trailing-semicolon': 'always',
    'declaration-block-semicolon-newline-after': 'always',
    'comment-whitespace-inside': 'always',
    'comment-empty-line-before': [
      'always',
      'except': ['first-nested']
    ],
    'block-closing-brace-empty-line-before': 'never',
    'block-closing-brace-newline-after': 'always',
    'block-closing-brace-newline-before': 'always',
    'block-opening-brace-newline-after': 'always',
    'block-opening-brace-space-before': 'always',
    'rule-empty-line-before': [
      'always-multi-line',
      'except': ['first-nested', 'after-single-line-comment']
    ],
    'at-rule-empty-line-before': [
      'always',
      except: ['first-nested', 'blockless-after-same-name-blockless'],
      ignore: ['after-comment']
    ],

    'selector-list-comma-newline-after': 'always'
  }
}
```
