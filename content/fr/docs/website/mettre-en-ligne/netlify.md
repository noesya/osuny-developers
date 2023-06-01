---
title: Netlify 
---

En connectant Netlify au référentiel Github, tout est pris en charge automatiquement.

[Suivre la documentation officielle](https://docs.netlify.com/welcome/add-new-site/#import-from-an-existing-repository)

Pour déployer le site avec Netlify, penser à ajouter la deploy key. 
TODO comment faire sans deploy key? 

## Gérer la préproduction

Il peut être nécessaire ou utile d'avoir une version de staging du site. Pour préparer cette version il faut set la variable d’environnement **HUGO_ENV** à **staging** (ou le nom de la configuration voulue dans /config de votre site) lors d'un déploiement *branch-deploy* :

Ajouter dans le fichier netlify.toml :

```toml
[context.branch-deploy.environment]
  HUGO_ENV = "staging"
```

Il faut également modifier le fichier de config staging (config/staging/config.yaml) pour mettre l'url netlify de la branche en question :

```yaml
baseURL: https://staging--osuny-www.netlify.app/
```

![Netlify Branch](/static/images/v1_to_v2-netlify-branches.png)

Cette configuration permet de déployer une seule autre branche, mais un setup libre devrait permettre plusieurs version / branches.

Par exemple, dans config/staging/config.yaml :

```yaml
baseURL: /
```
