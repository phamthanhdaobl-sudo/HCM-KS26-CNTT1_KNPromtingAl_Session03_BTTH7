# HCM-KS26-CNTT1_KNPromtingAl_Session03_BTTH7
# BÀI THỰC HÀNH 7: XÂY DỰNG HỆ THỐNG HỖ TRỢ TUYỂN DỤNG BẰNG AI

**Họ và tên:** Phạm Thành Đạo  
**Lớp:** HCM-KS26-CNTT1

## 1. Mục tiêu

Thiết kế Prompt theo khung CREATE, kết hợp kỹ thuật Few-shot để xây dựng hệ thống hỗ trợ tuyển dụng bằng AI.

Hệ thống có nhiệm vụ đọc CV, đối chiếu với mô tả công việc (JD), chấm điểm ứng viên theo từng tiêu chí, tính tổng điểm và phân loại mức độ phù hợp với vị trí Junior Backend Developer.

## 2. Xây dựng Prompt theo khung CREATE

### C – Character (Vai trò)

Bạn là chuyên viên tuyển dụng nhân sự ngành công nghệ thông tin, có kinh nghiệm đánh giá CV cho vị trí Junior Backend Developer.

Bạn có khả năng phân tích kỹ năng lập trình, kiến thức chuyên môn và kinh nghiệm thực tế của ứng viên. Hãy đánh giá khách quan dựa trên thông tin được cung cấp, không suy đoán hoặc tự bổ sung dữ liệu.

### R – Request (Yêu cầu)

Hãy đọc mô tả công việc (JD) và các CV ứng viên, sau đó thực hiện:

1. Đối chiếu kỹ năng của từng ứng viên với yêu cầu tuyển dụng.
2. Chấm điểm kỹ năng chuyên môn trên thang 70 điểm.
3. Chấm điểm kinh nghiệm và dự án trên thang 30 điểm.
4. Tính tổng điểm trên thang 100.
5. Phân loại ứng viên theo mức điểm:
   - Từ 80 điểm trở lên: PHÙ HỢP CAO.
   - Từ 60 đến dưới 80 điểm: CẦN XEM XÉT.
   - Dưới 60 điểm: CHƯA PHÙ HỢP.
6. Nêu rõ điểm mạnh và thông tin còn thiếu của từng ứng viên.

### E – Examples (Ví dụ mẫu – Few-shot)

**Ví dụ 1:**

Thông tin ứng viên:

- Tên: Nguyễn X.
- Kỹ năng: Java, OOP, SQL, Git.
- Kinh nghiệm: 1 dự án cá nhân.

Kết quả đánh giá mẫu:

- Java: 20/20.
- OOP: 15/15.
- SQL và PostgreSQL: 10/20 vì chỉ có SQL.
- Git: 15/15.
- Tổng điểm chuyên môn: 60/70.
- Kinh nghiệm/dự án: 10/30 vì có 1 dự án cá nhân.
- Tổng điểm: 70/100.
- Phân loại: CẦN XEM XÉT.

Giải thích: Ứng viên có nền tảng Java, OOP, SQL và Git, nhưng chưa có thông tin về PostgreSQL. Có một dự án cá nhân nhưng chưa có mô tả chi tiết.

**Ví dụ 2:**

Thông tin ứng viên:

- Tên: Trần Y.
- Kỹ năng: Python, HTML, CSS.
- Kinh nghiệm: Chưa có dự án.

Kết quả đánh giá mẫu:

- Java: 0/20.
- OOP: 0/15 vì CV không đề cập.
- SQL và PostgreSQL: 0/20.
- Git: 0/15.
- Tổng điểm chuyên môn: 0/70.
- Kinh nghiệm/dự án: 0/30.
- Tổng điểm: 0/100.
- Phân loại: CHƯA PHÙ HỢP.

Giải thích: Các kỹ năng được cung cấp chưa đáp ứng những yêu cầu chuyên môn chính trong JD. Ứng viên chưa có thông tin về dự án hoặc kinh nghiệm thực tế.

Lưu ý: Hai ví dụ trên chỉ hướng dẫn cách chấm điểm. Không được sao chép điểm mẫu cho các ứng viên thực tế.

### A – Adjustments (Điều chỉnh và ràng buộc)

