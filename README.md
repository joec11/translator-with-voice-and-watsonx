# Translator with Voice and Watsonx

* <b>Set up the environment</b>

<pre>
pip3 install virtualenv
virtualenv venv
source venv/bin/activate

pip3 install -r requirements.txt
</pre>

* <b>Run the Application</b>

<pre>
python3 server.py
</pre>

* <b>Curl to test Speech-to-Text (STT)</b>

<pre>
curl https://sn-watson-stt.labs.skills.network/speech-to-text/api/v1/models

curl "https://github.com/watson-developer-cloud/doc-tutorial-downloads/raw/master/speech-to-text/0001.flac" -sLo example.flac
curl "https://sn-watson-stt.labs.skills.network/speech-to-text/api/v1/recognize" --header "Content-Type: audio/flac" --data-binary @example.flac
</pre>

* <b>Curl to test Text-to-Speech (TTS)</b>

<pre>
curl https://sn-watson-tts.labs.skills.network/text-to-speech/api/v1/voices

curl "https://sn-watson-stt.labs.skills.network/text-to-speech/api/v1/synthesize" --header "Content-Type: application/json" --data '{"text":"Hello world"}' --header "Accept: audio/wav" --output output.wav
curl "https://sn-watson-stt.labs.skills.network/text-to-speech/api/v1/synthesize?voice=es-LA_SofiaV3Voice" --header "Content-Type: application/json" --data '{"text":"Hola! Hoy es un dia muy bonito."}' --header "Accept: audio/mp3" --output hola.mp3
</pre>
