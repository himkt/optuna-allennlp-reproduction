### Experiments for reproducing results

This repo is for investigating the problem of reproducing results.
https://github.com/optuna/optuna/issues/1487


#### Run experiment on your environment

```
python3 -m venv venv
. ./venv/bin/activate

pip install -r ./requirements.txt
./run | tee log.new.txt
```


#### Results

I put the [running results](./log.txt).
In CPU experiment, the best result of Optuna and the result of retraining by `allennlp train` produce the same.
On the other hand, in GPU, the results are different.

- CPU results: https://github.com/himkt/optuna-allennlp-reproduction/blob/master/log.txt#L24-L56
  - same metrics
- GPU results: https://github.com/himkt/optuna-allennlp-reproduction/blob/master/log.txt#L70-L82
  - different metrics

This could be caused by the GPU non-deterministic computation.
https://github.com/allenai/allennlp/issues/387
