# JavaScript Undecorators (Раздекоратор)

## Status

Stage: pre-proposal (-1)

## Contents

1. [Description](#description)
2. [Motivation](#motivation)
3. [Examples](#examples)

## Description

Syntax construction for _ejecting_ original method or class from its _decorated_ version.

## Motivation

[Decorator's proposal](https://github.com/tc39/proposal-decorators) makes possible modify behaviour 
of methods and classes. But sometimes consumer of decorated entities need invoke or construct original one.

## Examples

```javascript
// unicorn.mjs
import { @awesomeness } from 'awesome-decorators';

@awesomeness
export class Unicorn {
    constructor() {
        // Construct unicorn
    }
}

// index.mjs
import { Unicorn } from './unicorn.mjs';

const originalUnicorn = new @@Unicorn;
const decoratedUnicorn = new Unicorn;
```