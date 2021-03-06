# This repo has been forked from :
https://github.com/pandegroup/reaction_prediction_seq2seq

# Code for "Retrosynthetic reaction prediction using neural sequence-to-sequence models" paper
http://pubs.acs.org/doi/full/10.1021/acscentsci.7b00303

### This works only on TF 1.x versions.

## Model training
The data has already been preprocessed for training the seq2seq model

Model training can be started by running the google_seq2seq_train_jul_5_2017_1.sh script

Also, a pretrained model checkpoint can be found at: http://deepchem.io.s3-website-us-west-1.amazonaws.com/trained_models/jul_5_2017_1.tar.gz. Copy the folder into model_working_directory. Then from within the train_options.json file, modify the vocab_target and vocab_source flag to the path of "vocab" file in the processed data folder.

## Model inference
First in the train_options.json modify the vocab_target and vocab_source flag to the path of "vocab" file in the processed data folder.

Model inference can then be performed by running the Inferencing Cell in run_command notebook.
For usage of each script see original repo.

### Note- If you use the pretrained model for inferencing then make sure you are working on TF 1.0.1 GPU. Else it throws Key not found error.

## Model evaluation
The prediction can be evaluated using reaction_evaluation.ipynb in the evaluation folder. For the no beam search predictions, need to change pred_path to the relevant prediction file. For the beam search predictions, need to change beam_width and beam_path to the relevant beam widths used for each particular .npz beam prediction file. 

## Visualize Molecules

Refer post processing cell of run_command notebook.
The prediction file contains SMILES texts. New text files are created that can be directly used for drawing the structure. Molecules can be easily visualised using rdkit library in Python.

