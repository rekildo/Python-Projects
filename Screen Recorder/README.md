# Python Screen Recorder

A simple desktop screen recording application built using Python. It captures screenshots continuously, converts them into video frames, and combines them into a video file using OpenCV.

## Features

- Captures the entire desktop screen.
- Records screen activity as a video.
- Saves recordings in AVI format.
- Uses the XVID video codec.
- Supports a configurable playback frame rate (default: 60 FPS).
- Displays a live preview while recording.
- Press `q` to stop recording.

## Technologies Used

- **Python** – Core programming language.
- **PyAutoGUI** – Captures screenshots.
- **NumPy** – Converts screenshots into numerical arrays.
- **OpenCV** – Processes video frames and writes the video file.
- **Pillow** – Image support used by PyAutoGUI.

## Project Structure

```text
Screen Recorder/
├── recorder/             # Python virtual environment (usually not committed)
├── main.py               # Main screen recording script
├── Recording.avi         # Generated video file (created when recording)
├── README.md             # Project documentation
└── requirements.txt      # Project dependencies
```

## Installation and Setup

### 1. Clone the repository

Replace `<your-repository-url>` with your repository URL.

```bash
git clone <your-repository-url>
cd "Screen Recorder"
```

### 2. Create a virtual environment

```bash
python -m venv recorder
```

### 3. Activate the virtual environment

**Windows PowerShell:**

```powershell
.\recorder\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
python -m pip install -r requirements.txt
```

## How to Run

Run the main script:

```bash
python main.py
```

- The application starts capturing your desktop.
- A live preview window displays the latest captured frame.
- Press `q` while the preview window is active to stop recording.
- The recorded video is saved as `Recording.avi` in the current working directory.

## How It Works

1. PyAutoGUI captures the current screen as an image.
2. NumPy converts the image into an array of pixel values.
3. OpenCV converts the image from RGB to BGR colour order.
4. OpenCV's `VideoWriter` writes each captured image as a video frame.
5. The frames are encoded using the selected codec and saved in an AVI container.

## Configuration

You can customize these settings in the Python script:

| Parameter | Default | Description |
|---|---:|---|
| Resolution | 1920 × 1080 | Width and height expected by the video writer |
| FPS | 60 | Video playback frame rate |
| Codec | XVID | Video codec |
| Output filename | `Recording.avi` | Name of the generated video |

**Note:** Setting the video to 60 FPS does not guarantee that 60 screenshots are captured every second. Actual capture speed depends on your computer and screenshot-processing time. Also, the captured frame dimensions must match the configured resolution.

## Future Improvements

- Add start and stop recording buttons.
- Allow users to select the screen resolution.
- Support additional video codecs and formats.
- Add audio recording functionality.
- Allow users to choose a custom output location.

## Author

Developed using Python.
