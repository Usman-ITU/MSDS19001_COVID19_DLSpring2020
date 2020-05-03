<center>
    <h1>
        Assignment 5 Part b
    </h1>
    <h4>
        Usman Anwar - MSDS19001
    </h4>
</center>
# Dataset

Dataset can be found [here](https://drive.google.com/file/d/1eytbwaLQBv12psV8I-aMkIli9N3bf8nO/view?usp=sharing).

# Weights 

Weights for the final models trained and used can be found [here](https://drive.google.com/open?id=12fK4viRlA4aHFfSn1egExf3UQxyUK-GA).

# Experiment Details

Final model used: Resnet with BCE with class balancing with SGD optimizer trained for 10 epochs with lr=0.001

Github link:  https://github.com/Usman-ITU/MSDS19001_COVID19_DLSpring2020

## VGG-16

In all experiments, we finetune pretained VGG net end to end by using SGD with momentum of 0.9. (We explictly mention when we change the optimizer). lr=0.001 and batch size of 8.

### Binary Cross Entropy Loss

**(a) With Class Balancing**

**Training Plots**

![image-20200503042413567](/home/usman/.config/Typora/typora-user-images/image-20200503042413567.png)

**Testing Stats**

```bash
*************** Training Data ***************
Accuracy  [0.985, 0.9414516129032258, 0.9412903225806452]
Recall  [0.7452  0.9965 0.84  ]
Precision  [0.998      0.84136364 0.997     ]
Jaccard Score  0.9367741935483871
Confusion Matrix  

[[[5988   12]
  [  81  119]]

 [[1851  349]
  [  14 3986]]

 [[3988   12]
  [ 352 1848]]]
*************** Validation Data ***************
Accuracy  [0.9745222929936306, 0.9378980891719745, 0.9378980891719745]
Recall  [0.0.7234 0.995      0.8377193 ]
Precision  [1.        0.8377193 0.995    ]
Jaccard Score  0.9347133757961783
Confusion Matrix  [[[600   0]
  [ 16  12]]

 [[191  37]
  [  2 398]]

 [[398   2]
  [ 37 191]]]

```

**(b) Without Class Balancing**

SGD was used with momentum 0.9 and lr=0.001

![image-20200503203330305](/home/usman/.config/Typora/typora-user-images/image-20200503203330305.png)

**Testing Stats**

```bash
*************** Training Data ***************
Accuracy  [0.985, 0.9414516129032258, 0.9412903225806452]
Recall  [0.595  0.9965 0.84  ]
Precision  [0.998      0.84136364 0.997     ]
Jaccard Score  0.9367741935483871
Confusion Matrix  

[[[5988   12]
  [  81  119]]

 [[1851  349]
  [  14 3986]]

 [[3988   12]
  [ 352 1848]]]
*************** Validation Data ***************
Accuracy  [0.9745222929936306, 0.9378980891719745, 0.9378980891719745]
Recall  [0.42857143 0.995      0.8377193 ]
Precision  [1.        0.8377193 0.995    ]
Jaccard Score  0.9347133757961783
Confusion Matrix  [[[600   0]
  [ 16  12]]

 [[191  37]
  [  2 398]]

 [[398   2]
  [ 37 191]]]

```



### With Focal Loss

**(a) Without Class Balancing**

Adam optimizer with batch size of 8 and lr=0.001

**Training Plots**

![image-20200503183953955](/home/usman/.config/Typora/typora-user-images/image-20200503183953955.png)

**Testing Stats**

```bash
*************** Training Data ***************
Accuracy  [0.967741935483871, 0.6451612903225806, 0.6451612903225806]
Recall  [0. 1. 0.]
Precision  [1. 0. 1.]
F1  0.0
Jaccard Score  0.6451612903225806
Confusion Matrix  [[[6000    0]
  [ 200    0]]

 [[   0 2200]
  [   0 4000]]

 [[4000    0]
  [2200    0]]]
  
*************** Validation Data ***************
Accuracy  [0.9554140127388535, 0.6369426751592356, 0.6369426751592356]
Recall  [0. 1. 0.]
Precision  [1. 0. 1.]

F1  0.0
Jaccard Score  0.6369426751592356

Confusion Matrix  
[[[600   0]
  [ 28   0]]

 [[  0 228]
  [  0 400]]

 [[400   0]
  [228   0]]]

```

## ResNet 18

### BCE Loss

**(a) With Class Balancing**

Last layer was retrained with Adam optimizer, lr=0.001, batch size 8 for 10 epochs.

**Training Plots**

![image-20200503014934945](/home/usman/.config/Typora/typora-user-images/image-20200503014934945.png)

**Testing Stats**

```bash
*************** Training Data ***************
Accuracy  [0.9722580645161291, 0.9393548387096774, 0.9406451612903226]
Recall  [0.97       0.9455     0.92181818]
Precision  [0.97233333 0.92818182 0.951     ]
Jaccard Score  0.9238978494623655
Confusion Matrix  [[[5834  166]
  [   6  194]]

 [[2042  158]
  [ 218 3782]]

 [[3804  196]
  [ 172 2028]]]

*************** Validation Data ***************
Accuracy  [0.9725806451612903, 0.9425806451612904, 0.9440322580645162]
Recall  [0.97       0.95125    0.92272727]
Precision  [0.97266667 0.92681818 0.95575   ]
Jaccard Score  0.9279301075268817
Confusion Matrix  [[[5836  164]
  [   6  194]]

 [[2039  161]
  [ 195 3805]]

 [[3823  177]
  [ 170 2030]]]

```

**(b) Without Class Balancing**

![image-20200503032335725](/home/usman/.config/Typora/typora-user-images/image-20200503032335725.png)

**Testing Stats**

```bash
*************** Training Data ***************
Accuracy  [0.9896774193548387, 0.9491935483870968, 0.9490322580645161]
Recall  [0.785      0.9515     0.94363636]
Precision  [0.9965 0.945  0.952 ]
Jaccard Score  0.944274193548387
Confusion Matrix  
[[[5979   21]
  [  43  157]]

 [[2079  121]
  [ 194 3806]]

 [[3808  192]
  [ 124 2076]]]
  
*************** Validation Data ***************
Accuracy  [0.9890322580645161, 0.9519354838709677, 0.9514516129032258]
Recall  [0.77       0.95925    0.93818182]
Precision  [0.99633333 0.93863636 0.95875   ]
Jaccard Score  0.9466935483870967
Confusion Matrix  
[[[5978   22]
  [  46  154]]

 [[2065  135]
  [ 163 3837]]

 [[3835  165]
  [ 136 2064]]]
```



### Focal Loss

**(a) Class Balancing And Adam Optimizer**

**Training Plots**

![image-20200503004309236](/home/usman/.config/Typora/typora-user-images/image-20200503004309236.png)

**Test Stats**

```bash
*************** Training Data ***************
Accuracy  [0.9838709677419355, 0.8111290322580645, 0.8111290322580645]
Recall  [0.605      0.746      0.92954545]
Precision  [0.9965     0.92954545 0.746     ]
Jaccard Score  0.805241935483871

Confusion Matrix  
[[[5979   21]
  [  79  121]]

 [[2045  155]
  [1016 2984]]

 [[2984 1016]
  [ 155 2045]]]
  
*************** Validation Data ***************
Accuracy  [0.9830645161290322, 0.8074193548387096, 0.807258064516129]
Recall  [0.605      0.74325    0.92409091]
Precision  [0.99566667 0.92409091 0.743     ]
Jaccard Score  0.8010483870967742

Confusion Matrix  
[[[5974   26]
  [  79  121]]

 [[2033  167]
  [1027 2973]]

 [[2972 1028]
  [ 167 2033]]]

```

**(b) Class Balancing And SGD optimizer**

**Training Plots**

![image-20200503215656361](/home/usman/.config/Typora/typora-user-images/image-20200503215656361.png) 

```bash
*************** Training Data ***************
Accuracy  [0.9806451612903225, 0.9329032258064516, 0.9320967741935484]
Recall  [0.965      0.9485     0.90318182]
Precision  [0.98116667 0.90454545 0.948     ]
F1  0.9413553268102745
Jaccard Score  0.9256182795698926
Confusion Matrix  
[[[5887  113]
  [   7  193]]

 [[1990  210]
  [ 206 3794]]

 [[3792  208]
  [ 213 1987]]]
*************** Validation Data ***************
Accuracy  [0.9633757961783439, 0.9347133757961783, 0.9315286624203821]
Recall  [0.82142857 0.9575     0.89035088]
Precision  [0.97       0.89473684 0.955     ]
F1  0.9120504930151222
Jaccard Score  0.9219745222929936
Confusion Matrix  [[[582  18]
  [  5  23]]

 [[204  24]
  [ 17 383]]

 [[382  18]
  [ 25 203]]]
```



## Analysis

Following table lists recall and precision for Covid-19 class on validation set for different experiments as this is the class we are most interested in. Ideally we want as high recall as possible as we do not want to miss a patient with covid-19.  F1 score and other metrics can be found in the relevant experiment section.

| Loss Function        | Class Balancing | VGG                                 | ResNet                             |
| -------------------- | --------------- | ----------------------------------- | ---------------------------------- |
| Binary Cross Entropy | No              | Precision: 1.0<br />Recall: 0.428   | Precision: 0.99 <br />Recall: 0.77 |
| Binary Cross Entropy | Yes             | Precision: 0.998<br />Recall: 0.745 | Precision: 0.97<br />Recall: 0.97  |
| Focal Loss           | No              | Precision: 1.0 <br />Recall: 0      | -                                  |
| Focal Loss           | Yes             | N/A                                 | Precision: 0.97<br />Recall: 0.82  |

1. Adam optimizer consistently did worse on this task than SGD optimizer.
2. Focal loss did not prove very useful on this task.
3. Even though focal loss on resnet with class balancing achieved lowest loss, best recall was achieved on resnet with BCE loss and class balancing. This can be attributed to the fact that focal loss does not promote large margins and perhaps threshold of 0.5 should be lowered for focal loss. Another thing to do can be to ease the gamma parameter towards 0 as training progresses. 
4. Class balancing was very important, note that without class balancing, focal loss on VGG achieves recall of 0 on covid class. 
5. We also made the observation that VGG is much more prone to overfitting than resnet. 