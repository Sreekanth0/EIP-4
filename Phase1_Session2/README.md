## Result for the assignment: 

### Strategy:

For this experiment, i tried additional layers like **SeparableConv2D, GlobalAveragePooling2D GlobalMaxPooling2D**. 

So i started building convolutional layers by **avoiding bias values** along with **regularization techniques like Batch Norm & DropOut**. I started building with 16 & 32 filters. Near a transition block i used 1x1 to decrease the channels & did maxpooling. By doing this i got my **image down to 2x2 and used some GlobalPooling techniques or flatten when it is 1x1**. Before flattening or using Global pooling techniques i used 1x1 to get the desired output channels as reference to classes we have.

To decrease the parameters, i replaced one **Convolution layer with SeparableConv2D**, so that i can maintain my parameter count. 

When i used **GlobalMaxPooling2D** i was able to reach 99.54 & with **GlobalAveragePooling2D** able to reach 99.42. Both are build with same architecture except for this layers at the end. 

Models are trained for 20 epochs, while decreasing the learning rate every epoch & saved the results. 

i will provide both logs when i used **GlobalMaxPooling2D & GlobalAveragePooling2D**.



## Result when used GlobalMaxPooling2D

### print(score)

 **[0.016306352772796528, 0.9954] **

### Logs for 20 Epochs

 Epoch 1/20 Epoch 00001: LearningRateScheduler setting learning rate to 0.003. 60000/60000 [==============================] - 12s 198us/step - loss: 0.3302 - acc: 0.8978 - val_loss: 0.1061 - val_acc: 0.9668 

Epoch 2/20 Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503. 60000/60000 [==============================] - 6s 107us/step - loss: 0.0823 - acc: 0.9747 - val_loss: 0.0492 - val_acc: 0.9831 

Epoch 3/20 Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018. 60000/60000 [==============================] - 6s 105us/step - loss: 0.0605 - acc: 0.9815 - val_loss: 0.0336 - val_acc: 0.9896 

Epoch 4/20 Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586. 60000/60000 [==============================] - 6s 105us/step - loss: 0.0507 - acc: 0.9842 - val_loss: 0.0308 - val_acc: 0.9900 

Epoch 5/20 Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019. 60000/60000 [==============================] - 6s 107us/step - loss: 0.0442 - acc: 0.9869 - val_loss: 0.0332 - val_acc: 0.9902 

Epoch 6/20 Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694. 60000/60000 [==============================] - 6s 107us/step - loss: 0.0425 - acc: 0.9872 - val_loss: 0.0229 - val_acc: 0.9929 

Epoch 7/20 Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127. 60000/60000 [==============================] - 6s 106us/step - loss: 0.0377 - acc: 0.9885 - val_loss: 0.0220 - val_acc: 0.9927 

Epoch 8/20 Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307. 60000/60000 [==============================] - 6s 105us/step - loss: 0.0362 - acc: 0.9891 - val_loss: 0.0224 - val_acc: 0.9932 

Epoch 9/20 Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946. 60000/60000 [==============================] - 6s 103us/step - loss: 0.0342 - acc: 0.9893 - val_loss: 0.0209 - val_acc: 0.9938 

Epoch 10/20 Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935. 60000/60000 [==============================] - 6s 103us/step - loss: 0.0305 - acc: 0.9910 - val_loss: 0.0188 - val_acc: 0.9945 

Epoch 11/20 Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905. 60000/60000 [==============================] - 6s 106us/step - loss: 0.0311 - acc: 0.9904 - val_loss: 0.0193 - val_acc: 0.9938 

Epoch 12/20 Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336. 60000/60000 [==============================] - 6s 104us/step - loss: 0.0301 - acc: 0.9909 - val_loss: 0.0246 - val_acc: 0.9918 

Epoch 13/20 Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753. 60000/60000 [==============================] - 6s 105us/step - loss: 0.0273 - acc: 0.9916 - val_loss: 0.0179 - val_acc: 0.9950 

Epoch 14/20 Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638. 60000/60000 [==============================] - 6s 103us/step - loss: 0.0279 - acc: 0.9915 - val_loss: 0.0191 - val_acc: 0.9947 

Epoch 15/20 Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474. 60000/60000 [==============================] - 6s 104us/step - loss: 0.0258 - acc: 0.9920 - val_loss: 0.0214 - val_acc: 0.9938 

Epoch 16/20 Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825. 60000/60000 [==============================] - 6s 104us/step - loss: 0.0244 - acc: 0.9924 - val_loss: 0.0190 - val_acc: 0.9947 

Epoch 17/20 Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481. 60000/60000 [==============================] - 6s 103us/step - loss: 0.0238 - acc: 0.9931 - val_loss: 0.0186 - val_acc: 0.9941 

