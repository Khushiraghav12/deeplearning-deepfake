AI Media Detector
This project classifies uploaded images and videos as FAKE or REAL.

Links
GitHub Repository: https://github.com/kritika038/Real-Fake-image-and-video-detection
Live App: https://real-fake-image-and-video-detection-e7pum2tuwtmhjhsk3yfpwe.streamlit.app/
What this repo contains
app.py: main Streamlit interface
launch.py: one-command local launcher
utils/ensemble_predictor.py: image detection logic
video_detector.py: video frame-by-frame detection logic
models/baseline_model.py: EfficientNet-B0 model definition
models/efficientnet_model.pth: trained model weights used by the app
Features
Image detection
Video detection
Streamlit UI
FastAPI backend in api_server.py
Quick Start
1. Clone the repository
git clone https://github.com/kritika038/Real-Fake-image-and-video-detection.git
cd Real-Fake-image-and-video-detection
2. Create a virtual environment
Mac/Linux:

python3 -m venv venv
source venv/bin/activate
Windows:

python -m venv venv
venv\Scripts\activate
3. Install dependencies
pip install -r requirements.txt
4. Run the app
Option 1:

python3 launch.py
Option 2:

streamlit run app.py
Then open the local URL shown in the terminal, usually:

http://localhost:8501
Run the API instead
uvicorn api_server:app --reload
Usually available at:

http://127.0.0.1:8000
Notes
The current app uses models/efficientnet_model.pth.
Video detection works by extracting frames and analyzing each frame as an image.
Some image predictions also use heuristic checks like sharpness and EXIF metadata.
Important repo notes
The .gitignore already excludes large local-only folders and files such as:

data/
data_fast/
venv/
temp folders
unused large artifacts
So someone downloading the repo gets only the code and required model weights for running the app.

Deploy on Streamlit Community Cloud
Push this project to GitHub.
Go to https://share.streamlit.io/
Click New app
Select your GitHub repo
Set the main file path to app.py
Deploy
After deployment, Streamlit gives a public link that opens the running interface directly.

