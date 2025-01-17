---
title: no-empty-class
layout: doc
edit_link: https://github.com/eslint/eslint/edit/main/docs/src/rules/no-empty-class.md

---

Disallows empty character classes in regular expressions.

(removed) This rule was **removed** in ESLint v1.0 and **replaced** by the [no-empty-character-class](no-empty-character-class) rule.

Empty character classes in regular expressions do not match anything and can result in code that may not work as intended.

```js
var foo = /^abc[]/;
```

## Rule Details

This rule is aimed at highlighting possible typos and unexpected behavior in regular expressions which may arise from the use of empty character classes.

Examples of **incorrect** code for this rule:

::: incorrect

```js
var foo = /^abc[]/;

/^abc[]/.test(foo);

bar.match(/^abc[]/);
```

:::

Examples of **correct** code for this rule:

::: correct

```js
var foo = /^abc/;

var foo = /^abc[a-z]/;

var bar = new RegExp("^abc[]");
```

:::
