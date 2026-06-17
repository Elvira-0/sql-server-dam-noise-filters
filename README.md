# sql-server-dam-noise-filters
Optimized regex rules to filter out SQL Server infrastructure noise (Hangfire, JDBC, Temp Tables) for Database Activity Monitoring (DAM) tools.
# SQL Server DAM Noise Filter Rules 🛡️

A highly optimized and meticulously curated list of Regex rules designed to filter out infrastructure and tooling noise from SQL Server Database Activity Monitoring (DAM) systems like Imperva, IBM Guardium, and others.

## 🎯 The Problem
Database audit logs get heavily bloated by non-business infrastructure traffic (JDBC pings, SSMS intellisense, background jobs). This bloat costs storage, reduces DAM appliance performance, and hides real security threats.

## 🚀 The Solution
These 47 robust regex rules catch and drop safe, routine machine-to-machine chatter without risking your actual business logic (Stored Procedures, sensitive queries).

**Filters Included:**
* Driver & Connection Handshakes (JDBC, .NET SqlClient)
* Background Job Heartbeats (Hangfire, FileNet)
* Temporary Table Operations (`#temp`, `##global`)
* Environment Setups (`SET NOCOUNT ON`, `SET FMTONLY`)
* Tooling Metadata Queries (SSMS Intellisense, AlwaysOn Pings)

## 📂 Usage
Simply copy the raw contents of `dam_regex_rules.txt` and import them into your DAM appliance's global drop/ignore policy.

## 🤝 Contributing
Pull requests are welcome! If your company uses a specific APM tool or background service that generates safe noise, please open an issue or submit a PR with the tested regex.

## 📜 License
[MIT](LICENSE)
