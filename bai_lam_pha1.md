# BÀI LÀM PHA 1 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:**
- **Lớp:**
- **Link repository Pha1:**

> Pha 1 (70 phút đầu, KHÔNG dùng AI). Viết xong, kéo thả file này vào repository Pha1 trước mốc giờ giám thị công bố.

## 4.1. Bảo vệ dữ liệu và chống ảo giác

### a) Ghi chú đã ẩn danh hoá

**GHI CHU DA AN DANH**

```

Khách hàng Trịnh Quốc Huy, số điện thoại [SO_DIEN_THOAI], số CCCD [SO_CCCD], email [EMAIL], đặt lịch cạo vôi răng (mã CAOVOI) ngày 23/12/2026 cho 2 người lớn và 1 trẻ em 10 tuổi. Khách đã chuyển khoản đặt cọc 200.000 đồng. Khách yêu cầu khám buổi chiều.

```

### b) Hai câu lệnh chống ảo giác
1.''Khách huỷ lịch hẹn trước 3 tiếng thì có bị mất tiền cọc hay không?'' Chỉ sử dụng thông tin trong file, không được tự ý suy diễn; nếu không tìm thấy được thông tin trong file hãy trả lời là:''Thông tin này chưa có trong tài liệu chính sách hiện tại, tôi sẽ kiểm tra lại."

2. Với mỗi câu trả lời, hãy trích dẫn nguyên văn câu hoặc ghi rõ mục/điều khoản tương ứng trong file chính sách làm căn cứ.

```

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**PROMPT**
C-context: Bạn là nhân viên mới của Nha khao Nụ cười:

BẢNG MÃ DỊCH VỤ
CAOVOI – Khám và cạo vôi răng
TRAM – Trám răng thẩm mỹ (1 răng)
TAYTRANG – Tẩy trắng răng 

R- request:
- Hãy trích xuất 3 tin nhắn TN1, TN2, TN3 trong cặp thẻ <tin_nhan>...</tin_nhan> thành một mảng JSON gồm 3 đối tượng theo đúng thứ tự TN1, TN2, TN3, mỗi đối tượng có đủ 6 trường như ví dụ mẫu.

-Explanation: 
Áp dụng đúng 5 quy tắc chuẩn hoá sau:
1. ma_dich_vu lấy theo bảng mã dịch vụ
2. Ngay_kham dạng YYY-MM-DD; tin nhắn không ghi năm thì lấy năm 2026; nếu không có ngày cụ thể thì null.
3.Khách không nhắc đến trẻ em thì tre_em là 0 và mọi khách là người lớn.
4. khung_gio chỉ nhận "chieu","sang" hoặc null.
5. ghi_chu chỉ ghi yêu cầu đặc biệt về 1 bé rất sợ khoan còn lại là null.
```
A - Action:
Đọc 3 tin nhắn trong thẻ <tin_nhan>...</tin_nhan> và chuyển thành mảng JSON 3 đối tượng tuân thủ 5 quy tắc chuẩn hoá và 2 ví dụ trên.

T - Tone:
Chính xác, khách quan, tuân thủ nghiêm ngặt cấu trúc dữ liệu.

E - Extras:
Chỉ trả về duy nhất mảng JSON hợp lệ, không chào hỏi, không giải thích.


## 4.3. Báo giá bằng Chain-of-Thought

### a) Prompt

