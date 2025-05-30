🎵 Alexa Media Player – MP3 Converter Tool
Convert your .mp3 files into a format compatible with Alexa Media Player in Home Assistant.
video here: https://youtu.be/Jkkq9sz5s-k

📥 Download
🔗 Download the tool (7-Zip format):
https://github.com/LazyTechGeek/Alexa-Media-Player/blob/main/MP3ToAlexaConverter.7z
⚠️ Requires 7-Zip or another tool that supports .7z files.

🛠️ How to Use
1. Extract the MP3ToAlexaConverter.7z file to a folder on your computer.
2. Copy your .mp3 audio files into the same folder.
3. Run the batch file: MP3Convert.bat
4. The tool will convert all .mp3 files using ffmpeg and output new versions with -Converted added to the filename.

Example:
sample.mp3 → sample-Converted.mp3

# Automation (run once version)
https://github.com/LazyTechGeek/HomeAssistant-Alexa-Media-Player-MP3/blob/main/youve-got-mail-single-play.yaml

# Automation (run twice version)
https://github.com/LazyTechGeek/HomeAssistant-Alexa-Media-Player-MP3/blob/main/youve-got-mail-double-play.yaml

# Node-Red process flow code

``
[{"id":"d661bde1214894b5","type":"trigger-state","z":"178ec14a61e21081","name":"Mailbox Sensor","server":"4","version":5,"inputs":0,"outputs":2,"exposeAsEntityConfig":"","entities":{"entity":["binary_sensor.vibration_sensor_postbox_vibration"],"substring":[],"regex":[]},"debugEnabled":false,"constraints":[{"targetType":"this_entity","targetValue":"","propertyType":"previous_state","propertyValue":"old_state.state","comparatorType":"is","comparatorValueDatatype":"str","comparatorValue":"off"},{"targetType":"this_entity","targetValue":"","propertyType":"current_state","propertyValue":"new_state.state","comparatorType":"is","comparatorValueDatatype":"str","comparatorValue":"on"}],"customOutputs":[],"outputInitially":false,"stateType":"str","enableInput":false,"x":134.66667938232422,"y":153.666654586792,"wires":[["966314c1e9a5cf70"],[]]},{"id":"c41a3c1e467ddee8","type":"api-call-service","z":"178ec14a61e21081","name":"Play MP3 File","server":"4","version":7,"debugenabled":false,"action":"notify.alexa_media_dave_s_echo_spot","floorId":[],"areaId":[],"deviceId":[],"entityId":[],"labelId":[],"data":"{\"message\":\"<audio src='https://4321demodave.duckdns.org/local/mp3/mail.mp3'/>\",\"data\":{\"type\":\"tts\"}}","dataType":"json","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"notify","service":"alexa_media_dave_s_echo_spot","x":570.7811737060547,"y":153.666654586792,"wires":[["ada777a83590733d"]]},{"id":"ada777a83590733d","type":"delay","z":"178ec14a61e21081","name":"","pauseType":"delay","timeout":"5","timeoutUnits":"seconds","rate":"1","nbRateUnits":"1","rateUnits":"second","randomFirst":"1","randomLast":"5","randomUnits":"seconds","drop":false,"allowrate":false,"outputs":1,"x":752.774284362793,"y":153.666654586792,"wires":[["fd370288dddb784d"]]},{"id":"fd370288dddb784d","type":"api-call-service","z":"178ec14a61e21081","name":"Play MP3 File","server":"4","version":7,"debugenabled":false,"action":"notify.alexa_media_dave_s_echo_spot","floorId":[],"areaId":[],"deviceId":[],"entityId":[],"labelId":[],"data":"{\"message\":\"<audio src='https://4321demodave.duckdns.org/local/mp3/mail.mp3'/>\",\"data\":{\"type\":\"tts\"}}","dataType":"json","mergeContext":"","mustacheAltTags":false,"outputProperties":[],"queue":"none","blockInputOverrides":true,"domain":"notify","service":"alexa_media_dave_s_echo_spot","x":981.8958740234375,"y":153.666654586792,"wires":[[]]},{"id":"966314c1e9a5cf70","type":"delay","z":"178ec14a61e21081","name":"Limit per 5 mins","pauseType":"rate","timeout":"5","timeoutUnits":"seconds","rate":"1","nbRateUnits":"5","rateUnits":"minute","randomFirst":"1","randomLast":"5","randomUnits":"seconds","drop":true,"allowrate":false,"outputs":1,"x":328.7812328338623,"y":153.666654586792,"wires":[["c41a3c1e467ddee8"]]},{"id":"c0b33b445a162823","type":"comment","z":"178ec14a61e21081","name":"Sensor","info":"","x":105.33338928222656,"y":94.66667366027832,"wires":[]},{"id":"208c78f360333bb3","type":"comment","z":"178ec14a61e21081","name":"Ignore request for minutes","info":"","x":355.6667251586914,"y":94.66667556762695,"wires":[]},{"id":"f70952612c1b55cc","type":"comment","z":"178ec14a61e21081","name":"Play mp3 File","info":"","x":561.6666717529297,"y":92.66667556762695,"wires":[]},{"id":"a0259fe92699262c","type":"comment","z":"178ec14a61e21081","name":"Play mp3 File","info":"","x":971.6666851043701,"y":92.66667556762695,"wires":[]},{"id":"e637bedeebab801f","type":"comment","z":"178ec14a61e21081","name":"Wait 5 Seconds","info":"","x":771.6666793823242,"y":94.66667461395264,"wires":[]},{"id":"4","type":"server","name":"Home Assistant","addon":true,"rejectUnauthorizedCerts":true,"ha_boolean":"","connectionDelay":false,"cacheJson":false,"heartbeat":false,"heartbeatInterval":"","statusSeparator":"","enableGlobalContextStore":false}]
``
