---
layout: page
title: AI-assisted Dental Disease Detection with Radiography
#description: Funded by NIHR
img: assets/img/BeCertain.png
importance: 1
#redirect: https://AI4Dentistry.github.io/AI4Dentistry
category: Projects
related_publications: false


---



###### We aim to develop reliable AI tools to assist dentists in abnormalities in dental radiographs. By supporting clinical decision-making with trustworthy AI models, our ultimate goal is to:
* Enhance diagnostic accuracy.
* Detect early diseases.
* Reduce unnecessary economic and human costs spent on dental X-ray diagnosis.

<div class="row justify-content-center">
    <div class="col-sm-9 col-md-9 col-lg-9 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/comparison.png" 
            class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

## **Background**

The World Health Organization (WHO) estimated that nearly 3.5 billion people worldwide, which is about **50%** of the global population, suffer from some form of oral disease[^1]. In the UK, NHS spends over **£3.6 billion** annually to provide dental care[^2]. Dental radiography is an essential tool for diagnosing dental diseases such as tooth decay and gum disease. **46 million** dental X-rays are taken in the UK each year[^3]. However, error rates in interpreting the X-rays by dentists are over **50%**.

Therefore, there is an urgent need for automated tools to assist dentists in identifying abnormalities in dental X-rays, with the goal of improving diagnostic accuracy while minimizing unnecessary clinical and economic burdens. One of the primary challenges in developing high-performance AI models is the lack of sufficiently large, annotated datasets. This project addresses that gap by providing a software platform that enables dental professionals to upload, annotate, and receive AI-assisted diagnoses on dental radiographs. By doing so, it establishes a positive feedback loop: improved diagnostic accuracy supports better annotations, which in turn enhance AI model performance—ultimately advancing both clinical decision-making and AI development.

The project has been sponsored by the National Institute for Health and Care Research (NIHR).

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

## **Our model**

We are developing a medical device, **Dx Annotator**, which aims to:
* Facilitate the collection and annotation of dental radiographs.
* Allow dentists to ultilise Artificial Intelligence (AI) model to predict disease on X-rays assist diagnosis. 

Dentist's diagnostic performance, especially sensitivity, can be significantly improved with AI-suggested dental findings[^4] [^5] [^6].

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

#### **What dental diseases can our model detect?** 
<div class="row justify-content-center">
    <div class="col-sm-12 col-md-12 col-lg-12 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/dxa.png" 
            class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Our AI model is capable of detecting **11** categories of dental conditions, including their subconditions where applicable:
* Bone loss 
  * Stage 1: <15%
  * Stage 2: Coronal Third
  * Stage 3: Mid Third
  * Stage 4: Apical Third)
* Calculus
* Dental caries
  * Grade 1: Outer Enamel
  * Grade 2: Inner Enamel
  * Grade 3: Outer Dentin
  * Grade 4: Middle Dentin
  * Grade 5: Inner Dentin
* External Resorption 
* Internal Resorption 
* Missing Coronal Restoration 
* Open Margin 
* Overhang
* Periapical Radiolucency 
* Remaining Root 
* Restoration Radiolucency (Adhesive/Liner)

If you are interested in our project and would like to see how our AI model works or contribute your images, you are more than welcome to try our product [Dx Annotator](https://dxa.becertain.ai)!

**Note:** The AI-suggested dental abnormalities from Dx Annotator are designed to supplement, not replace, the clinician's own assessment and professional judgment.

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

## **Our data**
Multiple rounds of data collection and annotation were performed to acquire sufficient training data for our AI model. The images, sourced from partner clinical sites, were carefully anonymized during annotation.

In particular, we have already collected:
* 100K+ dental radiographs from different clinical sites.
* 50K+ image-level annotations from 30+ dentists.

Due to the high variety of dental structures, positioning/orientation errors, area biases when ordering a scan, and differing diagnostic expertise among annotators, each dental radiograph is reviewed by multiple annotators. To further enhance our model's performance, we also applied state-of-the-art algorithms designed to effectively process and reconcile crowdsourced annotations[^7].

<div class="row justify-content-center">
    <div class="col-sm-12 col-md-12 col-lg-12 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/crowdsource.png" 
            class="img-fluid rounded" %}
    </div>
</div>

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

## **Recent News** 


<div class="container mt-4">
  <div class="row mb-3">
    <div class="col-sm-3 text-muted"><strong>May 2025</strong></div>
    <div class="col-sm-9">We are preparing for the clinical evaluation of Dx Annotator.</div>
  </div>
  <div class="row mb-3">
    <div class="col-sm-3 text-muted"><strong>April 2025</strong></div>
    <div class="col-sm-9">We have completed the development of Dx Annotator.</div>
  </div>
  <div class="row mb-3">
    <div class="col-sm-3 text-muted"><strong>January 2025</strong></div>
    <div class="col-sm-9">The second stage of Dx Annotator development has started.</div>
  </div>
  <div class="row mb-3">
    <div class="col-sm-3 text-muted"><strong>April 2024</strong></div>
    <div class="col-sm-9">We have started the development of Dx Annotator.</div>
  </div>
