---
layout: custom-project
title: Bayesian Detector Combination
description: Object Detection with Noisy Crowdsourced (Multi-Rater) Annotations
img: assets/img/bdc_eccv/bdc-diagram.png
redirect: 
importance: 2
category: Projects
include_description: true
authors:
  - Zhi Qin Tan <sup>1</sup>
  - Olga Isupova <sup>2</sup>
  - Gustavo Carneiro <sup>1</sup>
  - Xiatian Zhu <sup>1</sup>
  - Yunpeng Li <sup>1,3</sup>
institutions:
  - University of Surrey
  - University of Oxford
  - King's College London
venue: European Conference on Computer Vision 2024
venue_link: https://eccv2024.ecva.net/virtual/2024/poster/420
main_pdf: https://doi.org/10.1007/978-3-031-73036-8_19
supp_pdf: https://static-content.springer.com/esm/chp%3A10.1007%2F978-3-031-73036-8_19/MediaObjects/636743_1_En_19_MOESM1_ESM.pdf
github: https://github.com/zhiqin1998/bdc
arxiv: https://arxiv.org/abs/2407.07958
abstract: Acquiring fine-grained object detection annotations in unconstrained images is time-consuming, expensive, and prone to noise, especially in crowdsourcing scenarios. Most prior object detection methods assume accurate annotations; A few recent works have studied object detection with noisy crowdsourced annotations, with evaluation on distinct synthetic crowdsourced datasets of varying setups under artificial assumptions. To address these algorithmic limitations and evaluation inconsistency, we first propose a novel Bayesian Detector Combination (BDC) framework to more effectively train object detectors with noisy crowdsourced annotations, with the unique ability of automatically inferring the annotators' label qualities. Unlike previous approaches, BDC is model-agnostic, requires no prior knowledge of the annotators' skill level, and seamlessly integrates with existing object detection models. Due to the scarcity of real-world crowdsourced datasets, we introduce large synthetic datasets by simulating varying crowdsourcing scenarios. This allows consistent evaluation of different models at scale. Extensive experiments on both real and synthetic crowdsourced datasets show that BDC outperforms existing state-of-the-art methods, demonstrating its superiority in leveraging crowdsourced data for object detection.
images:
  slider: true
---

### **Noisy Crowdsourced (Multi-Rater Annotations)**
Accurate object annotations are often difficult and expensive to obtain. Researchers typically resorts to collecting crowdsourced or multi-rater annotations and perform aggregation to obtain better ground truth for model training. However, acquiring fine-grained object detection annotations in unconstrained images is time-consuming, expensive, and prone to noise. These challenges are especially significant in complex domains such as dental radiograph images, where interobserver variability and disagreement among expert annotators make it difficult to achieve unanimity.

<div class="w-50 ml-0 mr-0 mx-auto">
  <swiper-container keyboard="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true" rewind="true" centered-slides="true" autoplay-delay="5000">
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/70282.png" class="img-fluid rounded"
      caption="Noisy annotations in COCO dataset" min-height="300px" max-height="350px" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/326247.png" class="img-fluid rounded"
      caption="Noisy annotations in COCO dataset" min-height="300px" max-height="350px" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/416149.png" class="img-fluid rounded"
      caption="Noisy annotations in COCO dataset" min-height="300px" max-height="350px" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/disaster_110.png" class="img-fluid rounded"
      caption="Noisy crowdsourced annotations in a disaster response dataset" min-height="300px" max-height="350px" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/vindr_0.png" class="img-fluid rounded" 
      caption="Noisy multi-rater annotations in VinDR-CXR dataset" min-height="300px" max-height="350px" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/vindr_62.png" class="img-fluid rounded"
      caption="Noisy multi-rater annotations in VinDR-CXR dataset" min-height="300px" max-height="350px" %}</swiper-slide>
  </swiper-container>
</div>

This results in multiple noisy object annotations originating from different annotators, i.e. multi-rater problem in object detection. 

<hr style="height:10px;"/>

### **Bayesian Detector Combination**
We propose a novel Bayesian Detector Combination (BDC) framework to more effectively train object detectors with only noisy multi-rater annotations, with the unique ability of automatically inferring the annotators’ label qualities. Unlike previous approaches, the proposed method is model-agnostic, requires no prior knowledge of the annotators’ skill level, and seamlessly integrates with existing object detection models.  

