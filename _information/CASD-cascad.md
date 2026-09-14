---
title: CASD via cascad
---

The [Centre d'accès sécurisé aux données (CASD)](https://www.casd.eu/) provides remote secure access to confidential French administrative and statistical microdata (INSEE, DGFiP, ministries, etc.). Data cannot leave the secure environment, and no replication package can therefore contain the data.

[cascad](https://www.cascad.tech/) (Certification Agency for Scientific Code and Data) is a French certification agency, backed by CNRS and HEC Paris, that verifies the computational reproducibility of research and issues a certificate describing what was reproduced.

## How verification works

- The researcher's project must already have been approved for access to the relevant data (through the [Comité du secret statistique](https://www.comite-du-secret.fr/)). This is usually satisfied when the authors have submitted to a journal.
- The project must have an active CASD access - this can be reactivated.
- While the researcher can request a *cascad* verification, it is more usual to have the verification requested by the journal. The journal needs to know **the researcher's project name** and any special conditions.
- *cascad* requests approval for a clone of the researcher's project from the *Comité du secret statistique*. **This usually takes about two weeks.**
- The certifier runs the code inside the CASD environment, compares the output to the manuscript, and produces a certificate and a report.
- The report is provided to the journal's data editor.

