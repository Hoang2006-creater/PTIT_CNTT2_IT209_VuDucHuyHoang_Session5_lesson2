# Bài 2: Tái cấu trúc lịch sử commit bằng Interactive Rebase

## 1. Mục tiêu

Sử dụng Interactive Rebase để tái cấu trúc lịch sử commit trên nhánh làm việc.

Các thao tác thực hiện:

* Gộp các commit nhỏ bằng `squash`.
* Đặt lại commit message.
* Xóa commit chứa file rác `temp.txt` bằng `drop`.

## 2. Các commit ban đầu

Ban đầu có 4 commit:

```text
feat: khoi tao module auth
fix typo
adds utility functions
add temp file for debug
```

## 3. Thực hiện Interactive Rebase

Sử dụng lệnh:

```bash
git rebase -i HEAD~4
```

Cấu hình Interactive Rebase:

```text
pick   <commit1> feat: khoi tao module auth
squash <commit2> fix typo
squash <commit3> adds utility functions
drop   <commit4> add temp file for debug
```

Sau đó đặt commit message thành:

```text
feat: hoan thien module authentication
```

## 4. Kiểm tra kết quả

Sử dụng:

```bash
git log --oneline
```

Kết quả cuối cùng:

```text
<commit-id> feat: hoan thien module authentication
```

Commit chứa file `temp.txt` đã được loại bỏ.

## 5. Kết luận

Đã hoàn thành việc tái cấu trúc lịch sử commit bằng Interactive Rebase. Các commit nhỏ đã được gộp thành một commit có ý nghĩa và commit chứa file rác `temp.txt` đã được xóa.
