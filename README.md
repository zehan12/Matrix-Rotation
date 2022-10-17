```js
function rotateNinetyDeg(squareMatrix) {
    let left = 0, right = squareMatrix.length - 1;
    while (left < right) {
        for (let i = 0; i < right - left; i++) {
            let top = left, bottom = right;

            // save top left
            let topLeft = squareMatrix[top][left + i];
            
            // swap top left and bottom left
            squareMatrix[top][left + i] = squareMatrix[bottom - i][left];

            // swap bottom left and bottom right
            squareMatrix[bottom - i][left] = squareMatrix[bottom][right - i];
            
            // swap bottom right and top right
            squareMatrix[bottom][right - i] = squareMatrix[top + i][right];

            // swap top right and top left
            squareMatrix[top + i][right] = topLeft;

        }
        left++;
        right--;
    }
}


let squareMatrix = [
    ['A', 'B', 'C', 'D'],
    ['E', 'F', 'G', 'H'],
    ['I', 'J', 'K', 'L'],
    ['M', 'N', 'O', 'P']
            ]

console.log('before');
console.log(squareMatrix);
rotateNinetyDeg(squareMatrix);
console.log('after');
console.log(squareMatrix);
```
