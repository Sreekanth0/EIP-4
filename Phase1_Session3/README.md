## Results for this Assignment

#### Final Validation Accuracy for Base Network

**1)** model.evaluate(test_features, test_labels)

​	[0.6245143092155456, 0.8205]

#### Model definition with output channel size & Receptive Field

**2)**

my_model = Sequential()
my_model.add(SeparableConv2D(48, (3, 3), use_bias=False, input_shape=(32, 32, 3), kernel_regularizer=regularizers.l2(0.0001))) **#S-30, R-3**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(48, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-28, R-5**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(48, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-26, R-7**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(MaxPooling2D(pool_size=(2, 2))) **#S-13, R-8**
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(96, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-11, R-12**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(96, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-9, R-16**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(96, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-7, R-20**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(192, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-5, R-24**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(192, (3, 3), use_bias=False, kernel_regularizer=regularizers.l2(0.0001))) **#S-3, R-28**
my_model.add(BatchNormalization())
my_model.add(Activation('relu'))
my_model.add(Dropout(0.1))

my_model.add(SeparableConv2D(num_classes, (1,1), kernel_regularizer=regularizers.l2(0.0001))) **#S-3, R-28**
my_model.add(GlobalAveragePooling2D())
my_model.add(Activation('softmax'))



#### My 50 epoch Logs

**3)** 

```
Epoch 1/50
390/390 [==============================] - 18s 46ms/step - loss: 1.5426 - acc: 0.4339 - val_loss: 1.7436 - val_acc: 0.4707
Epoch 2/50
390/390 [==============================] - 16s 42ms/step - loss: 1.1997 - acc: 0.5681 - val_loss: 1.7805 - val_acc: 0.5120
Epoch 3/50
390/390 [==============================] - 16s 42ms/step - loss: 1.0745 - acc: 0.6176 - val_loss: 1.1780 - val_acc: 0.6217
Epoch 4/50
390/390 [==============================] - 16s 42ms/step - loss: 0.9910 - acc: 0.6502 - val_loss: 1.1953 - val_acc: 0.6275
Epoch 5/50
390/390 [==============================] - 17s 42ms/step - loss: 0.9354 - acc: 0.6679 - val_loss: 1.0795 - val_acc: 0.6492
Epoch 6/50
390/390 [==============================] - 16s 42ms/step - loss: 0.8943 - acc: 0.6838 - val_loss: 0.8922 - val_acc: 0.7004
Epoch 7/50
390/390 [==============================] - 17s 43ms/step - loss: 0.8580 - acc: 0.6977 - val_loss: 0.8271 - val_acc: 0.7163
Epoch 8/50
390/390 [==============================] - 16s 42ms/step - loss: 0.8360 - acc: 0.7047 - val_loss: 0.8401 - val_acc: 0.7277
Epoch 9/50
390/390 [==============================] - 17s 43ms/step - loss: 0.8136 - acc: 0.7150 - val_loss: 0.8306 - val_acc: 0.7213
Epoch 10/50
390/390 [==============================] - 16s 42ms/step - loss: 0.7941 - acc: 0.7203 - val_loss: 0.7702 - val_acc: 0.7384
Epoch 11/50
390/390 [==============================] - 16s 42ms/step - loss: 0.7824 - acc: 0.7233 - val_loss: 0.8778 - val_acc: 0.7087
Epoch 12/50
390/390 [==============================] - 17s 43ms/step - loss: 0.7615 - acc: 0.7330 - val_loss: 0.8788 - val_acc: 0.7167
Epoch 13/50
390/390 [==============================] - 17s 43ms/step - loss: 0.7460 - acc: 0.7377 - val_loss: 0.7857 - val_acc: 0.7393
Epoch 14/50
390/390 [==============================] - 17s 42ms/step - loss: 0.7391 - acc: 0.7414 - val_loss: 0.7075 - val_acc: 0.7610
Epoch 15/50
390/390 [==============================] - 17s 42ms/step - loss: 0.7272 - acc: 0.7459 - val_loss: 0.7031 - val_acc: 0.7584
Epoch 16/50
390/390 [==============================] - 17s 43ms/step - loss: 0.7184 - acc: 0.7470 - val_loss: 0.8017 - val_acc: 0.7357
Epoch 17/50
390/390 [==============================] - 17s 42ms/step - loss: 0.7083 - acc: 0.7508 - val_loss: 0.6307 - val_acc: 0.7842
Epoch 18/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6975 - acc: 0.7550 - val_loss: 0.6981 - val_acc: 0.7614
Epoch 19/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6832 - acc: 0.7621 - val_loss: 0.6651 - val_acc: 0.7713
Epoch 20/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6814 - acc: 0.7596 - val_loss: 0.6828 - val_acc: 0.7773
Epoch 21/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6365 - acc: 0.7770 - val_loss: 0.6858 - val_acc: 0.7705
Epoch 22/50
390/390 [==============================] - 17s 42ms/step - loss: 0.6255 - acc: 0.7785 - val_loss: 0.5771 - val_acc: 0.7976
Epoch 23/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6200 - acc: 0.7813 - val_loss: 0.6324 - val_acc: 0.7828
Epoch 24/50
390/390 [==============================] - 17s 42ms/step - loss: 0.6213 - acc: 0.7795 - val_loss: 0.6442 - val_acc: 0.7873
Epoch 25/50
390/390 [==============================] - 17s 42ms/step - loss: 0.6106 - acc: 0.7864 - val_loss: 0.5886 - val_acc: 0.8030
Epoch 26/50
390/390 [==============================] - 17s 43ms/step - loss: 0.6098 - acc: 0.7858 - val_loss: 0.6212 - val_acc: 0.7901
Epoch 27/50
390/390 [==============================] - 17s 42ms/step - loss: 0.6035 - acc: 0.7867 - val_loss: 0.5686 - val_acc: 0.8075
Epoch 28/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5964 - acc: 0.7896 - val_loss: 0.6195 - val_acc: 0.7915
Epoch 29/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5971 - acc: 0.7915 - val_loss: 0.5875 - val_acc: 0.8000
Epoch 30/50
390/390 [==============================] - 16s 42ms/step - loss: 0.5986 - acc: 0.7909 - val_loss: 0.5583 - val_acc: 0.8089
Epoch 31/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5941 - acc: 0.7910 - val_loss: 0.6051 - val_acc: 0.8004
Epoch 32/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5905 - acc: 0.7917 - val_loss: 0.5521 - val_acc: 0.8084
Epoch 33/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5866 - acc: 0.7945 - val_loss: 0.6122 - val_acc: 0.7913
Epoch 34/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5694 - acc: 0.7984 - val_loss: 0.5649 - val_acc: 0.8071
Epoch 35/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5534 - acc: 0.8053 - val_loss: 0.5429 - val_acc: 0.8113
Epoch 36/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5547 - acc: 0.8045 - val_loss: 0.5695 - val_acc: 0.8056
Epoch 37/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5551 - acc: 0.8045 - val_loss: 0.5481 - val_acc: 0.8128
Epoch 38/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5519 - acc: 0.8044 - val_loss: 0.5603 - val_acc: 0.8122
Epoch 39/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5464 - acc: 0.8079 - val_loss: 0.5390 - val_acc: 0.8179
Epoch 40/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5484 - acc: 0.8070 - val_loss: 0.5301 - val_acc: 0.8204
Epoch 41/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5474 - acc: 0.8069 - val_loss: 0.5633 - val_acc: 0.8080
Epoch 42/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5454 - acc: 0.8085 - val_loss: 0.5801 - val_acc: 0.8068
Epoch 43/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5488 - acc: 0.8055 - val_loss: 0.5470 - val_acc: 0.8161
Epoch 44/50
390/390 [==============================] - 16s 42ms/step - loss: 0.5338 - acc: 0.8110 - val_loss: 0.5419 - val_acc: 0.8155
Epoch 45/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5309 - acc: 0.8132 - val_loss: 0.5177 - val_acc: 0.8235
Epoch 46/50
390/390 [==============================] - 16s 42ms/step - loss: 0.5289 - acc: 0.8131 - val_loss: 0.5328 - val_acc: 0.8172
Epoch 47/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5296 - acc: 0.8140 - val_loss: 0.5413 - val_acc: 0.8164
Epoch 48/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5226 - acc: 0.8145 - val_loss: 0.5157 - val_acc: 0.8237
Epoch 49/50
390/390 [==============================] - 17s 42ms/step - loss: 0.5223 - acc: 0.8145 - val_loss: 0.5291 - val_acc: 0.8224
Epoch 50/50
390/390 [==============================] - 17s 43ms/step - loss: 0.5225 - acc: 0.8131 - val_loss: 0.5238 - val_acc: 0.8231
Model took 832.24 seconds to train
```

