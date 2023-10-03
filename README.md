# Speech-To-Text-ASR  
  
**IndianTTS**, AI driven technology firm, dedicated to solve complex business problems with Intelligent Speech Solutions.

Accuracy is subject to quality of data being served into our speech engine. We will put our best efforts to provide higher accuracy on every dataset. We use language and domain specific models. Speech to text services available in multiple language.

**We provide 3 type for ASR Services**
- Audio file length should be less than 1 Minute.
- Audio file length more than 1 Minute.
- Wehshocket method to get text in realtime on audio stream.

## (1) Details for  Audio file length should be less than 1 Minute.
Get text from audio
• 

*   URL   https://asr-api.vspeech.ai/api/asr/v1
*   Method:  PUT/POST
*   Data Params – All params must

    **audio_base64** : [string] – Wav file base64 buffer string  
    **modelID** : [string] – Model ID()  
    **command** : [string] – Commad name – transcribe  
    **ID** : [string] – Unique Request ID,  Use UUID  
    **userID** : [string] – User ID()  
    **mode** : [string] – Environment   - dev  

API  Format - 

Curl Sample Command :-

POST 
``` 
curl -F "audio_base64=@test_8Khz.wav" -F 'metadata={"ID":"test-1234","modelID":"XXX","mode":"dev","command":"transcribe","userID":"XXXXX"}' -X POST https://asr-api.vspeech.ai/api/asr/v1
```
