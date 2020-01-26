# This repo has been forked from :
https://github.com/pandegroup/reaction_prediction_seq2seq

# Code for "Retrosynthetic reaction prediction using neural sequence-to-sequence models" paper
http://pubs.acs.org/doi/full/10.1021/acscentsci.7b00303



## Model training
The data has already been preprocessed for training the seq2seq model

Model training can be started by running the google_seq2seq_train_jul_5_2017_1.sh script

Also, a pretrained model checkpoint can be found at: http://deepchem.io.s3-website-us-west-1.amazonaws.com/trained_models/jul_5_2017_1.tar.gz. Copy the folder into model_working_directory. Then from within the train_options.json file, modify the vocab_target and vocab_source flag to the actual vocab path in the processed data folder

## Model inference
Model inference can be performed by running the Inferencing Cell in run_command notebook.
For usage of each script see original repo.

## Model evaluation
The prediction can be evaluated using reaction_evaluation.ipynb in the evaluation folder. For the no beam search predictions, need to change pred_path to the relevant prediction file. For the beam search predictions, need to change beam_width and beam_path to the relevant beam widths used for each particular .npz beam prediction file. 

## Visualise Molecules

Refer post processing cell of run_command notebook.
The prediction file contains SMILES texts. So we do some post processing to visualise the molecules using rdkit.

## TO-DO
- [x] Understand dataset and conversion from smiles
- [ ] Understand seq2seq model working
- [ ] Perform Inference on all scripts
- [ ] Do Evaluation

