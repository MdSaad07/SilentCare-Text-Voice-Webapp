# 🧠 Voice/Text-Based Mental Health Chatbot

A voice and text-enabled mental health chatbot built with Flask and a deep learning model using TensorFlow/Keras. It allows users to interact via speech or text, get helpful responses, and also includes sentiment analysis to better understand users' emotions.

## ✨ Features

- 🤖 NLP-based chatbot with LSTM model  
- 🎙️ Voice input using Web Speech API  
- 🔊 Text-to-speech output for bot responses  
- 📊 Sentiment-aware response tuning  
- 🧠 Suicide-related keyword detection with emergency guidance  
- 💾 Model training & saving using `intent.json` patterns  
- 🌐 Flask-based backend with interactive frontend UI  

---

## 🗃️ Project Structure

```
├── app.py                # Main Flask app with chatbot logic
├── intent.json           # Training data with intents, patterns & responses ✅
├── chatbot_model.h5      # Trained model (auto-generated)
├── tokenizer.pkl         # Tokenizer (auto-generated)
├── labelencoder.pkl      # Label encoder (auto-generated)
├── templates/
│   └── index.html        # Frontend chat interface
├── static/
│   └── script.js         # Frontend JavaScript (voice, chat logic)
```

---

## 🧾 `intent.json` - Intent Data Format

The `intent.json` file contains training data structured in a simple JSON format. Each intent includes:

- `tag`: the label for the intent  
- `patterns`: list of user inputs the bot should recognize  
- `responses`: list of potential bot replies  

### Example:

```json
{
  "intents": [
    {
      "tag": "greeting",
      "patterns": ["Hi", "Hello", "Hey", "Good morning"],
      "responses": ["Hello! How can I help you today?", "Hi there, what’s on your mind?"]
    },
    {
      "tag": "sadness",
      "patterns": ["I am feeling sad", "I'm depressed", "I feel low"],
      "responses": ["I'm here for you. Want to talk about it?", "It’s okay to feel down sometimes."]
    }
  ]
}
```

> 📝 You can expand the file with more tags to improve chatbot understanding.

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/chatbot.git
cd chatbot
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the App

```bash
python app.py
```

Visit [http://127.0.0.1:5000](http://127.0.0.1:5000) in your browser.

---

## 🧠 How it Works

1. User sends a message via text or voice.  
2. The message is cleaned and tokenized.  
3. A trained LSTM model classifies the intent and selects a suitable response.  
4. Sentiment of the message is analyzed to adjust the tone of the response.  
5. Bot replies and reads the message aloud (TTS).  
6. Suicide-related keywords are detected to provide emergency help.

---

## 📦 API Endpoint

### `/chat` (POST)

**Request:**
```json
{
  "message": "I'm feeling very low"
}
```

**Response:**
```json
{
  "response": "I'm really sorry you’re feeling this way. I’m here to listen—want to tell me more?",
  "confidence": 93.75
}
```

---

## 📞 Emergency Support

If a user mentions:
- "kill myself"  
- "want to die"  
- "commit suicide"  

> The bot provides emotional support and shares a helpline: **9152987821**

---

## 🔮 Future Scope

- ✋ **Sign Language Integration**:  
  A **sign language detection module** is being developed separately and will be integrated into this chatbot in future updates. This will make the system accessible for users with speech and hearing impairments, completing the multi-modal communication capability.

---

## 👨‍💻 Authors

- **Mohammed Saad Fazal**  
- [Mohammed Kaifulla Kazim]([https://github.com/kaifulla-kazim])


---
