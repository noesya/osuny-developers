---
title: "Configuration SASS"
description: >
  Fichier de configuration SASS
---

# Configuration

```(sass)
// TODO: ranger

// MAIN COLORS
$main-color: black !default // Text color
$main-background-color: white !default // Background color

$body-color: $main-color !default
$body-background-color: $main-background-color !default

$link-color: $main-color !default

// TYPOGRAPHY

// Fonts family
// TODO: choisir typo system par défaut
$body-font-family: "Georgia", serif !default
$heading-font-family: "Helvetica", "Arial", sans-serif !default

// $font-size-base: 1rem
$line-height-base: 1.4

// Fonts sizes
$body-font-size: 16px !default
$small-font-size: 14px !default

$h1-size: px2rem(60) !default
$h2-size: px2rem(40) !default
$h3-size: px2rem(30) !default
$h4-size: px2rem(20) !default
$h5-size: px2rem(18) !default
$h6-size: px2rem(16) !default

// Font weight
$heading-font-weight: normal !default

$h1-weight: $heading-font-weight !default
$h2-weight: $heading-font-weight !default
$h3-weight: $heading-font-weight !default
$h4-weight: $heading-font-weight !default
$h5-weight: $heading-font-weight !default
$h6-weight: $heading-font-weight !default

// Breadcrumb
$breadcrumb-color: invert($main-color) !default

// Spacing
$spacing1: 24px !default
$spacing2: 48px !default
$spacing3: 64px !default
$spacing4: 128px !default
$spacing5: 256px !default

// Grid
$grid-gutter: 60px
$grid-max-width: 1980px

// Z-index
$zindex-nav-accessibility: 1010 !default
$zindex-stretched-link: 2 !default

// Header
$header-color: $main-color !default
$header-hover-color: rgba($header-color, 0.7) !default // TODO : Réflechir à plus élégant / générique
$header-background-color: $main-background-color !default
$header-sticky-enabled: true !default
$header-sticky-transition: 0.3s !default
$header-height: 74px !default
$header-height-md: 74px !default

// Footer
$footer-color: $main-color !default
$footer-background-color: darken($main-background-color, 2.5) !default

// Hero
$hero-height: 375px !default
$hero-height-md: 450px !default
$hero-color: invert($main-color) !default
$hero-background-color: invert($main-background-color) !default

// Icons
$icons: ()
$icons: map-merge($icons, ("arrow": "\e905"))
$icons: map-merge($icons, ("arrow-first": "\e906"))
$icons: map-merge($icons, ("arrow-last": "\e907"))
$icons: map-merge($icons, ("arrow-left": "\e908"))
$icons: map-merge($icons, ("arrow-right": "\e909"))
$icons: map-merge($icons, ("burger": "\e902"))
$icons: map-merge($icons, ("caret": "\e904"))
$icons: map-merge($icons, ("caret-bottom": "\e911"))
$icons: map-merge($icons, ("caret-left": "\e912"))
$icons: map-merge($icons, ("caret-right": "\e913"))
$icons: map-merge($icons, ("caret-top": "\e914"))
$icons: map-merge($icons, ("close": "\e90e"))
$icons: map-merge($icons, ("download": "\e900"))
$icons: map-merge($icons, ("eye": "\e901"))
$icons: map-merge($icons, ("link-blank": "\e903"))
$icons: map-merge($icons, ("play": "\e910"))
$icons: map-merge($icons, ("pause": "\e90f"))
$icons: map-merge($icons, ("social": "\e915"))
$icons: map-merge($icons, ("instagram": "\e90a"))
$icons: map-merge($icons, ("facebook": "\e90b"))
$icons: map-merge($icons, ("linkedin": "\e90c"))
$icons: map-merge($icons, ("twitter": "\e90d"))

// Breakpoints
// TODO: réécrire en sass les mixins bootstrap
$grid-breakpoints: (xs: 0, sm: 576px, md: 768px, lg: 992px, xl: 1200px, xxl: 1400px)
 
// BLOCKS

// Block call to action
$block-call-to-action-background: $main-background-color !default
$block-call-to-action-color: $main-color !default

// Block pages
$block-pages-card-background: lighten($main-background-color, 1) !default
$block-pages-card-page-background: white !default
$block-pages-card-page-color: $main-color !default
$block-pages-card-page-background-hover: lighten($main-background-color, 2) !default
$block-pages-card-page-color-hover: white !default

// Block timeline
$block-timeline-horizontal-background: black !default
$block-timeline-horizontal-color: white !default

// Sections
$post-media-background: darken($main-background-color, 2) !default
$post-media-aspect-ratio: 50%
$post-categories-color: lighten($main-color, 2) !default
$post-time-color: lighten($main-color, 2) !default

// MISC

// Animations
$arrow-ease-transition: cubic-bezier(0, 0.65, 0.4, 1.2) !default
$arrow-ease-transition-2: cubic-bezier(0, 0.65, 0.4, 1) !default
```