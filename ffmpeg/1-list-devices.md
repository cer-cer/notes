# List Devices On Mac

## By API
I want to list all devcies on my mac, and choose to recod audio or vido. so first i read the document and hope use the API to print it. This is the code i used.

```
#include <stdlib.h>
extern "C"{
#include "libavformat/avformat.h"
#include "libavdevice/avdevice.h"
}

AVProbeData* pdata = NULL;

int main(int argc, const char * argv[]) {
    // insert code here...
    avdevice_register_all();
    
    
    printf("%d\n", avdevice_version());
    AVInputFormat *iformat = NULL;
    
    do{
        iformat = av_input_video_device_next(iformat);
        AVDeviceInfoList *list = NULL;
        
        avdevice_list_input_sources(iformat, NULL, NULL, &list);
        
        if (list){
            printf("%d", list->nb_devices);
        }
    }while(iformat);
    
    
    
    
    return 0;
}

```
But sadnessly that it show nothing. i don't know why. 

## By Command.
I got nothing when i used API to list devices, so i use the ffmpeg command. as below:
```
./ffmpeg -f avfoundation -list_devices true -i ""
```
you can get the suggestion command as [here](https://ffmpeg.org/ffmpeg-devices.html) `https://ffmpeg.org/ffmpeg-devices.html`
luckly, the result as below:
![image list devices](./asset/list-devices1.jpg)

I want to know the reason, why i can't get the list by my command, and why the ffmpege command has a errro message. but also it list all the devices in my mac.
I will read the ffmpeg souce code, and find the root cause which can be resolve my problem.

