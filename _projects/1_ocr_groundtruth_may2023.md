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

First, we look at the confusion matrix for alphabetical characters -- *Click on a row to show the character distribution histogram on the left. (Double click on grid heatmap to un-select)*:
<vegachart schema-url="{{ site.baseurl }}/assets/json/alphas.json" style="width: 100%"></vegachart>


"INSERT" refers to when a character has to be inserted in the OCR text in order to make it align correctly with the ground-truth text -- i.e. the OCR engine has missed a character.

"DELETE" means a character has to be deleted in the ground-truth text in order to align correctly with the OCR text -- i.e. the OCR engine has added an extra character by mistake.

### Digit Characters

Now, let's look at digits:
<vegachart schema-url="{{ site.baseurl }}/assets/json/digits.json" style="width: 100%"></vegachart>

### Punctuation

And now punctuation marks:
<vegachart schema-url="{{ site.baseurl }}/assets/json/punctuation.json" style="width: 100%"></vegachart>
 
  

## Word-Level Matches

Next we look at word-level matchs.  Here we will be making use of a "cleaned" dataset in which the ground-truth words have all been made lowercase and have been cleaned of any leading or trailing punctuation.

### Stopwords

Stop-words are some of the most frequent words in the English language.  Here we show how accurate Tesseract is with these words in our dataset:
<vegachart schema-url="{{ site.baseurl }}/assets/json/stopwords.json" style="width: 100%"></vegachart>
Note for plotting purposes, we exclude any words that occur less than 5 times in our ground-truth word list.


### Frequent which are not stopwords

Below we show the 100 most frequent words in our dataset that are *not* stop-words.
<vegachart schema-url="{{ site.baseurl }}/assets/json/most_freq_nonstop.json" style="width: 100%"></vegachart>
Note for plotting purposes, we exclude any words that occur less than 5 times in our ground-truth word list.

### Frequently misspelled words (not stopwords)

Finally, we can take a look at words that are frequently misspelled (that are not stopwords).  There are a few ways to quantify this.  Here, let's only look at words that appear at least 10,000 times in our dataset (about 300 words).  Then, we sort by how often each word is wrong (in %) and take the 100 "most wrong" of these words.
<vegachart schema-url="{{ site.baseurl }}/assets/json/freqmiss.json" style="width: 100%"></vegachart>
Note for plotting purposes, we exclude any words that occur less than 5 times in our ground-truth word list.



<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/tree/main/data" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/ReadingTimeMachine/ocr_ground_truth/blob/main/explore_full_script_analysis.ipynb" text="The Analysis" %}
</div>

