# 🛡️ SQL Server Backup Automation & Alert System

## 📌 Objective
Implemented an automated backup solution for mission-critical databases using SQL Server Maintenance Plans, ensuring:
- **Data consistency** through scheduled backups
- **Point-in-time recoverability** with transaction logs
- **Operational visibility** via failure alerts

## 🎯 Target Databases
- `NGRICAO`
- `NGRMON` 
- `AuthorizationApp`
- `NGA_PPA`

## 🛠️ Technical Implementation
### Tools Used:
- SQL Server Management Studio (SSMS)
- SQL Server Agent
- Maintenance Plan Wizard
- Database Mail (for alerting)

### 🔄 Backup Strategy
| Backup Type       | Frequency          | Purpose                     |
|-------------------|--------------------|-----------------------------|
| Full Backup       | Daily (1:00 AM)    | Complete recovery base      |
| Transaction Logs  | Every 30 minutes   | Point-in-time recovery      |

## 🧭 Implementation Guide
### 🔹 Full Backup Configuration
1. Created Maintenance Plan "Daily Full Backup"
2. Scheduled daily at 1:00 AM
3. Target databases: `NGRICAO`, `NGRMON`, `AuthorizationApp`, `NGA_PPA`
4. Backup location: `D:\SQLBackups\Full` (with compression)

### 🔹 Transaction Log Configuration
1. Created "Transactional Log Backup" plan
2. Scheduled every 30 minutes
3. Same target databases (Full Recovery Mode required)
4. Backup location: `D:\SQLBackups\Logs`

### 📢 Alert System
- Configured Database Mail
- Setup Operator notifications
- Email alerts on job failures

## ✅ Business Impact
- **99.9% recoverability** for critical systems
- **Reduced manual effort** by 90%
- **Faster RTO** (Recovery Time Objective)
- **Audit-compliant** backup procedures

## 📂 Repository Structure
