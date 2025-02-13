# Recurrent Neural Net Ensembles for Complex Word Identification (SemEval-2016)

```bash
# Install passage for easy NN manipulation
# See https://github.com/IndicoDataSolutions/Passage
sudo pip install passage

# Train your model, e.g.
# $ python train.py cwi_input cwi_labels <embedding size> <size of gated recurrent layer> <no. of epochs>
python train.py cwi_inputs.txt cwi_labels.txt 10 10 10
# And two files will appear; (i) the RNN model, (ii) the tokenizer learnt from the training data.
ls stubborn_model.gridsearch.embedding100.gru10.epoch10.pkl
ls cwi_inputs.txt-tokenizer.pkl

# Best parameters (from our experiments: 
# (<embedding size>, <size of gated recurrent layer>, <no. of epochs>)
# [(10,10,10), (10,50,10), (50,200,10), (100,10,10), (200,20,10)]

# If you would like to do some parameter search, see paramsearch.py
nohup paramsearch.py cwi_input.txt cwi_labels.txt > paramsearch.log &

# Predict from the test data.
python stubborn_test.py cwi_test.txt stubborn_model.gridsearch.embedding10.gru10.epoch10.pkl cwi_test.txt-tokenizer.pkl 
```

Cite
====

Nat Gillin. 2016. Neural Nonsense Mangled in Ensemble Mess. In SemEval-2016. (forthcoming)

```

```
