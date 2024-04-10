# Homework

## Sambanova

*For BERT example, understand flags used in the script. Change values for flag `--ntasks` and measure its effect on performance.* 

The bert example was run with `--ntasks` = 8, `--ntasks` = 16 (original case),  and `--ntasks` = 32. In the last case, the parameter `--nodes` was 2. In all cases, the compilation stage was good but there were run errors due to the throughput values outside the threshold min and max value range for the default config.
Below are the links to the log files:
* [Compilation log file](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/BertLarge_Compile.out)
* [Execution log file for `--ntasks` = 8](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/BertLarge_Run_ntasks08.out)
* [Execution log file for `--ntasks` = 16](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/BertLarge_Run_ntasks16.out)
* [Execution log file for `--ntasks` = 32](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/BertLarge_Run_ntasks32.out)

## Graphcore

*Run MNIST example by changing values of the input parameters like batch-size, learning rate and number of epochs trained and observe and report the performance implications.* 

The MNIST example was run 4 times with the following values of learning rate: 0.0005, 0.005, 0.05 (original case), and 0.5. The accuracy on the test set is shown below:

learning rate	accuracy on test set	comments
0.0005			93.08%					learning rate is too small, needs more epochs to get a good accuracy
0.005			98.44%					good
0.05			98.58%					original case, good
0.5				9.58%					learning rate is too large, the solution may be overfitted or unstable/diverge 

* [Log file](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/Graphcore.txt)

## Cerebras

*Run BERT example with different batch sizes like 512, 2048 and observe the performance difference.*  

The BERT example was run 3 times with the batch sizes 512, 1024, and 2048. The run time increases with the batch size increasing as shown below:

batch size		run time, s
512				176
1024			211
2048			305

* [Log file](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/Cerebras.txt)

## Groq

*Run BERT example with custom input instead of dummy input.* 

The custom input has been implemented in the bert_tiny.py file. The input size has also been changed from 128 to 256.

* [Log file](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/Groq.txt)
* [Modified bert_tiny.py file](https://github.com/akozlov0/ai-science-training-series/blob/main/07_AITestbeds/bert_tiny.py)
