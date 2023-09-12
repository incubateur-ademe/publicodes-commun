<div align="center">
  <h3 align="center">
	<big>Publicodes règles communes</big>
  </h3>
  <p align="center">
   <a href="https://github.com/incubateur-ademe/publicodes-commun/issues">Report Bug</a>
   •
   <a href="https://incubateur-ademe.github.io/publicodes-commun/">API docs</a>
   •
   <a href="https://github.com/incubateur-ademe/publicodes-commun/blob/master/CONTRIBUTING.md">Contribute</a>
  </p>

Règles [publicodes](https://publi.codes) communes aux modèles publicodes de
l'[incubateur de l'ADEME](https://beta.gouv.fr/startups/?incubateur=ademe).

</div>

## Usage 

Ajouter le paquet à vos dépendances : 
```
bun add @incubateur-ademe/publicodes-commun
```

Instancier un nouveau moteur Publicode :
```typescript
import Engine from 'publicodes'
import rules from '@incubateur-ademe/publicodes-commun'

const engine = new Engine(rules)

engine.evaluate('intensité électricité')
```

Utiliser certaines règles dans un autre modèle publicodes :
```yaml
importer!:
  depuis:
    nom: @incubateur-ademe/publicodes-commun 
    url: https://github.com/incubateur-ademe/publicodes-commun
  dans: règles communes
  les règles:
    - intensité électricité
```

### En local

#### Compiler le modèle

> Les règles publicodes du modèle sont disponible dans le workspace
> [`rules/`](https://github.com/incubateur-ademe/publicodes-commun/tree/main/rules).

Pour installer les dépendances et compiler tous les fichiers `.publicodes` en
un seul fichier JSON, il suffit d'exécuter la commande suivante : 

```
bun && bun run build
```

#### Lancer la documentation

> Le code de la documentation est disponible dans le workspace
> [`doc/`](https://github.com/incubateur-ademe/publicodes-commun/tree/main/doc).

Pour lancer l'app React en local permettant de parcourir la documentation du
modèle, il suffit d'exécuter la commande suivante :

```
bun i --cwd doc

bun run doc
```

#### Lancer l'API

> Le code de l'API est disponible dans le workspace
> [`api/`](https://github.com/incubateur-ademe/publicodes-commun/tree/main/api).

Pour lancer le serveur Node permettant d'utiliser l'API REST, il faut utiliser les commandes
suivantes : 

```
bun run api

# En watch-mode
bun run api:watch
```

## Publier une nouvelle version

Afin de publier une nouvelle version il suffit d'exécuter la commande `npm
version`.
