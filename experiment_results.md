# n8n Workflow Generation 實驗結果統計表

本表格用於追蹤與比較不同 LLM 模型在不同微調策略下的表現評分（Graph Similarity Score / Pass Rate）。

| Fine-tune 方式 \ 模型名稱 | GPT-4.1 (Reference) | Qwen 3.5 27B | Gemma 4 31B |
| :--- | :---: | :---: | :---: |
| **S1: Zero-shot** | - | **16.8% / 2.8%** | - |
| **S2: FT-Original** | - | - | - |
| **S3: FT-Analysis (Model 5)** | - | - | - |
| **S4: FT-Human** | - | - | - |

---

### 📋 詳細實驗數據紀錄

#### S1: Zero-shot (Qwen 3.5 27B) - 實驗日期：2026-05-14
| 指標項目 | 數值 | 備註 |
| :--- | :--- | :--- |
| **樣本總數** | 100 | 使用 `testing_data_100` 子集 |
| **JSON 有效率 (Raw)** | 51.0% | 原始輸出能成功解析/修復的比例 |
| **Node Type (F1)** | **16.8%** | 全樣本平均 (若僅計解析成功者為 32.9%) |
| **Connection (F1)** | **2.8%** | 全樣本平均 |
| **Parameter Accuracy** | **6.4%** | 全樣本平均 |

---

### 實驗備註：
- **測試集：** 使用 `workflow_template/testing_data_100` 及其對應的 `testing_data_queries.json`。
- **評分標準：** 主要參考 Workflow 結構相似度與節點準確率（Node F1 / Connection F1 / Parameter Accuracy）。
- **Model 5 說明：** 該策略僅包含 Workflow 的詳細分析（節點與連線邏輯）。
- **策略 4 說明：** 該策略結合了原始 Description 與 Workflow JSON，模擬真實訪談後的 PRD 描述。
