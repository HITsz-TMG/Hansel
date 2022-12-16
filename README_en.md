
[**中文说明**](https://github.com/HITsz-TMG/Hansel) | [**English**](https://github.com/HITsz-TMG/Hansel/blob/main/README_en.md)


# Hansel: A Chinese Few-Shot and Zero-Shot Entity Linking Benchmark

This is the main page of our paper [**Hansel**](https://arxiv.org/abs/2207.13005).

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* **Updates** \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

- 19/09/2022: Our paper is accepted to [WSDM 2023](https://www.wsdm-conference.org/2023/)!
- 27/07/2022: We release the test set of Hansel, consisting of Hansel-FS and Hansel-ZS. More training data, knowledge base and baselines are to come!

## Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Citation](#citation)

## Overview

Hansel is a high-quality human-annotated Chinese entity linking dataset, focusing on tail entities and emerging entities. 
The test set has 10K examples and uses Wikidata as the corresponding knowledge base.

## Dataset

The data is available [here](https://drive.google.com/file/d/1n8nID5WWnZdDK9307-Imj43GuHJkRfpA/view).

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

## Citation

If you use our dataset in your work, please cite us.

```bibtex
@misc{xu2022hansel,
  title = {Hansel: A Chinese Few-Shot and Zero-Shot Entity Linking Benchmark},
  author = {Xu, Zhenran and Shan, Zifei and Li, Yuxin and Hu, Baotian and Qin, Bing},
  publisher = {arXiv},
  year = {2022},
  url = {https://arxiv.org/abs/2207.13005}
}
```

## License

Hansel dataset is licensed under the Creative Commons Attribution-Share Alike License (CC-BY-SA).
