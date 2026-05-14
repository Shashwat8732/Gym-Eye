# 🏋️‍♂️ Gym Eye — AI Workout Coach

> Real-time pose detection with proactive AI voice coaching — built with Streamlit, MediaPipe, and Groq.

---

## ✨ Features

- 📷 **Real-time Camera Analysis** — Live pose detection using MediaPipe
- 🤖 **AI Voice Coaching** — Proactive feedback powered by Groq LLM + gTTS
- 🏃 **5 Exercises Supported** — Squats, Push-ups, Biceps Curls, Shoulder Press, Lunges
- 📊 **Rep & Set Counting** — Automatic tracking with form feedback
- 📈 **Workout History** — Persistent logging per user session
- 🔐 **User Login** — Simple username-based authentication

---

## 🖥️ Demo

> Live App: [gym-eye on Streamlit Cloud](https://gym-eye.streamlit.app)

---

## 📁 Project Structure

```
gym-eye/
├── main.py                          # Main Streamlit app
├── static/
│   ├── style.css                    # Custom CSS
│   └── AdobeClean.otf               # Custom font
├── services/
│   ├── auth/
│   │   └── login.py                 # Login wall
│   ├── coaching/
│   │   ├── llm.py                   # Groq LLM coach
│   │   ├── tts.py                   # Text-to-speech
│   │   └── voice_pipeline.py        # Voice feedback pipeline
│   ├── config/
│   │   └── workout_config.py        # Exercise options & metrics config
│   ├── persistence/
│   │   └── exercise_repository.py   # SQLite database layer
│   ├── state/
│   │   └── session_defaults.py      # Streamlit session state defaults
│   ├── tracking/
│   │   └── metrics.py               # Rep/set counting logic
│   ├── ui/
│   │   └── style_loader.py          # CSS & font injection
│   └── vision/
│       └── exercise_video_processor.py  # MediaPipe pose processor
├── requirements.txt
└── packages.txt
```

---

## 🚀 Local Setup

### 1. Clone the repo

```bash
git clone https://github.com/shashwat8732/gym-eye.git
cd gym-eye
```

### 2. Install system dependencies

```bash
sudo apt-get install -y libgl1 libglib2.0-0 libsm6 libxext6 libgles2 libegl1
```

### 3. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 4. Set environment variables

Create a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key
```

### 5. Run the app

```bash
streamlit run main.py
```

---

## ☁️ Streamlit Cloud Deployment

### Secrets required

Go to **App Settings → Secrets** and add:

```toml
GROQ_API_KEY = "your_groq_api_key"
TURN_USERNAME = "your_metered_turn_username"
TURN_CREDENTIAL = "your_metered_turn_password"
```

> **Note:** TURN server credentials are required for WebRTC to work on Streamlit Cloud.
> Get free credentials at [dashboard.metered.ca](https://dashboard.metered.ca)

---

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| Streamlit | Web UI & deployment |
| streamlit-webrtc | Real-time camera access |
| MediaPipe | Pose landmark detection |
| OpenCV | Video frame processing |
| Groq (LLaMA 3) | AI coaching feedback |
| gTTS | Text-to-speech audio |
| SQLite | Workout history storage |
| Metered.ca | TURN server for WebRTC |

---

## 🏋️ Supported Exercises

| Exercise | Metrics Tracked |
|---|---|
| Squats | Knee angle, back angle, depth status |
| Push-ups | Elbow angle, body alignment, hip position |
| Biceps Curls | Elbow angle, shoulder stability, swing detection |
| Shoulder Press | Elbow angle, arm extension, back arch |
| Lunges | Front knee angle, torso angle, balance status |

---

---

## 🤝 Contributing

Pull requests welcome! For major changes, open an issue first.

---

**Made by Shashwat Raj** | [GitHub](https://github.com/Shashwat8732) | [LinkedIn](https://www.linkedin.com/in/shashwatraj1412/)
