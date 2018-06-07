# asterisk-video
<p> Hello Guys, This guide is for those who is trying to Play video file in sip phone using Asterisk. </p>
<p> Asterisk is really good open source software that handle sip registration, managing dialplan, sipchannel, capabilities,etc at one place </p>

<h2> About me </h2>
<p> My Name is Gopal Prasad and am a Python Developer at Pvt Ltd Company.  I am sharing my experiences and problem faced during converting Video compatible with Asterisk. </p>
<p> Problem in short,  Asterisk will only passthrough video which it can understand. i.e, that is created by Asterisk only.</p>
<p> I have done various research on available resources on internet and found following steps that worked for me </p>

<h2> Requirement : </h2>
<ul>
  <li> ffasterisk - you can download this file from link <a href="http://karlsbakk.net/asterisk/ffasterisk-1.0.tar.gz"> ffasterisk </a> </li>
  <li> ffmpeg - It is the ultimate converter ever found. Here is link <a  href="https://ffmpeg.org/releases/ffmpeg-3.4.2.tar.gz"> ffmpeg </a></li>
  <li> SOX - Swiss army knife of sound processing. For this, you need to check package manager <b> apt</b> for debian and <b> yum </b> for Redhat/Centos </li>
  
  </ul>
<h3> Following are steps to convert a video to asterisk compatible </h3>
<p> ffasterisk -i Ad_30sec2.mp4 --profile=h263  -o Ad_30sec3.h263 -video </p>
sox Ad_30sec3.wav -r 8000 Ad_30sec3.gsm
ffmpeg -i Ad_30sec3.mp4 -c:v mpeg2video -s 176X144 -f mp4 Ad_30sec2.mp4

ffmpeg -i samsung_old.mp4 -vn -acodec pcm_s16le -ac 1 -ar 16000 samsung.wav
