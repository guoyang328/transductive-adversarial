# Play with the code from https://papers.nips.cc/paper/2020/hash/b6c8cf4c587f2ead0c08955ee6e2502b-Abstract.html

# PQ Learning

The file Appendix.pdf contains proofs of the theorems in the body.

Below are instructions to reproduce experiments in our submission.

## Installation and usage

Requirements: PyTorch v1.0 or higher, Scikit-Learn, and emnist dataset package, which can be installed with:

```
pip install emnist
```

## Running Random Forest Experiments

The random forest experiments are in the file Random Forest Experiments.ipynb. 
Simply run the notebook to download the data and recreate the experiments.

## Running Neural Network Experiments

Choose either Q=EMNIST-Mix, or Q=EMNIST-Adv. 

To train a classifer:
```
python train.py --resume --task classifier --dataset EMNIST-Mix --arch MnistNet --epochs 85 --num_classes 8
```

To train a distinguisher:
```
python train.py --resume --task distinguisher --dataset EMNIST-Mix --arch MnistNet --epochs 85 --num_classes 8
```

To generate tradeoff plots: 
```
python evaluate.py --epochs 85 --dataset EMNIST-Mix --num_classes 8 --arch MnistNet
```

## Acknowledgement
This code builds on the code provided in the following repositories:
https://github.com/yaodongyu/TRADES
https://github.com/pytorch/examples/blob/master/mnist/main.py
