# Cyber Knowledge Graph

This project was developed during the NITK Cybersecurity Bootcamp held in February 2025. It integrates multiple cybersecurity datasets into a unified Neo4j-based graph database to enhance threat intelligence, vulnerability analysis, and cyberattack pattern discovery.

## Overview

The Cyber Knowledge Graph (CKG) brings together widely-used cybersecurity datasets such as CVE (Common Vulnerabilities and Exposures), CWE (Common Weakness Enumeration), CAPEC (Common Attack Pattern Enumeration and Classification), ICS Attack, and Mobile Attack datasets. These are mapped into a connected graph structure, enabling advanced querying, relationship-based reasoning, and graph analytics.

## Bootcamp Acknowledgment
This repository contains the project files from the Bootcamp on "Software and Systems Security" conducted by NITK Surathkal from 17th to 21st February 2025. The event was organized under the Information Security Education and Awareness (ISEA) – Phase III initiative supported by the Ministry of Electronics and Information Technology, Government of India.


## Features

- Unified graph-based representation of cybersecurity datasets.
- Support for importing and connecting CVE, CWE, CAPEC, ICS Attack, and Mobile Attack data.
- Visual and programmatic querying via Neo4j Browser and APIs.
- Graph analytics using Python libraries such as NetworkX and Pandas.
- Easy integration and extension for further threat intelligence applications.

## Technologies Used

- Python (data parsing, transformation, and import)
- Neo4j AuraDB (graph database)
- Cypher Query Language (graph queries)
- Pandas (data processing)
- NetworkX (graph analytics)

## Project Structure

| File/Folder           | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `import_data.py`      | Script to parse and import CSV/JSON data into Neo4j.                        |
| `graph_queries.cypher`| Sample Cypher queries to explore CVE → CWE → CAPEC relationships.           |
| `data/`               | Contains raw and processed cybersecurity datasets in CSV/JSON format.       |
| `.env`                | Neo4j connection credentials (not included for security reasons).           |
| `README.md`           | Project documentation and structure overview.                               |

## Sample Cypher Queries
```cypher
// Find CVEs linked to a specific CWE
MATCH (cve:CVE)-[:RELATED_TO]->(cwe:CWE {id: "CWE-89"})
RETURN cve.id, cve.description

// Trace attack paths
MATCH (cve:CVE)-[:RELATED_TO]->(cwe:CWE)-[:RELATED_TO]->(capec:CAPEC)
RETURN cve.id, cwe.id, capec.name
```
Use-Cases
Analyzing vulnerabilities across different attack patterns.

Identifying common weaknesses exploited in specific domains.

Supporting cyber threat detection using relationship-based reasoning.

Enabling visual threat mapping for SOC analysts or cybersecurity researchers.

Credits
This project was collaboratively developed during the NITK Cybersecurity Bootcamp in February 2025.

Team members:
Prajwal HP,
Amulya,
Nidhi v,
Pavan Bendre.


Special thanks to our mentors and faculty at NITK for guidance and support during the bootcamp.
