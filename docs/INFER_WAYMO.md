# Inference and Visualization on Waymo Dataset

### Environment Setup

We encourage you to create a separate environment for the unpacking of Waymo Open Dataset, execute below in `PCSeg` folder:
```
conda create -n wod python=3.6
pip install open3d==0.9.0
pip install opencv-python
pip install waymo-open-dataset-tf-2-1-0
pip install protobuf==3.19.0
pip install tqdm
python setup.py develop
```

### Prepare Waymo Data

First, download a sequence from [Waymo Perception Dataset v1.3.1](https://waymo.com/intl/en_us/open/download/).

For example, you can select `segment-10082223140073588526_6140_000_6160_000_with_camera_labels.tfrecord` from the training set.

```
mkdir ./infer_data
mkdir ./infer_data/raw_waymo/
```

Further, place `segment-10082223140073588526_6140_000_6160_000_with_camera_labels.tfrecord` in `./infer_data/raw_waymo/` directory. 

```
python ./tools/scripts/unpack_wod_sequence.py \
    --segment_path ./infer_data/raw_waymo/segment-10082223140073588526_6140_000_6160_000_with_camera_labels.tfrecord \
    --output_dir ./infer_data/output/segment-10082223140073588526_6140_000_6160_000_with_camera_labels.unpacked
```

### Infer
