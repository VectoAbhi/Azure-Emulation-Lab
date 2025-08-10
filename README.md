# Azure-Adversarial-Emulation-Lab

## Overview
A hands-on Azure lab used to emulate realistic attacker behavior and then shrink the attack surface through hardening and playbooks. The environment is split into three isolated subscriptions to keep experiments safe and reproducible.

## Objectives
- Reproduce common cloud attack paths in Azure.

- Find and fix misconfigurations that enable lateral movement or privilege escalation.

- Build incident-response playbooks aligned to MITRE ATT&CK.

## Environment
- **Azure subscriptions:** 3 isolated sandboxes

- **Core services:** VNets, NSGs, Azure AD, VM Scale Sets, Storage, Key Vault

- **Tooling:** OpenVAS, Nmap, Azure CLI, Microsoft Defender for Cloud

## What I did
- Ran adversary techniques across the sandboxes and surfaced more than 15 weaknesses across NSGs, IAM roles, and public endpoints that were too permissive.

- Performed targeted scans with OpenVAS and Nmap, classifying eight high‑risk exposures tied to outdated packages and open ports that didn’t need to be reachable.

- Authored four response playbooks mapped to ATT&CK that cut time-to-remediation in the lab by standardizing containment, triage, and recovery steps.

## Key Playbooks
- Suspicious service exposure (Initial Access)

- Overly permissive role assignment (Privilege Escalation)

- Public blob/container discovery (Exfiltration)

- Lateral movement via exposed management ports (Credential Access/Lateral Movement)

## Results
- Hardened NSGs with least‑privilege rules and service tags.

- Removed stale role assignments and introduced custom roles with narrower scopes.

- Documented repeatable IR flows that reduced decision time during simulations.

## How to reproduce
- Deploy the lab templates into separate Azure subscriptions or resource groups.

- Execute scan profiles with OpenVAS and Nmap; validate exposed services and outdated packages.

- Emulate the ATT&CK techniques listed in the MITRE section (e.g., service exposure, permissive role assignments, public storage access).

- Apply hardening steps: tighten NSGs, review IAM role scope, and remove unused public endpoints.

- Re-scan and document before/after results with screenshots.

## MITRE ATT&CK coverage
T1190 Exploit Public-Facing Application, T1068 Privilege Escalation, T1046 Network Service Discovery, T1078 Valid Accounts, T1041 Exfiltration Over C2 Channel.