</div>

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

## **Our team**

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

<table border="1" cellspacing="0" cellpadding="8" style="font-size: 18px; border-collapse: collapse; width: 100%;">
  <tr style="background-color: #f2f2f2;">
    <th style="text-align: left; padding: 12px; font-weight: bold;">Role</th>
    <th style="text-align: left; padding: 12px; font-weight: bold;">Name/Details</th>
  </tr>
  <tr>
    <td style="padding: 10px; font-weight: bold;">Chief Investigator(s)</td>
    <td style="padding: 10px;"> <a href="https://yunpengli.ac" target="_blank">Dr Yunpeng Li</a></td>
  </tr>
  <tr>
    <td style="padding: 10px; font-weight: bold;">Joint Lead Applicant</td>
    <td style="padding: 10px;"> <a href="https://www.kcl.ac.uk/people/owen-addison" target="_blank">Professor Owen Addison</a></td>
  </tr>
  <tr>
    <td rowspan="6" style="padding: 10px; font-weight: bold;">Co-investigators</td>
    <td style="padding: 10px;"><a href="https://www.surrey.ac.uk/people/matthew-glover" target="_blank">Dr Matthew Glover </a></td>
  </tr>
  <tr>
    <td style="padding: 10px;"> <a href="https://www.dentalhealth.org/dr-nigel-carter" target="_blank">Dr Nigel Carter </a></td>
  </tr>
  <tr>
    <td style="padding: 10px;"> <a href="https://www.surrey.ac.uk/people/samaneh-kouchaki" target="_blank">Dr Samaneh Kouchaki</a></td>
  </tr>
  <tr>
    <td style="padding: 10px;"> <a href="https://uk.linkedin.com/in/mark-halling-brown-92bbb611" target="_blank">Professor Mark Halling-Brown</a></td>
  </tr>
  <tr>
    <td style="padding: 10px;"> <a href="https://www.surrey.ac.uk/people/philip-evans" target="_blank">Professor Philip Evans</a></td>
  </tr>
  <tr>
    <td style="padding: 10px;"> <a href="https://www.surrey.ac.uk/people/simon-skene" target="_blank">Professor Simon Skene </a></td>
  </tr>
  <tr>
    <td style="padding: 10px; font-weight: bold;">Postdoctoral researcher</td>
    <td style="padding: 10px;"> <a href="https://xiongjiechen.com" target="_blank">Dr Xiongjie Chen</a></td>
  </tr>
  <tr>
    <td style="padding: 10px; font-weight: bold;">PhD student</td>
    <td style="padding: 10px;"> <a href="https://zhiqin1998.github.io/" target="_blank">Zhi Qin Tan</a></td>
  </tr>
</table>

<div class="clearfix" style="width: 100%; padding-bottom: 25px"></div>

[//]: # (<div class="container" style="display: flex; justify-content: space-between; width: 100%;">)

[//]: # (    <div style="font-size: 20px;">Start Date: June 2023</div>)

[//]: # (    <div style="font-size: 20px;">End Date: November 2025</div>)

[//]: # (</div>)

<br/>


## **References**

[^1]: [WHO's global oral health status report 2022: Actions, discussion and implementation](https://pubmed.ncbi.nlm.nih.gov/36680388/)
[^2]: [Inequalities in oral health in England](https://assets.publishing.service.gov.uk/media/6051f994d3bf7f0453f7b9a9/Inequalities_in_oral_health_in_England.pdf)
[^3]: [Frequency and Collective Dose for Medical and Dental X-ray Examinations in the UK, 2008](https://assets.publishing.service.gov.uk/media/5a7d618440f0b60a7f1aa285/HPA-CRCE-012_for_website.pdf)
[^4]: [The ADEPT study: a comparative study of dentists' ability to detect enamel-only proximal caries in bitewing radiographs with and without the use of AssistDent artificial intelligence software](https://pubmed.ncbi.nlm.nih.gov/34686815/)
[^5]: [Artificial intelligence for caries detection: randomized trial](https://www.cochranelibrary.com/central/doi/10.1002/central/CN-02375033/full)
[^6]: [Deep learning-based dental plaque detection on primary teeth: a comparison with clinical assessments](https://link.springer.com/article/10.1186/s12903-020-01114-6)
[^7]: [Bayesian Detector Combination for Object Detection with Crowdsourced Annotations](https://arxiv.org/abs/2407.07958)