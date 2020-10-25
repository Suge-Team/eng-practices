# Quy Chuẩn Của Code Review


Mục đích chính của code review là đảm bảo chất lượng tổng thể code base của Google được cải thiện qua thời gian. Tất cả các công cụ và tiến trình (process) đều được thiết kế cho mục tiêu này.

Để có thể đạt được điều này, những điểm được-mất (trade-off) sẽ được cân nhắc thực hiện một cách cân bằng.

Đầu tiên, developer phải _tạo được progress_ cho task của mình. Nếu bạn không bao giờ tạo PR đề xuất các cải thiện cho code base, thì code base đó sẽ không bao giờ tốt lên được. Và, nếu người review làm khó, quá khắt khe cho _bất kỳ_ thay đổi nào có thể merge, thì developer có thể nản lòng và mất động lực để tiếp tục đề xuất các cải thiện trong tương lai.

Mặt khác, người review cũng phải có bổn phận đảm bảo rằng mỗi CL phải đủ tốt dể chất lượng tổng thể của code base không bị giảm qua thời gian. Điều này cũng tương đối khó, bởi vì chất lượng code base sẽ bị giảm dần từ những những tích lũy nhỏ. Đặc biệt khi team đang bị áp lực về thời gian, họ thường cảm thấy cần đi đường tắt, dùng các biện pháp tạm thời để hoàn thành mục tiêu của mình.

Người review thường có ownership và trách nhiệm với phần code họ đang review. Vì thế họ sẽ muốn đảm bảo cho code base luôn nhất quán, dễ bảo trì, cũng như tất cả các tiêu chí khác được đề cập tới trong mục ["Chú ý tới điều gì khi thực hiện code review."](looking-for.md)

Vì vậy, chúng ta có quy tắc sau có thể coi như tiêu chuản trong code review:

**Nhìn chung, người review nên chấp nhập một CL khi chắc chắn rằng điều đó sẽ cải thiện chất lượng tổng thể của hệ thống đang được phát triển, mặc dù có thể CL đó chưa được hoàn hảo.**

Đó _là_ nguyên tắc cốt yếu nhất trong tất cả các nguyên tắc hướng dẫn về code review.

Tất nhiên cũng có những giới hạn. Ví dụ khi CL thêm một tính năng mà người review không muốn có trong hệ thống của mình, thì người review có thể từ chối CL đó mặc dù thiết kế của CL đã được làm rất tốt.

Điểm quan trọng ở đây là, không có khái niệm code "hoàn hảo"&mdash;chỉ có code "tốt hơn" mà thôi. Người review không cần thiết bắt người viết code phải sửa tất cả những thứ nhỏ nhặt trong CL trước khi chấp nhận (approve) đoạn code đó. Họ nên cân bằng giữa sự cần thiết của việc giữ tiến độ (make progress) so với mức độ quan trọng của những thay đổi họ đề xuất. Thay vì theo đuổi sự hoàn hảo, người review nên theo đuổi _việc cải thiện liên tục_ (continuous improvement). Một CL về mặt tổng thể, giúp cải thiện tính bảo trì, dễ đọc dễ hiểu của hệ thống thì không nên bị trì trệ (delay) trong nhiều ngày, nhiều tuần chỉ vì nó không "hoàn hảo".

Tất nhiên người review nên tự do comment những điểm mà họ nghĩ có thể tốt hơn, nhưng nếu nó không quan trọng lắm, hãy để lại lưu ý trước comment, ví dụ "Nit: " để người viết code biết rằng đó là chỗ có thể làm tốt hơn, nhưng có thể bỏ qua.

Ghi chú: Nothing in this document justifies checking in CLs that definitely
_worsen_ the overall code health of the system. The only time you would do that
would be in an [emergency](../emergencies.md).

## Kèm cặp (Mentoring)

Người review có thể có vai trò quan trọng trong việc dạy developer những điểm mới về ngôn ngữ lập trình, framework, hoặc những nguyên tắc thiết kế phần mềm cơ bản. Viết comment giúp một developer học những cái mới luôn là điều tốt. Chia sẻ kiến thức cũng là một cách để cải thiện chất lượng mã nguồn qua thời gian. Cần chú ý rằng nếu comment của bạn chỉ đơn thuần là chỉ dạy một điều gì đó, không quan trọng phải tuân theo những tiêu chuẩn đề cập trong tài liệu này, thì bạn nhớ băt đầu comment bằng "Nit: " hoặc ghi rõ ra là người viết CL không bắt buộc phải sửa theo comment.

## Nguyên tắc {#principles}

*   Dữ liệu và sự thực (fact) về kỹ thuật luôn luôn được ưu tiên hơn quan điểm và sở thích cá nhân.

*   Nói đến style, [hướng dẫn về style](http://google.github.io/styleguide/) có quyền cao nhất. Những style không được nếu ra trong tài liệu hướng dẫn (ví dụ khoảng trăng.v.v..) thì tùy sở thích cá nhân. Tuy nhiên nó nên thống nhất với style có sẵn của code. Nếu trước đấy không có style cụ thể nào, hãy chấp nhận style của tác giả đoạn code.

*   **Thiết kế phần mềm không phải là vấn đề về style hoặc sở thích cá nhân**. Nó phải dựa trên các nguyên tắc định sẵn, chứ không chỉ đơn giản dựa trên ý kiến của một người nào đó. Đôi khi sẽ có một vài lựa chọn với giá trị tương đương nhau, mà nếu developer có thể chứng minh điều đó (có dữ liệu hoặc dựa trên những nguyên tắc về enginneering) thì người review có thể nghe theo quyết định của developer. Ngược lại, nếu chỉ có một lựa chọn tuân theo tiêu chuẩn về thiết kế phần mềm, hãy làm theo nó.

*   Nếu không có nguyên tắc nào để áp dụng, thì người review có thể yêu cầu developer thống nhất về style với codebase có sẵn, miễn là nó không làm giảm chất lượng code tổng thể của hệ thống.

## Giải Quyết Xung Đột {#conflicts}

Nếu có xung đột xảy ra trong code review, bước đầu tiên developer và người review phải đi đến cùng một kết luận cùng nhau, dựa trên nội dung của tài liệu này, cũng như trong [Hướng dẫn cho tác giả CL](../developer/) và [Hướng dẫn cho người review](index.md).

Khi gặp khó khăn trong việc đi đến kết luận thống nhất, việc gọi nói chuyện trực tiếp giữa developer và người review sẽ tốt hơn là cố gắng giải quyết thông qua comment. (Tuy nhiên nếu bạn chọn giải quyết bằng cách nói chuyện trực tiếp, nhớ ghi lại kết quả cuộc thảo luận bằng một comment để những người xem sau có thể nắm rõ).

Nếu kể cả thế mà cũng không giải quyết được vấn đề, cách thường gặp nhất là nhờ một bên thứ ba. Bạn có thể gọi thêm người trong team vào thảo luận, nhờ Technical Lead giúp đỡ, hỏi ý kiến từ người chịu trách nhiệm maintain chính cho đoạn code hoặc Engineering Manager. **Đừng để CL mãi không được merge chỉ vì developer và người review không thể thống nhất quan điểm**. 

Tiếp: [Nên để ý những điểm gì khi review code](looking-for.md)
