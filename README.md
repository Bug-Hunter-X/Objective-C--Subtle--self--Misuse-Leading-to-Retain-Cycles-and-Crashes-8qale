# Objective-C `self` Misuse: Retain Cycles and Crashes

This repository demonstrates a common yet subtle bug in Objective-C related to the misuse of `self`, particularly within methods and blocks.  Improper handling of `self` can lead to retain cycles or crashes, making it crucial to understand and avoid these pitfalls.

## Bug Description
The bug involves incorrect usage of `self` in property setters and within blocks that are dispatched asynchronously.  In the property setter example, a retain cycle is created due to improper self reference, while in the asynchronous block scenario, accessing `self` after it has been deallocated results in a crash.

## Solution
The solution addresses these issues by employing proper memory management techniques and using weak references (`__weak`) where appropriate.  Specifically, this involves preventing self-retaining in the property setter and using weak references to `self` within asynchronous blocks.