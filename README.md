# Prep Exercise: Conway's Game of Life

It is JavaScript simulation of Conway's Game of Life.

Conway's Game of Life is a zero-player game where cells in a 2D grid live or die based on specific rules:
1. A live cell with 2 or 3 live neighbors survives.
2. A dead cell with 3 live neighbors becomes alive.
3. All other cells either die or stay dead.

Every 200ms, a new generation replaces the previous one according to these rules.


### Task Instructions

1. **In `createCell()`**:
   - Add a numeric `lifeTime` property to the cell object.
   - Assign `lifeTime` the value `1` if the cell is initially alive or `0` if it is dead.

2. **In `drawCell()`**:
   - Replace `rgb()` with `rgba()` to add an opacity parameter to the color like this:

   ```javascript
   context.fillStyle = `rgba(24, 215, 236, ${opacity})`;
   ```

   - The opacity of each rendered cell should depend on the `lifeTime` property, according to the following table:

   | `lifeTime` | `opacity` |
   |------------|-----------|
   | 1          | 0.25      |
   | 2          | 0.5       |
   | 3          | 0.75      |
   | 4+         | 1         |

3. **In `updateGrid()`**:
   - Update the `lifeTime` value of each cell as follows:
     - A living cell that remains alive increments its `lifeTime` by one.
     - A living cell that dies resets its `lifeTime` to zero.
     - A dead cell that comes to life has its `lifeTime` reset to one.
