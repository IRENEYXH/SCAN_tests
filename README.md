# SCAN_tests

The original work is from Sentence Constituent-Aware Aspect-Category Sentiment Analysis with Graph Attention Networks (NLPCC 2020) (arxiv.org/abs/2010.01461) and original code in (https://github.com/l294265421/SCAN). Here we are trying to reproduce the results, do some additional tests and compare to other LSTM based models.

## How to start training
### Get orginal_data folder from original SCAN repo
https://github.com/l294265421/SCAN

### Get additional required files:
glove.840B.300d.txt(http://nlp.stanford.edu/data/wordvecs/glove.840B.300d.zip)

bert-base-uncased.tar.gz(https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-uncased.tar.gz) 

vocab.txt(https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-uncased-vocab.txt) 

### Setup conda environment

spec in environment.yml

### Run this command in root dir:
python acd_and_sc_bootstrap_pytorch_sentence_constituency.py --embedding_filepath glove.840B.300d.txt --data_type constituency --current_dataset SemEval-2014-Task-4-REST-DevSplits --joint_type joint --attention_warmup_init False --acd_sc_encoder_mode same --acd_encoder_mode mixed --bert False --pair False --lstm_or_fc_after_embedding_layer lstm --aspect_graph gat --sentiment_graph gat --batch_size 32 --train True --evaluate False
