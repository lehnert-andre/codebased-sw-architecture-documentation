# Titel

> Code-basierte Dokumentation evolutionärer Software-Architekturen

## Motivation

Software-Systeme unterliegen durch wechselnde Anforderungen einem stetigem Wandel. Die Software-Entwicklung steht vor der Herausforderung einer evolutionären Software-Architektur.

Das Domain-Driven-Design und der Microservice-Ansatz addressieren diese Herausforderungen. Die Kapselung von Domänen-Funktionalitäten in Bounded Contexts erlauben eine inkrementelle und unabhängige Weiterentwicklung eines Systems.

Microservice-Architekturen erschweren allerdings die Dokumentation und die Erfassung der Beziehungen zwischen den beteiligten Komponenten und Systemen. Microservices abstraiieren Funktionalitäten und kommuniuieren über das Netzwerk per REST und Messaging (verteiltes System).

Auf Ebene der Microservices erlaubt die statische Code-Analyse die Auflösung der internen Abhängigkeiten zwischen Modulen, Packages und Klassen. Eine Zyklenfreiheit kann mit bewähreten Werkzeugen zuverlässig festgestellt und visualisiert werden (JDepend, Sonar, etc.).
Die Beziehungen zwischen Microservices sind allerdings nur indirekt über Schnittstellen-Aufrufe im Code oder anhand des Kommunikationsverhaltens zu Laufzeit sichtbar.

Unter der Prämisse "Dokumentation veraltet" erzeugt eine manuelle Aktualisierung der Microservice-Architektur zu einen unverhältnismäßig großen Aufwand. Die Dokumenation sollte daher zusammen mit dem Code versioniert werden und auf bereits bekannten Informationen basieren.

Diese Arbeit soll Möglichkeiten zur code-basierten Dokumentation von Software-Architekturen eruieren und prototypisch eine Lösung implementieren. Folgende Ansätze sollen beleuchtet werden:

Jeder Microservice stellt die Dokumentation zur inneren Struktur und der genutzten Services einheitlich in einem definierten Format bereit. Eine strukturierte Dokumentation gestattet eine maschinelle Analyse und Darstellung der Informationen.

Über den Build-Prozess sind allgemeine Informationen wie der Name, das
Repository, die Build-Version und die verwendete Bibliotheken (z.B. Maven Dependencies) bekannt.

Mit Hilfe der metadaten-basierten Schnittstellen-Dokumentation, wie Swagger (Open API Specification), liegt zur Kompilierzeit eine strukturierte Dokumenation des Service-Angebots vor.

Die Kommunikationsinfrastruktur, wie die Service Discovery, der Load-Balancer oder die Firewall, kann das Konsumieren der Service-Angebote, also die Kommunikationsbeziehungen zwischen den Microservices auflösen.

Ein Service zum Architektur-Management aggregiert und visualisiert die bereitgestellten Informationen. Wünschenswert ist eine automatische Erzeugung der Software-Architektur auf Ebene der Kontext- und Struktursicht.

Werkzeuge für das Architektur-Management:

- Structure 101
- Gephi
- jQAssistant

#### Tags:

- **`Discovery Service`**
- **`REST`**
- **`API-Design`**
- **`API-Dokumentation`**
- **`Definition`**
- ⭐ lesenswert

### Literatur

- Microservices, Grundlagen flexibler Softwarearchitekturen, Eberhard Wolff, ISBN: 978-3-86490-313-7
- Basiswissen Software-Architekturen, Verstehen, entwerfen, wiederverwenden, Thorsten Posch, Klaus Birken, Michael Gerdom, ISBN: 978-3-89864-736-6
- ...

## tl;dr;

> Within microservices architecture the inverse occurs and system maintainers now pay the price. Learnability improves, code changes are in smaller batches and thus more fluid, yet the system maintainer how has additional moving parts to deal with.<br>
> With containerization, deployment, and discovery now prominent in microservices architecture, a large transition occurs and trade off is made. A service will become less confusing, but holistic system complexity increases. We’re seeing that this complexity is worth paying the cost for.

> Another big challenge is how developers should cope with the growing number of APIs that organizations are releasing. With so many releases there will be new “API products [and] ensuring that they can create synergy with the existing APIs can be extremely difficult”, <br> says Jason Harmon, Head of API Design at PayPal.

> If your API uses calls that don’t run in the same environments, bug hunting becomes a chore. If your documentation is inconsistent with actual functionatliy, you risk confusing and segmenting your userbase.

### Referenzen

2019-02-20:

- JavaDoc Anforderungen https://www.oracle.com/technetwork/articles/javase/index-142372.html

- **`Definition`**

  - https://en.wikipedia.org/wiki/YAML
  - http://json.org/
  - https://en.wikipedia.org/wiki/RAML_(software)
  - https://de.wikipedia.org/wiki/Swagger_(Software)
  - Swagger/ OAS https://github.com/OAI/OpenAPI-Specification
  - ⭐ https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md

