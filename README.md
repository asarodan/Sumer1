Ur III ATF Pipeline

Pipeline for parsing Ur III administrative tablets in ATF format, extracting economic transactions, and modeling them as directed weighted networks.

Overview

This project processes cuneiform administrative texts from the Ur III period (ca. 2112–2004 BCE), particularly tablets from the Umma provincial archive.

The pipeline:

1. Loads ATF transliterations from a corpus directory.
2. Extracts quantities, commodities, issuers, recipients, and dates.
3. Normalizes personal names and institutions.
4. Builds a directed transaction network.
5. Computes standard network metrics.
6. Exports results for further analysis in Gephi and spreadsheet software.

Current commodity support includes barley and several additional agricultural products.

Requirements

Python 3.10 or newer is recommended.

Install dependencies:

pip install networkx

Directory Structure

project/
├── atf_pipeline.py
├── data/
│   └── raw_atf/
│       ├── P123456.atf
│       ├── P123457.atf
│       └── ...
└── output/

Place all ATF files inside:

data/raw_atf/

The program automatically loads every file ending in .atf.

Running the Pipeline

From the project directory:

python atf_pipeline.py

The script will:

1. Load all ATF files.
2. Extract transactions.
3. Filter barley transactions.
4. Construct a directed network.
5. Calculate network metrics.
6. Export results.

Output Files

Generated in:

output/

barley_network.gexf

Network file for visualization and analysis in Gephi.

Contains:

* Nodes representing individuals or institutions.
* Directed edges representing transfers.
* Edge weights based on transaction volume.

transactions.csv

Full transaction export.

Columns include:

* tablet_id
* issuer
* recipient
* quantity
* commodity
* date information
* transaction type

transactions_sulgi_45-48.csv

Subset of barley transactions dated to Šulgi years 45–48.

unresolved_names.txt

List of names that could not be matched to the authority tables.

These entries should be reviewed manually and added to the normalization authority before using the results as historical evidence.

Historical Notes

This software is designed for exploratory research and should not be treated as a replacement for philological analysis.

Name normalization, transaction extraction, and date identification are heuristic procedures and may require corpus-specific refinement.

All network results should be validated against the underlying tablet evidence.

Data Sources

* CDLI (Cuneiform Digital Library Initiative)
* BDTNS (Base de Datos de Textos Neosumerios)
* ORACC ATF Documentation

License

Research and educational use.