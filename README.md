# Flood Detection Challenge

This repository contains code for the [ETCI 2021 Competition on Flood Detection](https://competitions.codalab.org/competitions/30440) submission. 

## Executing the code

We executed the scripts and notebooks on a [Vertex AI](https://cloud.google.com/vertex-ai) Notebook instance. The instance has four
Tesla V100 GPUs and its base configuration is [`n1-standard-16`](https://cloud.google.com/compute/docs/machine-types).

We use Python 3.8 and PyTorch 1.9. Apart from the requirements specified in `requirements.txt` you'd need to install the following
as well to run the scripts and notebooks:

```shell
$ pip install git+https://github.com/qubvel/segmentation_models.pytorch
$ pip install git+https://github.com/lucasb-eyer/pydensecrf.git
```

Our scripts and notebooks make use of mixed-precision training (via [`torch.cuda.amp`](https://pytorch.org/docs/stable/notes/amp_examples.html)) and distributed training (via [`torch.nn.parallelDistributedDataParallel`](https://pytorch.org/docs/stable/generated/torch.nn.parallel.DistributedDataParallel.html)). With this combination we are able to achieve significant boosts in the overall model training time.

**Execution instructions for the scripts (`src`) and notebooks (`notebooks`) are provided in their respective directories.** 

## FAQ

- [Create a new Notebooks instance](https://cloud.google.com/notebooks/docs/create-new)

## Acknowledgements

* We are grateful to the [ML-GDE program](https://developers.google.com/programs/experts/) for providing GCP credits to support our experiments. 
* Thanks to [Charmi Chokshi](https://in.linkedin.com/in/charmichokshi) for insightful discussions.
