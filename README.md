# Emotion-Based Image Sorting Script

This Python script classifies facial images based on emotions and automatically sorts them into corresponding folders. The script uses a pre-trained TensorFlow/Keras model to detect emotions from images and organizes them into directories named after the detected emotion (e.g., `happy`, `sad`).

## Prerequisites

- Python 3.x
- Required libraries: `cv2` (OpenCV), `numpy`, `tensorflow`, `os`
  
  You can install these using pip:
  ```bash
  pip install opencv-python numpy tensorflow
  ```

## Model

The script uses a pre-trained emotion detection model saved as `emotion_detection_model.h5`. Ensure that this file is in the same directory as the script or provide the correct path to it.

## Usage

1. **Clone the repository** or copy the script to your local machine.

2. **Prepare your images**:
   Save the images you want to classify in a specified folder. Update the script with the path to this folder:
   ```python
   image_folder_path = 'path/to/your/images/folder/'
   ```

3. **Run the script**:
   Execute the script using Python:
   ```bash
   python emotion_sorting.py
   ```

4. **Output**:
   - The script will classify each image in the folder based on the detected emotion.
   - It will create directories named after each emotion class (e.g., `happy`, `sad`) if they do not already exist.
   - The images will be moved to the corresponding directory based on their classified emotion.
   - The script prints a confirmation message for each classified and moved image.

## Functions

- **`rgb_to_grayscale(rgb_image)`**: Converts an RGB image to grayscale.
- **`classify_emotion(face)`**: Resizes the grayscale face image to the required input size (48x48), prepares it as a 4D tensor, and predicts the emotion using the loaded model.

## Example

If your folder contains images named `image1.jpg`, `image2.jpg`, etc., running the script will classify each image (e.g., "happy", "sad") and move it to the corresponding folder within the specified directory.

## Notes

- The model expects grayscale images of size 48x48 pixels. The script handles resizing and conversion internally.
- Ensure the model file (`emotion_detection_model.h5`) is correctly loaded and corresponds to the expected input dimensions.
- Supported image formats include `.jpg` and `.png`, but you can modify the script to include other formats if necessary.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
