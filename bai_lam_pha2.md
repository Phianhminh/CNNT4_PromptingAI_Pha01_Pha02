# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:*Phí Anh Minh*
- **Lớp:**
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**KET QUA AI**
Trong file hiện tại, phần 4.2 có yêu cầu trích xuất 3 tin nhắn TN1, TN2, TN3 thành JSON, nhưng nội dung 3 tin nhắn này chưa xuất hiện trong tài liệu.

Tin nhắn đặt lịch được cung cấp ở phần 4.1 có thể trích xuất như sau:
{
  "ho_ten": "Trịnh Quốc Huy",
  "so_dien_thoai": null,
  "so_cccd": null,
  "email": null,
  "ma_dich_vu": "CAOVOI",
  "ngay_kham": "2026-12-23",
  "nguoi_lon": 2,
  "tre_em": 1,
  "do_tuoi_tre_em": 10,
  "khung_gio": "chieu",
  "tien_coc": 200000,
  "ghi_chu": null
}


Các thông tin điện thoại, CCCD và email đã được ẩn danh nên để null.

```

**Link trò chuyện:**

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

BẢNG TÍNH CHI PHÍ DỊCH VỤ CAOVOI

1. Tiền khám trẻ em
- Trẻ 7 tuổi: 350.000 × 80% = 280.000 đồng.
- Trẻ 11 tuổi: 350.000 × 80% = 280.000 đồng.
- Trẻ 4 tuổi: Miễn phí.
Tổng tiền trẻ em = 280.000 + 280.000 + 0 = 560.000 đồng.

2. Tiền khám người lớn

- 6 người lớn × 350.000 = 2.100.000 đồng.

3. Tổng tiền khám

- 2.100.000 + 560.000 = 2.660.000 đồng.

4. Giảm giá
- Nhóm có 6 người lớn (đủ điều kiện giảm 10%).
- 2.660.000 × 10% = 266.000 đồng.
Tiền sau giảm giá = 2.660.000 − 266.000 = 2.394.000 đồng.

5. Phụ thu
- 3 người chụp X-quang, mỗi người 1 phim.
- 3 × 150.000 = 450.000 đồng.
6. Tổng tiền

- 2.394.000 + 450.000 = 2.844.000 đồng.
Kết quả
2.844.000 đồng
[RESULT: 2.844.000 đồng]

**Link trò chuyện:**

### b) Kiểm tra kết quả AI

(Ghi kết luận AI đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó – xoá dòng này)

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
Dựa trên file BÀI LÀM PHA 1 – HACKATHON 02, mục 4.4, dưới đây là kết quả hoàn thiện cho Dây chuyền xử lý khiếu nại – Trạm 1.
1. Kết quả Trạm 1
Đã xác định yêu cầu
Trong file hiện tại chưa có nội dung email khiếu nại cụ thể, nên chưa thể tạo JSON kết quả thực tế. Tuy nhiên, cấu trúc đầu ra đúng là:
{
  "loai_su_co": "tre_hen",
  "so_khach": 2,
  "so_lan_hen_bi_tre": 3,
  "tom_tat": "Khách hàng phàn nàn lịch hẹn bị trễ nhiều lần."
}


Lưu ý: Đây chỉ là JSON minh họa, không phải dữ liệu khiếu nại thực tế.
2. Hai điều cần kiểm tra ở JSON đầu ra Trạm 1
1. Kiểm tra JSON hợp lệ, có đúng 4 trường theo yêu cầu và đúng kiểu dữ liệu.
2. Kiểm tra thông tin được trích xuất chính xác từ email, không tự suy diễn hoặc bịa đặt dữ liệu.
3. Câu lệnh viết tiếp
Dựa vào kết quả JSON của Trạm 1, hãy tiếp tục xử lý khiếu nại.

Yêu cầu:
- Phân tích loại sự cố và mức độ ảnh hưởng.
- Đề xuất phương án giải quyết phù hợp.
- Đưa ra hướng phản hồi khách hàng lịch sự, chuyên nghiệp.
- Không tự ý thêm thông tin chưa được cung cấp.
- Nếu thiếu dữ liệu, hãy ghi rõ thông tin cần xác minh.
- Chỉ sử dụng dữ liệu từ kết quả Trạm 1.
```

**Link trò chuyện:**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

Dưới đây là bài làm hoàn chỉnh cho mục 4.5. Prompt chấm bài theo Rubric, dựa trên nội dung bài tập Hackathon 02 của bạn.
4.5. Prompt chấm bài theo Rubric
[VAI TRÒ]
Bạn là giảng viên và chuyên gia đánh giá bài làm thực hành về Prompt Engineering.

[NHIỆM VỤ]
Đánh giá bài làm của học viên dựa trên Rubric chấm điểm được cung cấp. Chấm điểm khách quan, công bằng, không thiên vị và không tự ý cộng điểm khi học viên chưa đáp ứng yêu cầu.

[TIÊU CHÍ ĐÁNH GIÁ]
1. Tính chính xác: Nội dung có đúng yêu cầu đề bài, dữ liệu và quy tắc được cung cấp hay không.
2. Tính đầy đủ: Có hoàn thành tất cả các yêu cầu và các phần bắt buộc hay không.
3. Cấu trúc: Trình bày đúng định dạng yêu cầu như JSON, Prompt, System Prompt và các trường dữ liệu hay không.
4. Khả năng chống ảo giác: Có giới hạn nguồn dữ liệu, tránh suy diễn và yêu cầu trích dẫn căn cứ hay không.
5. Khả năng ứng dụng: Prompt có rõ ràng, logic, dễ thực hiện và có thể áp dụng vào tình huống thực tế hay không.

[QUY TẮC CHẤM ĐIỂM]
- Chấm từng tiêu chí theo thang điểm và trọng số trong Rubric.
- Chỉ cho điểm dựa trên bằng chứng thực tế trong bài làm.
- Không tự suy đoán những nội dung học viên chưa viết.
- Nếu thiếu nội dung bắt buộc, phải trừ điểm tương ứng.
- Nếu bài làm sai định dạng hoặc không tuân thủ yêu cầu, phải ghi rõ lỗi.
- Không tự ý thay đổi tổng điểm hoặc trọng số của Rubric.

[ĐỊNH DẠNG KẾT QUẢ]
1. Bảng đánh giá gồm:
   - Tiêu chí
   - Điểm tối đa
   - Điểm đạt được
   - Nhận xét và bằng chứng

2. Tổng điểm:
   - Tổng điểm đạt được
   - Tổng điểm tối đa
   - Xếp loại (nếu Rubric có quy định)

3. Nhận xét chung:
   - Những điểm làm tốt.
   - Những lỗi cần khắc phục.
   - Đề xuất cách cải thiện bài làm.

[NGUYÊN TẮC CUỐI]
Hãy chấm bài nghiêm túc, minh bạch và nhất quán. Không bịa đặt tiêu chí, không tự tạo trọng số và không đánh giá dựa trên cảm tính.

Nếu chưa được cung cấp Rubric chính thức, hãy yêu cầu người dùng cung cấp Rubric trước khi chấm điểm.




Lưu ý: Prompt này giúp AI chấm bài có căn cứ, tránh tự đặt tiêu chí hoặc tự ý cho điểm khi chưa có Rubric chính thức.

**Link trò chuyện:**
