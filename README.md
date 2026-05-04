# Day 18 — AI Financial Modeling & ROI

## Bài học hôm nay

Day 18 trả lời câu hỏi sống còn: **"Làm sao để sản phẩm AI của bạn không bị rơi tự do?"**

> 90% AI startups chết trước khi tìm thấy Product-Market Fit. Lý do số 1: **hết tiền** — không phải công nghệ dở.

---

## 4 Blocks chính

### 1. Cost & Revenue — Tốn tiền vào đâu? Thu tiền kiểu gì?

**5 Cost Components của AI Startup:**
1. **Cloud Infrastructure** — AWS, GCP, Azure
2. **Foundation Model API** — OpenAI, Anthropic, Gemini (trả theo token)
3. **R&D & Salaries** — lương dev, PM, designer (cục lớn nhất early-stage)
4. **Sales & Marketing** — ads, sales team (phình to khi scale)
5. **AI Hidden Costs** — **cục giết startup AI**:
   - Data Labeling (5-15% chi phí vận hành)
   - Model Retraining (≈20% chi phí build ban đầu mỗi năm)
   - Human-in-the-loop QA (10-30% COGS)
   - Compliance & Security (100-500M cho B2B enterprise)

**AI vs SaaS — Cú sốc về biên lợi nhuận:**
|              | SaaS truyền thống | AI Product |
|--------------|-------------------|------------|
| COGS         | 10-20% revenue    | 40-60% revenue |
| Gross Margin | 80-90%            | 40-60%     |

**Lý do:** API & compute đắt theo mỗi request, không như server cost SaaS gần như 0.

**4 Revenue Models:**
1. **SaaS/MRR** — phí cố định mỗi tháng (Notion AI, Linear)
2. **Consumption** — dùng bao nhiêu trả bấy nhiêu (OpenAI API, AWS)
3. **Transactional** — hoa hồng trên giao dịch (Stripe, Upwork)
4. **Hybrid** — base fee + overage (ChatGPT Plus, GitHub Copilot) — **recommended** cho AI để bảo vệ margin khỏi power users.

---

### 2. Unit Economics — Có lãi trên từng khách không?

**2 câu hỏi trọng tâm:**
- **CAC** = Tổng Sales & Marketing / Số khách mới
- **LTV** = ARPU × Gross Margin × Số tháng ở lại

**Tiêu chuẩn vàng VC:**
- **LTV/CAC > 3** (median public SaaS hiện nay: 4.2:1)
- **CAC Payback < 12 tháng** (thời gian thu hồi vốn marketing từ gross margin)

**Lỗi phổ biến:** Tính LTV bằng Revenue thay vì Gross Margin → sai.

**Churn Rate:** % khách rời đi mỗi tháng. Benchmark AI: < 5%/tháng.

---

### 3. ROI & Scenarios — Tổng thể dự án có đáng làm không?

**3 chỉ số sếp & nhà đầu tư hỏi:**

1. **NPV (Net Present Value)**  
   NPV = Tổng dòng tiền tương lai (đã chiết khấu) − Vốn đầu tư ban đầu  
   Nguyên tắc: **NPV > 0 → Dự án đáng làm**  
   Discount rate cho AI startup rủi ro cao: **20-25%/năm**.

2. **IRR (Internal Rate of Return)**  
   Tốc độ sinh lời nội tại (% mỗi năm).  
   Nguyên tắc: **IRR > WACC** (thường > 20% cho AI).

3. **Project Payback**  
   Bao lâu thu hồi toàn bộ vốn đầu tư (lương dev, setup, R&D)?  
   Benchmark: **< 24 tháng** cho dự án tech.

---

### 4. 3 Scenarios — Stress test

**Luôn có 3 kịch bản:**

| Scenario   | Mục đích          | Đặc điểm                                  |
|------------|-------------------|-------------------------------------------|
| Optimistic | Vẽ giấc mơ        | OpenAI giảm giá, viral lan, khách trả nhiều |
| Base       | Plan & budget thực tế | Dựa trên benchmark + giả định hợp lý |
| Pessimistic| **Cứu mạng**      | Google ra tool free, khách rời nhanh, CAC tăng 2x |

**Pessimistic case mới là cái cứu mạng bạn — không phải Optimistic.**

**Sensitivity Analysis:**  
Top 3 biến nguy hiểm:
1. Adoption Rate
2. ARPU
3. Churn Rate

Chỉ cần 1 trong 3 biến xấu đi 20% → dòng tiền sụp đổ.

