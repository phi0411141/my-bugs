# Hướng dẫn cài đặt
### Phần 1: Hệ thống phân loại công việc
*Yêu cầu: Python 3.6 trở lên* 
###### I. Windows
    1. [Tải gói numpy amd64 hoặc win32 tùy thuộc vào hệ thống](https://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy)
    2. [Tải gói scipy amd64 hoặc win32 tùy thuộc vào hệ thống](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy)
    3. Tải các gói cần thiết, gõ: "pip install flask flask_restful flask_cors nltk sklearn"
    4. Sử dụng các thư viện: Mở terminal ở thư mục pythonServer, gõ "python"
    5. Gõ "import nltk", sau đó gõ tuần tự các câu lệnh sau: 
      - "nltk.download('punkt')"
      - "nltk.download('wordnet')"
      - "nltk.download('stopwords')"
    6. Chạy hệ thống bằng lệnh: "python Server.py"
 
 ###### II. Linux (Ubuntu)
    1. Gõ "python -m pip install --user numpy scipy matplotlib ipython jupyter pandas sympy nose"
    3. Tải các gói cần thiết, gõ: "pip install flask flask_restful flask_cors nltk sklearn"
    4. Sử dụng các thư viện: Mở terminal ở thư mục pythonServer, gõ "python"
    5. Gõ "import nltk", sau đó gõ tuần tự các câu lệnh sau: 
      - "nltk.download('punkt')"
      - "nltk.download('wordnet')"
      - "nltk.download('stopwords')"
    6. Chạy hệ thống bằng lệnh: "python Server.py"
  
  ### Phần 2: Hệ thống back-end
  *Yêu cầu: [Nodejs 10.0 trở lên](https://nodejs.org/en/download/)  
            Hệ thống ở phần 1  
            [Hệ cơ sở dữ liệu Postgresql](https://www.postgresql.org/download/) (Cần lưu ý nếu hệ cơ sở dữ liệu đã có mật                 khẩu cho người dùng postgresql, cần sửa lại câu thông tin trong src/configs.js, phần DB_PASSWORD thành mật khẩu đã              có).*
  ###### I. Windows + Linux
    1. Tải redis: https://redislabs.com/ebook/appendix-a/a-3-installing-on-windows/a-3-2-installing-redis-on-window/ đối với Windows và sudo apt-get install redis-server đối với Linux.
    2. Mở terminal ở thư mục back-end.
    3. Gõ npm install -g yarn (Hệ thống back-end cần yarn để hoạt động).
    4. Gõ "yarn" để tải các thư viện cần thiết để khởi động hệ thống.
    5. Gõ "node -r esm index.js" để khởi động hệ thống (lưu ý, mỗi khi hệ thống khởi tạo sẽ chạy tạo mới dữ liệu).
    
  ### Phần 3: Hệ thống giao diện front-end
   *Yêu cầu: [Nodejs 10.0 trở lên](https://nodejs.org/en/download/)*
   ###### I. Windows + Linux    
    1. Mở terminal ở thư mục back-end.
    2. Gõ npm install -g yarn (Hệ thống front-end cần yarn để hoạt động).
    3. Gõ "yarn" để tải các thư viện cần thiết để khởi động hệ thống.
    4. Gõ "yarn start để khởi động hệ thống".
    5. Danh sách người dùng:
      - Sinh viên: student@gmail.com / 123
      - Giáo viên: teacher@gmail.com / 123
      - Phụ huynh: parent@gmail.com / 123
      
