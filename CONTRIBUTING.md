# Contributing to TRaSH Panda Guides

Thank you for wanting to improve the ecosystem! To maintain the integrity of this architecture, please adhere to the following guardrails:

1. **Adhere to the Decoupled Philosophy:** Do not submit monolithic, single-host Docker-compose stacks unless they are explicitly being added to the `monolithic` namespace as an alternative.
2. **Security First:** Any new services added must document their required network ports and whether they reside in VLAN 10 (LAN) or VLAN 20 (DMZ). Do not use `chmod 777` in any documentation.
3. **DokuWiki Syntax:** All files are written in DokuWiki markup. Please ensure your submissions match this formatting, not standard Markdown.
