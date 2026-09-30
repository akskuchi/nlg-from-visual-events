# Natural Language Generation from Visual Events: List of Resources

A curated list of models, pre-trained VLMs, datasets, evaluation metrics, and surveys relevant to **natural language generation from visual events**, i.e., generating text from temporally ordered sequences of images or video frames.

This list accompanies the paper:

> Aditya K Surikuchi, Raquel Fernández, and Sandro Pezzelle. *Natural Language Generation from Visual Events: State-of-the-Art and Key Open Questions.* [arXiv:2502.13034](https://arxiv.org/abs/2502.13034)

The paper argues that five seemingly distinct tasks are instances of one broader problem. Entries below are organized by task, following the paper, and include the main works discussed in it. The list is representative rather than exhaustive. Contributions via pull request are welcome.

---

## Tasks

### Change Captioning
Describe the semantic changes between a pair of related images.

**Task-specific models**
| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| CARD | ResNet, Transformer | – | Transformer | [Context-aware Difference Distilling for Multi-change Captioning](https://doi.org/10.18653/v1/2024.acl-long.430) (2024) |
| SCORER+CBR | ResNet, MH(S/X)A | – | Transformer | [Self-supervised Cross-view Representation Reconstruction for Change Captioning](https://doi.org/10.1109/iccv51070.2023.00263) (2023) |
| VARD-Trans | ResNet, Linear(s) | – | Transformer | [Viewpoint-Adaptive Representation Disentanglement Network for Change Captioning](https://doi.org/10.1109/TIP.2023.3268004) (2023) |
| DUDA | ResNet, RNN | – | RNN | [Robust Change Captioning](https://doi.org/10.1109/iccv.2019.00472) (2019) |

**Datasets**
- **Spot-the-Diff**: 13,192 image pairs (frames from surveillance video) with descriptions of their differences. [Learning to Describe Differences Between Pairs of Similar Images](https://doi.org/10.18653/v1/D18-1436) (2018)
- **CLEVR-Change**: 79,606 image pairs of synthetic 3D scenes with 493,735 generated change captions. [Robust Change Captioning](https://doi.org/10.1109/iccv.2019.00472) (2019)
- **LEVIR-CC**: 10,077 pairs of bi-temporal remote sensing images with 50,385 change descriptions. [Remote Sensing Image Change Captioning With Dual-Branch Transformers: A New Method and a Large Scale Dataset](https://doi.org/10.1109/TGRS.2022.3218921) (2022)

### Video Question Answering
Answer a natural-language question about a video or an ordered image set.

**Task-specific models**
| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| ViLA | ViT, Transformer | Q-Former | Flan-T5 XL | [ViLA: Efficient Video-Language Alignment for Video Question Answering](https://arxiv.org/abs/2312.08367) (2025) |
| LLaMA-VQA | CLIP-ViT-L | Linear | Llama | [Large Language Models are Temporal and Causal Reasoners for Video Question Answering](https://doi.org/10.18653/v1/2023.emnlp-main.261) (2023) |
| SeViLA | ViT | Q-Former | Flan-T5 XL | [Self-Chained Image-Language Model for Video Localization and Question Answering](https://proceedings.neurips.cc/paper_files/paper/2023/file/f22a9af8dbb348952b08bd58d4734b50-Paper-Conference.pdf) (2023) |
| FrozenBiLM | CLIP-ViT-L | Linear | DeBERTa-V2-XL | [Zero-Shot Video Question Answering via Frozen Bidirectional Language Models](https://proceedings.neurips.cc/paper_files/paper/2022/file/00d1f03b87a401b1c7957e0cc785d0bc-Paper-Conference.pdf) (2022) |

**Datasets**
- **MSVD-QA** and **MSRVTT-QA**: 1,970 videos with 50,505 QA pairs and 10,000 videos with 243,690 QA pairs, respectively; QA pairs generated from video captions, with one-word answers. [Video Question Answering via Gradually Refined Attention over Appearance and Motion](https://doi.org/10.1145/3123266.3123427) (2017)
- **NExT-QA**: 5,440 videos of daily activities with 52,044 manually annotated QA pairs targeting causal and temporal reasoning. [NExT-QA: Next Phase of Question-Answering to Explaining Temporal Actions](https://doi.org/10.1109/CVPR46437.2021.00965) (2021)
- **Image-set VQA**: question answering over sets of images. [Visual Question Answering on Image Sets](https://doi.org/10.1007/978-3-030-58589-1_4) (2020)
- **BDIQA**: Video QA benchmark for theory of mind. [BDIQA: A New Dataset for Video Question Answering to Explore Cognitive Reasoning through Theory of Mind](https://doi.org/10.1609/aaai.v38i1.27814) (2024)

### Video Captioning
Generate a description of a video.

**Task-specific models**
| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| Vid2Seq | CLIP-ViT-L, Transformer | – | T5-base | [Vid2Seq: Large-Scale Pretraining of a Visual Language Model for Dense Video Captioning](https://doi.org/10.1109/cvpr52729.2023.01032) (2023) |
| TextKG | Transformer | – | Transformer | [Text With Knowledge Graph Augmented Transformer for Video Captioning](https://doi.org/10.1109/cvpr52729.2023.01816) (2023) |
| VTAR | InceptionResNetV2, C3D | Transformer | Transformer | [Learning Video-Text Aligned Representations for Video Captioning](https://doi.org/10.1145/3546828) (2023) |
| ENC-DEC | 3D CNN | Attention | RNN | [Describing Videos by Exploiting Temporal Structure](https://doi.org/10.1109/iccv.2015.512) (2015) |

**Datasets**
- **MSR-VTT**: 10,000 open-domain web video clips (41.2 hours) with 200,000 captions. [MSR-VTT: A Large Video Description Dataset for Bridging Video and Language](https://doi.org/10.1109/CVPR.2016.571) (2016)
- **Charades**: 9,848 videos of indoor daily activities (30 s on average) with 27,847 descriptions. [Hollywood in Homes: Crowdsourcing Data Collection for Activity Understanding](https://doi.org/10.1007/978-3-319-46448-0_31) (2016)
- **YouCook2**: 2,000 cooking videos (176 hours) with temporally localized descriptions of procedure steps. [Towards automatic learning of procedures from web instructional videos](https://doi.org/10.1609/aaai.v32i1.12342) (2018)

### Movie Auto Audio Description
Generate descriptions that complement the dialogue and soundtrack of a movie clip.

**Task-specific models**
| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| MM-Narrator | CLIP-ViT-L | – | GPT-4 | [MM-Narrator: Narrating Long-form Videos with Multimodal In-Context Learning](https://doi.org/10.1109/cvpr52733.2024.01295) (2024) |
| AutoAD-III | EVA-CLIP | Q-Former | Llama 2 | [AutoAD III: The Prequel - Back to the Pixels](https://doi.org/10.1109/cvpr52733.2024.01720) (2024) |
| AutoAD-II | CLIP-ViT-L | – | GPT-2, MHXA | [AutoAD II: The Sequel - Who, When, and What in Movie Audio Description](https://arxiv.org/abs/2310.06838) (2023) |
| AutoAD | CLIP-ViT-L | Transformer | GPT-2 | [AutoAD: Movie Description in Context](https://doi.org/10.1109/cvpr52729.2023.01815) (2023) |

**Datasets**
- **LSMDC**: 118,114 sentences (audio descriptions and scripts) aligned to clips from 202 movies. [Movie Description](https://doi.org/10.1007/s11263-016-0987-1) (2017)
- **MAD**: 384.6K audio description sentences grounded in 650 full-length movies (1.2K hours); videos released as features only. [MAD: A Scalable Dataset for Language Grounding in Videos From Movie Audio Descriptions](https://doi.org/10.1109/cvpr52688.2022.00497) (2022)
- **CMD-AD**: 101,268 audio descriptions aligned to clips from 1,432 movies. [AutoAD III: The Prequel - Back to the Pixels](https://doi.org/10.1109/cvpr52733.2024.01720) (2024)

### Visual Storytelling
Generate a coherent narrative from a temporally ordered sequence of images or video frames.

**Task-specific models**
| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| MCSM+BART | ResNet, RNN | – | BART | [Commonsense Knowledge Aware Concept Selection For Diverse and Informative Visual Storytelling](https://doi.org/10.1609/aaai.v35i2.16184) (2021) |
| TAPM | ResNet, Faster R-CNN | – | GPT-2 | [Transitional Adaptation of Pretrained Models for Visual Storytelling](https://doi.org/10.1109/cvpr46437.2021.01247) (2021) |
| KG Story | Faster R-CNN | – | Transformer | [Knowledge-Enriched Visual Storytelling](https://doi.org/10.1609/aaai.v34i05.6303) (2020) |
| GLAC Net | ResNet, RNN | – | RNN | [GLAC Net: GLocal Attention Cascading Networks for Multi-image Cued Story Generation](https://arxiv.org/abs/1805.10973) (2018) |

**Datasets**
- **VIST**: 20,211 sequences of photos from Flickr albums (81,743 photos), aligned with stories and descriptive captions. [Visual Storytelling](https://doi.org/10.18653/v1/N16-1147) (2016)
- **VWP**: almost 2K sequences of 5–10 movie shots with 12K character-grounded stories. [Visual Writing Prompts: Character-Grounded Story Generation with Curated Image Sequences](https://doi.org/10.1162/tacl_a_00553) (2023)

---

## Pre-trained multi-purpose VLMs used off-the-shelf

| Model | Vision encoder | Projector | Language decoder | Paper |
|---|---|---|---|---|
| Qwen2.5-VL | ViT | Linear | Qwen2.5 | [Qwen2.5-VL Technical Report](https://arxiv.org/abs/2502.13923) (2025) |
| DeepSeek-VL | SigLIP, SAM-B | Linear (x2) | DeepSeek | [DeepSeek-VL: Towards Real-World Vision-Language Understanding](https://arxiv.org/abs/2403.05525) (2024) |
| LLaVA-NeXT | CLIP-ViT-L | Linear | Mistral | [Visual Instruction Tuning](https://proceedings.neurips.cc/paper_files/paper/2023/file/6dcf277ea32ce3288914faf369fe6de0-Paper-Conference.pdf) (2023) |
| Video-LLaMA | ViT-G/14 | Q-Former | Llama | [Video-LLaMA: An Instruction-tuned Audio-Visual Language Model for Video Understanding](https://doi.org/10.18653/v1/2023.emnlp-demo.49) (2023) |
| mPLUG-Owl3 | SigLIP SO (400M) | Linear | Qwen2 | [mPLUG-Owl3: Towards Long Image-Sequence Understanding in Multi-Modal Large Language Models](https://openreview.net/forum?id=pr37sbuhVa) (2025) |
| Video-LLaVA | OpenCLIP ViT-L | Linear (x2) | Vicuna v1.5 | [Video-LLaVA: Learning United Visual Representation by Alignment Before Projection](https://doi.org/10.18653/v1/2024.emnlp-main.342) (2024) |
| Molmo | CLIP ViT-L/14 (336px) | Attention pooling, MLP | OLMo, OLMoE, or Qwen2 | [Molmo and PixMo: Open Weights and Open Data for State-of-the-Art Vision-Language Models](https://arxiv.org/abs/2409.17146) (2024) |
| Mantis (multi-image) | CLIP or SigLIP | LLaVA projector | Llama 3 | [Mantis: Interleaved Multi-Image Instruction Tuning](https://openreview.net/forum?id=skLtdUVaJa) (2024) |

---

## Evaluation

### Reference-based metrics
- *n*-gram overlap:
  - BLEU: [BLEU: a method for automatic evaluation of machine translation](https://aclanthology.org/P02-1040/) (2002)
  - METEOR: [METEOR: An Automatic Metric for MT Evaluation with Improved Correlation with Human Judgments](https://aclanthology.org/W05-0909/) (2005)
  - ROUGE: [ROUGE: A Package for Automatic Evaluation of Summaries](https://aclanthology.org/W04-1013/) (2004)
  - CIDEr: [CIDEr: Consensus-based Image Description Evaluation](https://doi.org/10.1109/CVPR.2015.7299156) (2015)
  - SPICE: [SPICE: Semantic Propositional Image Caption Evaluation](https://doi.org/10.1007/978-3-319-46454-1_24) (2016)
- Embedding-based:
  - WMD: [From Word Embeddings To Document Distances](https://proceedings.mlr.press/v37/kusnerb15.html) (2015)
  - BERTScore: [BERTScore: Evaluating Text Generation with BERT](https://openreview.net/forum?id=SkeHuCVFDr) (2020)
  - ViLBERTScore: [ViLBERTScore: Evaluating Image Caption Using Vision-and-Language BERT](https://doi.org/10.18653/v1/2020.eval4nlp-1.4) (2020)

### Reference-free metrics
- Text-only:
  - MAUVE: [MAUVE: Measuring the Gap Between Neural Text and Human Text using Divergence Frontiers](https://proceedings.neurips.cc/paper_files/paper/2021/file/260c2432a0eecc28ce03c10dadc078a4-Paper.pdf) (2021)
  - UNION: [UNION: An Unreferenced Metric for Evaluating Open-ended Story Generation](https://doi.org/10.18653/v1/2020.emnlp-main.736) (2020)
- Visual grounding:
  - CLIPScore: [CLIPScore: A Reference-free Evaluation Metric for Image Captioning](https://doi.org/10.18653/v1/2021.emnlp-main.595) (2021)
  - GROOViST: [GROOViST: A Metric for Grounding Objects in Visual Storytelling](https://doi.org/10.18653/v1/2023.emnlp-main.202) (2023)
- Coherence, repetition, and grounding: RoViST: [RoViST: Learning Robust Metrics for Visual Storytelling](https://doi.org/10.18653/v1/2022.findings-naacl.206) (2022)
- Task-specific:
  - CRITIC (character naming in audio description): [AutoAD III: The Prequel - Back to the Pixels](https://doi.org/10.1109/cvpr52733.2024.01720) (2024)
  - Character matching (visual storytelling): [Visual Coherence Loss for Coherent and Visually Grounded Story Generation](https://doi.org/10.18653/v1/2023.findings-acl.603) (2023)
- LLMs/VLMs as judges: [Wolf: Captioning Everything with a World Summarization Framework](https://arxiv.org/abs/2407.18908) (2024)
  - On their reliability: [LLMs instead of Human Judges? A Large Scale Empirical Study across 20 NLP Evaluation Tasks](https://arxiv.org/abs/2406.18403) (2024)

### Human evaluation
- Per-sample rating: [GROOViST: A Metric for Grounding Objects in Visual Storytelling](https://doi.org/10.18653/v1/2023.emnlp-main.202) (2023)
- Pairwise comparison: [RoViST: Learning Robust Metrics for Visual Storytelling](https://doi.org/10.18653/v1/2022.findings-naacl.206) (2022)
- Reliability of evaluation protocols: [Transparent Human Evaluation for Image Captioning](https://doi.org/10.18653/v1/2022.naacl-main.254) (2022); [Better than Random: Reliable NLG Human Evaluation with Constrained Active Sampling](https://doi.org/10.1609/aaai.v38i17.29857) (2024)

### Benchmarks
- Multi-image reasoning: ReMI: [ReMI: A Dataset for Reasoning with Multiple Images](https://openreview.net/forum?id=930e8v5ctj) (2024)
- Survey of MLLM benchmarks: [A Survey on Benchmarks of Multimodal Large Language Models](https://arxiv.org/abs/2408.08632) (2024)
- Visual content irrelevance and data leakage in benchmarks: [Are We on the Right Way for Evaluating Large Vision-Language Models?](https://openreview.net/forum?id=evP9mxNNxJ) (2024)

---

## Related surveys

**Task-specific**
- Image captioning: Stefanini et al., [From Show to Tell: A Survey on Deep Learning-Based Image Captioning](https://doi.org/10.1109/TPAMI.2022.3148210), TPAMI 2023.
- Video description: Aafaq et al., [Video Description: A Survey of Methods, Datasets, and Evaluation Metrics](https://doi.org/10.1145/3355390), ACM CSUR 2019.
- Video QA: Zhong et al., [Video Question Answering: Datasets, Algorithms and Challenges](https://doi.org/10.18653/v1/2022.emnlp-main.432), EMNLP 2022.
- Visual storytelling: Oliveira et al., [Story Generation from Visual Inputs: Techniques, Related Tasks, and Challenges](https://doi.org/10.3390/info16090812), Information 2025.
- Audio description: Gao et al., [Audio Description Generation in the Era of LLMs and VLMs: A Review of Transferable Generative AI Technologies](https://doi.org/10.18653/v1/2025.findings-naacl.29), Findings of NAACL 2025.
- Change captioning (remote sensing): Zou et al., [Remote Sensing Image Change Captioning: A Comprehensive Review](https://doi.org/10.1007/s13735-025-00375-7), IJMIR 2025.

**General VLMs and MLLMs**
- Zhang et al., [Vision-Language Models for Vision Tasks: A Survey](https://doi.org/10.1109/TPAMI.2024.3369699), TPAMI 2024.
- Yin et al., [A Survey on Multimodal Large Language Models](https://doi.org/10.1093/nsr/nwae403), National Science Review 2024.
- Tang et al., [Video Understanding with Large Language Models: A Survey](https://doi.org/10.1109/TCSVT.2025.3566695), IEEE TCSVT 2026.
- Li et al., [A Survey on Benchmarks of Multimodal Large Language Models](https://arxiv.org/abs/2408.08632) (2024)
- Wang et al., [Exploring the Reasoning Abilities of Multimodal Large Language Models (MLLMs): A Comprehensive Survey on Emerging Trends in Multimodal Reasoning](https://arxiv.org/abs/2401.06805) (2024)
- Suglia et al., [Visually Grounded Language Learning: a review of language games, datasets, tasks, and models](https://doi.org/10.1613/jair.1.15185) (2024)

---

## Citation

<!-- Update to the ACM Computing Surveys reference once published. -->
```bibtex
@article{surikuchi2025nlgvisualevents,
  title   = {Natural Language Generation from Visual Events: State-of-the-Art and Key Open Questions},
  author  = {Surikuchi, Aditya K and Fern{\'a}ndez, Raquel and Pezzelle, Sandro},
  journal = {arXiv preprint arXiv:2502.13034},
  year    = {2025}
}
```
