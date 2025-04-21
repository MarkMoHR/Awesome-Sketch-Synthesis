# Awesome-Sketch-Synthesis

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A collection of papers about Sketch Synthesis (Generation). Mainly focus on stroke-level vector sketch synthesis.

> Feel free to create a PR or an issue.

![examples](https://magenta.tensorflow.org/assets/sketch_rnn_demo/img/sketch_garden.gif)

**Outlines**

- [0. Survey](#0-survey)
- [1. Datasets](#1-datasets)
- [2. Sketch-Synthesis Approaches](#2-sketch-synthesis-approaches)
  - [1) Semantic Concept-to-sketch](#1-semantic-concept-to-sketch)
  - [2) Photo-to-sketch](#2-photo-to-sketch)
  - [3) Text/Attribute-to-sketch](#3-textattribute-to-sketch)
  - [4) 3D shape-to-sketch](#4-3d-shape-to-sketch)
  - [5) Art-to-sketch](#5-art-to-sketch)
- [3. Vector Graphics Generation (2D)](#3-vector-graphics-generation-2d)
- [4. Vector Graphics Generation (3D)](#4-vector-graphics-generation-3d)

---

## 0. Survey

| Paper | Source | Code/Project Link  |
| --- | --- | --- |
| [Deep Learning for Free-Hand Sketch: A Survey](https://ieeexplore.ieee.org/abstract/document/9706366) | TPAMI 2022 | [[code]](https://github.com/PengBoXiangShang/torchsketch) |

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
    <td rowspan="1"><strong>Icon</strong></td>
    <td> <a href="https://github.com/marcdemers/FIGR-8-SVG">FIGR-8-SVG</a> </td> 
    <td> </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Icons with text descriptions </td>
  </tr>
  <tr>
    <td rowspan="1"><strong>Systematic Symbol</strong></td>
    <td> <a href="https://github.com/GuangmingZhu/SketchIME">SketchIME</a> </td> 
    <td> ACM MM 2023</td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> Systematic sketches with semantic annotations </td>
  </tr>
  <tr>
    <td rowspan="9"><strong>Instance-level</strong></td>
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
    <td> <a href="https://drive.google.com/file/d/15s2BR-QwLgX_DObQBrYlUlZqUU90EL9G/view">QMUL-Shoe-Chair-V2</a> </td> 
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
    <td> <a href="https://seva-benchmark.github.io/">SEVA</a> </td> 
    <td> NeurIPS 2023 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> 90K human-generated sketches that vary in detail </td>  
  </tr>
  <tr>
    <td rowspan="6"><strong>Scene-level</strong></td>
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
    <td> <a href="http://www.pinakinathc.me/fscoco/">FS-COCO</a> </td> 
    <td> ECCV 2022 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Scene sketches with text description </td>  
  </tr>
  <tr>
    <td> <a href="https://link.springer.com/article/10.1007/s00371-022-02731-8">SFSD</a> </td> 
    <td> VC 2022 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Completely hand-drawn scene sketches with label annotation </td>  
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
    <td rowspan="1"><strong>Drawing from 3D models</strong></td>
    <td> <a href="https://chufengxiao.github.io/DifferSketching/">DifferSketching</a> </td> 
    <td> SIGGRAPH Asia 2022 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> 3D model-sketch paired, with novice and professional ones </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Portrait</strong></td>
    <td> <a href="https://mmlab.ie.cuhk.edu.hk/datasets.html">CUFS</a> </td> 
    <td> TPAMI 2009 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Face-sketch pairs </td>  
  </tr>
  <tr>
    <td> <a href="https://github.com/yiranran/APDrawingGAN">APDrawing</a> </td> 
    <td> CVPR 2019 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Portrait-sketch paired </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/kwanyun/SKSF-A">SKSF-A</a> </td> 
    <td> EG 2024 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Face-sketch pairs of seven styles </td>  
  </tr>
  <tr>
    <td rowspan="1"><strong>Children's Drawing</strong></td>
    <td> <a href="https://github.com/facebookresearch/AnimatedDrawings">Amateur Drawings</a> </td> 
    <td> TOG 2023 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> With character bounding boxes, segmentation masks, and joint location annotations </td>
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
    <td rowspan="5"><strong>CAD</strong></td>
    <td> <a href="https://gfx.cs.princeton.edu/proj/ld3d/">ld3d</a> </td> 
    <td> SIGGRAPH 2008 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Line Drawings of 3D Shapes </td>
  </tr>
  <tr>
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
  <tr>
    <td> <a href="https://floorplancad.github.io/">FloorPlanCAD</a> </td> 
    <td> ICCV 2021 </td> 
    <td> :heavy_check_mark: </td> 
    <td> :x: </td> 
    <td> With instance and semantic annotations </td>  
  </tr>
  <tr>
    <td rowspan="11"><strong>Anime</strong></td>
    <td> <a href="https://gwern.net/danbooru2021">Danbooru2021</a> </td> 
    <td> / </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Anime images annotated with tags </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/lllyasviel/DanbooRegion">DanbooRegion</a> </td> 
    <td> ECCV 2020 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Anime images with region annotations </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/zsl2018/StyleAnime">Danbooru-Parsing</a> </td> 
    <td> TOG 2023 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> For anime portrait parsing and anime translation </td>
  </tr>
  <tr>
    <td> <a href="https://www.cs.toronto.edu/creativeflow/">CreativeFlow+</a> </td> 
    <td> CVPR 2019 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Large densely annotated artistic video dataset </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/lisiyao21/AnimeInterp">ATD-12K</a> </td> 
    <td> CVPR 2021 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Animation frames with flow annotations </td>
  </tr>
  <tr>
    <td> <a href="https://lisiyao21.github.io/projects/AnimeRun">AnimeRun</a> </td> 
    <td> NeurIPS 2022 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Correspondence dataset for 2D-styled cartoons </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/kangyeolk/AnimeCeleb">AnimeCeleb</a> </td> 
    <td> ECCV 2022 </td> 
    <td> :x: </td> 
    <td> :x: </td> 
    <td> Animation head images with pose annotations </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/ykdai/BasicPBC/tree/main/dataset">PaintBucket-Character</a> </td> 
    <td> CVPR 2024 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Animation frames with region annotations </td>
  </tr>
  <tr>
    <td> <a href="https://zhenglinpan.github.io/sakuga_dataset_webpage/">Sakuga-42M</a> <a href="https://github.com/KytraScript/SakugaDataset">(link 2)</a> </td> 
    <td> arxiv 24.05 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Cartoon videos with text descriptions and tags </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/zhenglinpan/AnitaDataset">Anita</a> </td> 
    <td> online 2024 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Professional hand-drawn cartoon keyframes, with 1080P sketch and color images </td>
  </tr>
  <tr>
    <td> <a href="https://huggingface.co/datasets/MS92/MangaSegmentation">MangaSeg</a> </td> 
    <td> CVPR 2025 </td> 
    <td> :x: </td> 
    <td> :heavy_check_mark: </td> 
    <td> Manga segmentation annotation </td>
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
    <td rowspan="13"><strong>Instance-level</strong></td>
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
    <td> <a href="https://ieeexplore.ieee.org/abstract/document/8854308">Stroke-based sketched symbol reconstruction and segmentation (stroke-rnn)</a> </td> 
    <td> CGA 2019 </td> 
    <td> </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2007.02190">BézierSketch: A generative model for scalable vector sketches</a> </td> 
    <td> ECCV 2020 </td> 
    <td> 
      <a href="https://github.com/dasayan05/stroke-ae">[Code]</a>  
    </td>
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
  <tr>
    <td> <a href="https://arxiv.org/abs/2112.03258">DoodleFormer: Creative Sketch Drawing with Transformers</a> </td> 
    <td> ECCV 2022 </td> 
    <td> 
      <a href="https://ankanbhunia.github.io/doodleformer/">[Project]</a> 
      <a href="https://github.com/ankanbhunia/doodleformer">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://openreview.net/forum?id=4eJ43EN2g6l">SketchKnitter: Vectorized Sketch Generation with Diffusion Models</a> </td> 
    <td> ICLR 2023 </td> 
    <td> 
      <a href="https://github.com/XDUWQ/SketchKnitter">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/abstract/document/10144693">Self-Organizing a Latent Hierarchy of Sketch Patterns for Controllable Sketch Synthesis</a> </td> 
    <td> TNNLS 2023 </td> 
    <td> 
      <a href="https://github.com/CMACH508/RPCL-pix2seqH">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://openreview.net/forum?id=5xadJmgwix">Scale-Adaptive Diffusion Model for Complex Sketch Synthesis</a> </td> 
    <td> ICLR 2024 </td> 
    <td> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2503.23752">StrokeFusion: Vector Sketch Generation via Joint Stroke-UDF Encoding and Latent Sequence Diffusion</a> </td> 
    <td> arxiv 25.03 </td> 
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
    <td rowspan="1"><strong>Facial</strong></td>
    <td> <a href="https://dl.acm.org/citation.cfm?id=2461964">Style and abstraction in portrait sketching</a> </td> 
    <td> TOG 2013 </td> 
    <td>
    </td>
  </tr>
  <tr>
    <td rowspan="5"><strong>Instance-level</strong></td>
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
    <td> <a href="https://arxiv.org/abs/2202.05822">CLIPasso: Semantically-Aware Object Sketching</a> </td> 
    <td> SIGGRAPH 2022 </td> 
    <td> 
      <a href="https://clipasso.github.io/clipasso/">[Project]</a> 
      <a href="https://github.com/yael-vinker/CLIPasso">[Code]</a>
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2502.08642">SwiftSketch: A Diffusion Model for Image-to-Vector Sketch Generation</a> </td> 
    <td> arxiv 25.02 </td> 
    <td> 
      <a href="https://swiftsketch.github.io/">[Project]</a> 
      <a href="https://github.com/swiftsketch/SwiftSketch">[Code]</a>
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/abs/2012.09004">Sketch Generation with Drawing Process Guided by Vector Flow and Grayscale</a> </td> 
    <td> AAAI 2021 </td> 
    <td>
      <a href="https://github.com/TZYSJTU/Sketch-Generation-with-Drawing-Process-Guided-by-Vector-Flow-and-Grayscale">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2211.17256">CLIPascene: Scene Sketching with Different Types and Levels of Abstraction</a> </td> 
    <td> ICCV 2023 </td> 
    <td> 
      <a href="https://clipascene.github.io/CLIPascene/">[Project]</a> 
      <a href="https://github.com/yael-vinker/SceneSketch">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://openreview.net/forum?id=fLbdDspNW3">Learning Realistic Sketching: A Dual-agent Reinforcement Learning Approach</a> </td> 
    <td> ACM MM 2024 </td> 
    <td> 
    </td>
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
</table>


- raster image generation

<table>
  <tr>
    <td><strong>Type</strong></td>
    <td><strong>Paper</strong></td>
    <td><strong>Source</strong></td>
    <td><strong>Code/Project Link</strong></td>
  </tr>
  <tr>
    <td rowspan="7"><strong>Facial</strong></td>
    <td> <a href="https://github.com/vijishmadhavan/ArtLine">ArtLine</a> </td> 
    <td> Online demo </td> 
    <td> 
      <a href="https://github.com/vijishmadhavan/ArtLine">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="http://openaccess.thecvf.com/content_CVPR_2019/papers/Yi_APDrawingGAN_Generating_Artistic_Portrait_Drawings_From_Face_Photos_With_Hierarchical_CVPR_2019_paper.pdf">APDrawingGAN: Generating Artistic Portrait Drawings from Face Photos with Hierarchical GANs</a> </td> 
    <td> CVPR 2019 </td> 
    <td> 
      <a href="https://github.com/yiranran/APDrawingGAN">[Code]</a> 
      <a href="https://face.lol/">[Demo]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://openaccess.thecvf.com/content_CVPR_2020/papers/Yi_Unpaired_Portrait_Drawing_Generation_via_Asymmetric_Cycle_Mapping_CVPR_2020_paper.pdf">Unpaired Portrait Drawing Generation via Asymmetric Cycle Mapping</a> </td> 
    <td> CVPR 2020 </td> 
    <td> 
      <a href="https://github.com/yiranran/Unpaired-Portrait-Drawing">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/document/9069416">Line Drawings for Face Portraits From Photos Using Global and Local Structure Based GANs</a> </td> 
    <td> TPAMI 2020 </td> 
    <td> 
      <a href="https://github.com/yiranran/APDrawingGAN2">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/abstract/document/9699090">Quality Metric Guided Portrait Line Drawing Generation from Unpaired Training Data</a> </td> 
    <td> TPAMI 2022 </td> 
    <td> 
      <a href="https://github.com/yiranran/QMUPD">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2309.00216">Human-Inspired Facial Sketch Synthesis with Dynamic Adaptation</a> </td> 
    <td> ICCV 2023 </td> 
    <td> 
      <a href="https://github.com/AiArt-HDU/HIDA">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://arxiv.org/abs/2403.11263">Stylized Face Sketch Extraction via Generative Prior with Limited Data</a> </td> 
    <td> EG 2024 </td> 
    <td> 
      <a href="https://github.com/kwanyun/StyleSketch/">[Code]</a> 
      <a href="https://kwanyun.github.io/stylesketch_project/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="2"><strong>Instance-level</strong></td>
    <td> <a href="http://openaccess.thecvf.com/content_ECCV_2018/papers/Kaiyue_Pang_Deep_Factorised_Inverse-Sketching_ECCV_2018_paper.pdf">Deep Factorised Inverse-Sketching</a> </td> 
    <td> ECCV 2018 </td> 
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
    <td rowspan="4"><strong>Anime</strong></td>
    <td> <a href="https://github.com/lllyasviel/sketchKeras">sketchKeras</a> </td> 
    <td> online demo </td> 
    <td> 
      <a href="https://github.com/lllyasviel/sketchKeras">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/hepesu/LineDistiller">LineDistiller</a> </td> 
    <td> online demo </td> 
    <td>
      <a href="https://github.com/hepesu/LineDistiller">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://github.com/Mukosame/Anime2Sketch">Anime2Sketch</a> </td> 
    <td> online demo </td> 
    <td>
      <a href="https://github.com/Mukosame/Anime2Sketch">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://dl.acm.org/doi/10.1145/3550454.3555504">Reference Based Sketch Extraction via Attention Mechanism</a> </td> 
    <td> SIGGRAPH Asia 2022 </td> 
    <td>
      <a href="https://github.com/ref2sketch/ref2sketch">[Code]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="2"><strong>Scene-level</strong></td>
    <td> <a href="https://arxiv.org/pdf/1901.00542.pdf">Photo-Sketching: Inferring Contour Drawings from Images</a> </td> 
    <td> WACV 2019 </td> 
    <td>
      <a href="https://github.com/mtli/PhotoSketch">[Code]</a> 
      <a href="http://www.cs.cmu.edu/~mengtial/proj/sketch/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://carolineec.github.io/informative_drawings/">Learning to generate line drawings that convey geometry and semantics</a> </td> 
    <td> CVPR 2022 </td> 
    <td> 
      <a href="https://github.com/carolineec/informative-drawings">[Code]</a> 
      <a href="https://carolineec.github.io/informative_drawings/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Arbitrary</strong></td>
    <td> <a href="https://dl.acm.org/doi/abs/10.1145/3592392">Semi-supervised reference-based sketch extraction using a contrastive learning</a> </td> 
    <td> SIGGRAPH 2023 </td> 
    <td>
      <a href="https://github.com/Chanuku/semi_ref2sketch_code">[Code]</a> 
      <a href="https://chanuku.github.io/Semi_ref2sketch/">[Project]</a> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ieeexplore.ieee.org/abstract/document/10758215">MixSA: Training-free Reference-based Sketch Extraction via Mixture-of-Self-Attention</a> </td> 
    <td> TVCG 2024 </td> 
    <td> 
    </td>
  </tr>
  <tr>
    <td> <a href="https://ojs.aaai.org/index.php/AAAI/article/view/33000">One-Shot Reference-based Structure-Aware Image to Sketch Synthesis</a> </td> 
    <td> AAAI 2025 </td> 
    <td> 
      <a href="https://github.com/Ref2Sketch-SA">[Code]</a> 
    </td>
  </tr>
</table>

---

### 3) Text/Attribute-to-sketch


- raster image generation

| Type | Paper | Source | Code/Project Link |
| --- | --- | --- | --- |
| **Facial** | [Text2Sketch: Learning Face Sketch from Facial Attribute Text](https://ieeexplore.ieee.org/abstract/document/8451236) | ICIP 2018 |  |
| **Scene-level** | [Sketchforme: Composing Sketched Scenes from Text Descriptions for Interactive Applications](https://arxiv.org/pdf/1904.04399.pdf) | UIST 2019 |  |
| **Scene-level** | [Scones: Towards Conversational Authoring of Sketches](http://people.eecs.berkeley.edu/~eschoop/docs/scones.pdf) | IUI 2020 |  |

- vector image generation

| Type | Paper | Source | Code/Project Link |
| --- | --- | --- | --- |
| **Arbitrary** | [Modern Evolution Strategies for Creativity: Fitting Concrete Images and Abstract Concepts](https://arxiv.org/abs/2109.08857) | arxiv 21.09 | [[code]](https://github.com/google/brain-tokyo-workshop) [[project]](https://es-clip.github.io/) |
| **Arbitrary** | [CLIPDraw: Exploring Text-to-Drawing Synthesis through Language-Image Encoders](https://arxiv.org/abs/2106.14843) | NeurIPS 2022 | [[code]](https://colab.research.google.com/github/kvfrans/clipdraw/blob/main/clipdraw.ipynb) |
| **Arbitrary** | [StyleCLIPDraw: Coupling Content and Style in Text-to-Drawing Translation](https://arxiv.org/abs/2202.12362) | IJCAI 2022 | [[code]](https://github.com/pschaldenbrand/StyleCLIPDraw) |
| **SVG** | [VectorFusion: Text-to-SVG by Abstracting Pixel-Based Diffusion Models](https://arxiv.org/abs/2211.11319) | CVPR 2023 |  [[project]](https://ajayj.com/vectorfusion) |
| **Arbitrary** | [SketchDreamer: Interactive Text-Augmented Creative Sketch Ideation](https://arxiv.org/abs/2308.14191) | BMVC 2023 |  [[code]](https://github.com/WinKawaks/SketchDreamer) |
| **Arbitrary** | [DiffSketcher: Text Guided Vector Sketch Synthesis through Latent Diffusion Models](https://arxiv.org/abs/2306.14685) | NeurIPS 2023 |  [[project]](https://ximinng.github.io/DiffSketcher-project/) [[code]](https://github.com/ximinng/DiffSketcher) |
| **Icon** | [IconShop: Text-Based Vector Icon Synthesis with Autoregressive Transformers](https://arxiv.org/abs/2304.14400) | SIGGRAPH Asia 2023 |  [[project]](https://icon-shop.github.io/) |
| **SVG** | [Text-Guided Vector Graphics Customization](https://arxiv.org/abs/2309.12302) | SIGGRAPH Asia 2023 |  [[project]](https://intchous.github.io/SVGCustomization/)  |
| **Arbitrary** | [Text-based Vector Sketch Editing with Image Editing Diffusion Prior](https://www.sysu-imsl.com/files/ICME2024/ICME2024_sketch_editing_final.pdf) | ICME 2024 |  [[code]](https://github.com/MarkMoHR/DiffSketchEdit)  |
| **SVG** | [SVGDreamer: Text Guided SVG Generation with Diffusion Model](https://arxiv.org/abs/2312.16476) | CVPR 2024 |  [[project]](https://ximinng.github.io/SVGDreamer-project/) [[code]](https://github.com/ximinng/SVGDreamer) |
| **SVG** | [SVGDreamer++: Advancing Editability and Diversity in Text-Guided SVG Generation](https://arxiv.org/abs/2411.17832) | arxiv 24.11 |  [[code]](https://github.com/ximinng/SVGDreamer) |
| **SVG** | [NIVeL: Neural Implicit Vector Layers for Text-to-Vector Generation](https://arxiv.org/abs/2405.15217) | CVPR 2024 |  [[project]](https://vikastmz.github.io/NIVeL/)  |
| **SVG** | [Text-to-Vector Generation with Neural Path Representation](https://arxiv.org/abs/2405.10317) | SIGGRAPH 2024 |  [[project]](https://intchous.github.io/T2V-NPR/)  |
| **Arbitrary** | [SVGCraft: Beyond Single Object Text-to-SVG Synthesis with Comprehensive Canvas Layout](https://arxiv.org/abs/2404.00412v1) | arxiv 24.04 | [[code]](https://github.com/ayanban011/SVGCraft) |
| **SVG** | [VectorPainter: A Novel Approach to Stylized Vector Graphics Synthesis with Vectorized Strokes](https://arxiv.org/abs/2405.02962) | arxiv 24.05 |  |
| **SVG** | [Chat2SVG: Vector Graphics Generation with Large Language Models and Image Diffusion Models](https://arxiv.org/abs/2411.16602) | CVPR 2025 | [[webpage]](https://chat2svg.github.io/) |
| **Arbitrary** | [SketchAgent: Language-Driven Sequential Sketch Generation](https://arxiv.org/abs/2411.17673) | CVPR 2025 | [[code]](https://github.com/yael-vinker/SketchAgent) [[webpage]](https://yael-vinker.github.io/sketch-agent/) |
| **SVG** | [SVGBuilder: Component-Based Colored SVG Generation with Text-Guided Autoregressive Transformers](https://arxiv.org/abs/2412.10488) | AAAI 2025 | [[webpage]](https://svgbuilder.github.io/) |
| **SVG** | [SVGFusion: Scalable Text-to-SVG Generation via Vector Space Diffusion](https://arxiv.org/abs/2412.10437) | arxiv 24.12 | [[webpage]](https://ximinng.github.io/SVGFusionProject/) [[code]](https://github.com/ximinng/SVGFusion) |
| **SVG** | [Empowering LLMs to Understand and Generate Complex Vector Graphics](https://arxiv.org/abs/2412.11102) | CVPR 2025 | [[webpage]](https://ximinng.github.io/LLM4SVGProject/) [[code]](https://github.com/ximinng/LLM4SVG) |
| **SVG** | [StarVector: Generating Scalable Vector Graphics Code from Images and Text](https://arxiv.org/abs/2312.11556) | CVPR 2025 | [[webpage]](https://starvector.github.io/) [[code]](https://github.com/joanrod/star-vector) |
| **SVG** | [NeuralSVG: An Implicit Representation for Text-to-Vector Generation](https://arxiv.org/abs/2501.03992) | arxiv 25.01 | [[webpage]](https://sagipolaczek.github.io/NeuralSVG/) [[code]](https://github.com/SagiPolaczek/NeuralSVG) |
| **SVG** | [LayerTracer: Cognitive-Aligned Layered SVG Synthesis via Diffusion Transformer](https://arxiv.org/abs/2502.01105) | arxiv 25.02 | [[code]](https://github.com/showlab/LayerTracer) |

---

### 4) 3D shape-to-sketch

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [DeepShapeSketch : Generating hand drawing sketches from 3D objects](https://shizhezhou.github.io/projects/DeepFreeHandSke2019/deepFreehandSke2019.pdf) | IJCNN 2019 |  |
| [Neural Contours: Learning to Draw Lines from 3D Shapes](https://people.cs.umass.edu/~dliu/papers/NeuralContours.pdf) | CVPR 2020 | [[project]](https://people.cs.umass.edu/~dliu/projects/NeuralContours/) [[code]](https://github.com/DifanLiu/NeuralContours) |
| [Cloud2Curve: Generation and Vectorization of Parametric Sketches](https://arxiv.org/abs/2103.15536) | CVPR 2021 | [[project]](https://ayandas.me/pubs/2021/03/01/pub-9.html) |
| [Neural Strokes: Stylized Line Drawing of 3D Shapes](https://openaccess.thecvf.com/content/ICCV2021/papers/Liu_Neural_Strokes_Stylized_Line_Drawing_of_3D_Shapes_ICCV_2021_paper.pdf) | ICCV 2021 | [[code]](https://github.com/DifanLiu/NeuralStrokes) |
| [Learning a Style Space for Interactive Line Drawing Synthesis from Animated 3D Models](https://graphics.cs.yale.edu/sites/default/files/linedrawinganimation_pg2022.pdf) | PG 2022 |  |
| [CAD2Sketch: Generating Concept Sketches from CAD Sequences](https://repo-sam.inria.fr/d3/cad2sketch/cad2sketch_paper.pdf) | SIGGRAPH Asia 2022 | [[project]](https://ns.inria.fr/d3/cad2sketch/) |

---

### 5) Art-to-sketch

Here we list sketch synthesis based on other image types, like Manga, line art, rough sketch, etc.

a) Line art

- Vector-to-Vector

| Paper | Source | Code/Project Link | Deep learning? |
| --- | --- | --- | --- |
| [Closure-aware Sketch Simplification](http://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.pdf) | SIGGRAPH Asia 2015 | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/sketch/sketch.html) | No |
| [StrokeAggregator: Consolidating Raw Sketches into Artist-Intended Curve Drawings](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/StrokeAggregator_authorversion.pdf) | SIGGRAPH 2018 | [[Project]](https://www.cs.ubc.ca/labs/imager/tr/2018/StrokeAggregator/) | No |
| [StrokeStrip: Joint Parameterization and Fitting of Stroke Clusters](https://www.davepagurek.com/programming/strokestrip/) | SIGGRAPH 2021 | [[Project]](https://www.davepagurek.com/programming/strokestrip/) [[code]](https://github.com/davepagurek/StrokeStrip) | No |
| [StripMaker: Perception-driven Learned Vector Sketch Consolidation](https://dl.acm.org/doi/abs/10.1145/3592130) | SIGGRAPH 2023 |  | No |
| [Region-Aware Simplification and Stylization of 3D Line Drawings](https://onlinelibrary.wiley.com/doi/10.1111/cgf.15042) | EG 2024 |  | No |

- Raster-to-Vector (a.k.a. Vectorization)

| Paper | Source | Code/Project Link | Deep learning? |
| --- | --- | --- | --- |
| [Topology-Driven Vectorization of Clean Line Drawings](https://cgl.ethz.ch/Downloads/Publications/Papers/2013/Nor13/Nor13.pdf) | TOG 2013 | | No |
| [Fidelity vs. Simplicity: a Global Approach to Line Drawing Vectorization](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/fidelity_simplicity.pdf) | SIGGRAPH 2016 | [[Project]](https://www-sop.inria.fr/reves/Basilic/2016/FLB16/) | No |
| [A Delaunay triangulation based approach for cleaning rough sketches](https://ed.iitm.ac.in/~raman/agcl/sketchSMI.pdf) | C&G 2018 | [[Code]](https://github.com/amaldevp/RoughSketchSimplification) | No |
| [Semantic Segmentation for Line Drawing Vectorization Using Neural Networks](http://www.byungsoo.me/project/vectornet/paper.pdf) | EG 2018 | [[project]](http://www.byungsoo.me/project/vectornet) [[code]](https://github.com/byungsook/vectornet) | Yes |
| [Deep Line Drawing Vectorization via Line Subdivision and Topology Reconstruction](https://www.researchgate.net/profile/Chu_Han8/publication/337249870_Deep_Line_Drawing_Vectorization_via_Line_Subdivision_and_Topology_Reconstruction/links/5f0fec43299bf1e548ba370f/Deep-Line-Drawing-Vectorization-via-Line-Subdivision-and-Topology-Reconstruction.pdf) | PG 2019 | | Yes |
| [Inertia-based Fast Vectorization of Line Drawings](https://www.researchgate.net/profile/Rafal_Scherer/publication/336936860_Inertia-based_Fast_Vectorization_of_Line_Drawings/links/5dbbc8ad299bf1a47b0721d1/Inertia-based-Fast-Vectorization-of-Line-Drawings.pdf) | PG 2019 | | No |
| [Vectorization of Line Drawings via Polyvector Fields](https://dl.acm.org/doi/10.1145/3202661) | TOG 2019 | [[Code]](https://github.com/bmpix/PolyVectorization) | No |
| [Integer-Grid Sketch Simplification and Vectorization](http://www-sop.inria.fr/reves/Basilic/2020/SBBB20/paper.pdf) | SGP 2020 | [[Project]](https://repo-sam.inria.fr/d3/grid-vectorization/) [[Code]](https://gitlab.inria.fr/D3/grid-vectorization/) | No |
| [Deep Vectorization of Technical Drawings](https://arxiv.org/abs/2003.05471) | ECCV 2020 | [[project]](http://adase.group/3ddl/projects/vectorization/) [[code]](https://github.com/Vahe1994/Deep-Vectorization-of-Technical-Drawings) | Yes |
| [General Virtual Sketching Framework for Vector Line Art](https://esslab.jp/publications/HaoranSIGGRAPH2021.pdf) | SIGGRAPH 2021 | [[project]](https://markmohr.github.io/virtual_sketching/) [[code]](https://github.com/MarkMoHR/virtual_sketching) | Yes |
| [Keypoint-Driven Line Drawing Vectorization via PolyVector Flow](http://www-labs.iro.umontreal.ca/~bmpix/pdf/polyvector_flow.pdf) | SIGGRAPH Asia 2021 | [[project]](https://puhachov.xyz/publications/keypoint-driven-polyvector-flow/) | Hybrid |
| [End-to-end Line Drawing Vectorization](https://www.aaai.org/AAAI22Papers/AAAI-52.LiuH.pdf) | AAAI 2022 |  | Yes |
| [Vectorizing Line Drawings of Arbitrary Thickness via Boundary-based Topology Reconstruction](https://onlinelibrary.wiley.com/doi/full/10.1111/cgf.14485) | CGF 2022 |  | No |
| [Singularity-Free Frame Fields for Line Drawing Vectorization](https://diglib.eg.org/handle/10.1111/cgf14901) | SGP 2023 | [[code]](https://github.com/SingularityFreeFrameFields/Code) | No |
| [Deep Sketch Vectorization via Implicit Surface Extraction](https://cragl.cs.gmu.edu/sketchvector/Deep%20Sketch%20Vectorization%20via%20Implicit%20Surface%20Extraction%20(Chuan%20Yan,%20Yong%20Li,%20Deepali%20Aneja,%20Matthew%20Fisher,%20Edgar%20Simo-Serra,%20Yotam%20Gingold%202024%20SIGGRAPH).pdf) | SIGGRAPH 2024 | [[project]](https://cragl.cs.gmu.edu/sketchvector/) [[code]](https://github.com/Nauhcnay/Deep-Sketch-Vectorization) | Hybrid |


b) Rough sketch simplification / cleanup

- Datasets and benchmark

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [A Benchmark for Rough Sketch Cleanup](https://hal.archives-ouvertes.fr/hal-02939477/document) | SIGGRAPH Asia 2020 | [[Project]](https://cragl.cs.gmu.edu/sketchbench/)  [[Code]](https://github.com/Nauhcnay/A-Benchmark-for-Rough-Sketch-Cleanup) |

- Methods

| Paper | Source | Code/Project Link |
| --- | --- | --- | 
| [Learning to Simplify: Fully Convolutional Networks for Rough Sketch Cleanup](https://esslab.jp/publications/SimoSerraSIGGRAPH2016.pdf) | SIGGRAPH 2016 | [[Code]](https://github.com/bobbens/sketch_simplification) [[Project]](https://esslab.jp/~ess/en/research/sketch/) |
| [Mastering Sketching: Adversarial Augmentation for Structured Prediction](https://esslab.jp/~ess/publications/SimoSerraTOG2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/sketch_simplification)  [[Project]](https://esslab.jp/~ess/en/research/sketch_master/) |
| [Real-Time Data-Driven Interactive Rough Sketch Inking](https://esslab.jp/~ess/publications/SimoSerraSIGGRAPH2018.pdf) | SIGGRAPH 2018 | [[Code]](https://github.com/bobbens/line_thinning) [[Project]](https://esslab.jp/~ess/en/research/inking/) |
| [Perceptual-aware Sketch Simplification Based on Integrated VGG Layers](https://ieeexplore.ieee.org/abstract/document/8771128/) | TVCG 2019 |  |

c) Manga (Comics)

| Paper | Source | Code/Project Link |
| --- | --- | --- | 
| [Deep extraction of manga structural lines](https://dl.acm.org/citation.cfm?id=3073675) | SIGGRAPH 2017 | [[Code]](https://github.com/ljsabc/MangaLineExtraction) |
| [Manga Filling Style Conversion with Screentone Variational Autoencoder](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) | SIGGRAPH Asia 2020 | [[Project]](https://www.cse.cuhk.edu.hk/~ttwong/papers/screenstyle/screenstyle.html) [[Code]](https://github.com/msxie92/ScreenStyle) |
| [Generating Manga from Illustrations via Mimicking Manga Workflow](https://openaccess.thecvf.com/content/CVPR2021/papers/Zhang_Generating_Manga_From_Illustrations_via_Mimicking_Manga_Creation_Workflow_CVPR_2021_paper.pdf) | CVPR 2021 | [[Project]](https://lllyasviel.github.io/MangaFilter/) [[Code]](https://github.com/lllyasviel/MangaFilter) |
| [MangaGAN: Unpaired Photo-to-Manga Translation Based on The Methodology of Manga Drawing](https://arxiv.org/abs/2004.10634) | AAAI 2021 | |
| [MARVEL: Raster Gray-level Manga Vectorization via Primitive-wise Deep Reinforcement Learning](https://ieeexplore.ieee.org/abstract/document/10233891) | TCSVT 2023 | |
| [Manga Generation via Layout-controllable Diffusion](https://arxiv.org/abs/2412.19303) | arxiv 24.12 | [[code]](https://github.com/siyuch-fdu/MangaDiffusion) [[webpage]](https://siyuch-fdu.github.io/MangaDiffusion/) |
| [DiffSensei: Bridging Multi-Modal LLMs and Diffusion Models for Customized Manga Generation](https://arxiv.org/abs/2412.07589) | CVPR 2025 | [[code]](https://github.com/jianzongwu/DiffSensei) [[webpage]](https://jianzongwu.github.io/projects/diffsensei/) |



## 3. Vector Graphics Generation (2D)

Here we focus on learning-based vector graphics generation **without** depending on vector training data, and traditional vectorization algorithms.


- Learning with external black-box (non-differentiable) rendering simulator

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Synthesizing Programs for Images using Reinforced Adversarial Learning](http://proceedings.mlr.press/v80/ganin18a/ganin18a.pdf) | ICML 2018 | [[Code]](https://github.com/deepmind/spiral) |
| [Unsupervised Doodling and Painting with Improved SPIRAL](https://arxiv.org/abs/1910.01007) | arxiv 1910 | [[Project]](https://learning-to-paint.github.io/) |

- Learning with built-in differentiable rendering module

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Layered Image Vectorization via Semantic Simplification](https://arxiv.org/abs/2406.05404) | arxiv 24.06 | [[webpage]](https://szuviz.github.io/layered_vectorization/) [[code]](https://github.com/SZUVIZ/layered_vectorization/) |
| [Inverse Painting: Reconstructing The Painting Process](https://dl.acm.org/doi/full/10.1145/3680528.3687574) | SIGGRAPH Asia 2024 | [[code]](https://github.com/ArmastusChen/inverse_painting) |
| [ProcessPainter: Learning to draw from sequence data](https://arxiv.org/abs/2406.06062) | SIGGRAPH Asia 2024 | [[code]](https://github.com/nicolaus-huang/ProcessPainter) |
| [Segmentation-guided Layer-wise Image Vectorization with Gradient Fills](https://arxiv.org/abs/2408.15741) | ECCV 2024 | |
| [Towards High-fidelity Artistic Image Vectorization via Texture-Encapsulated Shape Parameterization](https://openaccess.thecvf.com/content/CVPR2024/papers/Chen_Towards_High-fidelity_Artistic_Image_Vectorization_via_Texture-Encapsulated_Shape_Parameterization_CVPR_2024_paper.pdf) | CVPR 2024 |  |
| [SuperSVG: Superpixel-based Scalable Vector Graphics Synthesis](https://openaccess.thecvf.com/content/CVPR2024/papers/Hu_SuperSVG_Superpixel-based_Scalable_Vector_Graphics_Synthesis_CVPR_2024_paper.pdf) | CVPR 2024 | [[code]](https://github.com/sjtuplayer/SuperSVG) |
| [Vector Graphics Generation via Mutually Impulsed Dual-domain Diffusion](https://openaccess.thecvf.com/content/CVPR2024/papers/Zhao_Vector_Graphics_Generation_via_Mutually_Impulsed_Dual-domain_Diffusion_CVPR_2024_paper.pdf) | CVPR 2024 |  |
| [Optimize and Reduce: A Top-Down Approach for Image Vectorization](https://arxiv.org/abs/2312.11334) | AAAI 2024 | [[code]](https://github.com/ajevnisek/optimize-and-reduce) |
| [Segmentation-Based Parametric Painting](https://arxiv.org/abs/2311.14271) | arxiv 23.11 | [[code]](https://github.com/manuelladron/semantic_based_painting) [[project]](https://manuelladron.github.io/semantic_based_painting/) |
| [Editable Image Geometric Abstraction via Neural Primitive Assembly](https://openaccess.thecvf.com/content/ICCV2023/papers/Chen_Editable_Image_Geometric_Abstraction_via_Neural_Primitive_Assembly_ICCV_2023_paper.pdf) | ICCV 2023 |  |
| [Stroke-based Neural Painting and Stylization with Dynamically Predicted Painting Region](https://arxiv.org/abs/2309.03504) | ACM MM 2023 | [[code]](https://github.com/sjtuplayer/Compositional_Neural_Painter) |
| [Intelli-Paint: Towards Developing More Human-Intelligible Painting Agents](https://arxiv.org/abs/2112.08930) | ECCV 2022 | [[project]](https://1jsingh.github.io/intelli-paint) |
| [Towards Layer-wise Image Vectorization](https://ma-xu.github.io/LIVE/index_files/CVPR22_LIVE_main.pdf) | CVPR 2022 | [[code]](https://github.com/ma-xu/LIVE) [[project]](https://ma-xu.github.io/LIVE/) |
| [Paint Transformer: Feed Forward Neural Painting with Stroke Prediction](https://arxiv.org/abs/2108.03798) | ICCV 2021 | [[code]](https://github.com/Huage001/PaintTransformer) |
| [Combining Semantic Guidance and Deep Reinforcement Learning For Generating Human Level Paintings](https://openaccess.thecvf.com/content/CVPR2021/papers/Singh_Combining_Semantic_Guidance_and_Deep_Reinforcement_Learning_for_Generating_Human_CVPR_2021_paper.pdf) | CVPR 2021 | [[code]](https://github.com/1jsingh/semantic-guidance) |
| [Rethinking Style Transfer: From Pixels to Parameterized Brushstrokes](https://arxiv.org/abs/2103.17185) | CVPR 2021 | [[code]](https://github.com/CompVis/brushstroke-parameterized-style-transfer) |
| [Im2Vec: Synthesizing Vector Graphics without Vector Supervision](https://arxiv.org/abs/2102.02798) | CVPR 2021 | [[Project]](http://geometry.cs.ucl.ac.uk/projects/2021/im2vec/) [[code]](https://github.com/preddy5/Im2Vec) |
| [Stylized Neural Painting](https://arxiv.org/abs/2011.08114) | CVPR 2021 | [[Code]](https://github.com/jiupinjia/stylized-neural-painting) [[project]](https://jiupinjia.github.io/neuralpainter/) |
| [Painting Many Pasts: Synthesizing Time Lapse Videos of Paintings](https://openaccess.thecvf.com/content_CVPR_2020/papers/Zhao_Painting_Many_Pasts_Synthesizing_Time_Lapse_Videos_of_Paintings_CVPR_2020_paper.pdf) | CVPR 2020 | [[Code]](https://github.com/xamyzhao/timecraft) [[project]](https://xamyzhao.github.io/timecraft/) |
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
| [TCB-Spline-Based Image Vectorization](https://dl.acm.org/doi/10.1145/3513132) | TOG 2022 |  |
| [Image vectorization and editing via linear gradient layer decomposition](https://cragl.cs.gmu.edu/gradientlayers/Image%20vectorization%20and%20editing%20via%20linear%20gradient%20layer%20decomposition%20(Zheng-Jun%20Du,%20Liang-Fu%20Kang,%20Jianchao%20Tan,%20Yotam%20Gingold,%20Kun%20Xu%202023%20SIGGRAPH)%20small.pdf) | SIGGRAPH 2023 |  |


## 4. Vector Graphics Generation (3D)

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [3Doodle: Compact Abstraction of Objects with 3D Strokes](https://arxiv.org/abs/2402.03690) | SIGGRAPH 2024 | [[code]](https://github.com/changwoonchoi/3Doodle) |
| [Diff3DS: Generating View-Consistent 3D Sketch via Differentiable Curve Rendering](https://arxiv.org/abs/2405.15305) | ICLR 2025 | [[webpage]](https://yiboz2001.github.io/Diff3DS/) |
| [Recovering Dynamic 3D Sketches from Videos](https://arxiv.org/abs/2503.20321) | CVPR 2025 | [[webpage]](https://jaeah.me/liv3stroke_web/) |

- Wire Art

| Paper | Source | Code/Project Link |
| --- | --- | --- |
| [Wired Perspectives: Multi-View Wire Art Embraces Generative AI](https://openaccess.thecvf.com/content/CVPR2024/papers/Qu_Wired_Perspectives_Multi-View_Wire_Art_Embraces_Generative_AI_CVPR_2024_paper.pdf) | CVPR 2024 | [[code]](https://github.com/WinKawaks/DreamWire) [[webpage]](https://dreamwireart.github.io/) |
| [Fabricable 3D Wire Art](https://doi.org/10.1145/3641519.3657453) | SIGGRAPH 2024 |  |




