## ✅ README_Policies_Comparison_Tool.md

```markdown
# ✅ Policies Comparison Tool

## 📌 Purpose
Compare policy configurations (DynamoDB style) across different DCs (like DCA, DCB, etc.) to validate consistency and identify mismatches.

## 📂 Input Format (CSV)

- The CSV must contain the following headers:
  - `OverRideID` (row identifier)
  - `DCA`, `DCB`, `DCC`, `DCD` — each column is a **JSON array** of key-value pairs

### 🧾 Sample Cell Value
```json
[{"S":"hevc_hdr10_5994"},{"S":"dolby"},{"S":"noDrm"},{"S":"three8xl"},{"S":"outletCollapse"},{"S":"disableDolbyDashWeb"},{"S":"dolby5994"},{"S":"default"},{"S":"sixHourDvrWindow"}]
🧾 Sample Row
OverRideID,DCA,DCB,DCC,DCD
Policy123,"[{""S"":""hevc_hdr10_5994""},{""S"":""dolby""},{""S"":""noDrm""}]","[{""S"":""hevc_hdr10_5994""},{""S"":""dolby""}]","[{""S"":""dolby""},{""S"":""default""}]","[{""S"":""dolby""}]"

⚙️ Features

Highlights policy differences across all DCs
  ✅ Green background if policy set matches DCA
  ❌ Red background if any policy deviates from DCA
  JSON policies automatically rendered and expanded
  Search across entire table including OverRideID
  Download table as .xlsx

🔍 Search Behavior
  Highlights only the exact matched word in each cell
  Expands JSON cells that contain the matched word
  Automatically scrolls to matches

🎨 UI Features
  Theme toggle (dark/light)
  Expand/Collapse all JSONs
  Paste JSON manually or upload via CSV
  Filter/search with instant highlight

🧠 Notes
  All JSON in the policy fields should be a valid JSON array of {"S": "<policy_name>"} items
  Matching is order-insensitive and case-sensitive by default
  Use consistent quoting and escaping for CSV JSON values

