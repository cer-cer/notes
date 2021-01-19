### list device 
```
./ffmpeg -f avfoundation -list_devices true -i ""
```
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
  5. `avf_read_header`list the devices and check the input file.
```
filename: -i "none: none"
options: -list_devices true
```
- core data struct
  - AVOption
  `AVOption` 描述了 `AVClass` 的属性，类型，以及在struct中的offset(`offsetof()`)。
  - AVClass
  `AVClass` 作为ffmpeg中大多数struct的第一个元素，描述了struct中可以被option设置的类型，范围等信息。可以看作一个struct的元描述。
  
- base data type
  - AVDictionary
    - av_dict_set 
    - av_dict_free
    
  
### capture the devices
  - the access to mac(c++ application)
  copy the `Info.plist` to the direction same as ffmpeg
  - list the devices supported
  `ffmpeg -f avfoundations -list_devices true -i "none:none"`
  - open cameras
  `ffmpeg -f avfoundations -i "0:none" out.avi`
  - open screen captures
  `ffmpeg -f avfoundations -i "1:none" out.avi`


### 参考
- [ffmpeg 使用基础](https://www.cnblogs.com/leisure_chn/p/10297002.html)
