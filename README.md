
# c-Fos Detection Code

This repository contains code for detecting c-Fos protein expression in images using a deep learning approach. The implementation employs a U-Net model to process multi-channel fluorescence images and segment c-Fos-positive cells.

## Overview

The main images contain different colors and channels:

![Alt text](blevel_eq_lowerQ.png)
The code utilizes three channels from the main images:

- **Alexa Fluor 488**
- **Alexa Fluor 594**
  
![Alt text](blevel_Alexa_Fluor_594_lowerQ.png)

- **DAPI**

The workflow includes the following steps:

1. **Image Preprocessing**:
   - High-resolution images are divided into smaller tiles of size **100x100 pixels** for efficient processing.
     
     ![Alt text](blevel_Alexa_Fluor_594_chunks_chunk_13_56.png)


2. **Model Training**:
   - The U-Net model is trained on these smaller image tiles, using the corresponding ground truth annotations for accurate segmentation.

3. **Testing**:
   - The trained model is tested using smaller chunks of images to evaluate performance.
     
     ![Alt text](test_image.png)


4. **Image Assembly**:
   - After segmentation, the smaller tiles are assembled back into a larger image for comprehensive analysis.

   ![Alt text](stitched_image_blevel_Alexa_Fluor_488_edited_chunks_after_test_mask.png)


## Requirements

- Python 3.10.12
- torch
- cv2
- torchvision
