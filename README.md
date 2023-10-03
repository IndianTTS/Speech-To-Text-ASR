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
## (2) Details for  Audio file length more than 1 Minute.

*   URL Endpoint:- https://h5kfjte0x3.execute-api.ap-south-1.
*   Method:- PUT/POST/GET
*   Params:-

    **S3_URL**
    - Audio file URL
    - Only wav and mp3 audio format supported.

    **modelID**
    - Model ID
    - It will provide by Vspeech.ai team.

    **command**
    1. **transcribe**
    - It will provide transcription of Audio files.
    2. **segment**
    - It will provide segment with word timing and confidence score.

    **ID**
    - Unique request ID (UUID)

    **userID**
    - userID (API key)  (GfpMaS5kutCtVIktyJT1BM)
    - It will provide by Vspeech.ai team.

    **webhook**
    - Webhook URL, ASR response will POST in webhook url

    **lang  (Optional)**
    - Transcription language 
    - en for English
    - hi for Hindi
    - By Default its give Mix output.

  ### API Format :-

    For get Transcription:-  
    POST :-  
      ```javascript
      curl -X POST 'https://h5kfjte0x3.execute-api.ap-south-1.amazonaws.com/webhook' \
      -H 'Content-Type: application/json' \
      -d '{
            "S3_URL":"Any public access Audio URL",
            "modelID":32,
            "ID":"Use_UUID",
            "userID":"GfpMaS5kutCtVIktyJT1BM",
            "command":"transcribe",
            "webhook":" Webhook URL"
          }'
      ```

  ### Acknowledgement Status:-

  Request Verification:-

    - 1.1) Success:Send success acknowledgement  
        ```
        {
          status: 'success',
          message: 'Request Received Successfully',
          params:
          {
            S3_URL: < Audio File URL > ,
            modelID: < Model ID > ,
            ID: < Unique Request ID > ,
            userID: < User ID > ,
            webhook: < Webhool URL > ,
            mode: < Environment > ,
            command: < Commad Name >
          },
          timestamp: < Timestamp >
        }
        ```
    - 1.2) Params Error:Send acknowledgement with parameters error message  
        ```
        {
          status: 'fail',
          message: < Invalid Params Error >,
          params:
            {
              S3_URL: < Audio File URL > ,
              modelID: < Model ID > ,
              ID: < Unique Request ID > ,
              userID: < User ID > ,
              webhook: < Webhool URL > ,
              mode: < Environment > ,
              command: < Commad Name >
            },
          timestamp: < Timestamp >
        }
        ```
