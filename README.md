# JavaScript Loose vs. Strict Comparison Bug

This repository demonstrates a common, yet subtle, bug in JavaScript related to loose comparison (==) versus strict comparison (===). The code appears to correctly handle null, negative, and positive numbers; however, it fails with an unexpected output when given an input of 0.

The bug arises because of JavaScript's loose comparison. The `if (x === null)` condition only checks for strict equality, therefore `0` is not equal to `null`. However, when `x` is `0`, the else block is executed resulting in the unexpected return value of `1`.

## Bug Explanation

The `else if (x < 0)` condition isn't met when `x` is 0 which leads the code to execute the `else` block always returning `1` when `x` is `0`. This is a classic example of how loose comparison can lead to unexpected behavior.