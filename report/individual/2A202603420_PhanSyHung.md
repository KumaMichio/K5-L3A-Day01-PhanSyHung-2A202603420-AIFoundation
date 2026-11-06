# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

> Đổi tên file này thành `MSSV_HoTen.md` của bạn, ví dụ `2A20260000_NguyenVanAn.md`, rồi điền từng mục. Xoá các dòng hướng dẫn in nghiêng khi xong.

- **MSSV:**2A202603420
- **Họ và tên:**Phan Sỹ Hùng
- **SEED** (in ở ô đầu notebook):2186

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | ☐ |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | ☐ |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | ☐ |

## 2. Kết quả chính

| Cách tiếp cận | F1 test | F1 SUB 40 | p95 ms/tin | USD/1k tin |
|---|---|---|---|---|
| 1. BoW + LogReg (tự code) | 0.886 | 0.889 | 0.099 | 0.000 |
| 2. BoW + MLP (deep learning) | 0.952 | 0.974 | 0.482 | 0.000 |
| 3a. Encoder (MiniLM) + kNN | 0.913 | 1.000 | 82.236 | 0.000 |
| 3b. Encoder (MiniLM) + LogReg | 0.959 | 0.976 | 44.159 | 0.000 |
| 3c. Encoder (MiniLM) + MLP head | 0.974 | 1.000 | 43.045 | 0.000 |
| 4a. LLM nhỏ zero-shot (mistral-nemo) | — | 0.930 | 1641.158 | 0.002 |
| 4b. LLM lớn zero-shot (mistral-small-24b) | — | 0.930 | 1379.144 | 0.004 |
| 4c. LLM nhỏ few-shot (mistral-nemo) | — | 0.952 | 1177.834 | 0.006 |


## 3. Dự đoán và thực tế

tradeoff: Em đoán chỉ BoW + LogReg nằm trên đường Pareto. Thực tế có thêm BoW + MLP và 3c. 
Em không nghĩ đến việc một lớp ẩn giúp BoW giảm lỗi từ ~11 % xuống ~2.6 % mà gần như không tốn thêm thời gian (0.3 ms).

## 4. Phân tích 50 case khó

*Model nào tụt nhiều nhất, ở nhóm case nào? Nêu 2 case cụ thể và cơ chế khiến model sai.*

## 5. Thử thách cá nhân

*Đề theo SEED của bạn, cách làm, kết quả, giải thích.*

## 6. Phương án cho sản phẩm thật

*Với yêu cầu p95 < 50 ms/tin cho 10 triệu SMS/ngày: chọn phương án nào, dẫn số liệu nào, chấp nhận đánh đổi gì.*

## 7. AI log và điều đã học

*Mỗi lần dùng AI: hỏi gì, nhận gì, bạn sửa gì. Sau đó 2–3 câu: điều bạn hiểu ra hôm nay mà trước đó chưa hiểu.*