**Mô tả công việc (JD):**

- Có kiến thức Java cơ bản.
- Biết lập trình hướng đối tượng (OOP).
- Có kiến thức SQL và PostgreSQL.
- Biết sử dụng Git.
- Ưu tiên ứng viên đã có dự án thực tế.

**Quy tắc chấm điểm:**

*Điểm kỹ năng chuyên môn: 70 điểm*

| Tiêu chí | Điểm tối đa |
|---|---:|
| Java cơ bản | 20 |
| Lập trình hướng đối tượng (OOP) | 15 |
| SQL và PostgreSQL | 20 |
| Git | 15 |
| **Tổng** | **70** |

Đối với SQL và PostgreSQL, mỗi kỹ năng được tính tối đa 10 điểm. Chỉ chấm điểm khi CV có đề cập rõ ràng.

*Điểm kinh nghiệm/dự án: 30 điểm*

- Mỗi dự án cá nhân được đề cập: 10 điểm, tối đa 20 điểm.
- Kinh nghiệm thực tập hoặc làm việc được đề cập: tối đa 30 điểm, đánh giá theo thời gian được cung cấp.
- Ví dụ: 6 tháng thực tập được 15 điểm; 1 năm làm việc được 20 điểm.
- Không tự suy đoán lĩnh vực hoặc mức độ liên quan của kinh nghiệm nếu CV không cung cấp.

**Các ràng buộc bắt buộc:**

- Không tự suy diễn kỹ năng hoặc kinh nghiệm không có trong CV.
- Nếu thiếu dữ liệu phải ghi "Chưa có thông tin".
- Không cộng điểm cho kỹ năng chưa được đề cập.
- Không sử dụng điểm ví dụ làm điểm mặc định.
- Trường `teamwork` trong cấu trúc JSON mẫu phải để 0 vì JD không có tiêu chí đánh giá kỹ năng làm việc nhóm. Không tính trường này vào tổng điểm.
- Kết quả chỉ phục vụ sàng lọc sơ bộ, không thay thế quyết định của nhà tuyển dụng.

### T – Type of Output (Định dạng đầu ra)

Chỉ xuất kết quả dưới dạng JSON hợp lệ, theo cấu trúc:

{
  "candidates": [
    {
      "name": "Tên ứng viên",
      "scores": {
        "technical": 0,
        "experience": 0,
        "teamwork": 0
      },
      "totalScore": 0,
      "classification": "CHƯA PHÙ HỢP",
      "strengths": [],
      "missingInformation": []
    }
  ]
}

Không sử dụng Markdown Code Fence hoặc giải thích bên ngoài JSON.

### E – Evaluation (Tiêu chí đánh giá)

- Đánh giá đầy đủ tất cả ứng viên.
- Điểm chuyên môn không vượt quá 70.
- Điểm kinh nghiệm/dự án không vượt quá 30.
- Tổng điểm bằng điểm chuyên môn cộng điểm kinh nghiệm.
- Phân loại đúng theo ngưỡng điểm đã quy định.
- Không tự bổ sung thông tin không có trong CV.
- JSON phải đúng cú pháp và có đầy đủ các trường yêu cầu.

## 3. Dữ liệu CV đầu vào

| Ứng viên | Kỹ năng | Kinh nghiệm |
|---|---|---|
| Nguyễn A | Java, OOP, SQL, Git | 2 dự án cá nhân |
| Trần B | Python, HTML, CSS | Chưa có dự án |
| Lê C | Java, OOP, PostgreSQL, Git | 6 tháng thực tập |
| Phạm D | Java, SQL | 1 năm làm việc |

## 4. Kết quả đánh giá ứng viên bằng AI

