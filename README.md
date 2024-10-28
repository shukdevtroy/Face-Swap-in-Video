# Face Swap in Video

This project allows you to swap faces from a source image with faces detected in a video, utilizing deep learning models for face detection and face swapping. It employs the InsightFace library for high-performance face analysis and swapping.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [License](#license)

## Features

- Face detection using InsightFace.
- Face swapping from a single source image to all detected faces in a video.
- Output video with swapped faces saved in AVI format.

## Requirements

To run this project, you'll need the following libraries:

- Python 3.x
- NumPy
- OpenCV
- InsightFace

You can install the required packages using pip:

```bash
pip install numpy opencv-python insightface
```

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/shukdevtroy/Face-Swap-in-Video.git
   cd Face-Swap-in-Video
   ```

2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Download the necessary models if they are not automatically downloaded. The code will handle model downloads when executed.

## Usage

To swap faces in a video, you can use the provided function `swap_faces_in_video`. Here's how to do it:

```python
from swap_faces import swap_faces_in_video
from insightface.app import FaceAnalysis

# Initialize face analysis and load model
app = FaceAnalysis(name='buffalo_l')
app.prepare(ctx_id=0, det_size=(640, 640))

# Load the face swapper model
swapper = insightface.model_zoo.get_model('inswapper_128.onnx', download=False, download_zip=False)

# Call the face swapping function
swap_faces_in_video('path_to_source_image.jpg', 'path_to_input_video.mp4', 'path_to_output_video.avi', app, swapper)
```

### Parameters:

- `image_path`: Path to the source image containing the face you want to swap.
- `video_path`: Path to the input video file where faces will be swapped.
- `output_path`: Path for the output video file with swapped faces.
- `app`: Initialized FaceAnalysis instance.
- `swapper`: Loaded face swapper model.

## How It Works

1. The script reads a source image and detects faces using the InsightFace library.
2. It then opens the specified video file and processes each frame, detecting faces in the current frame.
3. For each detected face in the video, it swaps the face with the face from the source image.
4. The modified frames are written to a new video file, which is saved upon completion.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or issues, please contact:

- **Email**: shukdevdatta@gmail.com
- **GitHub**: [Click to here to access the Github Profile](https://github.com/shukdevtroy)
- **WhatsApp**: [Click here to chat](https://wa.me/+8801719296601)

