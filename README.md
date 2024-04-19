# RRAF
This work proposes an effective Visual Object Relationship Reasoning and Adaptive Fusion (RRAF) model to address the shortcomings of existing VQA model research. The model can simultaneously model visual objects’ position, appearance, and semantic features and uses an adaptive fusion mechanism to achieve fine-grained multi-modal reasoning and fusion.
![image](https://user-images.githubusercontent.com/108173532/226158210-f4e98c44-6066-47bf-a5d7-56b762a6c642.png)
# Note*
After the paper is accepted, the code will be released in time.

## Validation and Testing

**Warning**: If you train the model use ```--MODEL``` args or multi-gpu training, it should be also set in evaluation.


#### Offline Evaluation

Offline evaluation only support the VQA 2.0 *val* split. If you want to evaluate on the VQA 2.0 *test-dev* or *test-std* split, please see [Online Evaluation](#Online-Evaluation).

There are two ways to start:

(Recommend)

```bash
$ python3 run.py --RUN='val' --CKPT_V=str --CKPT_E=int --MODEL=rraf --DATASET=vqa/gqa
```

or use the absolute path instead:

```bash
$ python3 run.py --RUN='val' --CKPT_PATH=str
```


#### Online Evaluation

The evaluations of both the VQA 2.0 and GQA *test-dev* /*test-std* splits are run as follows:

```bash
$ python3 run.py --RUN='test' --CKPT_V=str --CKPT_E=int --MODEL=rraf --DATASET=vqa/gqa
```

Result files are stored in ```results/result_test/result_run_<'PATH+random number' or 'VERSION+EPOCH'>.json```

VQA 2.0: You can upload the obtained result json file to [Eval AI](https://eval.ai/web/challenges/challenge-page/830/overview) to evaluate the scores on *test-dev* and *test-std* splits.


GQA :You can upload the obtained result json file to [Eval AI](https://eval.ai/web/challenges/challenge-page/225/overview) to evaluate the scores on *test-dev* and *test-std* splits.



## Citation
if RRAF is helpful for your research or you wish to refer the baseline results published here, we'd really appreciate it if you could cite this paper:
```
@article{shen2024relational,
  title={Relational reasoning and adaptive fusion for visual question answering},
  author={Shen, Xiang and Han, Dezhi and Zong, Liang and Guo, Zihan and Hua, Jie},
  journal={Applied Intelligence},
  pages={1--19},
  year={2024},
  publisher={Springer}
}
```