---

## File Excel Template

**Tabs:**
1. **Assumptions** — Điền ô màu vàng với 3 scenarios (Optimistic/Base/Pessimistic)
2. **Unit Economics** — Tự tính, kiểm tra LTV/CAC > 3 và CAC Payback < 12
3. **P&L & ROI** — Chọn scenario, xem NPV, IRR, Project Payback, và Pessimistic Runway

**Checkpoints:**
1. Tab 1 đầy đủ, Pessimistic có Churn ≥1.5x Base, CAC ≥1.5x Base, TAM có nguồn
2. Tab 2 Base: LTV/CAC > 3 (xanh), CAC Payback < 12 (xanh), Verdict: HEALTHY
3. Tab 3 Base: NPV > 0, IRR > 20%, Project Payback < 24
4. Tab 3 Pessimistic: **Runway ≥ 12 tháng** (nếu < 12 → cần cắt scope hoặc raise thêm vốn)

**Decision Note (Section 9):**  
Viết 1-2 đoạn trả lời: *"Tại sao chọn ARPU và CAC như trên? Logic gì để bảo vệ con số này trước nhà đầu tư?"*

---

## Ứng dụng vào TA_Chatbot (Day 16-17)

**Product:** AI Teaching Assistant cho VinUniversity, first-year CS students.

**Unit Economics (Base):**
- ARPU: 500,000 VND/tháng (~$20)
- Active Users: 192 (80% của SAM 240)
- Gross Margin: 430,000 VND (500K - 70K COGS)
- Months Retained: 33 (3% monthly churn)
- **LTV: 14,190,000 VND**
- **CAC: 500,000 VND**
- **LTV/CAC: 28.38 > 3 ✓**
- **CAC Payback: 1.16 tháng < 12 ✓**

**ROI (Base):**
- Gross Profit: 82.56M VND/tháng
- Fixed Costs: 60M VND/tháng
- Operating Income: **22.56M VND/tháng** (profit)
- Initial Investment: 200M VND
- **Project Payback: ~8.9 tháng < 24 ✓**
- Initial Cash: 2.5B VND → runway dài

**Pessimistic:**
- Gross Profit: 43.34M VND/tháng
- Fixed Costs: 100M VND/tháng
- Operating Loss: 56.66M VND/tháng
- **Runway: ~44 tháng ≥ 12 ✓**

**Key Insight:** TA_Chatbot là internal tool nên không có revenue truyền thống. Tuy nhiên, Unit Economics tính theo cost savings perspective và vẫn đạt benchmarks nhờ:
- ARPU hợp lý (university có thể allocate budget)
- CAC thấp (direct access qua TA network, không cần paid ads)
- Churn thấp (3% — students dùng xuyên suốt học kỳ)
- Fixed costs kiểm soát (lean team)

---

## Rubric — 100 điểm

| Tiêu chí                | Điểm | Focus                                   |
|-------------------------|------|-----------------------------------------|
| Assumption Realism      | 30   | Số có nguồn, defendable trước VC       |
| AI Cost Awareness       | 25   | Hidden Costs đầy đủ (4 loại)           |
| Unit Economics Quality  | 20   | LTV/CAC > 3, Payback < 12, dùng Gross Margin |
| Scenario Stress-Test    | 15   | Pessimistic thực sự khác Base, Runway ≥12 |
| Decision Note Quality   | 10   | Giải thích logic, có cite benchmark    |

**Grade bands:**
- Outstanding: 90–100 (mang đi pitch VC không cần sửa)
- Strong: 75–89
- Pass: 60–74
- Needs rework: 40–59
- Fail: <40

---

## Takeaways cốt lõi

1. **"Running out of money is how startups die."** — Tim Brady, YC
2. **AI có COGS cao hơn SaaS — biên lợi nhuận mỏng hơn rất nhiều.**
3. **Hidden Costs là cục giết startup AI.** Đừng bỏ 4 thứ: Labeling, Retraining, Human-in-loop, Compliance.
4. **LTV phải dùng Gross Margin, không phải Revenue.**
5. **LTV/CAC > 3 là tiêu chuẩn vàng VC, không phải > 1.**
6. **Pessimistic case mới là cái cứu mạng bạn — không phải Optimistic.**
7. **Mô hình tài chính không phải để đẹp — để biết khi nào cần đổi hướng.**

---

**Chúc các bạn không hết tiền.**  
From product → to numbers → to survival.
