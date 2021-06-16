# Awesome-Sketch-Synthesis

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A collection of papers about Sketch Synthesis (Generation). Mainly focus on stroke-level vector sketch synthesis.

> Feel free to create a PR or an issue.

![examples](https://magenta.tensorflow.org/assets/sketch_rnn_demo/img/sketch_garden.gif)

**Outlines**

- [1. Datasets](#1-datasets)
- [2. Sketch-Synthesis Approaches](#2-sketch-synthesis-approaches)
  - [1) Semantic Concept-to-sketch](#1-semantic-concept-to-sketch)
  - [2) Photo-to-sketch](#2-photo-to-sketch)
  - [3) Text/Attribute-to-sketch](#3-textattribute-to-sketch)
  - [4) 3D shape-to-sketch](#4-3d-shape-to-sketch)
  - [5) Sketch(vector)-to-sketch(vector)](#5-sketchvector-to-sketchvector)
  - [6) Art-to-sketch](#6-art-to-sketch)
- [3. Vector Graphics Generation](#3-vector-graphics-generation)

---

## 1. Datasets
Here `Vector strokes` means having *svg* data. `With photos` means having the photo-sketch paired data.

<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Dataset</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Vector strokes</strong></td>
    <td><strong>With photos</strong></td>
    <td><strong>Notes</strong></td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Characters</strong></td>
    <td> <a href="https://github.com/brendenlake/omniglot/">Omniglot</a> </td> 
    <td> </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Alphabets characters </td>
  </tr>
  <tr>
    <td> <a href="http://kanjivg.tagaini.net/">KanjiVG</a> </td> 
    <td> </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Chinese characters </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/rois-codh/kmnist">Kuzushiji</a> </td> 
    <td> </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Japanese characters </td>
  </tr>
  <tr>
    <td rowspan="8"><strong>Instance-level</strong></td>
    <td> <a href="http://cybertron.cg.tu-berlin.de/eitz/projects/classifysketch/">TU-Berlin</a> </td> 
    <td> SIGGRAPH 2012 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Multi-category hand sketches </td>
  </tr>
  <tr>
    <td> <a href="http://sketchy.eye.gatech.edu/">Sketchy</a> </td> 
    <td> SIGGRAPH 2016 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Multi-category photo-sketch paired </td>
  </tr>
  <tr>
    <td> <a href="https://quickdraw.withgoogle.com/data">QuickDraw</a> </td> 
    <td> ICLR 2018 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Multi-category hand sketches </td>
  </tr>
  <tr>
    <td> <a href="http://www.eecs.qmul.ac.uk/~qian/Project_cvpr16.html">QMUL-Shoe-Chair-V2</a> </td> 
    <td> CVPR 2016 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Only two categories </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/KeLi-SketchX/SketchX-PRIS-Dataset">Sketch Perceptual Grouping (SPG)</a> </td> 
    <td> ECCV 2018 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With part-level semantic segmentation information </td>
  </tr>
  <tr>
    <td> <a href="https://facex.idvxlab.com/">FaceX</a> </td> 
    <td> AAAI 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Labeled facial sketches </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/facebookresearch/DoodlerGAN">Creative Sketch</a> </td> 
    <td> ICLR 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With annotated part segmentation </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/HaohanWang/ImageNet-Sketch">ImageNet-Sketch</a> </td> 
    <td> NeurIPS 2019 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> 50 images for each of the 1000 ImageNet classes </td>  
  </tr>
  <tr>
    <td rowspan="4"><strong>Scene-level</strong></td>
    <td> <a href="https://sketchyscene.github.io/SketchyScene/">SketchyScene</a> </td> 
    <td> ECCV 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> With semantic/instance segmentation information </td>  
  </tr>
  <tr>
    <td> <a href="http://projects.csail.mit.edu/cmplaces/">CMPlaces</a> </td> 
    <td> TPAMI 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Cross-modal scene dataset </td>  
  </tr>
  <tr>
    <td> <a href="http://sweb.cityu.edu.hk/hongbofu/doc/context_based_sketch_classification_Expressive2018.pdf">Context-Skecth</a> </td> 
    <td> Expressive 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Context-based scene sketches for co-classification </td>  
  </tr>
  <tr>
    <td> <a href="https://sysu-imsl.github.io/EdgeGAN/index.html">SketchyCOCO</a> </td> 
    <td> CVPR 2020 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Scene sketch, segmentation and normal images </td>  
  </tr>
  <tr>
    <td rowspan="2"><strong>Drawing from photos</strong></td>
    <td> <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">Photo-Sketching</a> </td> 
    <td> WACV 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> ScenePhoto-sketch paired </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/zachzeyuwang/tracing-vs-freehand">Tracing-vs-Freehand</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Tracings and freehand drawings of images </td>  
  </tr>
  <tr>
    <td rowspan="2"><strong>Rough sketch</strong></td>
    <td> <a href="https://esslab.jp/~ess/en/data/davincidataset/">Da Vinci</a> </td> 
    <td> CGI 2018 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Line drawing restoration dataset </td>
  </tr>
  <tr>
    <td> <a href="https://cragl.cs.gmu.edu/sketchbench/">Rough Sketch Benchmark</a> </td> 
    <td> SIGGRAPH Asia 2020 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Rough and clean sketch pairs (only for evaluation) </td>  
  </tr>
  <tr>
    <td rowspan="3"><strong>CAD</strong></td>
    <td> <a href="https://ns.inria.fr/d3/OpenSketch/">OpenSketch</a> </td> 
    <td> SIGGRAPH Asia 2019 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Product Design Sketches </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/PrincetonLIPS/SketchGraphs">SketchGraphs</a> </td> 
    <td> ICML 2020 Workshop </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Sketches extracted from real-world CAD models </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/AutodeskAILab/Fusion360GalleryDataset">Fusion 360 Gallery</a> </td> 
    <td> SIGGRAPH 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> For 'sketch and extrude' designs </td>  
  </tr>
  
</table>



## 2. Sketch-Synthesis Approaches

### 1) Semantic Concept-to-sketch


<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="8"><strong>Instance-level</strong></td>
    <td> <a href="https://openreview.net/pdf?id=Hy6GHpkCW">A Neural Representation of Sketch Drawings (sketch-rnn)</a> </td> 
    <td> ICLR 2018 </td> 
    <td> 
      <a href="https://github.com/tensorflow/magenta/tree/master/magenta/models/sketch_rnn">[Code]</a> 
      <a href="https://magenta.tensorflow.org/sketch-rnn-demo">[Project]</a> 
      <a href="https://magenta.tensorflow.org/assets/sketch_rnn_demo/index.html">[Demo]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/pdf/1709.04121.pdf">Sketch-pix2seq: a Model to Generate Sketches of Multiple Categories</a> </td> 
    <td>  </td> 
    <td> 
      <a href="https://github.com/MarkMoHR/sketch-pix2seq">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://idvxlab.com/papers/2019AAAI_Sketcher_Cao.pdf">AI-Sketcher : A Deep Generative Model for Producing High-Quality Sketches</a> </td> 
    <td> AAAI 2019 </td> 
    <td> <a href="https://facex.idvxlab.com/">[Project]</a> </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/pdf/1901.03427.pdf">Stroke-based sketched symbol reconstruction and segmentation (stroke-rnn)</a> </td> 
    <td> </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2007.02190">BézierSketch: A generative model for scalable vector sketches</a> </td> 
    <td> ECCV 2020 </td> 
    <td>  </td>
  </tr>
  <tr>
    <td> <a href="http://sketchx.ai/pixelor">Pixelor: A Competitive Sketching AI Agent. So you think you can beat me?</a> </td> 
    <td> SIGGRAPH Asia 2020 </td> 
    <td> 
      <a href="http://sketchx.ai/pixelor">[Project]</a> 
      <a href="https://github.com/dasayan05/neuralsort-siggraph">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2011.10039">Creative Sketch Generation</a> </td> 
    <td> ICLR 2021 </td> 
    <td> 
      <a href="http://doodlergan.cloudcv.org/">[Project]</a> 
      <a href="https://github.com/facebookresearch/DoodlerGAN">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2105.02769">Computer-Aided Design as Language</a> </td> 
    <td> arxiv 2105 </td> 
    <td> 
    </td>
  </tr>
  
</table>

---

### 2) Photo-to-sketch

- vector image generation

<table>
  <tr>
    <td><strong>Data type</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Facial</strong></td>
    <td> <a href="https://dl.acm.org/citation.cfm?id=2461964">Style and abstraction in portrait sketching</a> </td> 
    <td> TOG 2013 </td> 
    <td>
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2005.05526">Making Robots Draw A Vivid Portrait In Two Minutes</a> </td> 
    <td> IROS 2020 </td> 
    <td> 
      <a href="https://github.com/Ricelll/AiSketcher">[Code]</a> 
      <a href="https://ricelll.github.io/AiSketcher/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/1912.05099">RoboCoDraw: Robotic Avatar Drawing with GAN-based Style Transfer and Time-efficient Path Optimization</a> </td> 
    <td> AAAI 2020 </td> 
    <td> 
      <a href="https://github.com/Psyche-mia/Avatar-GAN">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Instance-level</strong></td>
    <td> <a href="https://link.springer.com/content/pdf/10.1007%2Fs11263-016-0963-9.pdf">Free-Hand Sketch Synthesis with Deformable Stroke Models</a> </td> 
    <td> IJCV 2017 </td> 
    <td>
      <a href="https://panly099.github.io/skSyn.html">[Project]</a> 
      <a href="https://github.com/panly099/sketchSynthesis">[code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_cvpr_2018/papers/Song_Learning_to_Sketch_CVPR_2018_paper.pdf">Learning to Sketch with Shortcut Cycle Consistency</a> </td> 
    <td> CVPR 2018 </td> 
    <td> <a href="https://github.com/seindlut/deep_p2s">[Code1]</a> <a href="https://github.com/MarkMoHR/sketch-photo2seq">[Code2]</a> </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_cvpr_2018/papers/Muhammad_Learning_Deep_Sketch_CVPR_2018_paper.pdf">Learning Deep Sketch Abstraction</a> </td> 
    <td> CVPR 2018 </td> 
    <td>  </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Technical Drawings</strong></td>
    <td> <a href="https://arxiv.org/abs/2003.05471">Deep Vectorization of Technical Drawings</a> </td> 
    <td> ECCV 2020 </td> 
    <td>
      <a href="http://adase.group/3ddl/projects/vectorization/">[Project]</a> 
      <a href="https://github.com/Vahe1994/Deep-Vectorization-of-Technical-Drawings">[code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/abs/2012.09004">Sketch Generation with Drawing Process Guided by Vector Flow and Grayscale</a> </td> 
    <td> AAAI 2021 </td> 
    <td>
      <a href="https://github.com/TZYSJTU/Sketch-Generation-with-Drawing-Process-Guided-by-Vector-Flow-and-Grayscale">[Code]</a> 
    </td>
  </tr>
</table>


- pixelwise image generation

<table>
  <tr>
    <td><strong>Level</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Facial</strong></td>
    <td> <a href="http://openaccess.thecvf.com/content_CVPR_2019/papers/Yi_APDrawingGAN_Generating_Artistic_Portrait_Drawings_From_Face_Photos_With_Hierarchical_CVPR_2019_paper.pdf">APDrawingGAN: Generating Artistic Portrait Drawings from Face Photos with Hierarchical GANs</a> </td> 
    <td> CVPR 2019 </td> 
    <td> 
      <a href="https://github.com/yiranran/APDrawingGAN">[Code]</a> 
      <a href="https://face.lol/">[Demo]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Instance-level</strong></td>
    <td> <a href="http://openaccess.thecvf.com/content_ECCV_2018/papers/Kaiyue_Pang_Deep_Factorised_Inverse-Sketching_ECCV_2018_paper.pdf">Deep Factorised Inverse-Sketching</a> </td> 
    <td> ECCV 2018 </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="https://www.spiedigitallibrary.org/journals/Journal-of-Electronic-Imaging/volume-27/issue-6/063006/Making-better-use-of-edges-for-sketch-generation/10.1117/1.JEI.27.6.063006.short?SSO=1">Making better use of edges for sketch generation</a> </td> 
    <td> JEI 2018 </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_WACV_2020/papers/Kampelmuhler_Synthesizing_human-like_sketches_from_natural_images_using_a_conditional_convolutional_WACV_2020_paper.pdf">Synthesizing human-like sketches from natural images using a conditional convolutional decoder</a> </td> 
    <td> WACV 2020 </td> 
    <td> 
      <a href="https://github.com/kampelmuehler/synthesizing_human_like_sketches">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/pdf/1901.00542.pdf">Photo-Sketching: Inferring Contour Drawings from Images</a> </td> 
    <td> WACV 2019 </td> 
    <td>
      <a href="https://github.com/mtli/PhotoSketch">[Code]</a> 
      <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">[Project]</a> 
    </td>
  </tr>
</table>

---

### 3) Text/Attribute-to-sketch

| Level | Paper | Source | Code/Project Link |
| --- | --- | --- | --- |
| **Scene-level** | [Scones: Towards Conversational Authoring of Sketches](http://people.eecs.berkeley.edu/~eschoop/docs/scones.pdf) | IUI 2020 |  |
| **Scene-level** | [Sketchforme: Composing Sketched Scenes from Text Descriptions for Interactive Applications](https://arxiv.org/pdf/1904.04399.pdf) | UIST 2019 |  |
| **Facial** | [Text2Sketch: Learning Face Sketch from Facial Attribute Text](https://ieeexplore.ieee.org/abstract/document/8451236) | ICIP 2018 |  |

---

### 4) 3D shape-to-sketch

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [DeepShapeSketch : Generating hand drawing sketches from 3D objects](https://shizhezhou.github.io/projects/DeepFreeHandSke2019/deepFreehandSke2019.pdf) | IJCNN 2019 |  |
| [Neural Contours: Learning to Draw Lines from 3D Shapes](https://people.cs.umass.edu/~dliu/papers/NeuralContours.pdf) | CVPR 2020 | [[project]](https://people.cs.umass.edu/~dliu/projects/NeuralContours/) [[code]](https://github.com/DifanLiu/NeuralContours) |
| [Cloud2Curve: Generation and Vectorization of Parametric Sketches](https://arxiv.org/abs/2103.15536) | CVPR 2021 | [[project]](https://ayandas.me/pubs/2021/03/01/pub-9.html) |

---


### 5) Sketch(vector)-to-sketch(vector)


This means translating a disordered vector sketch into an ordered sequential sketch imitating human's drawing order. The appearance of the sequential sketch is exactly the **same** as the pixelwise one.


| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Animated Construction of Line Drawings](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/animatedConstructionOfLineDrawings_SiggA11.pdf) | SIGGRAPH ASIA 2011 | [[Project]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/) [[code]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer_src.zip) [[Demo]](http://sweb.cityu.edu.hk/hongbofu/projects/animatedConstructionOfLineDrawings_SiggA11/Viewer.zip) |

---

### 6) Art-to-sketch

Here we list sketch synthesis based on other image types, like Manga, line art, rough sketch, etc.

- Hand drawn line art / rough sketch (a.k.a. Vectorization / Sketch Simplification)

a) Datasets and benchmark

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [A Benchmark for Rough Sketch Cleanup](https://hal.archives-ouvertes.fr/hal-02939477/document) | SIGGRAPH Asia 2020 | [[Project]](https://cragl.cs.gmu.edu/sketchbench/)  [[Code]](https://github.com/Nauhcnay/A-Benchmark-for-Rough-Sketch-Cleanup) |

b) Optimization-based approaches

| Paper | Source | Input Type | Output Type | Code/Project Link |
| --- | --- | --- | --- | --- |
| [Closure-aware Sketch Simplification](http://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.pdf) | SIGGRAPH Asia 2015 | vector | vector | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.html) |
| [StrokeAggregator: Consolidating Raw Sketches into Artist-Intended Curve Drawings](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/StrokeAggregator_authorversion.pdf) | SIGGRAPH 2018 | vector | vector | [[Project]](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/) |
| [StrokeStrip: Joint Parameterization and Fitting of Stroke Clusters](https://www.davepagurek.com/programming/strokestrip/) | SIGGRAPH 2021 | vector | vector | [[Project]](https://www.davepagurek.com/programming/strokestrip/) [[code]](https://github.com/davepagurek/StrokeStrip) |
| --- | --- | --- | --- | --- |
| [Topology-Driven Vectorization of Clean Line Drawings](https://cgl.ethz.ch/Downloads/Publications/Papers/2013/Nor13/Nor13.pdf) | TOG 2013 | raster | vector |  |
| [Fidelity vs. Simplicity: a Global Approach to Line Drawing Vectorization](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/fidelity_simplicity.pdf) | SIGGRAPH 2016 | raster | vector | [[Project]](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/) |
| [A Delaunay triangulation based approach for cleaning rough sketches](https://ed.iitm.ac.in/~raman/agcl/sketchSMI.pdf) | C&G 2018 | raster | vector | [[Code]](https://github.com/amaldevp/RoughSketchSimplification) |
| [Inertia-based Fast Vectorization of Line Drawings](https://www.researchgate.net/profile/Rafal_Scherer/publication/336936860_Inertia-based_Fast_Vectorization_of_Line_Drawings/links/5dbbc8ad299bf1a47b0721d1/Inertia-based-Fast-Vectorization-of-Line-Drawings.pdf) | PG 2019 | raster | vector |  |
| [Vectorization of Line Drawings via Polyvector Fields](https://dl.acm.org/doi/10.1145/3202661) | TOG 2019 | raster | vector | [[Code]](https://github.com/bmpix/PolyVectorization) |
| [Integer-Grid Sketch Simplification and Vectorization](http://www-sop.inria.fr/reves/Basilic/2020/SBBB20/paper.pdf) | SGP 2020 | raster | vector | [[Project]](https://repo-sam.inria.fr/d3/grid-vectorization/) [[Code]](https://gitlab.inria.fr/D3/grid-vectorization/) |

c) Learning-based approaches

| Paper | Source | Input Type | Output Type | Code/Project Link |
| --- | --- | --- | --- | --- |
| [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/publications/SimoSerraSIGGRAPH2016.pdf) | SIGGRAPH 2016 | raster | raster | [[Code]](https://github.com/bobbens/sketch_simplification) [[Project]](https://esslab.jp/~ess/en/research/sketch/) |
| [Mastering Sketching: Adversarial Augmentation for Structured Prediction](https://esslab.jp/~ess/publications/SimoSerraTOG2018.pdf) | SIGGRAPH 2018 | raster | raster | [[Code]](https://github.com/bobbens/sketch_simplification)  [[Project]](https://esslab.jp/~ess/en/research/sketch_master/) |
| [Real-Time Data-Driven Interactive Rough Sketch Inking](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2018.pdf) | SIGGRAPH 2018 | raster | raster | [[Code]](https://github.com/bobbens/line_thinning) [[Project]](https://esslab.jp/~ess/en/research/inking/) |
| [Perceptual-aware Sketch Simplification Based on Integrated VGG Layers](https://ieeexplore.ieee.org/abstract/document/8771128/) | TVCG 2019 | raster | raster |  |
| --- | --- | --- | --- | --- |
| [Semantic Segmentation for Line Drawing Vectorization Using Neural Networks](http://www.byungsoo.me/project/vectornet/paper.pdf) | EG 2018 | raster | vector | [[project]](http://www.byungsoo.me/project/vectornet) [[code]](https://github.com/byungsook/vectornet) |
| [Deep Line Drawing Vectorization via Line Subdivision and Topology Reconstruction](https://www.researchgate.net/profile/Chu_Han8/publication/337249870_Deep_Line_Drawing_Vectorization_via_Line_Subdivision_and_Topology_Reconstruction/links/5f0fec43299bf1e548ba370f/Deep-Line-Drawing-Vectorization-via-Line-Subdivision-and-Topology-Reconstruction.pdf) | PG 2019 | raster | vector |  |
| [Deep Vectorization of Technical Drawings](https://arxiv.org/abs/2003.05471) | ECCV 2020 | raster | vector | [[project]](http://adase.group/3ddl/projects/vectorization/) [[code]](https://github.com/Vahe1994/Deep-Vectorization-of-Technical-Drawings) |
| [General Virtual Sketching Framework for Vector Line Art](https://esslab.jp/publications/HaoranSIGRAPH2021.pdf) | SIGGRAPH 2021 | raster | vector | [[project]](https://markmohr.github.io/virtual_sketching/) [[code]](https://github.com/MarkMoHR/virtual_sketching) |


- Manga (Comics)

| Paper | Source | Input Type | Output Type | Code/Project Link |
| --- | --- | --- | --- | --- |
| [Deep extraction of manga structural lines](https://dl.acm.org/citation.cfm?id=3073675) | SIGGRAPH 2017 | raster | raster | [[Code]](https://github.com/ljsabc/MangaLineExtraction) |
| [Manga Filling Style Conversion with Screentone Variational Autoencoder](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) | SIGGRAPH Asia 2020 | raster | raster | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) [[Code]](https://github.com/msxie92/ScreenStyle) |
| [Generating Manga from Illustrations via Mimicking Manga Workflow](https://openaccess.thecvf.com/content/CVPR2021/papers/Zhang_Generating_Manga_From_Illustrations_via_Mimicking_Manga_Creation_Workflow_CVPR_2021_paper.pdf) | CVPR 2021 | raster | raster | [[Project]](https://lllyasviel.github.io/MangaFilter/) [[Code]](https://github.com/lllyasviel/MangaFilter) |



## 3. Vector Graphics Generation

Here we focus on learning-based vector graphics generation **without** depending on vector training data, and traditional vectorization algorithms.


- Learning with external black-box (non-differentiable) rendering simulator

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Synthesizing Programs for Images using Reinforced Adversarial Learning](http://proceedings.mlr.press/v80/ganin18a/ganin18a.pdf) | ICML 2018 | [[Code]](https://github.com/deepmind/spiral) |
| [Unsupervised Doodling and Painting with Improved SPIRAL](https://arxiv.org/abs/1910.01007) | arxiv 1910 | [[Project]](https://learning-to-paint.github.io/) |

- Learning with built-in differentiable rendering module

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Rethinking Style Transfer: From Pixels to Parameterized Brushstrokes](https://arxiv.org/abs/2103.17185) | CVPR 2021 | [[code]](https://github.com/CompVis/brushstroke-parameterized-style-transfer) |
| [Im2Vec: Synthesizing Vector Graphics without Vector Supervision](https://arxiv.org/abs/2102.02798) | CVPR 2021 | [[Project]](http://geometry.cs.ucl.ac.uk/projects/2021/im2vec/) [[code]](https://github.com/preddy5/Im2Vec) |
| [Stylized Neural Painting](https://arxiv.org/abs/2011.08114) | CVPR 2021 | [[Code]](https://github.com/jiupinjia/stylized-neural-painting) [[project]](https://jiupinjia.github.io/neuralpainter/) |
| [Learning to Paint With Model-based Deep Reinforcement Learning](http://openaccess.thecvf.com/content_ICCV_2019/papers/Huang_Learning_to_Paint_With_Model-Based_Deep_Reinforcement_Learning_ICCV_2019_paper.pdf) | ICCV 2019 | [[code]](https://github.com/megvii-research/ICCV2019-LearningToPaint) |
| [Strokenet: A neural painting environment](https://openreview.net/forum?id=HJxwDiActX) | ICLR 2019 | [[Code]](https://github.com/vexilligera/strokenet) |
| [Neural Painters: A learned differentiable constraint for generating brushstroke paintings](https://arxiv.org/abs/1904.08410) | arxiv 1904 | [[Code]](https://github.com/reiinakano/neural-painters-pytorch) |
| [Learning to Sketch with Deep Q Networks and Demonstrated Strokes](https://arxiv.org/abs/1810.05977) | arxiv 1810 |  |
| [Unsupervised Image to Sequence Translation with Canvas-Drawer Networks](https://arxiv.org/abs/1809.08340) | arxiv 1809 |  |


- Vectorization

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Depixelizing pixel art](https://dl.acm.org/doi/abs/10.1145/1964921.1964994) | SIGGRAPH 2011 |  |
| [Perception-Driven Semi-Structured Boundary Vectorization](http://www.cs.ubc.ca/labs/imager/tr/2018/PerceptionDrivenVectorization/perception-driven-vectorization.pdf) | SIGGRAPH 2018 | [[Webpage]](http://www.cs.ubc.ca/labs/imager/tr/2018/PerceptionDrivenVectorization/) |
| [PolyFit: Perception-aligned Vectorization of Raster Clip-art via Intermediate Polygonal Fitting](http://www.cs.ubc.ca/labs/imager/tr/2020/ClipArtVectorization/paper.pdf) | SIGGRAPH 2020 | [[Webpage]](http://www.cs.ubc.ca/labs/imager/tr/2020/ClipArtVectorization/) [[Code]](https://github.com/dedoardo/polyfit) |
| [ClipGen: A Deep Generative Model for Clipart Vectorization and Synthesis](https://ieeexplore.ieee.org/abstract/document/9444657) | TVCG 2021 |  |

