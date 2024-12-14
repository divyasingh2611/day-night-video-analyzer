
# Time-Lapse Video Processing with OpenCV

## Project Overview

This project provides a Python-based solution for downloading and processing time-lapse videos using **OpenCV** and **yt-dlp**. The primary functionalities include:  
- Downloading YouTube videos.  
- Analyzing frame brightness.  
- Classifying frames as day or night.  
- Generating annotated videos with brightness analysis and day/night classification.  

Additionally, this project includes a **Gradio demo** to showcase the processing pipeline in a user-friendly interface. Try the demo here: [Gradio Demo Link](#).

---

## Prerequisites

### **System Requirements**
- Python 3.x

### **Required Libraries**
Install the following libraries using pip:  
```bash
pip install pandas opencv-python yt-dlp numpy
```

If you are using **Google Colab**, run this command to install the required libraries:  
```python
!pip install yt-dlp opencv-python
```

---

## Project Structure

The project is divided into the following key components:

### **1. Video Download Function (`download_video()`)**
- **Purpose**: Downloads videos from YouTube in high quality using **yt-dlp**.
- **Customizations**: Supports configurable download paths and video formats.

### **2. Video Processing Function (`process_video()`)**
- **Purpose**: 
  - Analyzes the brightness of each video frame.
  - Classifies frames as "Day" or "Night" based on brightness thresholds.
  - Annotates frames with classification text.
  - Adjusts playback speed for smoother visualization.
  - Outputs a processed video with brightness annotations.
- **Customizations**: Configurable brightness threshold and playback speed.

---

## Key Functions

### **`download_video(url, download_path)`**

#### **Parameters**:
- `url`: URL of the YouTube video to download.
- `download_path`: Directory to save the downloaded video.

#### **Features**:
- Downloads the best quality video using **yt-dlp**.
- Automatically saves the video with its original title.
- Handles single video downloads seamlessly.

---

### **`process_video(input_path, output_path, brightness_threshold=100, slow_factor=2)`**

#### **Parameters**:
- `input_path`: Path to the input video file.  
- `output_path`: Path to save the processed video.  
- `brightness_threshold`: Threshold to distinguish between day and night frames (default: 100).  
- `slow_factor`: Factor to reduce video playback speed (default: 2).  

#### **Features**:
- **Frame Brightness Analysis**: Calculates frame brightness using the HSV color space for accuracy.  
- **Day/Night Classification**: Classifies each frame based on brightness.  
- **Text Overlay**: Adds "Day" or "Night" text to the video frames using **`cv2.putText()`**.  
- **Playback Adjustment**: Modifies playback speed for improved visualization.  
- **Output Video**: Generates an annotated video with day/night labels and adjusted playback speed.  

---

## Usage Example

Below is an example of how to use the project:

```python
# Import functions
from your_script_name import download_video, process_video

# Step 1: Download a time-lapse video
url = "https://youtu.be/example_video"
download_path = "/path/to/download/directory"
download_video(url, download_path)

# Step 2: Process the downloaded video
input_video = "/path/to/downloaded/video.mp4"
output_video = "/path/to/processed/video.mp4"
process_video(input_video, output_video, brightness_threshold=100, slow_factor=2)
```

---

## Customization Options

1. **Brightness Threshold**: Adjust the `brightness_threshold` parameter to fine-tune the day/night classification accuracy.  
2. **Playback Speed**: Use the `slow_factor` parameter to control the output video playback speed.  
3. **Text Overlay Style**: Customize the appearance of the "Day/Night" text annotations by modifying parameters in the `cv2.putText()` function.

---

## Notes

- Ensure you have the necessary permissions to download and process videos.  
- The effectiveness of brightness-based classification depends on the source video. Complex lighting conditions might require advanced algorithms.  
- Output video quality may vary based on the input video's resolution.  

---

## Potential Improvements

1. **Advanced Day/Night Detection**: Integrate machine learning or advanced image processing techniques for more accurate frame classification.  
2. **Batch Processing**: Extend support to process multiple videos in a single execution.  
3. **Command-Line Interface**: Develop a CLI tool for easier access and automation.  
4. **Enhanced User Interface**: Expand the functionality of the **Gradio demo** to include parameter tuning.  

---

## Gradio Demo

Try the live **Gradio demo** to upload and process your own videos directly in your browser:  
[Gradio Demo Link](#)

---

## License

This project is distributed under the [Your License Name Here].  

---

## Contributing

We welcome contributions! Please review the [contribution guidelines](#) before submitting a pull request.  

For questions or suggestions, feel free to open an issue or contact us directly.
