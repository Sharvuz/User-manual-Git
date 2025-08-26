# I. Giới thiệu Git (Cre: HaoSvit)

* **Tóm tắt:**
  - Git dùng để quản lý phiên bản code, rất thuận lợi trong làm việc nhóm thậm chí làm 1 mình.  
  - Git có nhiều trang hỗ trợ như: [github.com](https://github.com), [bitbucket.com](https://bitbucket.com), ...  
    Không phải Git là chỉ riêng trang GitHub, Git giống như là 1 **chuẩn quản lý phiên bản**.  
    Ngoài ra còn có **SVN** là 1 chuẩn khác để quản lý phiên bản (theo cách hiểu của t).

---

# II. Các khái niệm trong Git
- **Repository (kho):** là thư mục.  
  - Thư mục trên github.com gọi là **remote repository (kho xa)**.  
  - Thư mục ở máy tính gọi là **local repository**.  

- **Branch (nhánh):**  
  Ví dụ: t làm 1 phần trên 1 nhánh, m rẽ sang nhánh khác làm chức năng khác, sau này hợp lại (**merge**).  

- **Remote (máy chủ):** khỏi giải thích, lát ví dụ.  

- **add (thêm):** sau khi làm gì đó thay đổi thì add cái thay đổi đó vào.  

- **commit:** chốt thay đổi.  

- **pull (kéo về):** lấy code của người làm chung đã push lên.  
  - Pull từ branch nào về branch hiện tại cũng được.  
  - Nếu pull từ branch khác thì sẽ có **merge** xảy ra.  
  - Nếu pull từ cùng branch thì giống như update code base.  
  - Khi mình làm thay đổi dưới local trùng với chỗ người nào đó đã sửa và push lên (nhưng mình chưa pull về trước đó), thì khi pull về sẽ có **conflict**.  
    - *Conflict* nghĩa là “đụng độ”.  
    - Khi code bị conflict, cần phải **resolve conflict** bằng cách chọn thay đổi nào giữ lại, cái nào bỏ đi, hoặc giữ lại cả 2 và chỉnh sửa cho chạy được.  

- **push (đẩy):** đưa code lên remote repository (đẩy lên để người khác kéo về).  

- **Collaborators:** làm việc nhóm với git như nào:  
  - Ai tạo repos thì vào đây:  
    `https://github.com/<tên_tài_khoản>/<tên_repos>/settings/collaboration`  
  - Gõ email GitHub của thành viên. Người được mời đồng ý thì làm chung thôi.  

---

# III. Ví dụ thực tế
1. **Tải Git:** [https://git-scm.com/](https://git-scm.com/)  

2. **Tạo remote repository** (thư mục trên github.com) – đó là chỗ khi push code lên. Repo sẽ có 1 đường dẫn, đuôi là `.git`.  
   - Ví dụ: `https://github.com/Haosvit/QLPV.git`  
   - Việc này phải tạo trên GitHub → bấm nút **New repository**.  

3. **Tạo thư mục chứa code ở máy tính.**  

4. **Khởi tạo Git trong thư mục mới:**  
   ```bash
   git init
# Liên kết thư mục local với repository trên GitHub:
- git remote add origin <đường_dẫn_đến_repo_trên_github>
# Ví dụ:
- git remote add origin https://github.com/Haosvit/QLPV.git
# Lấy nội dung trên GitHub về:
- git pull origin master
# Quy trình khi thay đổi code ở local:
- git add *                     # Thêm thay đổi
- git commit -m "nội dung đã thực hiện"   # Ghi chú commit
- git push origin master        # Đẩy code lên GitHub
# Khi có người khác push code mới, lấy về:
- git pull origin master

