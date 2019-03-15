# Awesome-Sketch-Synthesis

A collection of papers about Sketch Synthesis (Generation). Mainly focus on stroke-level vector sketch synthesis.

![examples](https://github.com/MarkMoHR/Awesome-Sketch-Synthesis/blob/master/examples.png)

**Outlines**

- [1. Datasets](#datasets)
  - [Instance-level](#instance-level)
  - [Scene-level](#scene-level)
- [2. Sketch-Synthesis Approaches](#sketch-synthesis-approaches)
  - [1) category-to-sketch](#1-category-to-sketch)
  - [2) photo-to-sketch](#2-photo-to-sketch)
  - [3) art-to-sketch](#3-art-to-sketch)


---

## 1. Datasets
Here we mainly focus on sketch datasets with `svg` data.

### Instance-level

| Dataset | Source | Notes |
| --- | --- | --- |
| [KanjiVG](http://kanjivg.tagaini.net/) |  | Chinese characters |
| [TU-Berlin](http://cybertron.cg.tu-berlin.de/eitz/projects/classifysketch/) | SIGGRAPH 2012 | Multi-category hand sketches |
| [Sketchy](http://sketchy.eye.gatech.edu/) | SIGGRAPH 2016 | Multi-category photo-sketch paired |
| [QuickDraw](https://quickdraw.withgoogle.com/data) |  | Multi-category hand sketches |
| [QMUL-Shoe-Chair-V2](http://www.eecs.qmul.ac.uk/~qian/Project_cvpr16.html) |  | Only two categories; fine-grained paired |
| [FaceX](https://facex.idvxlab.com/) | AAAI 2019 | Labeled facial sketches |

### Scene-level

| Dataset | Source | Notes |
| --- | --- | --- |
| [Photo-Sketching](http://www.cs.cmu.edu/~mengtial/proj/sketch/) | WACV 2019 | ScenePhoto-sketch paired |


## 2. Sketch-Synthesis Approaches

### 1) Category-to-sketch

- Instance-level

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [A Neural Representation of Sketch Drawings (sketch-rnn)](https://openreview.net/pdf?id=Hy6GHpkCW) | ICLR 2018 | [magenta/sketch_rnn](https://github.com/tensorflow/magenta/tree/master/magenta/models/sketch_rnn) |
| [Sketch-pix2seq: a Model to Generate Sketches of Multiple Categories](https://arxiv.org/pdf/1709.04121.pdf) |  |  |
| [AI-Sketcher : A Deep Generative Model for Producing High-Quality Sketches](https://idvxlab.com/papers/2019AAAI_Sketcher_Cao.pdf) | AAAI 2019 | [facex](https://facex.idvxlab.com/) |
| [Stroke-based sketched symbol reconstruction and segmentation (stroke-rnn)](https://arxiv.org/pdf/1901.03427.pdf) |  | |



### 2) Photo-to-sketch

#### vector image generation

- Instance-level

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Learning to Sketch with Shortcut Cycle Consistency](http://openaccess.thecvf.com/content_cvpr_2018/papers/Song_Learning_to_Sketch_CVPR_2018_paper.pdf) | CVPR 2018 | [seindlut/deep_p2s](https://github.com/seindlut/deep_p2s) |
| [Learning Deep Sketch Abstraction](http://openaccess.thecvf.com/content_cvpr_2018/papers/Muhammad_Learning_Deep_Sketch_CVPR_2018_paper.pdf) | CVPR 2018 |  |


#### pixelwise image generation

- Instance-level

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Deep Factorised Inverse-Sketching](http://openaccess.thecvf.com/content_ECCV_2018/papers/Kaiyue_Pang_Deep_Factorised_Inverse-Sketching_ECCV_2018_paper.pdf) | ECCV 2018 |  |

- Scene-level

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Photo-Sketching: Inferring Contour Drawings from Images](https://arxiv.org/pdf/1901.00542.pdf) | WACV 2019 | [mtli/PhotoSketch](https://github.com/mtli/PhotoSketch) |


### 3) Art-to-sketch

Here we list sketch synthesis based on other image types, like Manga and line art.

- Hand drawn line art


| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/publications/SimoSerraSIGGRAPH2016.pdf) | SIGGRAPH 2016 | [Sketch Simplification](https://esslab.jp/~ess/en/research/sketch.html) |
| [Mastering Sketching: Adversarial Augmentation for Structured Prediction](https://esslab.jp/~ess/publications/SimoSerraTOG2018.pdf) | SIGGRAPH 2018 | [Mastering Sketching](https://esslab.jp/~ess/en/research/sketch_master.html) |
| [Real-Time Data-Driven Interactive Rough Sketch Inking](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2018.pdf) | SIGGRAPH 2018 | [Smart Inker](https://esslab.jp/~ess/en/research/inking.html) |
| [StrokeAggregator: Consolidating Raw Sketches into Artist-Intended Curve Drawings](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/StrokeAggregator_authorversion.pdf) | SIGGRAPH 2018 | [StrokeAggregator](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/) |

- Manga (Comics)

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Deep extraction of manga structural lines](https://dl.acm.org/citation.cfm?id=3073675) | SIGGRAPH 2017 | [ljsabc/MangaLineExtraction](https://github.com/ljsabc/MangaLineExtraction) |
