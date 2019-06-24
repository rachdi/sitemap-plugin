# Upgrade 1.1 to 2.0

## TL-DR

* Sitemaps are now generated via the command line, see below.
* Plugin structure upgraded to PluginSkeleton:^1.3 

## New features

* Generation of sitemaps is done via the CLI, schedule them in a cronjob:
    * Sitemap Index: `bin/console sylius:sitemap:generate-index`
* Sitemap URLs now support adding images. The default providers do this where possible. It can be disabled using the `images` configuration key.

## Class changes

* Several classes have been marked `final`.

## Interface changes

* Interface `SitemapUrlInterface` has new methods:
    * `getImages(): Collection`
    * `setImages(Collection $images): void`
    * `addImage(SitemapImageUrlInterface $image): void`
    * `hasImage(SitemapImageUrlInterface $image): bool`
    * `removeImage(SitemapImageUrlInterface $image): void`
    * `public function hasImages(): bool`
