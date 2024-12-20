DIRECTORY: /data/ushelf-mf-pba/projects/AIU/lane_markings/luca/MapTR
DATA: /data/ushelf-mf-pba/data/public_datasets/lane_marking

## NuScenes
Download nuScenes V1.0 full dataset data  and CAN bus expansion data [HERE](https://www.nuscenes.org/download). Prepare nuscenes data by running


**Download CAN bus expansion**
```
# download 'can_bus.zip'
unzip can_bus.zip 
# move can_bus to data dir
```

**Prepare nuScenes data**

*We genetate custom annotation files which are different from mmdet3d's*
```
python tools/create_data.py nuscenes --root-path /data/ushelf-mf-pba/data/public_datasets/lane_marking/NuScenes/nuscenes --out-dir /data/ushelf-mf-pba/data/public_datasets/lane_marking/NuScenes/nuscenes --extra-tag nuscenes --version v1.0 --canbus /data/ushelf-mf-pba/data/public_datasets/lane_marking/NuScenes
```

Using the above code will generate `nuscenes_infos_temporal_{train,val}.pkl`.

**Folder structure**
```
MapTR
├── mmdetection3d/
├── projects/
├── tools/
├── configs/
├── ckpts/
│   ├── r101_dcn_fcos3d_pretrain.pth
├── data/
│   ├── can_bus/
│   ├── nuscenes/
│   │   ├── maps/
│   │   ├── samples/
│   │   ├── sweeps/
│   │   ├── v1.0-test/
|   |   ├── v1.0-trainval/
|   |   ├── nuscenes_infos_temporal_train.pkl
|   |   ├── nuscenes_infos_temporal_val.pkl
```

## Argoverse2
Download the Argoverse2 Sensor Dataset [here](https://www.argoverse.org/av2.html#download-link).

**Folder structure**
```
MapTR
├── mmdetection3d/
├── projects/
├── tools/
├── configs/
├── ckpts/
│   ├── r101_dcn_fcos3d_pretrain.pth
├── data/
│   ├── can_bus/
│   ├── nuscenes/
│   ├── argoverse2/
│   │   ├── sensor/
|   |   |   |—— train/
|   |   |   |—— val/
|   |   |   |—— test/
```

**Prepare Argoverse2 data**

*We genetate custom annotation files which are different from mmdet3d's*
```
python tools/data_converter/av2_converter.py --data-root ./data/argoverse2/sensor/
```
