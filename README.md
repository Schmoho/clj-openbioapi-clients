# clj-openbioapi-clients

Meta repository tracking auto-generated Clojure API clients for various bioinformatics and biomedical databases.

## Overview

This repository maintains a collection of auto-generated Clojure API clients for accessing popular biological and biomedical databases. Each client is generated from OpenAPI specifications and hosted in its own dedicated repository.

## Installation

Each client is available as a separate Clojure library. To use a client in your project, add the appropriate dependency to your `deps.edn` or `project.clj` file.

### Leiningen (project.clj)

```clojure
:dependencies [[io.github.schmoho/clj-<client-name>-client "VERSION"]]
```

### CLI/deps.edn

```clojure
{:deps {io.github.schmoho/clj-<client-name>-client {:git/url "https://github.com/Schmoho/clj-<client-name>-client"
                                                      :git/sha "COMMIT_SHA"}}}
```

Replace `<client-name>` with the specific client you want to use (e.g., `uniprot`, `ncbi`, `kegg`).

## Available Clients

The following table lists all currently implemented API clients:

| Client | Repository | Database/API | Description |
|--------|-----------|--------------|-------------|
| **GO** | [clj-go-client](https://github.com/Schmoho/clj-go-client) | [Gene Ontology](http://geneontology.org/) | Access to Gene Ontology terms, annotations, and relationships for biological processes, molecular functions, and cellular components |
| **UniProt** | [clj-uniprot-client](https://github.com/Schmoho/clj-uniprot-client) | [UniProt](https://www.uniprot.org/) | Comprehensive protein sequence and functional information from UniProtKB |
| **UniRef** | [clj-uniprot-uniref-client](https://github.com/Schmoho/clj-uniprot-uniref-client) | [UniRef](https://www.uniprot.org/help/uniref) | UniProt Reference Clusters - clustered protein sequences at 100%, 90%, and 50% identity |
| **Proteomes** | [clj-uniprot-proteomes-client](https://github.com/Schmoho/clj-uniprot-proteomes-client) | [UniProt Proteomes](https://www.uniprot.org/proteomes/) | Complete protein sets for species with fully sequenced genomes |
| **UniRule** | [clj-uniprot-unirule-client](https://github.com/Schmoho/clj-uniprot-unirule-client) | [UniRule](https://www.uniprot.org/help/unirule) | Automatic annotation rules used in UniProtKB |
| **ID Mapping** | [clj-uniprot-id-mapping-client](https://github.com/Schmoho/clj-uniprot-id-mapping-client) | [UniProt ID Mapping](https://www.uniprot.org/help/id_mapping) | Convert between different protein database identifiers |
| **Citations** | [clj-uniprot-citations-client](https://github.com/Schmoho/clj-uniprot-citations-client) | [UniProt Citations](https://www.uniprot.org/help/publications) | Scientific literature citations for protein entries |
| **SIGNAL** | [clj-signal-client](https://github.com/Schmoho/clj-signal-client) | SIGNAL | Signal peptide and protein localization predictions |
| **NCBI** | [clj-ncbi-client](https://github.com/Schmoho/clj-ncbi-client) | [NCBI](https://www.ncbi.nlm.nih.gov/) | Access to National Center for Biotechnology Information databases and tools |
| **Physiome Project** | [clj-physiomeproject-client](https://github.com/Schmoho/clj-physiomeproject-client) | [Physiome Project](https://physiomeproject.org/) | Computational models of physiological systems |
| **CellML** | [clj-cellml-client](https://github.com/Schmoho/clj-cellml-client) | [CellML](https://www.cellml.org/) | Mathematical models of cellular and physiological processes |
| **BioModels** | [clj-biomodels-client](https://github.com/Schmoho/clj-biomodels-client) | [BioModels](https://www.ebi.ac.uk/biomodels/) | Repository of mathematical models of biological processes |
| **KEGG** | [clj-kegg-client](https://github.com/Schmoho/clj-kegg-client) | [KEGG](https://www.kegg.jp/) | Kyoto Encyclopedia of Genes and Genomes - pathways, diseases, drugs, and genomes |

## Usage

After installing a client, you can use it in your Clojure code. Each client provides functions that correspond to the API endpoints of the respective database.

Example (conceptual):

```clojure
(require '[clj-uniprot-client.api :as uniprot])

;; Search for proteins
(uniprot/search-proteins {:query "insulin" :format "json"})

;; Get specific protein entry
(uniprot/get-protein {:accession "P01308"})
```

*Note: Refer to each client's repository for specific API documentation and usage examples.*

## Source Specifications

All clients are generated from OpenAPI specifications maintained in the [Schmoho/openbioapi](https://github.com/Schmoho/openbioapi) repository.

## Client Updates

The `clients.json` file in this repository tracks the current state of all generated clients, including their last update timestamp.

## Contributing

These clients are auto-generated. To contribute:

1. Submit improvements to the OpenAPI specifications in the [openbioapi](https://github.com/Schmoho/openbioapi) repository
2. Report issues specific to individual clients in their respective repositories
3. Report general issues or suggestions in this meta-repository

## License

Each client inherits the license from its respective source API specification. Please refer to individual client repositories for license information.
