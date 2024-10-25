
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

## Requirements

- Python 3.x
- TensorFlow or PyTorch (specify your preference)
- NumPy
- OpenCV
- Other dependencies (list any other libraries used)

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/amirhyous/c-Fos_Detection_Brain.git
   ```

2. Navigate to the project directory:

   ```bash
   cd c-Fos_Detection_Brain
   ```

3. Install required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Prepare your dataset according to the structure used in this repository.

5. Run the training script:

   ```bash
   python train.py
   ```

6. Test the model:

   ```bash
   python test.py
   ```

7. Assemble the segmented tiles into a full-size image:

   ```bash
   python assemble.py
   ```

## Contributing

Contributions are welcome! If you have suggestions for improvements or additional features, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
