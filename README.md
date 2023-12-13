# regional_bias draft
sentiment140:
* Data preparation (tag country code): "sentiment140/geo_info_tagging/"
    .profile_geo_extraction.ipynb is the code for extracting location data from user file of twitter
    .geo_tagging.ipynb is the code for getting country code from the location information extracted from profile_geo_extraction.ipynb
    . The input data: sentiment140 dataset can be downloaded from https://www.tensorflow.org/datasets/catalog/sentiment140
    . The final outputs of geo_tagging.ipynb are countryInfo0-50k.csv and countryInfo50k-100k.csv
  Data preparation (data split): to save the time of searching for regional data each time for running, we split the output results into files by regions:
    .data_splitting.ipynb is the code for file splitting
    . The output of file splitting is in the folder "sentiment140/"

  *Model training:
    . training_cv25.ipynb is the code for fine-tuning BERT model with sentiment140 data(train set); The trained models can be downloaded from 10.17608/k6.auckland.24796683

  *Performance reuslts: To save the computation cost of embedding the documents, a sample of 1000 for US and UK is drawn for evaluation calculation, we repeat the sampling for 30 times.
    . performance results.ipynb: the code generating performance evaluation results (accuracy, AUC, precision and recall) for each round of sampling; results are in the corresponding folders in sentiment140/performance_results  
    . performance-results-summary.ipynb: calculate the mean values of performance evaluation (30 rounds of sampling), and the distance correlation results of performance variation from 25 model results.
    The mean value results and the distance correlation results can be found in the output cells in the notebook "performance-results-summary.ipynb".

  *BERT embedding results:
    .bert-embedding-sentiment140 is the code for obtaining bert embedding distance results in the EMBEDDING stream.
    .The results can be found in the folder sentiment140/bert_embedding results: with mean value and the individual value from the 100 sampling process.
  
  *LDA results:
    . LDA-sentiment140.ipynb is the code for getting the embedding distance results in the LDA stream.
    . The results can be found in  sentiment140/lda_results
  
All the results are summarized in "results_gathering.csv"

Reuters21578-multilcass_labelling:
  *Data preparation
      .code: reuters-text-apte.ipynb; results: Reuters21578-multiclass/test_sets_docbert
  
  *training:
      .code: docbert-training.ipynb - needs to git-clone docbert environment first from "https://github.com/castorini/hedwig"
      trained model can be downloaded from: 10.17608/k6.auckland.24796740
    
  *performance results: outputcell in docbert-training.ipynb, summarized in "reuters_results.csv"
  *embedding results:
  code: reuters-bert-embedings.ipynb
  results: in folder "Reuters21578-multiclass/reuters_bert_embedding"
  
  All the results are summarized in "reuters_results_gathering.csv"
  
  
  
