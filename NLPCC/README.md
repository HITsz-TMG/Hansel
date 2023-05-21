# [NLPCC 2023 Shared Task 6: Chinese Few-shot and Zero-shot Entity Linking](http://tcci.ccf.org.cn/conference/2023/cfpt.php)

Entity Linking (EL) is the task of grounding a textual mention in context to a corresponding entity in a knowledge base (KB).
However, current EL systems demonstrate a popularity bias, significantly underperforming on **tail and emerging entities**. 

To this end, this task aims at testing the generalization ability of Chinese EL systems to **less popular and newly emerging entities**.
The dataset for this task is **Hansel**, a high-quality human-calibrated and multi-domain Chinese EL benchmark:
- The test set for NLPCC 2023 is a mixture of few-shot and zero-shot slices, together with some adversarial examples. The test set has 8K examples and uses Wikidata as the corresponding knowledge base.
- The training and validation sets are from Wikipedia hyperlinks, useful for large-scale pretraining of Chinese EL systems.

Please refer to our paper "[Hansel: A Chinese Few-Shot and Zero-Shot Entity Linking Benchmark](https://dl.acm.org/doi/10.1145/3539597.3570418)" to learn more about our dataset.
If there are any differences between the paper and this page, the content of this page should prevail.


## Important Dates
- **April 6, 2023**: Training data is available at [link](https://drive.google.com/drive/folders/1XdRLHDreTUGX4_BU9fFRiG_6dOBreJMl?usp=sharing).
- **May 5, 2023**: Registration deadline. The registration information is recorded at link, please check if your information is recorded correctly and contact us if any problems occur.
- **May 21, 2023**: Test data is available at [link](https://github.com/HITsz-TMG/Hansel/blob/main/NLPCC/hansel-nlpcc-eval.jsonl).
- **May 31, 2023**: Results submission deadline.

## How to participate
Please fill out the Shared Task 6 Registration Form ([Word File](http://tcci.ccf.org.cn/conference/2023/dldoc/NLPCC2023.SharedTask6.RegistrationForm.doc)) and send it to the following registration email: [xuzhenran@stu.hit.edu.cn](mailto:xuzhenran@stu.hit.edu.cn).

## Data

### Data Splits

- The training data for NLPCC 2023 is available [here](https://drive.google.com/drive/folders/1XdRLHDreTUGX4_BU9fFRiG_6dOBreJMl?usp=sharing), and also available in [the HuggingFace's datasets library :hugs:](https://huggingface.co/datasets/HIT-TMG/Hansel). The training data is derived from Wikipedia hyperlinks, and we hold out 1K full documents (9.7K mentions) as the validation set.
- The test data for NLPCC 2023 is available [here](https://github.com/HITsz-TMG/Hansel/blob/main/NLPCC/hansel-nlpcc-eval.jsonl), consisting of a few-shot slice, a zero-shot slice and some adversarial examples for both slices.

**More resources**:
We also release the knowledge base (i.e., Wikidata) and the alias table we use in our paper [here](https://drive.google.com/drive/folders/19u5L1eaG7fzRF1ujBsaof6wZjZdnFJSm?usp=sharing).

### Statistics

|     | # Mentions |  # Entities | Domain |
| ----  | ---- | ---- | ---- |
|  Train   | 9,879,813 | 541,058 | Wikipedia |
|  Validation   | 9,674 | 6,320  | Wikipedia |
|  Test     |  8,000 | - |   News, Social Media, E-books, etc.   |


### Data Format
The training data is in the following format. You can get a preview of it [here](https://huggingface.co/datasets/HIT-TMG/Hansel/viewer/wiki/train).

    {"id": "hansel-train-89", 
     "text": "丹尼尔·马克·内斯特（Daniel Mark Nestor，），原名达尼耶尔·内斯托罗维奇（塞尔维亚语：），出生于塞尔维亚贝尔格莱德，加拿大职业网球运动员，最高ATP男单排名第58位及男双世界排名第1位，曾获澳大利亚网球公开赛男子双打（2002年）、美国网球公开赛男子双打（2004年）、法国网球公开赛男子双打（2007年）、温布顿网球公开赛男子双打（2008年）及2000年悉尼奥运会男子双打冠军等等。", 
     "start": 104, 
     "end": 113, 
     "mention": "澳大利亚网球公开赛", 
     "gold_id": "Q60874"
    }

Every example in the evaluation data is in the following format.

    {"id": "hansel-nlpcc-8000", 
     "text": "1905电影网讯 已经筹备了十余年的吉尔莫·德尔·托罗的《匹诺曹》，在上个月顺利被网飞公司买下，成为了流媒体巨头旗下的新片。近日，这部备受关注的影片确定了自己的档期：2021年。虽然具体时间未定，但影片却已经实实在在地向前迈出了一步。", 
     "start": 29, 
     "end": 32, 
     "mention": "匹诺曹", 
     "gold_id": "", 
     "source": "https://www.1905.com/news/20181107/1325389.shtml", 
     "domain": "news"
    }

Your task is to fill in the `gold_id` field with the corresponding Wikidata QID as demonstrated below. Note that all examples are linkable, and all of the corresponding entities are among the 110,6489 entities in [our KB]((https://drive.google.com/drive/folders/19u5L1eaG7fzRF1ujBsaof6wZjZdnFJSm?usp=sharing)).

    {"id": "hansel-nlpcc-8000", 
     "text": "1905电影网讯 已经筹备了十余年的吉尔莫·德尔·托罗的《匹诺曹》，在上个月顺利被网飞公司买下，成为了流媒体巨头旗下的新片。近日，这部备受关注的影片确定了自己的档期：2021年。虽然具体时间未定，但影片却已经实实在在地向前迈出了一步。", 
     "start": 29, 
     "end": 32, 
     "mention": "匹诺曹", 
     "gold_id": "Q73895818", 
     "source": "https://www.1905.com/news/20181107/1325389.shtml", 
     "domain": "news"
    }
  
### Evaluation
Evaluation metric: **Accuracy** on the test set.

### Submission
**Time**: We will only evaluate the **latest** submission by following timeslots and update the leaderboard coordinately.
- May 23, 23:59
- May 25, 23:59
- May 27, 23:59
- May 29, 23:59
- **Final submission**: May 31, 23:59

**Time**: Please submit your result to [link](https://forms.gle/QPnW81doq6HJzK9N7).


## Contact

If you have any questions about this task, feel free to email me at [xuzhenran@stu.hit.edu.cn](mailto:xuzhenran@stu.hit.edu.cn).

