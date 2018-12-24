The original dataset is labeled with RoIs for 43 classes.  Meletis labeled the masks inside each RoI providing a per-pixel label used for semantic segmentation approaches.

We used the masks provided by Meletis from: https://github.com/pmeletis/IV2018-hierarchical-semantic-segmentation-for-heterogeneous-datasets/tree/master/datasets] and labeled all the traffic signs not included in the original dataset.

The extended version of the GTSDB is labeled with 164 classes following the definition of the European Traffic Sign Database. It contains 2655 traffic signs:
- 1814 labels for the train set and 
- 841 for the test set. 

At the same time, we provide the instance number for each label and use the format of Mapillary Vistas for the semantic class:
- Traffic sign front

The instance images are saved with 16 bits, where the first 8 correspond to the semantic class and the last 8 to the instance ID.
