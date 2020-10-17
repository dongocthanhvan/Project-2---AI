# MultiAgent
Question 1 (4 points): Reflex Agent
 
  Chúng ta sẽ dùng list lấy ra vị trí của những thức ăn ở trạng thái hiện tại. Sau đó action= 'Stop' nếu gặp tường và return -Inf, pacman không thế đi được vị trí đó. Nếu không phải tường, ta chạy vòng for kiểm tra xe có gặp ma hay không. Nếu gặp ma thì pacman không đi nữa, trả về -Inf, còn nếu không gặp ma thì trả về khoảng cách đến thức ăn gần nhất
  
Question 2 (5 points): Minimax
   Chúng ta dùng để quy, kết thúc khi thua, thắng khi duyệt xong.Ta duyệt độ sâu bắt đầu 0 với hàng động của pacman bằng hàm findmax, hành động của ma với hàm findMin
   Hàm findMin để tìm ra giá trị nhỏ nhất của state khi ghost đang chạy. Nếu là state kết thúc sẽ trả về giá trị của state qua hàm evaluationFunction. Nếu chưa kết thúc thì ta sẽ xét từng hành động của một con ma, tính giá trị state của khi các từng ma hành động và trả về giá trị nhỏ nhất của chúng, xét đến ma cuối cùng. Sau đó, chúng ta sẽ thực hiện duyệt đến độ sâu tiếp theo bằng cách gọi findMax để xem hành động của pacman tiếp theo là gì.
   Hàm findMax để tìm ra giá trị lớn nhất của state khi ghost đang chạy. Nếu là state kết thúc sẽ trả về giá trị của state qua hàm evaluationFunction. Nếu chưa kết thúc thì ta sẽ xét từng hành động của pacman, tính giá trị state của hành động. Sau đó, chúng ta sẽ thực hiện duyệt đến độ sâu tiếp theo bằng cách gọi findMin để xem hành động của con ma tiếp theo là gì.

Question 3 (5 points): Alpha-Beta Pruning
   Trong hàm findMax, khi ta tìm được giá trị ở findMin nhỏ hơn Beta thì findMin kết thúc, nếu không thì gắn beta cho giá trị đó rồi tiếp tục thực hiện đến khi kết thúc. Trong hàm findMin, khi ta tìm được giá trị ở findMax lớn hơn Alpha thì findMax kết thúc, nếu không thì gắn Alpha cho giá trị đó rồi tiếp tục thực hiện đến khi kết thúc
(Biến Alpha lưu giá trị nhỏ nhất, Beta lưu giá trị lớn nhất)

Question 4 (5 points): Expectimax
Câu 4 khá giống câu minmax, nhưng khác nhau là expectimax sẽ lấy giá trị trung bình ở các Node của ghost 

Question 5 (6 points): Evaluation Function
Khá giống câu 1 nhưng thêm biến để tăng độ chính xác của bài