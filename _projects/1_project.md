---
layout: page
title: Erosion-SAM
description: Erosion and deposition segmentation
img: assets/img/Erosion-SAM.png
importance: 1
category: work
related_publications: true
---

The **Erosion-SAM** project aims to automatically detect soil erosion and deposition using high-resolution aerial imagery (0.2 m). For this purpose, the study area was defined as the **southeastern region of Bavaria, Germany**.

The project involved acquiring orthophotos following heavy rainfall events in erosion-prone areas **between May and September of 2011 and 2012**. To determine suitable acquisition times, **RADOLAN** rainfall data, with a spatial resolution of **1 × 1 km²**, were analyzed. When rainfall events met specific thresholds—either a total rainfall of at least 10 mm or a maximum 30-minute intensity exceeding 10 mm/h—indicating high erosion potential, aerial surveys were conducted using a small aircraft within 30 days after the identified erosive event.
The images were then georeferenced. We manually identified and masked **405 individual images** from the aerial imagery that exhibited erosion and deposition features such as ephemeral gullies, rills and sediment fans. The fields were categorized into grassland (n = 128) and cropland (n = 277), whereas the latter was then subdivided into vegetated cropland (n = 131) and bare cropland (n = 146).
<!-- 
    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    --- -->

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Erosion-SAM1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A) soil erosion map of Germany in a 75 × 75 m raster and b) examples of manual segmentation of agricultural fields with erosive rainfall, showing erosion and deposition features across different land covers.
</div>

The **<a href="https://segment-anything.com/" target="_blank">Segment Anything Model (SAM)</a>** represents a major breakthrough in image segmentation technology. Although SAM delivers high accuracy with minimal or no training data, its performance can be challenged by complex tasks such as detecting soil erosion and deposition. To overcome these limitations, we applied fine-tuning—a transfer learning approach that adapts a pre-trained model (including its architecture and weights) to a specific task rather than training a new model from scratch. This method improves performance, reduces the need for large labeled datasets, lowers computational demands, and saves time. Pre-training on a broad dataset proves especially beneficial when the task-specific dataset is limited in size or labeling.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Erosion-SAM2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Overview of the Segment Anything Model (SAM) .
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