- **`API-Dokumentation`**

  - https://apiblueprint.org/
  - https://swagger.io/
  - https://entwickler.de/online/web/openapi-swagger-579827368.html
  - https://swagger.io/tools/open-source/
  - ⭐ https://swagger.io/tools/open-source/open-source-integrations/
    - https://github.com/swagger-api/swagger-ui
    - https://github.com/swagger-api/swagger-core
    - https://github.com/swagger-api/swagger-parser
    - https://github.com/garethjevans/swagger-codegen-maven-plugin
    - https://search.maven.org/artifact/io.swagger.codegen.v3/swagger-codegen-maven-plugin/3.0.5/maven-plugin
    - http://kongchen.github.io/swagger-maven-plugin/
    - https://github.com/RSuter/NSwag
      - https://github.com/RSuter/NSwag/wiki/SwaggerToTypeScriptClientGenerator
  - https://inspector.swagger.io/builder
  - ⭐ https://nordicapis.com/top-specification-formats-for-rest-apis/
  - https://nordicapis.com/spark-api-adoption-good-documentation-practises/
  - https://blog.readme.io/what-is-swagger-and-why-it-matters/
  - https://blog.vsoftconsulting.com/blog/is-raml-or-swagger-better-for-building-apis
  - https://github.com/apigee-127/a127-documentation/wiki
  - ⭐ https://github.com/lord/slate
  - https://github.com/raml-org/raml-spec
    - https://www.baeldung.com/raml-restful-api-modeling-language-tutorial

- ⭐ https://nordicapis.com/api-design-testing-state-art/

- **`Discovery Service`** https://read-the-docs.readthedocs.io/en/latest/webhooks.html

- **`API-Design`**
  - https://nordicapis.com/top-5-development-tips-for-a-killer-api/
  - https://nordicapis.com/rest-better-than-soap-yes-use-cases/
  - https://nordicapis.com/balancing-complexity-and-simplicity-in-api-design/
  - API Evangelist http://kinlane.com/about/
  - Lifecycle
    - https://nordicapis.com/api-lifecycle-analysis-stage-preparing-your-api-strategy-pre-launch/
    - https://nordicapis.com/7-api-design-lessons-world-tour-roundup/
- https://nordicapis.com/envisioning-the-entire-api-lifecycle/
- **`REST`** https://developer.twitter.com/en/docs/basics/response-codes
- ⭐ **`REST`** https://de.wikipedia.org/wiki/HTTP-Statuscode

- ⭐ https://dzone.com/articles/patterns-for-microservices-sync-vs-async
- ⭐ https://dzone.com/articles/centralized-documentation-in-microservice-spring-b

#### API Blueprint Example

https://apiblueprint.org/

```yaml
# GET /message
+ Response 200 (text/plain)
Hello World!
```

```yaml
# Data Structures

## Blog Post (object)
+ id: 42 (number, required)
+ text: Hello World (string)
+ author (Author) - Author of the blog post.

## Author (object)
+ name: Boba Fett
+ email: fett@intergalactic.com

----

# Blog Posts [/posts]

## Retrieve All Posts [GET]
+ Response 200 (application/json)
    + Attributes (array[Blog Post])
```

#### Swagger Example

https://app.swaggerhub.com/apis/Andre_Lehnert_eXX/Demo/1.0.0

https://github.com/OAI/OpenAPI-Specification/tree/master/examples/v3.0

````yaml
openapi: 3.0.0
# Added by API Auto Mocking Plugin
servers:
  - description: SwaggerHub API Auto Mocking
    url: https://virtserver.swaggerhub.com/Andre_Lehnert_eXX/Demo/1.0.0
info:
  description: This is a simple API
  version: "1.0.0"
  title: Simple Inventory API
  contact:
    email: you@your-company.com
  license:
    name: Apache 2.0
    url: "http://www.apache.org/licenses/LICENSE-2.0.html"
tags:
  - name: admins
    description: Secured Admin-only calls
  - name: developers
    description: Operations available to regular developers
paths:
  /inventory:
    get:
      tags:
        - developers
      summary: searches inventory
      operationId: searchInventory
      description: |
        By passing in the appropriate options, you can search for
        available inventory in the system
      parameters:
        - in: query
          name: searchString
          description: pass an optional search string for looking up inventory
          required: false
          schema:
            type: string
        - in: query
          name: skip
          description: number of records to skip for pagination
          schema:
            type: integer
            format: int32
            minimum: 0
        - in: query
          name: limit
          description: maximum number of records to return
          schema:
            type: integer
            format: int32
            minimum: 0
            maximum: 50
      responses:
        "200":
          description: search results matching criteria
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: "#/components/schemas/InventoryItem"
        "400":
          description: bad input parameter
components:
  schemas:
    InventoryItem:
      type: object
      required:
        - id
        - name
        - manufacturer
        - releaseDate
      properties:
        id:
          type: string
          format: uuid
          example: d290f1ee-6c54-4b01-90e6-d701748f0851
        name:
          type: string
          example: Widget Adapter
        releaseDate:
          type: string
          format: date-time
          example: "2016-08-29T09:12:33.001Z"
        manufacturer:
          $ref: "#/components/schemas/Manufacturer"
    Manufacturer:
      required:
        - name
      properties:
        name:
          type: string
          example: ACME Corporation
        homePage:
          type: string
          format: url
          example: "https://www.acme-corp.com"
        phone:
          type: string
          example: 408-867-5309
      type: object```
````
