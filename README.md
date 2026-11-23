# Home SIEM Lab (Wazuh)

A virtual security operations lab built to practise threat detection and incident investigation.

**What it does:**
- Wazuh SIEM server collecting logs from Windows 11 and Linux endpoints
- Sysmon for detailed Windows process and network logging
- Simulated attacks (brute force, port scanning, privilege escalation) from a Kali Linux VM
- Custom Wazuh detection rules mapped to MITRE ATT&CK techniques
- Write-ups documenting each attack, what was detected, and detection gaps

**Tools:** Wazuh 4.x, Ubuntu Server 24.04, Windows 11, Sysmon, Kali Linux, VMware Workstation Pro

## Lab Architecture

```mermaid
flowchart LR
    subgraph Host["Windows 11 Host · VMware Workstation Pro · NAT 192.168.151.0/24"]
        K["Kali Linux<br/>Attacker"]
        W["WIN11-VICTIM<br/>Windows 11 + Sysmon<br/>Wazuh agent"]
        S["Wazuh Server<br/>192.168.151.10<br/>Indexer · Manager · Dashboard"]
    end
    K -- "simulated attacks" --> W
    W -- "logs & events (1514/TCP)" --> S
    A["Analyst browser<br/>(host)"] -- "HTTPS 443" --> S
```




**Status:** In progress