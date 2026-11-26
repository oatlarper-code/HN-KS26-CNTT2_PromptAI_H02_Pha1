# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 04
- **Họ tên:** Nguyễn Hoàng Minh Phúc
- **Lớp:** CNTT2
- **Link repository Pha2:** [Pha2](https://github.com/oatlarper-code/HN-KS26-CNTT2_PromptAI_H02_Pha1)
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

**KET QUA AI**

```
[
  {
    "ma_tuyen": "SGDL",
    "ngay_di": "2026-12-22",
    "ve_nguoi_lon": 2,
    "ve_tre_em": 1,
    "loai_cho": "giuong",
    "ghi_chu": null
  },
  {
    "ma_tuyen": "SGNT",
    "ngay_di": "2027-01-02",
    "ve_nguoi_lon": 3,
    "ve_tre_em": 0,
    "loai_cho": null,
    "ghi_chu": "một người đang mang thai 6 tháng"
  },
  {
    "ma_tuyen": "SGCT",
    "ngay_di": null,
    "ve_nguoi_lon": 4,
    "ve_tre_em": 0,
    "loai_cho": "ghe",
    "ghi_chu": "bà nội đi xe lăn"
  }
]
```

**Link trò chuyện:** [Dat_ve_xe](https://share.gemini.google/iiYw2gBU1Zw5)

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```
Tuyến SGDL (Sài Gòn – Đà Lạt) có đơn giá vé người lớn là 320.000 đồng. Chi tiết tính toán cho đoàn như sau:Bước 1: Tiền vé người lớnĐoàn có 8 người lớn:Phép tính: $8 \times 320.000 = 2.560.000\text{ đồng}$Bước 2: Tiền vé trẻ em3 trẻ em (6, 7 và 9 tuổi) nằm trong độ tuổi từ 5 đến 10 tuổi nên tính 75% giá vé người lớn; 1 bé 2 tuổi (dưới 5 tuổi) được miễn phí.Phép tính: $(3 \times 320.000 \times 75\%) + (1 \times 0) = 720.000\text{ đồng}$Bước 3: Tiền véTổng tiền vé người lớn và tiền vé trẻ em:Phép tính: $2.560.000 + 720.000 = 3.280.000\text{ đồng}$Bước 4: Giảm giá đoànĐoàn có 8 người lớn (đủ điều kiện từ 6 người lớn trở lên) nên được giảm 5% trên tổng tiền vé:Phép tính giảm giá: $3.280.000 \times 5\% = 164.000\text{ đồng}$Tiền vé sau giảm: $3.280.000 - 164.000 = 3.116.000\text{ đồng}$Bước 5: Phụ thu (không được giảm giá)Đoàn có 2 kiện hành lý cồng kềnh với mức phí 100.000 đồng/kiện:Phép tính: $2 \times 100.000 = 200.000\text{ đồng}$Bước 6: Tổng tiềnCộng tiền vé sau giảm và phụ thu hành lý:Phép tính: $3.116.000 + 200.000 = 3.316.000\text{ đồng}$[RESULT: 3.316.000 đồng]
```

**Link trò chuyện:** [Tien_ve](https://share.gemini.google/xmJTj5j7ANsK)

### b) Kiểm tra kết quả AI

- Kết quả AI tính đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```
{
  "loai_su_co": "sai_loai_xe",
  "so_khach": 3,
  "so_chang_bi_doi": 2,
  "tom_tat": "Khách đặt xe giường nằm cho 3 người nhưng cả 2 chặng đi về đều bị đổi sang ghế ngồi."
}
```

**Link trò chuyện:** [khieu_nai](https://share.gemini.google/CQl6z3dMExUx)

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```
Tiêu chíĐiểmMinh chứngĐề xuất sửaĐúng thông tin (50% - Tối đa 5.0đ)0.0 / 5.0- Sai giá vé: "Vé đi Nha Trang bên em 350.000đ nha chị" — Giá chuẩn của công ty là 380.000 đồng/vé người lớn.Sai chính sách đổi vé: "Chị đổi trước 12 tiếng thì đổi free nha chị." — Đổi trước từ 6 đến dưới 24 giờ phải chịu phí 20% giá vé, không được miễn phí. | "Giá vé chặng Sài Gòn – Nha Trang là 380.000 đồng/vé người lớn ạ. Nếu chị đổi vé trước giờ xe chạy 12 tiếng (thuộc khung từ 6 đến dưới 24 tiếng), phí đổi vé là 20% giá vé ạ." |
| Đầy đủ (30% - Tối đa 3.0đ) | 1.5 / 3.0 | - Thiếu lời mời đặt chỗ: Bài trả lời có giải đáp 2 ý của khách nhưng thiếu bước mời khách cung cấp ngày đi và số lượng vé để hỗ trợ đặt chỗ. | "Dạ chị dự kiến đi ngày nào và đặt bao nhiêu vé để em hỗ trợ giữ chỗ cho mình ạ?" |
| Giọng điệu (20% - Tối đa 2.0đ) | 0.5 / 2.0 | - Dùng từ ngữ suồng sã, thiếu chuyên nghiệp: "nha chị", "xe xịn lắm luôn", "đổi free", "nhắn em liền!". | "Dạ chào chị! Giá vé chặng Sài Gòn – Nha Trang bên em hiện là 380.000 đồng/vé người lớn ạ. Nếu chị đổi ngày đi trước giờ xe chạy 12 tiếng, phí đổi vé sẽ là 20% giá vé. Chị dự kiến khởi hành ngày nào và đặt bao nhiêu vé để em hỗ trợ kiểm tra chỗ cho chị ạ?" |Tổng điểm: 2.0 / 10
```

**Link trò chuyện:** [cham_bai_rubric](https://share.gemini.google/uevhE9X8vfHU)
