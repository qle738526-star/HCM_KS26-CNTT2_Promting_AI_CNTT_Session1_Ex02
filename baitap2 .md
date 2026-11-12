**Bài 2: \[Vận dụng cơ bản 2\] Khắc phục lỗi rò rỉ dữ liệu mật khi chat với AI công cộng**

**1: các thông tin nhạy cảm:**

\-            db\_password : chứa mất khẩu của cơ sở dữ liệu  
\-            api\_key : Chứa khóa bảo mật của API hệ thống

**2: Làm sạch code**

def connect\_database():  
     db\_password \= \[YOUR\_DATABASE\_PASSWORD\]'  
     api\_key \= \[YOUR\_API\_KEY\]'  
     print('Đang kết nối...')

**2.1: viết prompt an toàn**

"Tôi có đoạn code Python kết nối database. Tôi đã che mật khẩu và API key bằng \[YOUR\_DATABASE\_PASSWORD\] và \[YOUR\_API\_KEY\]. Hãy tối ưu đoạn code này cho tôi để quản lý cấu hình và bảo mật tốt hơn trong thực tế.

**3\. Kết quả lời khuyên tối ưu của AI:**

* **Bạn không nên gán cứng (hardcode) trực tiếp biến vào file. Hãy dùng thư viện os để lấy thông tin từ biến môi trường (Environment Variables).**  
* **Code tối ưu (AI viết lại):**

**import os**

**def connect\_database():**

	**db\_password \= os.getenv('DB\_PASSWORD')**

	**api\_key \= os.getenv('API\_KEY')**

	    **if not db\_password or not api\_key:**

        **print("Lỗi: Thiếu biến môi trường\!")**

    	**return**

   	**print('Đang kết nối an toàn...')**

