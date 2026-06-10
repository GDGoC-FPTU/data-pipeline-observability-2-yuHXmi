[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112709&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** xhuy8248@gmail.com
**Name:** Ha Xuan Huy

---

## Mo ta

Bài lab này thực hành xây dựng một quy trình ETL (Extract, Transform, Load) hoàn chỉnh và tự động. Nhiệm vụ chính bao gồm việc trích xuất dữ liệu thô từ định dạng JSON, thiết lập các bộ quy tắc (validation) để kiểm tra và tự động loại bỏ các dữ liệu rác (giá trị âm hoặc thiếu thông tin danh mục). Tiếp theo, dữ liệu được chuẩn hóa, tính toán lại giá trị và ghi nhận timestamp trước khi lưu trữ ra file CSV. 

Cuối cùng thực hiện một bài Stress Test (Agent Simulation) nhằm kiểm chứng và đưa ra báo cáo thực tế về việc chất lượng dữ liệu đầu vào (Data Quality) sẽ ảnh hưởng trực tiếp như thế nào đến độ chính xác và độ tin cậy của một AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Có 5 record đã xử lý, trong đó 3 đã được chấp nhận và 2 bị loại.

