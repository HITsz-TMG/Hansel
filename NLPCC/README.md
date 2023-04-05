# NLPCC 2023 Shared Task 6: Chinese Few-shot and Zero-shot Entity Linking

## Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Citation](#citation)

## Overview

Hansel is a high-quality human-annotated Chinese entity linking (EL) dataset, aimed at testing Chinese EL systems' generalization ability to tail entities and emerging entities:
- The test set contains Few-shot (FS) and zero-shot (ZS) slices, has 10K examples and uses Wikidata as the corresponding knowledge base.
- The training and validation sets are from Wikipedia hyperlinks, useful for large-scale pretraining of Chinese EL systems.

## Dataset

The data is available [here](https://drive.google.com/drive/folders/1rpEyFWzoayUHBmxGitpWVOmf2MkZTsCt?usp=sharing). You can also download and use Hansel through  [the HuggingFace's datasets library :hugs:](https://huggingface.co/datasets/HIT-TMG/Hansel).

The knowledge base (i.e., Wikidata) we use in our experiments is available [here](https://drive.google.com/drive/folders/19u5L1eaG7fzRF1ujBsaof6wZjZdnFJSm?usp=sharing).

### Data Statistics

|     | # Mentions |  # Entities | Domain |
| ----  | ---- | ---- | ---- |
|  Train   | 9,879,813 | 541,058 | Wikipedia |
|  Validation   | 9,674 | 6,320  | Wikipedia |
|  Hansel-FS   | 5,260 | 2,720 | News, Social Media |
|  Hansel-ZS  | 4,715  | 4,046 | News, Social Media, E-books, etc.|


### Data Format

    {"id": "hansel-eval-zs-1463", 
     "text": "1905电影网讯 已经筹备了十余年的吉尔莫·德尔·托罗的《匹诺曹》，在上个月顺利被网飞公司买下，成为了流媒体巨头旗下的新片。近日，这部备受关注的影片确定了自己的档期：2021年。虽然具体时间未定，但影片却已经实实在在地向前迈出了一步。", 
     "start": 29, 
     "end": 32, 
     "mention": "匹诺曹", 
     "gold_id": "Q73895818", 
     "source": "https://www.1905.com/news/20181107/1325389.shtml", 
     "domain": "news"
    }
