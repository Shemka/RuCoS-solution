# RuCoS-solution
## Dataset description
Russian reading comprehension with Commonsense reasoning (RuCoS) is a large-scale reading comprehension dataset which requires commonsense reasoning. RuCoS consists of queries automatically generated from CNN/Daily Mail news articles; the answer to each query is a text span from a summarizing passage of the corresponding news. The goal of RuCoS is to evaluate a machine's ability of commonsense reasoning in reading comprehension.
## Approach description
First of all, all possible queries with replaced @placeholder must created, so we can classify if it is right replacement. I used DeepPavlov RuBERT, so input must be constructed as [CLS] context_tokens [SEP] query_tokens [SEP]. Then BERT were finetuned with AdamW, linear scheduler with 10% warmup and 2e-5 learning rate over 3 epochs. Then the most probable words for certain queries were chosen. This approach gave me **0.8447 F1**.
