## NAME: RAMYA P
## REGISTER NO:212223230168
## EX. NO.8

<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>

## Aim:

 To implement the conversion of live speech to text.
 
## Algorithm:

Step 1: Import the speech_recognition library


Step 2: Initialize the Recognizer


Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.


Step 4: Set the duration for audio capture


Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.


Step 6: Display a message in the console to prompt the user to speak.


Step 7: Capture audio from the default microphone


Step 9: Use the default microphone as the audio source.


Step 10: Record audio for the specified duration using the Recognizer instance.


Step 11: Perform speech recognition with exceptional handling:


•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.


•	If successful, print the recognized text.


•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.


•	A generic exception block captures any other unexpected errors.


## Program:

```
import speech_recognition as sr

r = sr.Recognizer()
duration = 15

print("Say something... (you have 15 seconds)")

try:
    with sr.Microphone() as source:
        r.adjust_for_ambient_noise(source)
        print("Listening...")
        audio_data = r.listen(source, timeout=duration)
        print("Processing...")

    text = r.recognize_google(audio_data)
    print("You said:", text)

except sr.WaitTimeoutError:
    print("No speech detected in given time.")
except sr.UnknownValueError:
    print("Sorry, could not understand the audio.")
except sr.RequestError as e:
    print(f"Error with the request to Google Speech Recognition service: {e}")
except Exception as e:
    print(f"Error: {e}")
```

## Output:

<img width="312" height="74" alt="image" src="https://github.com/user-attachments/assets/15c4fd22-c833-4c2a-96ca-a89f23b09a1b" />


## Result:
Thus, the live speech was successfully converted into text using the Speech Recognition library in Python.
