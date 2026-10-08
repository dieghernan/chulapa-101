---
layout: default
title: Metadata and video examples
subtitle: 'Page options in <span class="chulapa">Chulapa</span> 2.1.0'
permalink: /theme-options
seo_title: Chulapa metadata and video examples
og_title: Explore Chulapa page options
description: Examples of article metadata, social images and a video with complete descriptive metadata.
locale: en-GB
og_locale: en_GB
og_type: article
og_image: https://img.youtube.com/vi/1hXYuWTWVww/hqdefault.jpg
og_image_alt: Thumbnail of the Menorca travel video
og_image_width: 480
og_image_height: 360
og_image_type: image/jpeg
schema_image: https://img.youtube.com/vi/1hXYuWTWVww/hqdefault.jpg
include_on_search: true
# Set canonical_url only when this page should point to another canonical URL.
# List og_locale_alternate only when translated versions of this page exist.
---

The visible heading, browser title and social title can be configured
independently.
This page also declares its language and article type. The video thumbnail
represents
its content in social previews and article structured data.

## Video metadata

This example uses the video metadata provided in the <span class="chulapa">Chulapa</span> documentation.
Replace all metadata together when embedding your own video. Upload dates use
ISO 8601 and durations use ISO 8601 durations, such as `PT2M52S`.

{% include snippets/video.html id="1hXYuWTWVww" provider="youtube"
   name="Menorca - Isla Bonita"
   thumbnail_url="https://img.youtube.com/vi/1hXYuWTWVww/hqdefault.jpg"
   upload_date="2019-07-27T12:44:00-07:00"
   description="Exploring Menorca with a Mavic Pro drone in 2019."
   duration="PT2M52S" %}

[Read the page and snippet reference](https://dieghernan.github.io/chulapa/docs/04-layouts).
