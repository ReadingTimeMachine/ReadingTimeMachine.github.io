---
name: OCR-Ground Truth Dataset
tools: [OCR, LaTeX mining, interactive plots]
image: assets/pngs/digits_save.png
description: Learn more about the ~200M+ character OCR-ground truth Astronomy literature dataset.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Visualizing the 200M Astonomy Ground-Truth/OCR Dataset

When "reading" scanned text with [Optical Character Recognition (OCR)](https://en.wikipedia.org/wiki/Optical_character_recognition) we are often left with messy results with wrong punctuation and a lot of misspellings. This can be an especially bit issue when trying to digitize historical scientific literature as there are many specialized words and characters.

This project aims at addressing this by creating a large "synthetic" dataset that we can use to train machine learning models.  We do this by "mining" the [arXiv](https://arxiv.org/) [Bulk Downloads](https://info.arxiv.org/help/bulk_data/index.html) and finding the location of each word in each scientific document.  We can then run the same documents through an OCR Engine, in this 
case [Tesseract](https://github.com/tesseract-ocr/tesseract) and see what the computer thinks each OCR word should be:

![ocr and pdf words are aligned]({{site.baseurl}}/assets/pngs/diagram_website.png)

This work focuses on the Astronomy & Astrophysics literature (journals like MNRAS, ApJ & AJ) in the years 1991-2011 which is a subset of the full arXiv holdings in that time period:
<vegachart schema-url="{{ site.baseurl }}/assets/json/timechart.json" style="width: 100%"></vegachart>


Below we show the "confusion matricies" for several combinations of character and word pairs.  To explore the dataset, click on a row to see the distribution of correct vs. incorrect characters and word combinations.

## Character Level Plots

### Alphabetical Characters

First, we look at the confusion matrix for alphabetical characters:
<vegachart schema-url="{{ site.baseurl }}/assets/json/alphas.json" style="width: 100%"></vegachart>
Click on a row to show the character distribution histogram on the left. (Double click on grid heatmap to un-select).

"INSERT" refers to when a character has to be inserted in the OCR text in order to make it align correctly with the ground-truth text -- i.e. the OCR engine has missed a character.

"DELETE" means a character has to be deleted in the ground-truth text in order to align correctly with the OCR text -- i.e. the OCR engine has added an extra character by mistake.

### Digit Characters

Now, let's look at digits:
<vegachart schema-url="{{ site.baseurl }}/assets/json/digits.json" style="width: 100%"></vegachart>


 
 
# Other stuff Below here!
 
## Character-Level Matches

### Digits

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/digits3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Alpha characters

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/alphas3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Punctuation characters

Below shows the confusion matrix for OCR and PDF characters.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/punctuation3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Other characters

Below shows the confusion matrix for OCR and PDF characters.

**Note:** There are some characters that are not rendered correctly on the x/y axis labels due to not being glyphs that are tracked explicitly within the used matplotlib font.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/others3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

## Word-Level Matches

### Stopwords

Below shows the confusion matrix for OCR and PDF words.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/words_stopwords3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.


### Frequent which are not stopwords

Below shows the confusion matrix for OCR and PDF words.  This subset is the 100 most frequent words which are not pure punctuation, digits, or stopwords.

Hover over boxes to show percentages, select multiple with SHIFT+click to see full percentage, colors are in log-scale:
<vegachart schema-url="{{ site.baseurl }}/assets/json/words_nmost_nonstopwords3.json" style="width: 100%"></vegachart>
Note: OCR/PDF pairs with <0.1% of the distribution are not shown.  Percentages are over all OCR possibilities for each PDf character.

### Frequently misspelled words (not stopwords)

<vegachart schema-url="{{ site.baseurl }}/assets/json/most_misspelled3.json" style="width: 100%"></vegachart>



<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/tree/main/data" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/blob/main/explore_full_script_analysis.ipynb" text="The Analysis" %}
</div>

