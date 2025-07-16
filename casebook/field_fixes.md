### 🔍 Case ID: Client_VoIP_Yealink

**Tool Used**: Remote Voice Assist + Live Device Observation

**Issue Summary**:  
Client could dial out from all devices but could not receive inbound calls on Yealink T40P desktop phone. Other extension devices were ringing correctly.

**Root Cause**:  
Do Not Disturb (DND) was enabled on Yealink T40P, blocking incoming call notifications. User unaware DND was active.

**Resolution Steps**:
- Guided client (non-technical) via phone call:
  - Verified device was powered and responsive.
  - Asked client to press “volume up” to confirm ringer not muted.
  - Identified DND icon was active.
  - Instructed client to disable DND via physical button.
  - Rebooted phone to refresh SIP registration.

**Outcome**:  
Inbound calls now ring on all devices as expected. Client successfully tested with both DID numbers.

**Confidence Level**: High  
**Escalation Needed**: No

