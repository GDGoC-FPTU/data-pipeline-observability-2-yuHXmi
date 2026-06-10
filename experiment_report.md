# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600829
**Name:** Ha Xuan Huy
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.0. | 10 | Agent nhận diện đúng sản phẩm đồ điện tử thực tế có giá cao nhất sau khi dữ liệu đã được làm sạch. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bị đánh lừa bởi dữ liệu rác không hợp lý được gán mác là "electronics". |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent trả lời sai vì bộ dữ liệu thô chứa các lỗi nghiêm trọng làm sai lệch logic tìm kiếm của AI. Cụ thể, Agent sử dụng hàm `idxmax()` để tìm giá trị cao nhất, dẫn đến việc chọn "Nuclear Reactor" - một extreme outlier (giá 999,999) không có thực trong danh mục đồ điện tử. 

Ngoài ra, dữ liệu còn chứa sai lệch về kiểu dữ liệu (wrong type: "ten dollars" thay vì số nguyên), trùng lặp ID (Duplicate IDs) và các giá trị Null ("Ghost Item"). Những yếu tố này làm hỏng tính toàn vẹn của dữ liệu, khiến cho các mô hình AI hoặc thuật toán tìm kiếm RAG (Retrieval-Augmented Generation) đưa ra quyết định sai lầm hoặc bị crash trong môi trường thực tế.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý.

Cho dù Prompt có được thiết kế chi tiết và thông minh đến đâu, nếu nguồn dữ liệu cung cấp cho Agent là rác (Garbage In), thì kết quả đầu ra chắc chắn sẽ là rác (Garbage Out). Dữ liệu sạch, chính xác và được chuẩn hóa (Quality Data) là điều kiện tiên quyết để AI Agent hoạt động đáng tin cậy.