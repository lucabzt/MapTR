# Prerequisites

**Please ensure you have prepared the environment and the nuScenes dataset.**

# Train and Test

Train MapTR with 8 GPUs 
```
./tools/dist_train.sh ./projects/configs/maptr/maptr_tiny_r50_24e.py 8
```

Eval MapTR with 8 GPUs
```
./tools/dist_test_map.sh ./projects/configs/maptr/maptr_tiny_r50_24e.py ./path/to/ckpts.pth 8
```

# Current Problems
compatibility issues specifically with mmdet3d. bev_tool cant be found in installation and difficulties with numpy (code requires >1.21, mmdet3d requires <1.20).
Also cannot upgrade mmdet3d too high, due to cuda compatibility.




# Visualization 

we provide tools for visualization and benchmark under `path/to/MapTR/tools/maptr`
