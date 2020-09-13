# How are faults and failures related to testing and debugging?

Một phần mềm có lỗi (fault) trong mã nguồn khi chạy sẽ đưa ra kết quả không đúng với mong muốn của lập trình viên, hay còn gọi là thất bại (failure).

Theo em mối liên quan giữa lỗi và thất bại với kiểm thử và gỡ lỗi là: Những tester thực hiện việc kiểm thử (testing) bằng cách cho chương trình chạy với một bộ dữ liệu đầu vào nào đó, nếu chương trình cho ra kết quả không giống với mong muốn, họ sẽ xác định chương trình đó bị thất bại (failure) và trong mã nguồn sẽ có lỗi (fault). Từ đó, họ sẽ đi tới giai đoạn gỡ lỗi (debugging) để tìm ra và khắc phục các lỗi đó trong mã nguồn.
