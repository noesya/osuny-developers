---
title: Modèle de données
weight: 1
description: Structurer la base de données
---

## websites/Site

```
#  id                  :uuid             not null, primary key
#  about_type          :string           indexed => [about_id]
#  access_token        :string
#  git_branch          :string
#  git_endpoint        :string
#  git_provider        :integer          default("github")
#  in_production       :boolean          default(FALSE)
#  name                :string
#  plausible_url       :string
#  repository          :string
#  style               :text
#  style_updated_at    :date
#  theme_version       :string           default("NA")
#  url                 :string
#  created_at          :datetime         not null
#  updated_at          :datetime         not null
#  about_id            :uuid             indexed => [about_type]
#  default_language_id :uuid             not null, indexed
#  university_id       :uuid             not null, indexed
```

## websites/Post

Attributes:
- university:references
- website:references
- title:string
- description:text
- text:text
- published:boolean
- published_at:datetime

## websites/Page

Attributes:
- university:references
- website:references
- title:string
- description:text
- text:text
- parent:references
- published:boolean

## websites/Document

Est-ce vraiment dans ce namespace ? Peut-être un DAM ?

1 document peut concerner :
- toute l'université (charte numérique)
- 1 école (règlement intérieur de l'école)
- 1 campus (règlement intérieur du campus)
- 1 formation (contrat d'alternance type)
- 1 session (calendrier pédagogique de l'année en cours)

Attributes:
- university:references
- name:string
- school:references (optional)
- campus:references (optional)
- program:references (optional)
- session:references (optional)

## websites/Menu

Attributes:
- university:references
- website:references
- title:string
- identifier:string

## websites/menu/Item

Attributes:
- university:references
- website:references
- menu:references
- title:string
- parent:references
- position:integer
- kind:integer (enum: page, url)
- about:references (polymorphic)

## Export du menu

/_data/menus.yml

```yaml
primary:
    - title: Accueil
      target: /
    - title: Formations
      target: /formations
      children:
          - title: DUT
            target: /formations/dut
    - title: ENT
      target: https://ent.u-bordeaux3.fr
legal:
    - title: Mentions légales
      target: /mentions-legales
```