{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/bdc-diagram.png" class="img-fluid rounded z-depth-1" %}

At a high level, BDC models each annotators’ annotation accuracy in terms of bounding boxes as a Gaussian distribution with a Gaussian-Gamma prior and class labels as a multinomial distribution with a Dirichlet prior. During model training, we perform a many-to-one matching of each annotator’s annotation to the model output via a simple heuristic matching rule. The annotation-prediction matches are then used to update each annotators’ prior distributions with the mean-field variational Bayesian method. Then, the updated posterior distributions are used to aggregate all annotations matched to the same prediction to learn the object detector’s parameters. The process of optimizing the object detector’s parameters and updating the prior distributions is repeated iteratively until convergence.  

<hr style="height:10px;"/>

### **Experiments Results**
To demonstrate the superiority, robustness and generalizability of BDC, our experiments span across three popular object detectors and includes several natural images and medical images datasets. Our extensive evaluation showed that BDC outperforms prior methods with negligible computation overhead, improving detection accuracy up to 12.7% AP50 when ground truth is available. Please see the [paper]({{ page.arxiv }}) for the full results. 

#### **VinDR-CXR**
<div class="container">
  <div class="row">
    <span>Comparison of aggregated labels on the VinDR-CXR chest radiograph dataset. For WBF-EARL, the number beside the class label is the annotators' level of agreement while for Crowd R-CNN and BDC, the number indicates the class probability.</span>
  </div>
  <div class="row">
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1428_na.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1428_mv.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1428_earl.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1428_crcnn.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1428_bdc.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
  </div>
  <div class="row">
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1623_na.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1623_mv.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1623_earl.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1623_crcnn.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/1623_bdc.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
  </div>
  <div class="row text-center mb-3">
    <div class="col px-2">No Aggregation</div>
    <div class="col px-2">Majority Voting</div>
    <div class="col px-2">WBF-EARL</div>
    <div class="col px-2">Crowd R-CNN</div>
    <div class="col px-2">BDC (ours)</div>
  </div>
</div>

#### **VOC-MIX**
<div class="container">
  <div class="row">
    <span>Comparison of aggregated labels on the VOC-MIX synthetic dataset. For WBF-EARL, the number beside the class label is the annotators' level of agreement while for Crowd R-CNN and BDC, the number indicates the class probability.</span>
  </div>
  <div class="row">
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_na.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_mv.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_earl.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_crcnn.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_bdc.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/127_gt.png" class="img-fluid rounded z-depth-1" zoomable="true" %}</div>
  </div>
  <div class="row">
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_na.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_mv.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_earl.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_crcnn.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_bdc.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
    <div class="col px-2">{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/146_gt.png" class="img-fluid rounded z-depth-1 mb-n2" zoomable="true" %}</div>
  </div>
  <div class="row text-center mb-3">
    <div class="col px-2">No Aggregation</div>
    <div class="col px-2">Majority Voting</div>
    <div class="col px-2">WBF-EARL</div>
    <div class="col px-2">Crowd R-CNN</div>
    <div class="col px-2">BDC (ours)</div>
    <div class="col px-2">Ground truth</div>
  </div>
</div>

#### **Scability and Robustness**
We analyse the scability and Robustness of our method by varying the number of annotators and changing the percentage of noisy or poor-performing annotators.
Our method consistently outperform other alternatives under all scenarios.

<div class="w-50 ml-0 mr-0 mx-auto">
  {% include figure.liquid loading="eager" path="assets/img/bdc_eccv/leg_title_abls.png" class="img-fluid rounded mb-n2" %}
  <swiper-container keyboard="true" navigation="true" pagination="true" pagination-clickable="true" pagination-dynamic-bullets="true" rewind="true" centered-slides="true" autoplay-delay="5000">
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/k_ablation.png" class="img-fluid rounded"
                     caption="Scalability of BDC" %}</swiper-slide>
    <swiper-slide>{% include figure.liquid loading="eager" path="assets/img/bdc_eccv/nr_ablation.png" class="img-fluid rounded"
                     caption="Robustness of BDC" %}</swiper-slide>
  </swiper-container>
</div>

<hr style="height:10px;"/>

### **Presentation**
<div class="w-75 ml-0 mr-0 mx-auto">
  <div class="embed-responsive embed-responsive-16by9">
    {% include video.liquid path="https://www.youtube.com/embed/yddjKV1hmrI" class="embed-responsive-item rounded z-depth-1"
        title="Bayesian Detector Combination for Object Detection with Crowdsourced Annotations - ECCV 2024" 
        caption="Poster presentation at ECCV 2024" %}
  </div>
</div>

<hr style="height:10px;"/>

### **Poster**
<div class="container">
  <iframe src="/assets/pdf/bdc_eccv_poster.pdf" class="w-100" height="700px"></iframe>
</div>

<hr style="height:10px;"/>

### **BibTeX**
```bibtex
@inproceedings{bdc2024tan,
   title     = {Bayesian Detector Combination for Object Detection with Crowdsourced Annotations},
   author    = {Tan, Zhi Qin and Isupova, Olga and Carneiro, Gustavo and Zhu, Xiatian and Li, Yunpeng},
   booktitle = {Proc. Eur. Conf. Comput. Vis.},
   pages     = {329--346},
   year      = {2024},
   address   = {Milan, Italy},
}
```
