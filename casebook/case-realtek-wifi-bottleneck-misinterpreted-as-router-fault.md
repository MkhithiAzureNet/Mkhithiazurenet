🧾 Realtek Wi-Fi Bottleneck misintrepeted as router fault 

## 🧩 Problem Statement
Client on 500/200 line reported poor PC speed (180/200 Mbps). Suspected WR1300 router fault.

## 🔍 Investigative Steps
- Bypass test confirmed full line (500/200)
- Phone over Wi-Fi reached 350 Mbps
- PC had Realtek RTL8821CE Wi-Fi adapter

## 📉 RCA
PC’s 1x1 Realtek adapter inherently limited to ~180–220 Mbps real-world speeds despite high link rate. No LAN port for validation.

## 🧰 Resolution
- Advised client to upgrade to USB 3.0 AC1200 adapter (Intel/MediaTek)
- Rejected router swap (managed expectations)
- Documented adapter constraints and Wi-Fi design limits