Epoch 18/20 Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715. 60000/60000 [==============================] - 6s 103us/step - loss: 0.0255 - acc: 0.9922 - val_loss: 0.0177 - val_acc: 0.9938 

Epoch 19/20 Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718. 60000/60000 [==============================] - 6s 104us/step - loss: 0.0234 - acc: 0.9926 - val_loss: 0.0164 - val_acc: 0.9949 

Epoch 20/20 Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869. 60000/60000 [==============================] - 6s 105us/step - loss: 0.0219 - acc: 0.9933 - val_loss: 0.0163 - val_acc: 0.9954 



## Result when used GlobalAveragePooling2D

### print(score)

 **[0.018937324004343826, 0.9942] ** 

### Logs for 20 Epochs

 Epoch 1/20 Epoch 00001: LearningRateScheduler setting learning rate to 0.003. 60000/60000 [==============================] - 17s 280us/step - loss: 0.2493 - acc: 0.9253 - val_loss: 0.0902 - val_acc: 0.9727 

Epoch 2/20 Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503. 60000/60000 [==============================] - 11s 184us/step - loss: 0.0666 - acc: 0.9794 - val_loss: 0.0498 - val_acc: 0.9837 

Epoch 3/20 Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018. 60000/60000 [==============================] - 12s 193us/step - loss: 0.0532 - acc: 0.9845 - val_loss: 0.0335 - val_acc: 0.9888 

Epoch 4/20 Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586. 60000/60000 [==============================] - 11s 188us/step - loss: 0.0454 - acc: 0.9858 - val_loss: 0.0318 - val_acc: 0.9895 

Epoch 5/20 Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019. 60000/60000 [==============================] - 11s 188us/step - loss: 0.0397 - acc: 0.9879 - val_loss: 0.0268 - val_acc: 0.9910 

Epoch 6/20 Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694. 60000/60000 [==============================] - 12s 193us/step - loss: 0.0360 - acc: 0.9891 - val_loss: 0.0250 - val_acc: 0.9917 

Epoch 7/20 Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127. 60000/60000 [==============================] - 11s 186us/step - loss: 0.0334 - acc: 0.9896 - val_loss: 0.0263 - val_acc: 0.9912 

Epoch 8/20 Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307. 60000/60000 [==============================] - 12s 198us/step - loss: 0.0308 - acc: 0.9905 - val_loss: 0.0235 - val_acc: 0.9927 

Epoch 9/20 Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946. 60000/60000 [==============================] - 12s 192us/step - loss: 0.0288 - acc: 0.9912 - val_loss: 0.0238 - val_acc: 0.9925 

Epoch 10/20 Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935. 60000/60000 [==============================] - 11s 191us/step - loss: 0.0279 - acc: 0.9911 - val_loss: 0.0222 - val_acc: 0.9934 

Epoch 11/20 Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905. 60000/60000 [==============================] - 12s 192us/step - loss: 0.0265 - acc: 0.9922 - val_loss: 0.0272 - val_acc: 0.9915 

Epoch 12/20 Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336. 60000/60000 [==============================] - 12s 194us/step - loss: 0.0247 - acc: 0.9919 - val_loss: 0.0209 - val_acc: 0.9937 

Epoch 13/20 Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753. 60000/60000 [==============================] - 12s 193us/step - loss: 0.0227 - acc: 0.9928 - val_loss: 0.0232 - val_acc: 0.9925 

Epoch 14/20 Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638. 60000/60000 [==============================] - 11s 190us/step - loss: 0.0236 - acc: 0.9928 - val_loss: 0.0215 - val_acc: 0.9934 

Epoch 15/20 Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474. 60000/60000 [==============================] - 12s 195us/step - loss: 0.0236 - acc: 0.9927 - val_loss: 0.0225 - val_acc: 0.9924 

Epoch 16/20 Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825. 60000/60000 [==============================] - 11s 189us/step - loss: 0.0220 - acc: 0.9928 - val_loss: 0.0215 - val_acc: 0.9930 

Epoch 17/20 Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481. 60000/60000 [==============================] - 11s 189us/step - loss: 0.0194 - acc: 0.9941 - val_loss: 0.0198 - val_acc: 0.9938 

Epoch 18/20 Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715. 60000/60000 [==============================] - 11s 183us/step - loss: 0.0207 - acc: 0.9937 - val_loss: 0.0197 - val_acc: 0.9936 

Epoch 19/20 Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718. 60000/60000 [==============================] - 11s 188us/step - loss: 0.0189 - acc: 0.9940 - val_loss: 0.0209 - val_acc: 0.9937 

Epoch 20/20 Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869. 60000/60000 [==============================] - 12s 192us/step - loss: 0.0185 - acc: 0.9945 - val_loss: 0.0189 - val_acc: 0.9942 



