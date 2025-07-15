# Tuto MkDocs

Documentation complète [mkdocs.org](https://www.mkdocs.org).

Petite vidéo tuto 
<iframe width="560" height="315" src="https://www.youtube.com/embed/xlABhbnNrfI?si=kPEMzQLnTQk9PUO2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

[https://www.youtube.com/watch?v=xlABhbnNrfI&t=0s](https://www.youtube.com/watch?v=xlABhbnNrfI&t=40s)

## Commandes locales pour démarrer et construire le site

On se rend dans le bon dossier ou avec vscodium directement.

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## L'arborescence du projet

    mkdocs.yml    # Le fichier de configuration.
    docs/
        assets/   # Un dossier pour les images
        index.md  # La page d'accueil du site.
        test.md   # Test des extensions md et autre bidouilles (cette page).
        ...       # le reste.

## Ajout d'extensions

Doc pour trouver les extensions à ajouter dans la conf pour avoir des améliorations de MarkDown dans mkdocs material.
En fait j'ai tout ajouté dans le yaml de configuration.

[https://squidfunk.github.io/mkdocs-material/reference](https://squidfunk.github.io/mkdocs-material/reference)

## Les emojis

J'adore boire une petite 🍺 après avoir mangé un :alien:

## Bloc code et tab code

### Bloc code simple avec colorisation syntaxique (ici sql)
```sql
SELECT *
FROM table t1
Where condition like "compliquée";
```

### Bloc code avec des tabulations

=== "Code Md"

    ``` md
      - [x] Est-ce un génie ?
      - [ ] Est-ce un génie génial ?
    ```
=== "Rendu"

    - [x] Est-ce un génie ?
    - [ ] Est-ce un génie génial ?
    - [ ] Zut alors le rendu fonctionne pas là je suis deg


-[x] Est-ce un génie ?
-[ ] Est-ce un génie génial ?
-[ ] Zut alors le rendu fonctionne pas là je suis deg


## Test Admonition

!!! note "On peut mettre un titre ici, mais pas obligé"

    On indente pour y mettre ce qu'on veut dedans, trop classe !

???+ info "J'ai toujours révé de savoir faire ça"

    Doc sur tous les type de admonition [https://squidfunk.github.io/mkdocs-material/reference/admonitions/](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)

## Test Diagramm

Ouah y a même les diagrammes entité relation !
[https://squidfunk.github.io/mkdocs-material/reference/diagrams/](https://squidfunk.github.io/mkdocs-material/reference/diagrams/)
Et avec un soupçon de css par dessus ça doit être terrible.

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```
!!! success

    Ouah y a même les diagrammes entité relation !

``` mermaid
classDiagram
  Person <|-- etudiant
  Person <|-- Formateur
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Adresse "1" <-- "0..1" Person:lives at
  class etudiant{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Formateur{
    +int salary
  }
  class Adresse{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```
