# Fully-Convolutional Network in TensorFlow (Custom)

## Script

This repository provides a basic implementation of Fully-Convolutional Network in TensorFlow. The main script can be executed as:

```
python trainer_fcn.py --trainModel --testModel -s --modelName IncResV2 --trainFileName ./data/train_pre_encoded.csv --valFileName ./data/val_pre_encoded.csv --testFileName ./data/val_pre_encoded.csv --trainingEpochs 50 --useSparseLabels --learningRate 1e-4 --weightDecayLambda 1e-6 --maxImageSize 1024 --tensorboardVisualization
```

Since both the --trainModel and --testModel flags are passed to the system, the system will first train the model based on the given data followed by evaluation. -s flag specifies that the model has to be trained from scratch. If -s is not passed, the system will attempt to reload previous saved checkpoint. The system loads the pretrained ImageNet model if -s is passed.
The system supports two different models at this point, Inception ResNet v2 and NASNet. 
--useSparseLabels specifies that the system has to load sparse labels where the shape of the mask is [H, W, 1]. Each entry in the grid specifies the class label [0, C) where C is the total number of classes. --tensorboardVisualization flag enables the tensorboard logging.

## TODO:

+ **NASNet model:** The system is not yet functional with the NASNet base.
+ **Load un-encoded images:** The system cannot load unencoded images at this point (TF data loading pipeline) where RGB maps to label values.
+ **ResNeXt:** Add support for the ResNeXt model.

## License:

MIT

## Issues/Feedback:

In case of any issues, feel free to drop me an email or open an issue on the repository.

Email: **mkarimi@nvidia.com**