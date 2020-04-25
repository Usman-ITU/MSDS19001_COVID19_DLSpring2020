<center>
    <h1>
        Assignment 5
    </h1>
    <h4>
        Usman Anwar - MSDS19001
    </h4>
</center>

In all experiments, early stopping was used as a regularization technique to prevent overfitting to train data.

## VGG-16

### Task 1

**Experiment Settings**

Last FC layer was removed, all conv layers weights were freezed and retraining was done for 10 epochs using batch size 8 and SGD optimizer with momentum of 0.9 and learning rate 0.001.

**Training Plots**

![image-20200424210625724](/home/usman/.config/Typora/typora-user-images/image-20200424210625724.png)

![image-20200424210607589](/home/usman/.config/Typora/typora-user-images/image-20200424210607589.png)

**Final Test Accuracy**

$92.96$

**F1 Score On Test Set**

$0.9405$

**Confusion Matrix**

```bash
Train:
[[ 911  205]
 [  54 1030]]

Validation:
[[506 109]
 [ 87 798]]

Test:
[[531  84]
 [ 16 791]]
```

**Well Classified Images**

![image-20200424210755129](/home/usman/.config/Typora/typora-user-images/image-20200424210755129.png)

**Badly Classified Images**

![image-20200424210821044](/home/usman/.config/Typora/typora-user-images/image-20200424210821044.png)

### Task 2(a)

FC Layer + last conv layer were retrained with lr=0.001 with Adam optimizer, batch size 8 for 10 epochs. 

**Training Plots**

![image-20200424221838114](/home/usman/.config/Typora/typora-user-images/image-20200424221838114.png)

![image-20200424221910243](/home/usman/.config/Typora/typora-user-images/image-20200424221910243.png)

**Final Test Accuracy**

$94.79$

**F1 Score On Test Set**

$0.9547$

**Confusion Matrix**

```bash
Train:
[[1024   92]
 [  50 1034]]

Validation:
[[536  79]
 [ 84 801]]

Test:
[[568  47]
 [ 27 780]]
```

**Well Classified Images**

![image-20200424223727479](/home/usman/.config/Typora/typora-user-images/image-20200424223727479.png)

**Badly Classified Images**

![image-20200424223753481](/home/usman/.config/Typora/typora-user-images/image-20200424223753481.png)

### Task 2(b)

Whole network was retrained with Adam optimizer, lr=0.001. batch size 8 for 10 epochs. 

**Training Plots**

![image-20200425001605794](/home/usman/.config/Typora/typora-user-images/image-20200425001605794.png)

![image-20200425001628858](/home/usman/.config/Typora/typora-user-images/image-20200425001628858.png)

**Final Test Accuracy**

$96.48$

**F1 Score On Test Set**

$0.9695$

**Confusion Matrix**

```bash
Train:
[[1024   92]
 [  22 1062]]

Validation:
[[532  83]
 [ 58 827]]

Test:
[[576  39]
 [ 11 796]]
```

**Well Classified Images**

![image-20200425002604175](/home/usman/.config/Typora/typora-user-images/image-20200425002604175.png)

**Badly Classified Images**

![image-20200425002625676](/home/usman/.config/Typora/typora-user-images/image-20200425002625676.png)

## ResNet 18

### Task 1

Last layer was retrained with Adam optimizer, lr=0.001, batch size 8 for 10 epochs.

**Training Plots**

![image-20200424064956334](/home/usman/.config/Typora/typora-user-images/image-20200424064956334.png)

![image-20200424065018906](/home/usman/.config/Typora/typora-user-images/image-20200424065018906.png)

**Final Test Accuracy**

$91.42%$

**F1 Score On Test Set**

$0.9246$

**Confusion Matrix**

```bash
Train:
[[946 170]
 [ 94 990]]
 
Validation:
[521  94]
 [126 759]]
 
Test:
[[551  64]
 [ 58 749]]
```

**Well Classified Images**

![image-20200424120011128](/home/usman/.config/Typora/typora-user-images/image-20200424120011128.png)

**Badly Classified Images**

![image-20200424185500706](/home/usman/.config/Typora/typora-user-images/image-20200424185500706.png)

### Task 2(a)

Last layer + last convolutional block were retrained with Adam optimizer, lr=0.001, batch size 8 for 21 epochs. This network was initialized with wieghts from previous task. 

**Training Plots**

![image-20200424135654111](/home/usman/.config/Typora/typora-user-images/image-20200424135654111.png)

![image-20200424135720269](/home/usman/.config/Typora/typora-user-images/image-20200424135720269.png)

**Final Test Accuracy**

$94.72$

**F1 Score On Test Set**

$0.954$

**Confusion Matrix**

```bash
Train:
[[1028   88]
 [  21 1063]]

Validation:
[[522  93]
 [ 85 800]]

Test:
[[557  58]
 [ 17 790]]

```

**Well Classified Images**

![image-20200424135852022](/home/usman/.config/Typora/typora-user-images/image-20200424135852022.png)

**Badly Classified Images**

![image-20200424185409496](/home/usman/.config/Typora/typora-user-images/image-20200424185409496.png)

### Task 2(b)

Whole network was retrained for about 10 epochs with initialization from previous tasks. Adam optimizer was used.

**Training Plots**

![image-20200424183802636](/home/usman/.config/Typora/typora-user-images/image-20200424183802636.png)

![image-20200424183832785](/home/usman/.config/Typora/typora-user-images/image-20200424183832785.png)

**Final Test Accuracy**

$94.86$

**F1 Score On Test Set**

$0.9566$

**Confusion Matrix**

```bash
Train:
[[ 967  149]
 [  45 1039]]

Validation:
[[526  89]
 [ 74 811]]

Test:
[[564  51]
 [ 22 785]]

```

**Well Classified Images**

![image-20200424185115665](/home/usman/.config/Typora/typora-user-images/image-20200424185115665.png)

**Badly Classified Images**

![image-20200424185244197](/home/usman/.config/Typora/typora-user-images/image-20200424185244197.png)

## Analysis

Following table lists test accuracy. 

| Training Extent                  | VGG     | ResNet  |
| -------------------------------- | ------- | ------- |
| FC Layer                         | $92.96$ | $91.42$ |
| FC Layer + Last Conv Layer/Block | $94.79$ | $94.72$ |
| Whole Network                    | $96.48$ | $94.86$ |

1. For both VGG and ResNet whole network retraining achieved highest test accuracy; and retraining only FC layer achieved >90% accuracy but greater training extent improved on this accuracy. This is presumably because ImageNet is a dataset of natural images, however, medical images are not natural images, hence, allowing the network to adjust for this change gives best performance.
2. Further, as an experiment, for VGG all three times network was initialized from imageNet weights and for ResNet we used weights from previous layers. However, we did not observe any discernable effects and training of both networks largely progressed in the same way.
3. From confusion matrix, it can be seen that network is more likely to predict infected for normal image than vice versa. This is useful in medical settings where we want to be conservative.