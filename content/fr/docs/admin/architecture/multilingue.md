---
title: Multilingue
weight: 3
description: >
  Parti-pris sur la gestion des langues
---

D'une façon générale, les langues se gèrent en 2 phases :
- l'internationalisation (i18n) qui vise à rendre possible les langues multiples
- la localisation (l10n) qui vise à intégrer une langue spécifique

Dans Osuny, le système a 2 facettes :
- l'admin en Ruby on Rails, qui permet d'écrire les contenus
- le site en Hugo, qui permet de lire les contenus

Il faut donc partir du multilingue [tel qu'il fonctionne dans les sites Hugo](https://gohugo.io/content-management/multilingual/) pour générer des fichiers corrects depuis Osuny.

## Hugo

### La configuration

Nous utilisons un fichier languages.yml
```
ar:
  languagedirection: rtl
  title: مدونتي
  contentDir: content/ar
en:
  title: My blog
  contentDir: content/en
fr:
  title: Mon blogue
  contentDir: content/fr
pt-pt:
  title: O meu blog
  contentDir: content/pt-pt
```

Il faut aussi dans le fichier `config.yaml` indiquer
```
defaultContentLanguage: fr
languageCode: fr
```

Comme on spécifie toutes les urls on n'a a priori pas besoin d'indiquer
```
defaultContentLanguageInSubdir: true
```

### Les contenus

Il y a 2 façons de gérer les contenus multilingues dans Hugo :
- toutes les langues d'un contenu dans le même répertoire
- un répertoire par langue contenant tous les contenus

Nous utilisons le second système.  
On range les contenus dans un dossier `/content/fr/`.  
Chaque fichier a son url inclue. Il faut penser à préfixer toutes les urls par la langue (`/fr/actualites/2022-01-01-mon-article`)

### Les menus

Nous n'utilisons pas les menus natifs de Hugo mais un système parallèle.  
On range les menus pour chaque langue dans un dossier `/data/menus/fr/``

### Les clés de traduction

Dans le thème on a un dossier `i18n` dans lequel on pose un fichier par langue.  
Ces fichiers (ou juste certains termes) peuvent éventuellement être overwrite dans un thème précis.  

### Questions / réponses sur le monolingue

Doit-on forcer le choix d'au moins une langue pour un site web ?  
Conceptuellement un site a toujours une langue donc ça semble bien  

Si on choisit une seule langue, doit-on écrire quand même les contenus (et les menus) dans /fr/ ?  
Ca ne semble pas poser de problème  

En cas de monolingue quel pattern d'url utiliser ?  
Si une seule langue il vaut mieux que les urls ne soient pas préfixées par la langue.
En cas d'activation d'une seconde langue a posteriori le jeu d'alias des permalinks permettra de tout transférer sur /fr/  
Si on est monolingue il faut désactiver dans la config `defaultContentLanguageInSubdir: true`

## Ruby on Rails

### Le paramétrage du site

On force le choix d'au moins une langue.

### La traduction

### L'export statique

En cas de monolingue les `url` des fichiers statiques ne doivent PAS être préfixées de la langue.  
En cas de multilingue toutes les urls sont préfixées.  
On créé les contenus dans `content/:lang/`.
On crée les menus dans `data/menus/:lang/`.  