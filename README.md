### Experiments for reproducing results

This repo is for investigating the problem of reproducing results.
https://github.com/optuna/optuna/issues/1487


#### Run experiment

```
python3 -m venv venv
. ./venv/bin/activate

pip install -r ./requirements.txt
./run
```


#### Results

I put the [running results](./log.txt).
In CPU experiment, the best result of Optuna and the result of retraining by `allennlp train` produce the same.
On the other hand, in GPU, the results are different.

This could be caused by the GPU non-deterministic computation.
https://github.com/allenai/allennlp/issues/387
