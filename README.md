# Talking-robot
mport pyttsx3
heres all the codes python
# STEP 1: Convert audio to text
def audio_to_text(audio_path):
    # Replace this with your preferred speech recognition API
    import speech_recognition as sr
    recognizer = sr.Recognizer()
    with sr.AudioFile(audio_path) as source:
        audio = recognizer.record(source)
    try:
        return recognizer.recognize_google(audio)
    except sr.UnknownValueError:
        return "Sorry, I could not understand the audio."
    except sr.RequestError:
        return "Speech recognition service is unavailable."

# STEP 2: Generate response using an LLM
def generate_response(prompt):
    # Replace this with your preferred LLM API call (e.g., Cohere, Hugging Face, etc.)
    # Placeholder simple logic
    return "You said: " + prompt

# STEP 3: Convert text to speech
def text_to_audio(text):
    engine = pyttsx3.init()
    engine.say(text)
    engine.runAndWait()

# Combine everything
def process_audio(audio_path):
    print("Transcribing...")
    user_input = audio_to_text(audio_path)
    print("Recognized:", user_input)

    print("Generating response...")
    reply = generate_response(user_input)
    print("Response:", reply)

    print("Converting response to speech...")
    text_to_audio(reply)
Install them using pip:
pip install SpeechRecognition pyttsx3 pyaudio
