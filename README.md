# MongoDB $inc operator silently fails on non-existent field

This repository demonstrates a common error when using MongoDB's `$inc` operator. The `$inc` operator is used to increment or decrement a numeric field in a document. However, if the field does not exist, the operation will fail silently, which can be hard to debug. 

The `bug.js` file shows the problematic code where `$inc` is used to decrement the `count` field. If `count` does not exist in the document, the operation fails without an error. The `bugSolution.js` file shows the corrected code that checks for the existence of the field using the `$setOnInsert` operator, ensuring a smooth operation in all cases.

## How to reproduce

1.  Clone this repository.
2.  Install MongoDB.
3.  Run `bug.js` and `bugSolution.js`.
4. Observe the outcomes to understand the difference in handling the non-existent field.