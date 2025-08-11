# UFEN-SLAM 

UFEN-SLAM is built on [ORB-SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3).

To run UFEN-SLAM please follow the prerequisite installation steps of ORB-SLAM3 first.

Download the vocabulary file from the ORB-SLAM3 repository and place it in the `Vocabulary/` directory.

## Installation Notes

UFEN-SLAM requires [LibTorch](https://pytorch.org/get-started/locally/).  
After installing LibTorch, make sure its path is correctly set in `CMakeLists.txt` if it is not detected automatically.

**Setup Steps:**
1. **Configure LibTorch Path**  
   Edit `CMakeLists.txt` to set the correct **LibTorch** path.
2. **Set UFEN Weights Path**  
   Update the code with the correct location of the `ufen.pt` weight file.
3. **Build the Project**  
   Follow the same build instructions as in [ORB-SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3).
4. **Set the Parameters**  
   Feature detection threshold is adjustable in `ufen.pt`: /ufen/code/__torch__/models/sup_model_extractor.py at line 92: thre1 = torch.gt(heatmap1, 0.001). The value 0.001 can be increased or decreased to change feature detection sensitivity. For most cases, 0.01 is a good starting point.