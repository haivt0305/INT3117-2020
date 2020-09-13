Ảnh 1: Tìm vị trí cuối cùng của phần tử
(a) Kết quả sai do ở vòng for duyệt phần tử từ vị trí i=length – 1 đến vị trí i=1 (vì i > 0 nên chỉ duyệt đến i=1) nên kết quả ra sai.
Cách sửa: thay i>0 thành i>=0

(b) Tất cả các đầu vào đều gây ra lỗi, vì không duyệt phần tử ở vị trí 0. 

(c) Input : x = [2, 1, 0, 3],  y=0
    Expected output: 2
    Actual output: 2

(d) Input : x = [1, 1, 0, 1], y=1
     Expected output: 3
     Actual output: 3

(e) Input : x = [2, 3, 5], y=2
   Expected output: 0
   Actual output: -1
  Code chạy:
  x = [2, 3, 5]
  i=2  có x[i] = 5 (!= 2) bỏ qua, i--
  i=1 có x[i] = 3 (!= 2) bỏ qua, i--
  i=0 thoát vòng lặp vì chỉ lấy i>0, lấy giá trị return -1.
=> Actual ouput: -1

(f) Sửa lại:
public int findLast (int[] x, int y) {
        for (int i=x.length-1; i>=0; i--) 
        {
            if (x[i] == y) {
                return i;
            }
        }
        return -1;
    }
Input: x = [2, 3, 5], y = 2
Output: 0

Ảnh 2: Tìm vị trí cuối của số 0.
(a) Kết quả sai do vì 0 xuất hiện ở vị trí 0 nên khi x[i] == 0 nên chương trình đã trả về kết quả 0, chương trình sẽ trả kết quả ngay khi có sự xuất hiện 0.
Cách sửa: thay vì duyệt từ đầu mảng, ta duyệt từ cuối mảng.

(b) Tất cả các đầu vào đều gây ra lỗi, vì không duyệt phần tử ở vị trí 0. 

(c) Input : x = [2, 1, 0, 1]
   Expected output: 2
   Actual output: 2

(d) Input : x = [2, 1, 0]    
    Expected output: 2    
    Actual output: 2

(e) Input : x = [0, 1, 0]    
     Expected output: 2   
     Actual output: 0
     Code chạy: x = [0, 1, 0]    
                       i=0 có x[i]=0 nên trả về kết quả là 0.

(f) Sửa lại:
 public static int lastZero (int[] x) {
        for (int i=x.length-1; i >= 0; i--) 
        {
            if (x[i] == 0) {
                return i;
            }
        }
        return -1;
    }
Input : x = [0, 1, 0]
Output: 2

 Ảnh 3: Đếm giá trị dương
(a) Kết quả sai do giá trị dương lớn hơn 0 nhưng trong chương trình lại so sánh các giá trị trong mảng lớn hơn hoặc bằng 0.
Cách sửa: thay x[i] >= 0 thành x[i] > 0

(b) Đầu vào là rỗng. Những đầu vào khác dẫn đến lỗi vẫn được thực thi.
Input : x = []
Expected output:  0
Actual output: 0

(c) Input : x = [2, 1, 3]
    Expected output: 3
    Actual output: 3
(d) Input : x = [2, 1, 1]     
     Expected output: 3    
     Actual output: 3

(e) Input : x = [-4, 2, 0, 2]
     Expected output: 2   
     Actual output: 3
Code chạy: x = [-4, 2, 0, 2]
	i = 0, x[i] = -4 (<0), count = 0.
	i = 1, x[i] = 2 (>0), count++ => count = 1.
	i = 2, x[i] = 0 (=0), count++ => count = 2.
	i = 3, x[i] = 2 (>0), count++ => count = 3.
	=> Actual output: 3

(f) Sửa lại:
public int countPositive(int[] x) {
        int count = 0;
        for (int i=0; i<x.length; i++) 
        {
            if (x[i] > 0) 
            {
                count++;
            }
        }
        return count;
    }

Ảnh 4: Đếm phần tử lẻ hoặc dương
(a) Kết quả sai do điều kiện if, vì trong mảng -3 là số lẻ âm nên điều kiện x[i] % 2 == 1 là sai trong trường hợp số lẻ âm.
Cách sửa: thay x[i]%2 == 1 thành Math.abs(x[i])%2 == 1.

(b) Đầu vào là rỗng. Những đầu vào khác dẫn đến lỗi vẫn được thực thi.
Input : x = []
Expected output:  0
Actual output: 0

(c)Tất cả đầu vào có giá trị dương
     Input: x = [2, 1, 4, 5]
     Expected output: 4
     Actual output: 4

(d) Input : x = [2, 1, 4]
     Expected output: 3
     Actual output: 3

(e) Input : x = [-3, -2, 0, 1, 4]
     Expected output:  3
    Actual output: 2
    Code chạy: x = [-3, -2, 0, 1, 4]
	     count = 0
	     i=0 thì x[i] = -3 (<0 và chia cho 2 dư -1), count = 0
	     i=1 thì x[i] = -2 (< 0 và chia cho 2 dư 0), count = 0
	     i=2 thì x[i] = 0  (= 0 và chia cho 2 dư 0), count = 0
	     i=3 thì x[i] = 1  (> 0), count = 1
	     i=4 thì x[i] = 4  (> 0), count = 2
    	=>Actual output: 2     

(f) Cài đặt:
public static int oddOrPos(int[] x){
        int count = 0;
        for (int i=0; i<x.length; i++)
        {
            if (Math.abs(x[i])%2 == 1 || x[i] > 0)
            {
                count++;
            }
        }
        return count;
    } 
Input: x = [-3, -2, 0, 1, 4]
Output: 3
