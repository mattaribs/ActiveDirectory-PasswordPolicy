# Active Directory Password Policy Lab

## 📌 Project Overview
This project demonstrates how to enforce password policies in an Active Directory environment using Group Policy Management. By configuring rules for password complexity, history, expiration, and length, I ensured that users in the hagital.local domain must use strong passwords to improve security.  

## ⚙️ Tools Used
- Windows Server 2019 (Domain Controller)
- Windows 10 (Client VM)
- Group Policy Management Console (GPMC)
- Active Directory Users and Computers (ADUC)

## 🚀 Steps
1. Open Group Policy Management
	 - On the Domain Controller, press Win + R, type gpmc.msc, and hit Enter.
   - This opens the Group Policy Management Console (GPMC).
   - <img width="1920" height="997" alt="GPMC opening" src="https://github.com/user-attachments/assets/b1a13d13-bea8-4306-b5e9-c62fe75d48b8" />

2. Edit the **Default Domain Policy**.
   - In the left pane, expand hagital.local.
   - Right-click Default Domain Policy → click Edit.
   - <img width="1900" height="950" alt="Default domain policy selectio" src="https://github.com/user-attachments/assets/364ebddc-90e8-44d3-abaf-01eb669079d7" />

3. Navigate to:
   - Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies → Password Policy.
   - <img width="421" height="378" alt="password policy path" src="https://github.com/user-attachments/assets/a552fb55-b066-41fe-9bdf-e08c62527701" />
 
4. Configure:
   - Enforce password history: `5`
   - Maximum password age: `30 days`
   - Minimum password age: `1 days`
   - Minimum password length: `7`
   - Complexity requirements: Enabled
   - <img width="591" height="514" alt="password policy setttings" src="https://github.com/user-attachments/assets/1ebaed1a-80d7-4ac5-aae8-481e3125319a" />

5. In the command prompt(admin), run:
   - <img width="775" height="457" alt="command prompt" src="https://github.com/user-attachments/assets/d7db6777-ba4e-4800-b95e-708b5566b5af" />

## ✅ Testing
Login and change password for a new user alice.fimmel@hagital.local
<img width="1701" height="879" alt="alice login" src="https://github.com/user-attachments/assets/fa9c8570-9245-4c62-9888-15faa7f113fd" />

- Tried setting `password123` → ❌ failed (too weak).
  <img width="1914" height="913" alt="failed password" src="https://github.com/user-attachments/assets/a40cb98f-46c9-48ed-9d7f-c23775e2a9ed" />
	

- Tried `Pa$$word123!` → ✅ success.
  <img width="1752" height="871" alt="password changed" src="https://github.com/user-attachments/assets/a351a7ff-e8cc-490f-b3e6-b58b4a88df3b" />

## ✅ Results
- Weak passwords were rejected.
- Strong passwords meeting the complexity and length requirements were accepted.
- Users are now forced to change their password every 30 days, preventing stale credentials.

## 🔐 Why This Matters
Weak passwords are one of the most common attack vectors in enterprise environments. By enforcing a strong password policy:
- Brute-force attacks are harder.
- Compromised accounts can be rotated more frequently.
- Security compliance standards (like ISO, NIST, CIS) are better met.

## 📖 Reflection
This project taught me:
- How Group Policy is used to manage domain-wide settings.
- The importance of the Default Domain Policy for enforcing account security.
- How to test and verify policy application across domain users.

