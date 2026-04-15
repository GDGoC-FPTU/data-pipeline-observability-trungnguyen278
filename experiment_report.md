# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600451
**Name:** Nguyen Thanh Trung
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 9 | Ket qua chinh xac, Laptop dung la san pham electronics dat nhat sau khi loc du lieu hop le |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | Ket qua sai hoan toan, Agent recommend san pham khong thuc te vi du lieu chua outlier |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung garbage data, Agent da tra loi sai hoan toan vi du lieu dau vao chua nhieu van de nghiem trong ve chat luong. Thu nhat, du lieu co Duplicate IDs (id=1 xuat hien 2 lan) khien Agent khong phan biet duoc ban ghi nao la chinh xac. Thu hai, wrong data types xuat hien o truong price voi gia tri "ten dollars" thay vi so, gay loi khi Agent tinh toan. Thu ba, outlier nhu "Nuclear Reactor" voi gia 999999 da lam lech ket qua hoan toan — Agent chon san pham nay la "best choice" vi no co gia cao nhat, nhung day la du lieu bat thuong khong phan anh thuc te. Thu tu, null values o ca id va category khien Agent khong the phan loai hoac truy van chinh xac. Tat ca nhung van de nay cho thay neu khong co buoc validation va data cleaning truoc khi dua du lieu vao Agent, ket qua tra ve se khong dang tin cay va co the gay hieu lam cho nguoi dung.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Du prompt co tot den dau, neu du lieu dau vao chua loi (outlier, null, duplicate, sai kieu du lieu) thi Agent van tra ve ket qua sai. Trong thi nghiem nay, cung mot cau hoi nhung voi clean data Agent tra loi chinh xac (Laptop - $1200), con voi garbage data Agent tra loi vo ly (Nuclear Reactor - $999999). Dieu nay chung minh rang Data Quality la nen tang quan trong nhat trong bat ky he thong AI nao — "Garbage In, Garbage Out".
