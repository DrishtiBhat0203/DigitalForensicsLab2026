# Experiment 10: Incident Reconstruction & Narrative Building

## Objective
To aggregate disparate log sources (System, Network, and Application) into a unified timeline using Timesketch to reconstruct the sequence of events during a security breach.

##  Tools Used
* **[Timesketch](https://github.com/google/timesketch):** An open-source tool for collaborative forensic timeline analysis.
* **[Plaso (log2timeline)](https://github.com/log2timeline/plaso):** Used to parse various log formats into a single `plaso` storage file for import.

## Methodology
1. **Data Ingestion:** Uploaded the CSV timelines generated in Experiment 04 (System) and Experiment 07 (Browser) into a Timesketch "Sketch."
2. **Filtering & Sketching:** Used SQL-like queries to filter for specific time windows (09:00 - 11:00 UTC) across all data sources.
3. **Event Annotation:** Starred "Key Events" such as the initial login, the execution of the wiping tool, and the final system shutdown.
4. **Narrative Creation:** Linked the "Wipe" command found in the mobile extraction (Exp 08) to the system logs to prove intent.

## Results
- Successfully reconstructed a 45-minute attack window.
- Proven that the attacker gained entry via a compromised VPN account at 09:12 AM.
- Identified the specific files exfiltrated before the `sdelete` (wiping) process began.
