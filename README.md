# keras1: cats & dogs

We experiment with tuning the model inspired by
[keras.io](https://keras.io/applications/#fine-tune-inceptionv3-on-a-new-set-of-classes)
for telling cats from dogs.  The model comprises a dense layer on top of a
MobileNet and an optional dropout.

|  No | Dense layer | Optimizer | Pooling | Dropout | Augmentation | Val. loss | Val. accuracy | Comment |
| --- | ----------- | --------- | ------- | ------- | ------------ | --------- | ------------- | ------- |
|   1 |        2048 |   RMSprop |     avg |       0 |           no | 0.0650    | 0.9738        | |
|   2 |        2048 |      Adam |     avg |       0 |           no | 0.0702    | 0.9738        | |
|   3 |        2048 |      Adam |     max |       0 |           no | 0.1200    | 0.9463        | |
|   4 |        2048 |      Adam |     avg |     0.5 |           no | 0.0593    | 0.9762        | |
|   5 |         256 |      Adam |     avg |     0.5 |           no | 0.0617    | 0.9788        | |
|   6 |         256 |      Adam |     max |     0.5 |           no | 0.0602    | 0.9825        | |
|   8 |         256 |      Adam |     max |     0.5 |          yes | 0.1053    | 0.9625        | |
|  11 |         256 |      Adam |     max |     0.5 |           no | 0.0653    | 0.9738        | Increasing resolution |
