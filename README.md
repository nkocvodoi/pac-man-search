# pac-man-search
Bai tap AI
   ***
Normal Game: 

Run file pacman-py (cmd: python pacman.py)
   
Question q1: Finding a Fixed Food Dot using Depth First Search
test cases:
 python pacman.py -l tinyMaze -p SearchAgent

 python pacman.py -l mediumMaze -p SearchAgent

 python pacman.py -l bigMaze -z .5 -p SearchAgent

Mô tả:
 stack - Sử dụng ngăn xếp(stack) để chứa các node trong quá trình duyệt DFS.
 check - Sử dụng set để lưu trữ các node đã duyệt qua.
 state - Thể hiện trạng thái(state) của node hiện tại.
 action - Các hành động đã thực thi từ vị trí bắt đầu đến vị trí hiện tại.

Mục tiêu
 ==> Duyệt DFS cho đến khi stack không còn phần tử nào/ khi đạt được tới goalState.

Question q2: Breadth First Search
test cases:
 python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs

 python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z .5

 python eightpuzzle.py

Mô tả: 
 Tương tự Question 1 nhưng thay vì sử dụng Stack thì ta sử dụng Queue để duyệt BFS

Mục tiêu
 ==> Duyệt BFS cho đến khi stack không còn phần tử nào/ khi đạt được tới goalState.

Question q3: Varying the Cost Function
test cases: 
 python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs

 python pacman.py -l mediumDottedMaze -p StayEastSearchAgent

 python pacman.py -l mediumScaryMaze -p StayWestSearchAgent

Mô tả:
 priorityQueue - Thay vì sử dụng Queue thông thường, ta sử dụng PriorityQueue (hàng đợi ưu tiên) để duyệt UCS. Các node có mức độ ưu tiên cao hơn (chi phí thấp hơn) sẽ được duyệt trước.
 check - Sử dụng set để lưu trữ các node đã duyệt qua.

Cải tiến:
Trong quá trình duyệt các node, nếu phát hiện ra chi phí thấp hơn để tới state thì tiến hành gán lại chi phí cho state trong check

Mục tiêu:
 Duyệt UCS cho đến khi nodePriorityQueue không còn phần tử nào/ khi đạt được tới goalState

Question q4: A* search
test cases:
 python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic

Mô tả:
 Sử dụng Priority Queue tương tự Question q3.
 Thay đổi công thức tính độ ưu tiên của từng node trong Priority Queue theo công thức F = G + H
 
Question q5: Finding All the Corners
test cases:
 python pacman.py -l tinyCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
 
 python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
 
Mô tả:
 Tại hàm init ta lưu lại trạng thái bắt đầu của Pacman, có thể lấy bằng hàm getStartState(...). Kiểm tra vị trí bắt đầu của Pacman có nằm ở góc không.
 Biến boolean isGoalState(...) kiểm tra Pacman đã tới tất cả các góc hay chưa và trả về giá trị True/False.
 getSuccessors(...) kiểm tra các hướng (xem có tường hay không), cập nhật trạng thái và trả về các successors có thể di chuyển đến.
 Sử dụng các thuật toán đã sử dụng ở các Question trên để giải quyết bài toán
 
Question q6: Corners Problem: Heuristic
test cases:
 python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.5
 
Mô tả: 

Question q7: Eating All The Dots
test cases: 
 python pacman.py -l testSearch -p AStarFoodSearchAgent
 
Mô tả: 

Question q8: Suboptimal Search
test cases:
 python pacman.py -l bigSearch -p ClosestDotSearchAgent -z .5

Mô tả:
 