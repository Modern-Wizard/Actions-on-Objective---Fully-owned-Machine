# Actions on Objective-Fully-owned-Machine

## Fully-Owned Machine
Now, the attacker has gained administrative privileges inside the machine. Find all persistence techniques used by the attacker.

In addition, the unusual executions are related to the malicious C2 binary used during privilege escalation.

## Investigation Guide
Now, we can rely on our cheatsheet to investigate events after a successful privilege escalation:

    Useful Brim filter to get all HTTP requests related to the malicious C2 traffic : _path=="http" "<replace domain>" id.resp_p==<replace port> | cut ts, host, id.resp_p, uri | sort ts
    The attacker gained SYSTEM privileges; now, the user context for each malicious execution blends with NT Authority\System.
    All child events of the new malicious binary used for C2 are worth checking.

Significant Data Sources:

    Packet Capture
    Sysmon
    Windows Event Logs
