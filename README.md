# Kavach: Voice-Activated Help Detection System

**Kavach** (Hindi for "Shield" or "Armor") is an advanced safety application designed to detect distress signals and automatically trigger emergency alerts. Built with a focus on personal security, this system utilizes offline speech recognition to listen for specific voice commands ("Help" followed by a user-defined security code) and immediately notifies emergency contacts with the user's real-time location.

This repository houses the source code for the software component of the **Kavach** project, which works in tandem with our custom hardware prototype.

## 🔬 Research & Publication

This project is the practical implementation of our ongoing research into accessible personal safety devices.

**Status:** *In process of publishing*

We have developed a comprehensive research paper that documents:
*   The **hardware prototype** design and integration.
*   The **algorithm** used for low-latency, offline voice recognition.
*   **Performance metrics** comparing response times and accuracy against existing solutions.

> **Paper Title:** *[To Be Announced]*
>
> **Abstract:**
> *[Placeholder for Abstract: This research presents a novel, offline-first approach to personal safety wearables...]*

*Once the paper is published, the full citation and a link to the document will be made available in this section.*

## 🚀 Key Features

*   **Voice Activation:** Uses **Vosk** for accurate, offline speech recognition to detect distress keywords.
*   **Secure Trigger:** Requires a user-defined security code to prevent false positives (e.g., "Help [Code]").
*   **Real-Time Alerts:**
    *   **SMS Notification:** Sends an immediate text message with a Google Maps link to the user's location.
    *   **SOS Call:** Initiates an automated voice call to emergency contacts with a distress message.
*   **Geolocation Tracking:** Fetches the current location using IP-based geolocation services.
*   **Web Interface:** Simple, user-friendly dashboard to set security codes and monitor recognized speech in real-time.
*   **Hardware Integration:** Designed to run on specific prototype hardware.

## 🛠️ Technology Stack

*   **Backend:** Python, Flask
*   **Speech Recognition:** Vosk (Offline ASR), Kaldi
*   **Communication:** Twilio API (SMS & Voice)
*   **Geolocation:** IPinfo API
*   **Frontend:** HTML, CSS, JavaScript (Socket.IO for real-time updates)
*   **NLP:** Transformers (Hugging Face) for emotion analysis (experimental)

## 📋 Prerequisites

Before running the application, ensure you have the following:

*   Python 3.8+
*   A **Twilio** account (Account SID, Auth Token, and a Twilio phone number).
*   An **IPinfo** (or OpenCage) API token for geolocation.
*   **Vosk Model:** You need to download a Vosk language model (e.g., `vosk-model-en-us-0.22`).

## ⚙️ Installation

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/kavach.git
    cd kavach
    ```

2.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Download Vosk Model**
    *   Download a model from the [Vosk Models page](https://alphacephei.com/vosk/models).
    *   Extract the downloaded folder.
    *   Update the `model_path` variable in `app.py` to point to your extracted model directory.

4.  **Configure API Keys**
    Open `app.py` and update the following variables with your credentials:
    ```python
    OPENCAGE_API_KEY = "your_api_key" # IPinfo/OpenCage token
    TWILIO_ACCOUNT_SIDS = ["your_twilio_sid"]
    TWILIO_AUTH_TOKENS = ["your_twilio_auth_token"]
    TWILIO_PHONE_NUMBERS = ["your_twilio_number"]
    TO_PHONE_NUMBERS = ["emergency_contact_number"]
    ```
    *(Note: For production, it is recommended to use environment variables instead of hardcoding credentials.)*

## 🏃 Usage

1.  **Start the Application**
    ```bash
    python app.py
    ```

2.  **Access the Dashboard**
    Open your web browser and navigate to `http://localhost:5000`.

3.  **Set Security Code**
    Enter a unique security code (e.g., "1234") in the input field and click "Set Code".

4.  **Activate System**
    Click **"Start Listening"**. The system will now monitor audio input.

5.  **Trigger Alert**
    Say **"Help [Your Security Code]"** clearly.
    *   *Example:* "Help 1234"
    *   The system will detect the command, fetch your location, and send alerts to the configured numbers.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

[License Name] - See the [LICENSE](LICENSE) file for details.

## 📞 Contact

For inquiries regarding the research paper or hardware prototype, please contact the repository owners.