{
  "candidates": [
    {
      "name": "Nguyễn A",
      "scores": {
        "technical": 60,
        "experience": 20,
        "teamwork": 0
      },
      "totalScore": 80,
      "classification": "PHÙ HỢP CAO",
      "strengths": [
        "Có kiến thức Java cơ bản.",
        "Có kiến thức lập trình hướng đối tượng OOP.",
        "Có kiến thức SQL.",
        "Biết sử dụng Git.",
        "Có 2 dự án cá nhân."
      ],
      "missingInformation": [
        "Chưa có thông tin về PostgreSQL.",
        "Chưa có mô tả chi tiết về nội dung và kết quả của 2 dự án cá nhân."
      ]
    },
    {
      "name": "Trần B",
      "scores": {
        "technical": 0,
        "experience": 0,
        "teamwork": 0
      },
      "totalScore": 0,
      "classification": "CHƯA PHÙ HỢP",
      "strengths": [
        "Có kiến thức Python, HTML và CSS."
      ],
      "missingInformation": [
        "Chưa có thông tin về Java.",
        "Chưa có thông tin về OOP.",
        "Chưa có thông tin về SQL và PostgreSQL.",
        "Chưa có thông tin về Git.",
        "Chưa có dự án hoặc kinh nghiệm thực tế được cung cấp."
      ]
    },
    {
      "name": "Lê C",
      "scores": {
        "technical": 60,
        "experience": 15,
        "teamwork": 0
      },
      "totalScore": 75,
      "classification": "CẦN XEM XÉT",
      "strengths": [
        "Có kiến thức Java cơ bản.",
        "Có kiến thức lập trình hướng đối tượng OOP.",
        "Có kiến thức PostgreSQL.",
        "Biết sử dụng Git.",
        "Có 6 tháng kinh nghiệm thực tập."
      ],
      "missingInformation": [
        "Chưa có thông tin về SQL được đề cập riêng trong CV.",
        "Chưa có thông tin về nội dung công việc và kết quả thực tập."
      ]
    },
    {
      "name": "Phạm D",
      "scores": {
        "technical": 30,
        "experience": 20,
        "teamwork": 0
      },
      "totalScore": 50,
      "classification": "CHƯA PHÙ HỢP",
      "strengths": [
        "Có kiến thức Java cơ bản.",
        "Có kiến thức SQL.",
        "Có 1 năm kinh nghiệm làm việc."
      ],
      "missingInformation": [
        "Chưa có thông tin về OOP.",
        "Chưa có thông tin về PostgreSQL.",
        "Chưa có thông tin về Git.",
        "Chưa có thông tin về vị trí công việc và lĩnh vực làm việc trước đây."
      ]
    }
  ]
}

## 5. Nhận xét kết quả

| Ứng viên | Điểm chuyên môn | Điểm kinh nghiệm | Tổng điểm | Phân loại |
|---|---:|---:|---:|---|
| Nguyễn A | 60/70 | 20/30 | 80/100 | Phù hợp cao |
| Trần B | 0/70 | 0/30 | 0/100 | Chưa phù hợp |
| Lê C | 60/70 | 15/30 | 75/100 | Cần xem xét |
| Phạm D | 30/70 | 20/30 | 50/100 | Chưa phù hợp |

**Nhận xét:**

- **Nguyễn A:** Có đầy đủ các kỹ năng được đề cập trong JD ngoại trừ PostgreSQL, đồng thời có 2 dự án cá nhân. Đây là ứng viên đạt mức phù hợp cao.
- **Trần B:** Có kỹ năng Python, HTML và CSS nhưng chưa đáp ứng các kỹ năng chuyên môn chính của vị trí Junior Backend Developer.
- **Lê C:** Có nền tảng Java, OOP, PostgreSQL và Git, cùng 6 tháng thực tập. Tuy nhiên, cần xác minh thêm kiến thức SQL và nội dung thực tập.
- **Phạm D:** Có Java, SQL và 1 năm làm việc nhưng thiếu thông tin về OOP, PostgreSQL và Git.

## 6. Kết luận

Việc ứng dụng kỹ thuật Few-shot kết hợp khung CREATE giúp xây dựng Prompt tuyển dụng có cấu trúc rõ ràng, hướng dẫn AI đánh giá ứng viên theo các tiêu chí thống nhất.

Hệ thống hỗ trợ bộ phận nhân sự tiết kiệm thời gian đọc CV, so sánh năng lực và xác định những ứng viên cần được ưu tiên xem xét. Tuy nhiên, kết quả chỉ mang tính chất sàng lọc sơ bộ. Nhà tuyển dụng vẫn cần kiểm tra CV thực tế, phỏng vấn và đánh giá trực tiếp trước khi đưa ra quyết định tuyển dụng.