**PROMPT**
-Hãy tính tổng tiền cho yêu cầu báo giá dựa hoàn toàn vào dữ liệu trong cặp thẻ <du_lieu>...</du_lieu> dưới đây.
Yêu cầu suy luận từng bước theo đúng thứ tự 6 bước:
1. Tiền khám trẻ em
2. Tiền khám người lớn
3. Tiền khám
4. giảm giá
5. phục thu
6. Tổng tiền
Mỗi bước phải ghi rõ phép tính. Dòng cuối cùng bắt buộc ghi theo đúng định dạng: [RESULT: <tổng tiền> đồng]
<du_lieu>
BẢNG GIÁ DỊCH VỤ (đồng/người lớn)
CAOVOI – Khám và cạo vôi răng: 350.000
TRAM – Trám răng thẩm mỹ (1 răng): 500.000
TAYTRANG – Tẩy trắng răng: 2.500.000
```
QUY TẮC TÍNH GIÁ
1. Trẻ em từ 6 đến 12 tuổi tính 80% giá người lớn. Trẻ dưới 6 tuổi được khám miễn phí.
2. Nhóm từ 5 người lớn trở lên được giảm 10% trên tiền dịch vụ (tiền người lớn + tiền trẻ em).
3. Phí chụp X-quang: 150.000 đồng/phim. Phí này không được giảm giá.
4. Tổng tiền = tiền dịch vụ sau giảm + phí chụp X-quang.
YÊU CẦU BÁO GIÁ
Nhóm nhân viên công ty làm dịch vụ CAOVOI gồm 6 người lớn, 2 trẻ em (7 tuổi và 11 tuổi) và 1 bé 4 tuổi. Có 3 người cần chụp X-quang (mỗi người 1 phim).


## 4.4. Dây chuyền xử lý khiếu nại (Prompt Chaining)

### a) Prompt Trạm 1

**PROMPT**

```text
Đọc email khiếu nại của khách hàng trong thẻ <email>...</email> và trích xuất thông tin sự cố khách phàn nàn.
Chỉ trả về duy nhất một đối tượng JSON hợp lệ, không chào hỏi, không giải thích, gồm đúng 4 trường và kiểu dữ liệu sau:
{"loai_su_co": một trong "tre_hen" | "thiet_bi" | "bac_si" | "khac", "so_khach": số nguyên, "so_lan_hen_bi_tre": số nguyên hoặc null, "tom_tat": "không quá 20 từ"}

```

### b) Hai điều cần kiểm tra ở JSON đầu ra của Trạm 1

1. (Viết câu trả lời vào đây – xoá dòng này)

2.

### c) Câu lệnh viết tiếp

**CAU LENH**

```text
(Viết câu lệnh vào đây – xoá dòng này)
```

## 4.5. Prompt chấm bài theo Rubric

**PROMPT**

```text
(Viết prompt vào đây – xoá dòng này)
```

## 4.6. Hoàn thiện System Prompt

> Phần Vai trò và Chuẩn đầu ra đã cho sẵn. Viết tiếp phần Quy tắc ràng buộc và Xử lý ngoại lệ.

```text
[Vai trò]
Bạn là "Trợ lý Nụ Cười", nhân viên tư vấn trên website của Nha khoa Nụ Cười, giúp khách chọn và đặt lịch một trong 3 dịch vụ: CAOVOI (Khám và cạo vôi răng), TRAM (Trám răng thẩm mỹ), TAYTRANG (Tẩy trắng răng).

[Quy tắc ràng buộc]
1. Chỉ được tư vấn về 3 dịch vụ trên ( CAOVOI,TRAM,TAYTRANG) không tư vấn gì thêm
2. Báo giá đúng theo bảng giá,tuyệt đối không tự ý hứa giảm giá hay ưu đãi ngoài bảng giá.
3. Không bao giờ hỏi xin số CCCD hoặc số thẻ ngân hàng của khách hàng.


[Chuẩn đầu ra]
Trả lời bằng tiếng Việt, lịch sự, tối đa 120 từ. Giá dịch vụ trình bày dạng gạch đầu dòng. Kết thúc bằng một câu hỏi về nhu cầu tiếp theo của khách.

[Xử lý ngoại lệ]
- Khách hỏi ngoài phạm vi: Lịch sự thông báo công ty chỉ phục vụ 3 dịch vụ trên, có thể gợi ý khách tham khảo 1 trong 3 dịch vụ này
- Khách cung cấp thiếu thông tin: Chủ động hỏi lại khác các thông tin bị thiếu ( dịch vụ, ngày khám, số lượng người khám trẻ em/người lớn, phòng khám)
```
