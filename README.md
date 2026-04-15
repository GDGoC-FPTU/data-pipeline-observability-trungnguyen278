[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573974&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-2A202600451
**Student Email:** trung.nt202717@gmail.com
**Name:** Nguyen Thanh Trung

---

## Mo ta

Bai lab nay xay dung mot ETL Pipeline don gian voi 4 buoc: Extract du lieu tu file JSON, Validate de loai bo records khong hop le (gia <= 0, category rong), Transform de tinh gia giam 10% va chuan hoa category, va Load de xuat ra file CSV. Ngoai ra, bai lab con thuc hien stress test so sanh ket qua cua AI Agent khi su dung du lieu sach va du lieu rac de minh chung tam quan trong cua Data Quality.

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
├── raw_data.json            # Du lieu dau vao (5 records)
├── processed_data.csv       # Output cua pipeline (3 records hop le)
├── generate_garbage.py      # Script tao du lieu rac
├── agent_simulation.py      # Script mo phong AI Agent
├── experiment_report.md     # Bao cao thi nghiem stress test
├── tests/                   # Thu muc chua test autograder
└── README.md                # File nay
```

---

## Ket qua

- Tong so records dau vao: 5
- Records hop le sau validation: 3 (Laptop, Chair, Monitor)
- Records bi loai: 2 (Mystery Box — gia am, Phone — category rong)
- Cot moi: discounted_price (gia giam 10%), processed_at (timestamp)
- Ket qua Agent voi clean data: chinh xac (Laptop - $1200)
- Ket qua Agent voi garbage data: sai (Nuclear Reactor - $999999)
