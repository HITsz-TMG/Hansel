# [NLPCC 2023 Shared Task 6: Chinese Few-shot and Zero-shot Entity Linking](http://tcci.ccf.org.cn/conference/2023/cfpt.php)

Entity Linking (EL) is the task of grounding a textual mention in context to a corresponding entity in a knowledge base (KB).
However, current EL systems demonstrate a popularity bias, significantly underperforming on **tail and emerging entities**. 

To this end, this task aims at testing the generalization ability of Chinese EL systems to less popular and newly emerging entities.
The dataset for this task is Hansel, a high-quality human-calibrated and multi-domain Chinese EL benchmark:
- The test set for NLPCC 2023 is a mixture of Few-shot (FS) and zero-shot (ZS) slices, has 10K examples and uses Wikidata as the corresponding knowledge base.
- The training and validation sets are from Wikipedia hyperlinks, useful for large-scale pretraining of Chinese EL systems.

For more information related to this dataset, please refer to our paper: [Hansel: A Chinese Few-Shot and Zero-Shot Entity Linking Benchmark](https://dl.acm.org/doi/10.1145/3539597.3570418). 
If there are any differences between the paper and this page, the content of this page should prevail.


## Training Data

The training data for NLPCC 2023 is available [here](https://drive.google.com/drive/folders/1XdRLHDreTUGX4_BU9fFRiG_6dOBreJMl?usp=sharing). You can also download and use Hansel's training data through  [the HuggingFace's datasets library :hugs:](https://huggingface.co/datasets/HIT-TMG/Hansel).

The knowledge base (i.e., Wikidata) we use in our experiments is available [here](https://drive.google.com/drive/folders/19u5L1eaG7fzRF1ujBsaof6wZjZdnFJSm?usp=sharing).

### Data Statistics

|     | # Mentions |  # Entities | Domain |
| ----  | ---- | ---- | ---- |
|  Train   | 9,879,813 | 541,058 | Wikipedia |
|  Validation   | 9,674 | 6,320  | Wikipedia |


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
