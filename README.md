## Video Streaming with Flask Example

### Description
Modified to support streaming out with webcams, and not just raw JPEGs.

### Credits
Most of the code credits to Miguel Grinberg, except that I made a small tweak. Thanks!
http://blog.miguelgrinberg.com/post/video-streaming-with-flask

### Usage
1. Install Python dependencies: cv2, flask. (wish that pip install works like a charm)
2. Run "python main.py".
3. Navigate the browser to the local webpage(http://localhost:3000).

Audio-based detection
	Just using imaging processing to detect humans in fire rescue situation won’t be enough. Presence of Fire and smoke induce too much noise in Video streams. We need additional methods which are as reliable in detecting humans.
One ideal condition will say that human’s are to cry for help when stuck in fire situations.  Audio inputs collected via microphone installed in robot can be processed to identify human speech hence assuring human presence in the scene.
(1)VAD	

	[VAD] = >  https://ibb.co/fMWGwPP


	Voice Activity Detection (VAD), also known as speech activity detection or speech detection, is a technique used in speech processing in which the presence or absence of human speech is detected. The main uses of VAD are in speech coding and speech recognition but we will only use speech recognition here.
The typical design of a VAD algorithm is as follows: 
⦁	There may first be a noise reduction stage.
⦁	Then some features or quantities are calculated from a section of the input signal.
⦁	A ⦁	classification rule is applied to classify the section as speech or non-speech – often this classification rule finds when a value exceeds a threshold.
There may be some feedback in this sequence, in which the VAD decision is used to improve the noise estimate in the noise reduction stage, or to adaptively vary the threshold(s). These feedback operations improve the VAD performance in non-stationary noise (i.e. when the noise varies a lot).
here are many voice detection technique already exists like CMU Sphinx, Julius, kaidi, Bing, SILVIA, Vlingo, Microsoft Tellme, Ask Ziggy, wavelet etc. Among these technique wavelet is used and compressed signal by wavelet technique and which gives better results for lossless compression. Hence we will be using wavelet technique in our project for VAD.

The above image show how a voiced signal with significant noise can be treated using Wavelet algorithm.

(2) Heart-beat/breath detection(Hypothesis)
	
	Making human detection system near-to 100% can be done if we can detect Heart-beat/breath at least from distance roughly 10m. Heart-beat and breath are merely miliV signals and will be impossible to detect but we are considering that if we can apply proper filters and given a proper algorithm we can detect heart-beat from atleast 5m. It is still to be practically approved but we are trying to include it in our human detection system
