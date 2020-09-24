# Hướng Dẫn Thực Hiện Code Review Cho Developer

## Giới Thiệu {#intro}

Code review là quá trình mà một người nào đó phân tích, xem xét một phần code do người khác viết.

Ở Google, chúng tôi sử dụng code review để đảm bảo chất lượng code và sản phẩm.

Tài liệu này bao gồm các đặc tả tiêu chuẩn về quá trình và chính sách review code ở Google.

Đây là trang tổng quan về quá trình review code của chúng tôi. Ngoài ra còn có hai tài liệu khác cũng bao gốm trong loạt hướng dẫn này:

-   **[Cách Thực Hiện Code Review](reviewer/index.md)**: Hướng dẫn chi tiết cho người review.
-   **[Hướng Dẫn Cho Người Tạo CL](developer/index.md)**: Hướng dẫn chi tiết cho developer có CL được review.

## Người Review Code Nên Chú Ý Đến Cái Gì? {#look_for}

-   **Thiết kế**: Code có được thiết kế tốt và phù hợp với hệ thống không?
-   **Chức năng**: Code có hoạt động đúng như người viết dự tính hay không? Cách mà đoạn code hoạt động có tốt cho người dùng nó hay không?
-   **Tính phức tạp**: Có thể làm cho đoạn code đơn giản hơn không? Liệu một developer khác có dễ dàng hiểu và sử dụng nó trong tương lai hay không?
-   **Test**: Đoạn code có được viết automated test thiết kế tốt và đúng đắn hay khộng?
-   **Cách đặt tên**: Developer có đặt tên với ý nghĩa rõ ràng cho biến, class, hàm.v.v.. hay chưa?
-   **Comment**: Comment có rõ ràng và hữu dụng hay không?
-   **Style**: Code có được định dạng theo đúng
    [hướng dẫn về style](http://google.github.io/styleguide/) hay không?
-   **Tài liệu/chú thích (documentation)**: Developer đã cập nhật tài liệu/chú thích liên quan đến đoạn code hay chưa?

Xem thêm **[Cách Thực Hiện Code Review](reviewer/index.md)** để hiểu rõ hơn.

### Chọn Người Review Tốt Nhất {#best_reviewers}

Nhìn chung, bạn sẽ muốn tìm người review *tốt nhất* có thể, người có khả năng tham gia/phản hồi lại review của bạn trong khoảng thời gian hợp lý.

Người review tốt nhất là người có khả năng review code kỹ càng và chính xác nhất cho đoạn code mà bạn đang viết. Thường thì đó có nghĩa là người từng viết đoạn code đó, không nhất thiết phải là người trong file OWNERS.
Đôi khi điều đó nghĩa là bạn phải nhờ những người khác nhau review những đoạn code khác nhau trong một CL.

Nếu bạn tìm thấy người review lý tưởng nhưng vì lý do nào đó mà người ta đang bận thì ít nhất bạn cũng nên CC cho người đó biết về đoạn code bạn đã sửa.

### Review Trực Tiếp {#in_person}

Nếu bạn pair-programming với một người có đủ khả năng review tốt đoạn code đang viết, thì đoạn code coi như đã được review.
If you pair-programmed a piece of code with somebody who was qualified to do a
good code review on it, then that code is considered reviewed.

Bạn cũng thể thực hiện việc review trực tiếp theo kiểu người review sẽ đặt các câu hỏi và người viết code trực tiếp trả lời.

## Xem Thêm {#seealso}

-   [Cách Thực Hiện Code Review](reviewer/index.md): Hướng dẫn chi tiết cho người review.
-   [Hướng Dẫn Cho Người Tạo CL](developer/index.md): Hướng dẫn chi tiết cho developer có CL được review.
