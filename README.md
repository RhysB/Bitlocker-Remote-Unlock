# Bitlocker-Remote-Unlock-SMB
### What is this designed for
BitLocker Remote Unlock is designed as a simplistic replacement for BitLocker Network Unlock, allowing for the automatic unlocking of BitLocker volumes utilizing keys stored on a remote host.
### Limitations
This script will be unable to unlock the Windows volume as the script runs after the system has successfully booted. Therefore it is recommended to store all data that needs to be encrypted on other volumes and use BitLocker encryption stored on TPM if possible.
### Use Case
Automatically unlock volumes used to store VHDs for Virtual Machines on a server at a remote branch. For the unlock to occur, the script at the remote branch must connect to a server at HQ to get the required BitLocker keys.
### Security Implications
1.	Your BitLocker keys may be susceptible in transit over the network. Please ensure you consult any relevant policy and documentation to ensure your network is at a suitable baseline.
2.	BitLocker Remote Unlock will not protect a server that still has network access to the other server. The script is designed to protect against unsophisticated attacks such as physical theft of hardware or use on servers lacking a TPM chip.
3.	If the remote share containing BitLocker keys isn’t appropriately secured, the potential exists for BitLocker keys to be compromised.
