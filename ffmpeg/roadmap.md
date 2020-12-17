- parameter parse & get options
  - global options
  - codec
  - format
  - sdl
- read list devices
  1. get `AVInputFormat` from `av_find_input_format("avfoundations")`.
  2. set the `OptionGroup` from `AVInputFormat`'s `pri_data`
  3. create `avformat_alloc_context` from `avformat_alloc_context` 
  4. list devices out put by `avformat_open_input`.
```
filename: -i "none: none"
options: -list_devices true
```

- capture the devices
  - the access to mac(c++ application)
  copy the `Info.plist` to the direction same as ffmpeg
  - list the devices supported
  `ffmpeg -f avfoundations -list_devices true -i "none:none"`
  - open cameras
  `ffmpeg -f avfoundations -i "0:none" out.avi`
  - open screen captures
  `ffmpeg -f avfoundations -i "1:none" out.avi`
