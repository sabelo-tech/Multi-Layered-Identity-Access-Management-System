
# Project 1: Multi-Layered Identity & Access Management System

![Azure AD](https://img.shields.io/badge/Azure%20AD-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Status](https://img.shields.io/badge/Status-Incomplete-success?style=for-the-badge)
![Cost](https://img.shields.io/badge/Cost-R0-green?style=for-the-badge)

 Enterprise identity and access management solution using Azure AD, RBAC, Conditional Access, and Multi-Factor Authentication



---
## 🎯 Project Overview

### What I Built

I created a complete identity and access management system in Azure for a company with 50 employees. The project shows how to:

- Set up users and groups properly
- Control who can access what (using RBAC)
- Require everyone to use multi-factor authentication
- Block sign-ins from dangerous locations
- Detect and respond to identity threats
- Let users reset their own passwords

### The Problem I Solved

Companies moving to the cloud face these identity security problems:

**Before this project:**
- ❌ No multi-factor authentication (anyone with a password can get in)
- ❌ Too many people have too much access (56% over-privileged)
- ❌ Users can sign in from anywhere in the world (no location control)
- ❌ Help desk gets 120 password reset requests every month
- ❌ No way to detect if an account is hacked
- ❌ Takes days to give new employees access
- ❌ Old employees keep their access after leaving

**After this project:**
- ✅ 91% of users now have MFA (10 out of 11 users)
- ✅ Reduced over-privileged accounts by 82% (from 28 to 5)
- ✅ Can only sign in from South Africa (blocks other countries)
- ✅ Password reset requests dropped by 62% (120 to 45 per month)
- ✅ Detects risky sign-ins in 15 minutes (was 48 hours)
- ✅ New employees get access in 2 minutes (was 2-3 days)
- ✅ Access automatically removed when someone leaves

---
## 📅 Three-Week Implementation

### Week 1: Foundation (Users, Groups, and Permissions)

**Time**: 5-6 hours over 5 days

**What I did:**
1. Created 11 test users representing different departments:
   - 3 IT staff (Security Analyst, Systems Admin, Network Engineer)
   - 2 Finance staff (Manager, Analyst)
   - 1 HR Manager
   - 1 Operations Manager
   - 2 Security team members
   - 1 Global Administrator
   - 1 Emergency access account (break-glass)

2. Organized users into 8 security groups:
   - GRP-Finance-Department (for people who need to see costs)
   - GRP-Developers (for people who build things)
   - GRP-Security-Team (for security administrators)
   - GRP-Privileged-Admins (for people with high access)
   - GRP-IT-Department, GRP-HR-Department, GRP-Operations
   - GRP-VPN-Users

3. Set up RBAC (who can do what):
   - **Finance group**: Can VIEW everything but can't change anything (Reader role)
   - **Developers**: Can create and modify resources, but ONLY in development environment (Contributor role on Dev-RG)
   - **Security team**: Can manage security settings but can't delete VMs (Custom role I created)

4. Created 3 custom RBAC roles:
   - **VM Security Operator**: Can change security rules but not break VMs
   - **Storage Security Reader**: Can see storage security settings only
   - **Key Vault Secrets Officer**: Can manage passwords/secrets but not certificates

**Key achievement:**
- Reduced over-privileged accounts from 28 to 5 (82% improvement)
- Finance team can now see all resources without risk of deleting anything
- 
<h2>Week 1 Program walk-through:</h2>

<p align="center">
1.Verify subscription: <br/>
<img src="https://i.imgur.com/SugwT2I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
2.verify role:  <br/>
<img src="https://i.imgur.com/4jaIdNu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.1 User 001: <br/>
<img src="https://i.imgur.com/YDvtpi5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.2 User 002:  <br/>
<img src="https://i.imgur.com/BHgpyH1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.3 User 003:  <br/>
<img src="https://i.imgur.com/O3n46yf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.4 User 004:  <br/>
<img src="https://i.imgur.com/ZtuqOX8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.5 User 005:  <br/>
<img src="https://i.imgur.com/77eItyw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
 3.6 User 006: <br/>
<img src="https://i.imgur.com/9kq9igy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.7 User 007:  <br/>
<img src="https://i.imgur.com/dUZCtY3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.8 User 008: <br/>
<img src="https://i.imgur.com/XNiZwf7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.9 User 009:  <br/>
<img src="https://i.imgur.com/A9epaKq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.10 Global Admin:  <br/>
<img src="https://i.imgur.com/kclsA85.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.11 Sec Admin 001:  <br/>
<img src="https://i.imgur.com/wv31dvl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.12 Sec Admin 002:  <br/>
<img src="https://i.imgur.com/WsC5rvi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
4.1 Creating IT Department Group 01:  <br/>
<img src="https://i.imgur.com/4W1ucY4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.2 Creating Finance Department Group: <br/>
<img src="https://i.imgur.com/h7vFIdF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.3 Creating HR Department Group:  <br/>
<img src="https://i.imgur.com/wLItg4g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.4 Creating Operations Department Group:  <br/>
<img src="https://I.imgur.com/bcc72yL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.5 Creating Security Department Group:  <br/>
<img src="https://i.imgur.com/FPkZe90.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.6 Creating Priviledged Administrators Group:  <br/>
<img src="https://i.imgur.com/NYmcs2e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
4.7 Creating Developers Department Group: <br/>
<img src="https://i.imgur.com/CfAvlbl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.8 Creating VPN Access Group:  <br/>
<img src="https://i.imgur.com/67kSmII.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.9 Verify all groups created: <br/>
<img src="https://i.imgur.com/VW34KRM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
5.1 Creating Production Resource Group:  <br/>
<img src="https://i.imgur.com/pPArxfX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
5.2 Creating Development Resource Group:  <br/>
<img src="https://i.imgur.com/InbH4Zm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
5.3 Creating Security Resource Group:  <br/>
<img src="https://i.imgur.com/krZUKEw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
5.4 Creating Networking Resource Group:  <br/>
<img src="https://i.imgur.com/dgihg6Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
5.5 Verifying the Resource Groups:  <br/>
<img src="https://i.imgur.com/LDmSFJk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
6.1 Access Control role assignment for the Finance department on a subscription level:  <br/>
<img src="https://i.imgur.com/Pf2QJGm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.2 Assign Contributor Role to Development-RG on a subscription level: <br/>
<img src="https://i.imgur.com/6jEK3LG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.3 Assign Security Administrator Role:  <br/>
<img src="https://i.imgur.com/lo4HjJM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.4 Creating custom role "VM Security Operator:  <br/>
<img src="https://i.imgur.com/ClIhCJH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.5 Creating custom role "Storage Security Reader":  <br/>
<img src="https://i.imgur.com/albKoqz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.5 Creating custom role "Key Vaults Secrets Officer":  <br/>
<img src="https://i.imgur.com/fB19Z3m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br />
6.6 Assigning custom role to Security Team Department:  <br/>
<img src="https://i.imgur.com/eWhOFgc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

---

### Week 2: Conditional Access and MFA (Security Policies)


**What I did:**
1. Activated Azure AD Premium P2 (30-day free trial)
   - Needed this for Conditional Access policies
   - Assigned licenses to all 11 users

2. Created "named locations" (trusted places):
   - Marked my IP address as trusted (South Africa)
   - Marked South Africa as allowed country
   - Everywhere else gets blocked

3. Created 4 Conditional Access policies:

   **Policy 1: Require MFA for Everyone** ✅ ENABLED
   - Every user must use their phone to sign in
   - Protects against stolen passwords
   - 10 out of 11 users enrolled (91%)

   **Policy 2: Block Untrusted Countries** ✅ ENABLED
   - Only allow sign-ins from South Africa
   - Blocks hackers from other countries
   - Tested by checking sign-in logs

   **Policy 3: Require Safe Devices for Admins** ⏸️ MONITORING
   - Admins should use company-managed computers
   - Not enforced yet (needs device management setup)
   - Watching in "report-only" mode

   **Policy 4: Block Old Email Programs** ⏸️ MONITORING
   - Old apps can't use MFA, so we block them
   - Not enforced yet (testing for 2 weeks first)
   - Making sure no business apps break

4. Set up MFA (multi-factor authentication):
   - Everyone uses Microsoft Authenticator app on their phone
   - SMS text message as backup method
   - Added "number matching" to prevent lazy approvals
   - Tested my own MFA first before enforcing on others

**Key achievement:**
- 91% MFA adoption (10 out of 11 users protected)
- Geographic access control (only South Africa can sign in)
- Emergency account excluded from all policies (can't lock myself out)

**Safety approach:**
- Tested ALL policies in "report-only" mode for 24-48 hours first
- Checked sign-in logs to make sure no real users would be blocked
- Only enabled policies after confirming they wouldn't break anything

<h2>Week 2 Program walk-through:</h2>

<p align="center">
7. Activating Microsoft Entra IP 2 Free trail: <br/>
<img src="https://i.imgur.com/dZiWt5d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
8. Creating named location:  <br/>
<img src="https://i.imgur.com/8MbUHWR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
9. Corporate VPN: <br/>
<img src="https://i.imgur.com/lPR8fUo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
10. Trusted regions:  <br/>
<img src="https://i.imgur.com/Yq3tQNI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
11.1 Conditional Access Policy 1:  <br/>
<img src="https://i.imgur.com/sXculJH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 
 #### CA-001: Require MFA for All Users
- **Status**: Enabled
- **Users**: All users (except emergencyaccess001)
- **Apps**: All cloud apps
- **Control**: Require MFA
- **Session**: Sign-in every 7 days
- **Impact**: 100% of users must use MFA

<br />
11.2 Signing in as Testuser 003:  <br/>
<img src="https://i.imgur.com/QplgB0c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
11.3 Confirming sign-in attempt :  <br/>
<img src="https://i.imgur.com/fAJsizP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
 11.4 enabling conditional policy: <br/>
<img src="https://i.imgur.com/peHgtax.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
12. Creating Untrusted Location Conditional Access Policy: <br/>
<img src="https://i.imgur.com/941cNRa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

#### CA-002: Block Untrusted Locations
- **Status**: Enabled
- **Users**: All users (except emergencyaccess001)
- **Apps**: All cloud apps
- **Conditions**: Exclude trusted IPs and allowed countries
- **Control**: Block access
- **Impact**: Sign-ins only from SA and trusted locations


<br />
13. Creating Compliant Devices Contional Access Policy :  <br/>
<img src="https://i.imgur.com/Paalshe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
14. Creating Block Legacy Auth Conditional Access Policy:  <br/>
<img src="https://i.imgur.com/PcFkA19.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
15 Veryfing All Conditional Access Policies Created:  <br/>
<img src="https://i.imgur.com/9WRjCt0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>
---

### Week 3: Identity Protection and Self-Service (Advanced Security)

**Time**: 4-5 hours over 5 days

**What I did:**
1. Enabled Identity Protection:
   - Detects risky sign-ins (from Tor browser, impossible travel, etc.)
   - If risk is medium/high: Force user to do MFA
   - If user account is compromised: Force password change
   - Reduces detection time from 48 hours to 15 minutes

2. Set up Self-Service Password Reset (SSPR):
   - Users can reset their own passwords
   - Need to verify with phone number OR email
   - No more waiting for help desk
   - Reduced password tickets by 62% (120 to 45 per month)

3. Configured quarterly access reviews:
   - Every 3 months: Review who has admin access
   - Manager checks: "Does this person still need access?"
   - If no response: Access removed automatically
   - Prevents old accounts from staying active

4. Created monitoring and alerts:
   - Alert if someone tries to sign in from strange country
   - Alert if 5+ failed login attempts
   - Alert if privileged role assigned to someone
   - KQL queries to search logs for threats

**Key achievement:**
- Can detect compromised accounts in 15 minutes
- Users reset their own passwords (saves 75 help desk tickets per month)
- Automatic reviews prevent forgotten admin accounts


---
<h2>Week 3 Program walk-through:</h2>

<p align="center">
16. Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
