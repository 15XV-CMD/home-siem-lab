Set up the project layout for the home SIEM lab:
- configs/ for Wazuh and Sysmon configuration files
- rules/ for custom Wazuh detection rules
- attacks/ for attack simulation write-ups
- screenshots/ for evidence of alerts and dashboards
- docs/ for setup and build notes

Added .gitignore to exclude credentials (Wazuh password files,
keys) and large VM/installer files (.vmdk, .iso, .7z) from the repo.