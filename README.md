# Tensorflow Object Detection API

Forked from https://github.com/tensorflow/models/tree/master/object_detection


## Updates

### Add `from_detection_checkpoint` parameter in `train_config`

Old:

`bool from_detection_checkpoint`

- True: the checkpoint was an object detection model that have the same parameters with the exception of the num_classes parameter.

- False: the checkpoint was a object classification model.

New:

`uint32 from_detection_checkpoint`

- 3: don't load any variables.

- 2: load all variables.

- 1: load feature extractor variables from an object detection model, same as `True`.

- 0: load feature extractor variables from a object classification model, same as `False`.

Modified files:

- `trainer.py`

- `core/model.py`

- `protos/train.proto`

- `meta_architectures/ssd_meta_arch.py`

- `meta_architectures/faster_rcnn_meta_arch.py`

### Remove some summaries when training

Remove summaries about histograms and first_clone_scope when training.

Modified files:

- `trainer.py`
