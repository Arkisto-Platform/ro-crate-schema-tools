# ro-crate-schema-tools


Tools for RO-Crate to be used for creating and distributing Schema.org style ontologies. 

Given an RO-Crate containing `rdfs:Class`, `rdf:Property`, `schema:DefinedTerm` and `schema:DefinedTermSet` definitions, this code can generate:

-  HTML or Markdown landing pages to document an ontology - eg <http://purl.archive.org/textcommons/terms>

-  A Context file for inclusion in a crate or other JSON-LD



## Background

Schema.org is available in ... schema.org [JSON-LD format](https://schema.org/version/latest/schemaorg-current-https.jsonld). 

For example, `schema:Dataset` has the followinng definition:

```
   {
      "@id": "schema:Dataset",
      "@type": "rdfs:Class",
      "owl:equivalentClass": [
        {
          "@id": "dcmitype:Dataset"
        },
        {
          "@id": "dcat:Dataset"
        },
        {
          "@id": "void:Dataset"
        }
      ],
      "rdfs:comment": "A body of structured information describing some topic(s) of interest.",
      "rdfs:label": "Dataset",
      "rdfs:subClassOf": {
        "@id": "schema:CreativeWork"
      },
      "schema:source": {
        "@id": "http://www.w3.org/wiki/WebSchemas/SchemaDotOrgSources#source_DatasetClass"
      }
   }
```

Note that there is a `schema:Class` Class, but we follow Schema.org practice and use `rdfs:Class` and `rdf:Property` for describing classes and schemas.


## Usage

To see the usage:

 -  type `>> node roc-schema.js  -h`

 ```
Usage: roc-schema [options] <d>

Extracts a markdown or HTML page from an RO Crate containing Schema.org style Classes and Properties 

Options:
  -V, --version            output the version number
  -c, --config [conf]      configuration file
  --html                   Output HTML (default is markdown)
  -t,  --ro-crate-terms    Output vocabulary and context file for terms
  -u,  --url [url]         URL for the final result (so links can be made relative)
  -o, --output-path [rep]  Directory into which to write output (default: null)
  -h, --help               display help for command
```
