# This repository is archived under Pulsar due to no longer being in use. This module was remove from `atom/text-buffer` in [`atom/text-buffer#181`](https://github.com/atom/text-buffer/pull/181).

# line-length-index

This is a module used by Atom to keep track of the row with the longest line
length.

## Example

```js
let lineLengthIndex = new LineLengthIndex()

// Splice at a start row with a replacement row count
// and an array of line lengths...
lineLengthIndex.splice(0, 0, [10, 40, 10, 50, 10])

// Now you can efficiently query the point at the end of the longest row
lineLengthIndex.getPointWithMaxLineLength() // => {row: 3, column: 50}

// As text changes, you can splice in new rows
lineLengthIndex.splice(2, 2, [30, 20])

// And the max row is available...
lineLengthIndex.getPointWithMaxLineLength() // => {row: 1, column: 40}
```
