# 📺 Case Study: Samsung TV Wi-Fi Rejection (Error 107) – RCA + Hotspot Verification

### 📅 Date Logged: 2025  
**Author**: Nhlanhla Mkhithi  
**Diagnostic Framework**: CoolNet+ Pulse | Manual RCA  

---

## 🧠 Incident Summary

Samsung TV failed to connect to **Cudy WR1300** Wi-Fi, repeatedly displaying **Error 107** despite manual password entry and router visibility.  
Initial assumptions suggested TV hardware or firmware issue, but subsequent diagnostics revealed **router-side behavior rejection**.

---

## 🧪 Diagnostic Workflow

### ✅ 1. Hotspot Confirmation  
- TV connected successfully to a **mobile hotspot**  
- Internet access and app functionality confirmed  
- ❗ Proves TV’s **Wi-Fi module, DHCP, and DNS stack** are intact

### 🔍 2. DNS Overrides  
- Manually set **Google DNS (8.8.8.8 & 8.8.4.4)** on:
  - WR1300 router
  - TV settings  
- Increased handshake compatibility and reliability

### ⚙️ 3. MTU Optimization  
- Reduced MTU on WR1300 to `1440`  
- Eliminated potential fragmentation in VOIP-heavy ISP setups (Vodacom FNO context)

### 📶 4. Band Filtering  
- TV only detected **2.4 GHz**, even after Smart Connect disabled  
- Locked router to **channel 6 / width 20MHz** for stable visibility  
- Resolved intermittent band hopping or DFS channel conflicts

---

## 📡 Device Verdict Matrix

| Device          | Behavior               | Diagnostic Verdict            |
|-----------------|------------------------|-------------------------------|
| Samsung TV      | Error 107 – Wi-Fi fail | Wi-Fi hardware OK; router rejection |
| Mobile Hotspot  | Immediate success      | Confirms TV stack functional |
| Cudy WR1300     | Inconsistent response  | DNS/MTU/handshake conflict |

---

## 🛠️ Client-Safe Fix Summary

> 📋 _TV failed to connect due to router-side handshake issues. Resolved by setting DNS, lowering MTU, and forcing 2.4 GHz band._

---

## 🔧 CoolNet+ Pulse Extension (Proposed)

| Flag                  | Trigger Conditions                         | Suggested Action                         |
|-----------------------|--------------------------------------------|------------------------------------------|
| `📺 TV_RejectDetected` | Ping and gateway stable; device fails     | Run MTU/DNS scan module                  |
| `📶 BandMismatch`      | Device locks on 2.4 GHz only               | Suggest Smart Connect disable or DFS lock |
| `🔧 MTUConflict`       | Pathping latency + fragmentation symptoms | Lower MTU to 1440                        |

---

## 🎯 Recruiter/Peer Relevance

- **Reverse-engineered firmware-level negotiation patterns** with no device logs
- Demonstrates **multi-layer RCA**: DNS, MTU, Wi-Fi band analysis
- Example of **artifact-driven client insight** ready for SmartDetector Pro logic gate integration

---

