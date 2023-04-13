---
name: OCR-Ground Truth Dataset
tools: [OCR, LaTeX mining, interactive plots]
image: assets/pngs/digits.png
description: Learn more about the ~95M+ character OCR-ground truth Astronomy literature dataset.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Several plots, more coming soon!


### Digits

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/digits.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.




<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/tree/main/data" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/blob/main/explore_full_script_outputs.ipynb" text="The Analysis" %}
</div>

