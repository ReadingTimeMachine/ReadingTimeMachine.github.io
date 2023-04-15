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

Note: any `@` symbol is erronious -- this is used for alignment between ground truth and OCR results.

TODO:
 * **NOTE:** its possible that the `^` symbol is in there two for insertions but I haven't double checked yet
 * Fix the `@` to be something else too?
 * Make matching diagonals more obvious
 
 
## Character-Level Matches

### Digits

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/digits.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Alpha characters

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/alphas2.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Punctuation characters

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/punctuation2.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Other characters

Below shows the confusion matrix for OCR and PDF characters.

**Note:** There are some characters that are not rendered correctly on the x/y axis labels due to not being glyphs that are tracked explicitly within the used matplotlib font.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/others2.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

## Word-Level Matches

### Stopwords

Below shows the confusion matrix for OCR and PDF words.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/words_stopwords.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.


### Frequent which are not stopwords

Below shows the confusion matrix for OCR and PDF words.  This subset is the 100 most frequent words which are not pure punctuation, digits, or stopwords.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/words_nmost_nonstopwords.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.


<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/tree/main/data" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/blob/main/explore_full_script_analysis.ipynb" text="The Analysis" %}
</div>

