# Task1-Port-Scan
# Task 1 - Local Network Port Scan

## My IP
192.168.56.1

## Command run
nmap -sS 192.168.56.1 -oN scan_results.txt

## Results (from scan_results.txt)
Open ports:
- 135/tcp — msrpc
- 139/tcp — netbios-ssn
- 445/tcp — microsoft-ds (SMB)
- 7070/tcp — realserver (streaming)

## What this means (simple)
- Port 135: Windows RPC service (medium risk if exposed)
- Port 139: NetBIOS file sharing (medium-high risk)
- Port 445: SMB file sharing (high risk if exposed to internet)
- Port 7070: Streaming service (unknown, needs checking)

## Security notes / recommendations
- If you don't need file sharing, disable NetBIOS/SMB or stop the service.
- Keep the system updated with security patches.
- Use a firewall to block access to these ports from untrusted networks.
- Re-run scans after changes to verify.

## Files included
- scan_results.txt (raw Nmap output)
- README.md (this file)
