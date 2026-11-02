# LOF-ODP-005: Legal Time and Versions

Draft ontology design pattern for the [Legal Ontologies Foundry](https://legal-ontologies-foundry.github.io/odp/odp-005/).
Status: **draft 0.1.0**, for review by the founding coordinators.

When legal content is in force and when it applies (kept apart, because they
come apart); the legal acts that amend and repeal it; the consolidated
versions that state it as it stands at a time; and the periods within which
legal positions must be discharged, computed from the occurrences that start
them. Region bounds are BFO instants carrying time-zoned date-times
(`xsd:dateTimeStamp`); content is succeeded, not changed. Together with LOF-ODP-004 *undischarged during*, the pattern identifies
overdue positions.

## Files

| Path | Contents |
|---|---|
| `src/ontology/lof-odp-005-edit.ttl` | Editors' file |
| `src/ontology/imports/` | BFO 2020 core and the base releases of ODP-001 to 004 |
| `src/ontology/alternatives/` | ODP-003 Option B base, for testing under both placements |
| `src/examples/gdpr-timeline.ttl` | Worked example: the GDPR, Directive 95/46/EC and the UK Data Protection Act 1998, and a late Art. 33 notification |
| `src/shapes/time-checks.shacl.ttl` | Period bounds, compliance periods, repeal and consolidation checks |
| `src/mappings/odp-005-standards.sssom.tsv` | Alignment with ELI, Akoma Ntoso, OWL-Time and LOMO (SSSOM) |
| `src/sparql/` | QC checks (`*-violation.sparql`) and competency questions (`cq*.rq`) |

## Building and testing

```
cd src/ontology
make test           # HermiT consistency + seven SPARQL QC checks + ROBOT report
make test-options   # worked example under both ODP-003 options
make shacl          # shapes report (needs: pip install pyshacl)
make cq             # competency questions
make release VERSION=0.1.0
```

Verified on 0.1.0: consistent and OWL 2 DL; the example is consistent under
both ODP-003 options with identical classifications; the shapes report only
the deliberate defect (a period that ends before it begins); all five
competency questions answer as documented on the pattern page.

## License

[CC BY 4.0](LICENSE). Term ID range ODP005_0001000 to 0001999 (first editor).
