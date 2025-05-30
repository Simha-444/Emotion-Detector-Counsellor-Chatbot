# 🧠 Emotion Detector & Counsellor Chatbot

An AI-powered chatbot designed to detect emotional distress in users and provide empathetic, CBT-inspired counseling responses. This tool is intended to help teens cope with cyberbullying, anxiety, depression, and other emotional challenges by offering a safe, private space to express themselves.

---

## 🌐 Live Demo (Coming Soon)

The application will be deployed using Streamlit / Flask on platforms like Heroku, AWS, or GCP.

---

## 💡 Problem Statement

Cyberbullying and emotional challenges among teens have become widespread in today's digital world. Many teenagers are hesitant to share their problems with parents or seek professional help. This chatbot aims to:

- Detect emotional distress through natural language inputs.
- Provide real-time, empathetic responses using CBT techniques.
- Offer a non-judgmental space for self-expression.
- (Future) Alert guardians in cases of suicidal ideation.

---

## 🧰 Tech Stack

| Category        | Technology                |
|----------------|---------------------------|
| Programming     | Python 3.10+              |
| Deep Learning   | TensorFlow / Keras        |
| NLP             | Gensim, NLTK              |
| Data            | Sentiment140 (1.6M Tweets)|
| Model           | LSTM                      |
| Dialogue System | Decision Tree             |
| UI              | Streamlit / Flask         |
| Hosting         | Heroku / AWS / GCP        |

---

## 🧠 Model Architecture

- **Embedding Layer**: Converts words to 32-dim vectors
- **LSTM Layer**: 128 hidden units
- **Dense Output**: 1 neuron with sigmoid activation
- **Loss Function**: Binary Crossentropy
- **Optimizer**: Adam (with Nesterov momentum)

### Preprocessing
- Removal of hashtags, mentions, URLs
- Tokenization using Gensim
- Padding to fixed sequence length (20)
- Tweets shorter than 2 words discarded

---

## 📊 Dataset

- **Training**: 1.6M tweets labeled as positive (4) and negative (0)
- **Validation**: 20% of training data
- **Testing**: 494 tweets with 3 labels: positive (4), neutral (2), negative (0)
- **Label Normalization**: Mapped to binary (0: Negative, 1: Positive)

---

## 🤖 Chatbot Dialogue Engine

Implemented using a decision tree for flow control:

```text
IF sentiment == negative:
   IF emotion == "sad":
      RESPOND("I'm here for you. Want to talk about it?")
   IF emotion == "angry":
      RESPOND("It's okay to be upset. Do you want to vent?")
ELSE:
   RESPOND("That's great! Keep it up!")
