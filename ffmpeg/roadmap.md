- parameter parse & get options
  - global options
  - codec
  - format
  - sdl
- read list devices
- capture the devices
  - the access to mac(c++ application)
  copy the `Info.plist` to the direction same as ffmpeg
  - list the devices supported
  `ffmpeg -f avfoundations -list_devices true "none:none"`
  - open cameras
  `ffmpeg -f avfoundations -i "0:none" out.avi`
  - open screen captures
  `ffmpeg -f avfoundations -i "1:none" out.avi`
