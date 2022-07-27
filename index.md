---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: FS-COCO
---

<a href="http://sketchx.ai/"><img src="/assets/sketchx-logo.png" style="width:70%; max-width: 300px; border:None;" class='img-fluid img-thumbnail'></a><br/><br/>


## **FS-COCO: Towards Understanding of Freehand Sketches of Common Objects in Context.**

---

### **Authors**
**[Pinaki Nath Chowdhury](https://pinakinathc.me), [Aneeshan Sain](https://aneeshan95.github.io/), [Ayan Kumar Bhunia](https://ayankumarbhunia.github.io/), [Tao Xiang](https://scholar.google.com/citations?user=MeS5d4gAAAAJ&hl=en), [Yulia Gryaditskaya](https://yulia.gryaditskaya.com/), [Yi-Zhe Song](https://scholar.google.co.uk/citations?user=irZFP_AAAAAJ&hl=en)**

SketchX, Center for Vision Speech and Signal Processing

University of Surrey, United Kingdom

**Published at ECCV 2022**

[Paper](http://www.pinakinathc.me/assets/papers/fscoco.pdf) / [Github](https://github.com/pinakinathc/fscoco)

### **Abstract**
We advance sketch research to scenes with the first dataset of freehand scene sketches, FS-COCO. With practical applications in mind, we collect sketches that convey well scene content but can be sketched within a few minutes by a person with any sketching skills. Our dataset comprises 10,000 freehand scene vector sketches with per point space-time information by 100 non-expert individuals, offering both object- and scene-level abstraction. Each sketch is augmented with its text description. Using our dataset, we study for the first time the problem of fine-grained image retrieval from freehand scene sketches and sketch captions. We draw insights on: (i) Scene salience encoded in sketches using the strokes temporal order; (ii) Performance comparison of image retrieval from a scene sketch and an image caption; (iii) Complementarity of information in sketches and image captions, as well as the potential benefit of combining the two modalities. In addition, we extend a popular vector sketch LSTM-based encoder to handle sketches with larger complexity than was supported by previous work. Namely, we propose a hierarchical sketch decoder, which we leverage at a sketch-specific “pre-text” task. Our dataset enables for the first time research on freehand scene sketch understanding and its practical applications

### **Dataset Statistics**

For our dataset, we compute two estimates of the category distribution across our data: (1) Upper Bound: based on semantic segmentation labels in images and (2) Lower Bound: based on the occurrence of a word in a sketch caption. 

<table>
    <tr>
        <th>Total Sketches</th>
        <th># Categories</th>
        <th colspan="4"># Categories per Sketch</th>
        <th colspan="4"># Sketches per Category</th>
    </tr>
    <tr>
        <td colspan="2"></td>
        <td>Mean</td>
        <td>Std</td>
        <td>Min</td>
        <td>Max</td>
        <td>Mean</td>
        <td>Std</td>
        <td>Min</td>
        <td>Max</td>
    </tr>
    <tr>
        <td>10,000</td>
        <td>92/150</td>
        <td>1.37/7.17</td>
        <td>0.57/3.27</td>
        <td>1/1</td>
        <td>5/25</td>
        <td>99.42/413.18</td>
        <td>172.88/973.59</td>
        <td>1/1</td>
        <td>866/6789</td>
    </tr>
</table>
<style>
table, th, td {
  border: 1px solid black;
  text-align: center;
  padding: 15px;
}
tr:nth-child(odd) {
  background-color: #f2f2f2;
}
</style>

### **Dataset Sample and Comparison with existing dataset.**
![Sample Comparison FSCOCO dataset](/assets/fscoco-sample-comparison.jpg)

## **Code**

### >> Code for Data collection tool
[**https://github.com/pinakinathc/SketchX-SST**](https://github.com/pinakinathc/SketchX-SST)

You will need to install `npm`, `nodejs`, `mongodb`, `pymongo`, `numpy`

Once you have done the setup, you are ready to run the code. I used a Linode server to host this service. It takes £5 for a month.

```
npm install
python init_db.py
sudo node server.js
```

Once you are done collecting data, you can visualise your results at scale using `python visualise_sketch.py`. You will need to install `bresenham` and `cv2` for this. Also modify Line `60, 61` to set the path of **MSCOCO** data directory and **SketchyCOCO** data directory.

### >> Code for running experiments

[**https://github.com/pinakinathc/fscoco**](https://github.com/pinakinathc/scene-sketch-dataset)

I use `PyTorch` and `PyTorch Lightning` for the experiments. If you face some issues with dependencies, please contant me.

I also added some code to run the experiments using HPC (i.e., Condor).

Example for running:
```
git clone https://github.com/pinakinathc/scene-sketch-dataset.git
cd scene-sketch-dataset/src/sbir_baseline
python main.py
```

Before you run `main.py` ensure that the code is set up in training mode and data path are correct in `options.py`.

### **License / Terms of Use**
Downloading this dataset means you agree to the following License / Terms of Use:

<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

### **How to cite this dataset**
```
@inproceedings{fscoco,
    title={FS-COCO: Towards Understanding of Freehand Sketches of Common Objects in Context.}
    author={Chowdhury, Pinaki Nath and Sain, Aneeshan and Bhunia, Ayan Kumar and Xiang, Tao and Gryaditskaya, Yulia and Song, Yi-Zhe},
    booktitle={ECCV},
    year={2022}
}
```

### **Download this dataset**

[**[Official CVSSP Storage]**](http://cvssp.org/data/fscoco/fscoco.tar.gz)
[**[Download from Google Drive]**](https://drive.google.com/file/d/1sjWoONedi9PBK4aQFNJUEL7diFJ7FyIN/view?usp=sharing)

### **Acknowledgements**
This dataset would not be possible without the support of the following wonderful people:

**[Anran Qi](https://anranqi.github.io/), [Yue Zhong](http://sketchx.ai/people), [Lan Yang](http://sketchx.ai/people), [Dongliang Chang](https://scholar.google.com/citations?user=tIf50PgAAAAJ&hl=en), [Ling Luo](https://rowl1ng.com/), [Ayan Das](https://scholar.google.com/citations?user=x-WI_EgAAAAJ&hl=en), [Zhiyu Qu](http://sketchx.ai/people), [Yixiao Zheng](http://sketchx.ai/people), [Ruolin Yang](http://sketchx.ai/people), [Ranit](https://github.com/MaestroRon-001)**


### **Social Media**


<iframe id="reddit-embed" src="https://www.redditmedia.com/r/MachineLearning/comments/tsqm18/r_fscoco_towards_understanding_of_freehand/?ref_source=embed&amp;ref=share&amp;embed=true" sandbox="allow-scripts allow-same-origin allow-popups" style="border: none;" scrolling="no" width="640" height="146"></iframe><br>

<blockquote class="twitter-tweet" data-partner="tweetdeck"><p lang="en" dir="ltr">FS-COCO: Towards Understanding of Freehand Sketches of Common Objects in Context<br><br>Dataset of 10,000 freehand scene vector sketches drawn by 100 non-expert individuals within minutes, offering both object and scene-level abstraction<a href="https://t.co/fzmXrftsqv">https://t.co/fzmXrftsqv</a><a href="https://t.co/C1fTiWINca">https://t.co/C1fTiWINca</a> <a href="https://t.co/aWNh7ua8YK">pic.twitter.com/aWNh7ua8YK</a></p>&mdash; hardmaru (@hardmaru) <a href="https://twitter.com/hardmaru/status/1509370360428662794?ref_src=twsrc%5Etfw">March 31, 2022</a></blockquote>

<blockquote class="twitter-tweet" data-partner="tweetdeck"><p lang="en" dir="ltr">FS-COCO: Towards Understanding of Freehand Sketches of Common Objects in Context. (arXiv:2203.02113v1 [<a href="https://t.co/1uAOVrWCaz">https://t.co/1uAOVrWCaz</a>]) <a href="https://t.co/UO2B1xOzSi">https://t.co/UO2B1xOzSi</a></p>&mdash; Tim Leiner (@MLandDL_papers) <a href="https://twitter.com/MLandDL_papers/status/1500743888679710723?ref_src=twsrc%5Etfw">March 7, 2022</a></blockquote>

<blockquote class="twitter-tweet" data-conversation="none" data-cards="hidden" data-partner="tweetdeck"><p lang="tl" dir="ltr">FS-COCO: Towards Understanding of Freehand Sketches of Common Objects in Context. Pinaki Nath Chowdhury, Aneeshan Sain, Yulia Gryaditskaya, Ayan Kumar Bhunia, Tao Xiang, and Yi-Zhe Song <a href="https://t.co/YvCWuUtK0M">https://t.co/YvCWuUtK0M</a></p>&mdash; cs.CV Papers (@arxiv_cs_cv_pr) <a href="https://twitter.com/arxiv_cs_cv_pr/status/1500689283124187136?ref_src=twsrc%5Etfw">March 7, 2022</a></blockquote>

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
