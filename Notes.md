# Notes 
  

Here are some queries that I'm not sure I understand what it's doing:


1. Elements in an RDF collection:

`  { :list rdf:rest*/rdf:first ?element }`




Queries I am testing.

1. Query to get two broader terms away from the original.

`SELECT ?iri ?iriLabel?broadTerm1 ?broadTerm2 `

`WHERE {`

  `?iri skosxl:prefLabel ?o.`

  `?o skosxl:literalForm ?iriLabel.`

  `?iri gvp:broaderGeneric ?bLabel.`

  `?bLabel skosxl:prefLabel ?z.`

  `?z skosxl:literalForm ?broadTerm1.`

`OPTIONAL` 

  `{?iri gvp:broaderGeneric/gvp:broaderGeneric ?b2Label.`
  
  `?b2Label skosxl:prefLabel ?z2.`
  
  `?z2 skosxl:literalform ?broadTerm2.}`

`filter (lang(?iriLabel)="en")`

`filter (lang(?broadTerm1)="en")`

`filter (lang(?broadTerm2)="en")`

`} LIMIT 10`



