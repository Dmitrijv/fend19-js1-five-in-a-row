# FEND19 - JavaScript 1 - Five In a Row

![preview](/readme/fiveinarow.png)

## Description

Five In a Row is an abstract strategy board game. Players alternate turns placing a marker of their color on an empty board cell. The goal of the game is to order unbroken row of five markers horizontally, vertically, or diagonally.

## Win condition check

When a cell is clicked it's added to the list of cells owned by the active player.

```js
// all cell element IDs follow "cell-x-y" format
const coordinates = thisCell.getAttribute("id").match(/\d+/g);
const clickedCell = { x: Number(coordinates[0]), y: Number(coordinates[1]) };

PLAYER_INFO[activePlayer]["cells"].push(clickedCell);
```

After each successful click on a cell the game checks if the active player has won.

```js
if (hasPlayerWon(clickedCell, activePlayer) === true) {
  alert(PLAYER_INFO[activePlayer]["name"] + " wins !!!");
  clearBoard();
} else if (countAllClickedCells() === BOARD_WIDTH * BOARD_HEIGHT) {
  alert("Draw !!!");
  clearBoard();
}
```

Owned cells are used to determine if one of the winning conditions was triggered.

```js
function hasPlayerWon(clickedCell, activePlayer) {
  const ownedCells = PLAYER_INFO[activePlayer]["cells"];
  if (countHorizontalNeighbors(clickedCell) >= WINNING_LINE_LENGTH - 1) return true;
  else if (countVerticalNeighbors(clickedCell) >= WINNING_LINE_LENGTH - 1) return true;
  // and so on
```

Win conditions are determined by counting consecutive cells in various directions.

```js
function countHorizontalNeighbors(clickedCell) {
  return consecutiveCells(clickedCell, getNeighbourW) + consecutiveCells(clickedCell, getNeighbourE);
}
```

The number of consecutive cells is calculated by looking for a neigbour in a specific direction. If a neighbour is found the process is repeated with the new-found cell as the new starting point.

```js
function consecutiveCells(clickedCell, neighbourDirectionCheck) {
  let neighbours = 0;
  const pointerCell = { x: clickedCell.x, y: clickedCell.y };
  const maxDistance = Math.max(BOARD_WIDTH, BOARD_HEIGHT);
  while (neighbours < maxDistance) {
    const neighbourCell = neighbourDirectionCheck(pointerCell);
    if (neighbourCell) {
      neighbours++;
      pointerCell.x = neighbourCell.x;
      pointerCell.y = neighbourCell.y;
    } else {
      break;
    }
  }
  return neighbours;
}
```

Direction checks search ownedCells array for a cell with coordinates that a neigbour cell in that direction would have to have.

```js
function getNeighbourN(cell) {
  return ownedCells.find(neighbor => neighbor.y - 1 === cell.y && neighbor.x === cell.x);
}
```
