# ISLAND PERIMETER

You are given a map in form of a two-dimensional integer grid where 1 represents land and 0 represents water.

Grid cells are connected horizontally/vertically (not diagonally). The grid is completely surrounded by water, and there is exactly one island (i.e., one or more connected land cells).

The island doesn't have "lakes" (water inside that isn't connected to the water around the island). One cell is a square with side length 1. The grid is rectangular, width and height don't exceed 100. Determine the perimeter of the island.

### Example:
<pre>
Input:
[[0,1,0,0],
 [1,1,1,0],
 [0,1,0,0],
 [1,1,0,0]]

Output: 16

</pre>

### Solution:

```cpp


class Solution {
public:
    int islandPerimeter(vector<vector<int>> &grid) {
        if (grid.empty()) return 0;
        int perimeter = 0;
        int ros = grid.size();
        int cos = grid[0].size();
        for (int r = 0; r < ros; ++r) {
            for (int c = 0; c < cos; ++c) {
                if (grid[r][c]) {
                    if (r == 0 || !grid[r-1][c]) ++perimeter;
                    if ((r == ros - 1) || !grid[r+1][c]) ++perimeter;
                    if ((c == cos - 1) || !grid[r][c+1]) ++perimeter;
                    if ((c == 0) || (!grid[r][c-1])) ++perimeter;
                }
            }
        }
        return perimeter;
    }
};

```
