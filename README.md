[![DOI](https://zenodo.org/badge/132733125.svg)](https://zenodo.org/badge/latestdoi/132733125)

Linked Software Dependencies Components vocabulary for describing modules and components.

## Example

Creating a module with one component, and instantiating it with the `hello:say` parameter.

### HelloSomething module with component

```json
{
  "@context": {
    "@vocab": "https://w3id.org/lsd/vocabularies/object-oriented#",
    "rdf": "http://www.w3.org/1999/02/22-rdf-syntax-ns#",
    "rdfs": "http://www.w3.org/2000/01/rdf-schema#",
    "fn": "https://w3id.org/function/ontology#",
    "ex": "http://example.org/",
    "hello": "http://example.org/hello/"
  },
  "@graph": [
    {
      "@id": "ex:HelloSomethingModule",
      "@type": "Module",
      "hasComponent": {
        "@id": "ex:HelloSomethingModule#SayHelloComponent",
        "@type": "Component",
        "hasParameter": [
          {
            "@id": "hello:say",
            "@type": "Parameter"
          },
          {
            "@id": "hello:hello",
            "@type": "Parameter",
            "fn:required": "false"
          }
        ]
      }
    }
  ]
}
```

### HelloSomething component instantiation

```json
{
  "@context": {
    "@vocab": "http://linkedsoftwaredependencies.org/vocabulary/components#",
    "ex": "http://example.org/",
    "hello": "http://example.org/hello#"
  },
  "@graph": [
    {
      "@id": "ex:config",
      "@type": "ex:HelloSomethingModule#SayHelloComponent",
      "hello:say": "World"
    }
  ]
}
```
