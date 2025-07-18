🧾 MTU size adjustment resolves client access to websites and VOIP

## 🧩 Problem Statement
Client unable to access several websites and VOIP calls were failing. Line test confirmed stable connectivity, indicating potential MTU-based fragmentation.

## 🔍 Investigative Steps
- Verified line performance: 200/200 Mbps via ONT bypass
- Suspected SIP/RTP packet fragmentation at MTU 1480
- Ran MTU SweetSpot diagnostic (custom module developed by me) to discover optimal MTU
- Identified 1440 as compatible with VOIP traffic and site access

## 📉 Root Cause Analysis
Default MTU setting (1480) fragmented VOIP signaling packets. Fragmentation prevented proper session initiation and media delivery. SweetSpot test confirmed that 1440 restored handshake integrity.

## 🧰 Resolution
- Updated MTU on WR Cudy router to 1440
- Verified site accessibility and VOIP functionality post-change

## 🧠 Knowledge Value
- 1440 logged as stable dual-traffic MTU baseline
- Updated MTU SweetSpot logic gate to recommend 1440 default for VOIP-enabled clients
- Case documented for future Coolnet+ heuristic rules
