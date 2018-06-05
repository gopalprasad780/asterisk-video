# asterisk-video

Following are steps to convert a video to asterisk compatible
ffasterisk -i Ad_30sec2.mp4 --profile=h263  -o Ad_30sec3.h263 -video
sox Ad_30sec3.wav -r 8000 Ad_30sec3.gsm
ffmpeg -i Ad_30sec3.mp4 -c:v mpeg2video -s 176X144 -f mp4 Ad_30sec2.mp4

ffmpeg -i samsung_old.mp4 -vn -acodec pcm_s16le -ac 1 -ar 16000 samsung.wav
