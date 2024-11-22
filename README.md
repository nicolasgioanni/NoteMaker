# NotePal Assistant

# -------Python-------
Ensure you have Python 3.8+ installed, I haven't tried other versions but I am using Python 3.11.5

# -------Create a virtual environment, update pip, and install the required packages-------
```
python -m venv .venv
.venv\Scripts\activate
pip install -U pip
python -m ensurepip --upgrade
python -m pip install --upgrade pip
pip install -r requirements.txt
```

# -------Special Instructions for Specific Libraries-------

**PaddleOCR and PaddlePaddle (CPU-Only)**
PaddleOCR requires paddlepaddle. Install the CPU version using the command below. Not sure if you have 
the GPU version which will make the image processing quicker but for simple purposes I used just the CPU:
```
pip install paddlepaddle -f https://www.paddlepaddle.org.cn/whl/cpu/stable.html
```

# -------Set up the following environment variable-------
```
OPENAI_API_KEY="Your Openai Secret Key"
```

# -------External Tools-------

**FFmpeg**
Required for: `moviepy` (video editing and audio extraction).
Steps:
1. Download FFmpeg:
   - Download the essentials build: [FFmpeg Essentials Build](https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip).

2. Extract:
   - Extract the downloaded file to a location, e.g., `C:\ffmpeg`.

3. Add to PATH:
   - Add the `bin` folder (e.g., `C:\ffmpeg\bin`) to the system's `PATH`:
     - Open **System Properties** > **Environment Variables** > **Path** > **Edit** > **New** > Add `C:\ffmpeg\bin`.

4. Verify Installation:
   ```bash
   ffmpeg -version

**Git**
Required for: Installing openai-whisper from its Git repository.
1. Download and Install Git:
    - Download Git: [Git Downloads.](https://git-scm.com/)
    - During installation, ensure Git is added to the system's PATH.
    - Verify using: git --version

**Visual C++ Build Tools**
Required for: Building Python packages such as Cython, llvmlite, and numba.

- You probably already have it but make sure you do

# -------Verify Libaries and Tools-------
Run the following command to verify that all required libraries and tools are correctly installed:
```
python -c "import ffmpeg; import torch; import cv2; import paddle; import whisper; print('Libraries loaded successfully')"
```