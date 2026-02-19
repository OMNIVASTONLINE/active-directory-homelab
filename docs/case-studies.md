# Case Studies (Helpdesk-Style)

## Case Study 1 — Domain Join + DNS Troubleshooting
**Ticket:** PC unable to locate domain / domain join fails  
**Environment:** Windows Server 2022 DC (DNS), Windows 10 client, Hyper-V internal switch  
**Symptoms:** Client could not find `corp.local` / DC not discoverable  
**Troubleshooting:** Verified IP addressing and DNS configuration, confirmed DC discovery using `nltest` and SRV lookups  
**Root Cause:** Incorrect DNS/adapter configuration and lab network conflicts during initial setup  
**Resolution:** Corrected lab network addressing and ensured client DNS points to the domain controller; verified DC discovery and domain join success  
**Evidence:** See `screenshots/03-client-joined-corp-local.png`

---

## Case Study 2 — Password Expired / Force Change at Next Logon
**Ticket:** User needs password reset / password expired scenario  
**Symptoms:** Needed to simulate a “password expired” helpdesk ticket  
**Troubleshooting:** Noted that the user had **Password never expires** enabled, which prevents forced password change  
**Root Cause:** `PasswordNeverExpires=True`  
**Resolution:** Disabled PasswordNeverExpires, then set **User must change password at next logon**; confirmed setting in evidence  
**Evidence:** `screenshots/05-password-change-next-logon.png`

---

## Case Study 3 — USB Storage Restricted via Group Policy
**Ticket:** USB storage must be disabled on corporate workstations  
**Action:** Created and configured a GPO to disable USB storage (USBSTOR) and generated an HTML GPO report  
**Result:** USB storage policy configured and documented  
**Evidence:** `screenshots/07-gpo-usb-report-1.png`, `screenshots/08-gpo-usb-report-2.png`, `screenshots/09-usb-disable-setting.png`
