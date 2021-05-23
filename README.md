## FFMetrics — yet another program for video Visual Quality Metrics visualization

FFMpeg can be used for calculating different visual quality metrics (PSNR, SSIM, VMAF). 
FFMetrics is a FFMpeg GUI that purpose is to visualize quality metrics calculated by FFMpeg.
The program allows you to select files without dealing with command line, calculate & visualize PSNR, SSIM & VMAF quality metrics for all of them in one go.

Well, and build shiny interactive graphs of course:

<p align="center"><img src="screenshots/screenshot.png" width="919"/></p>



## Features
- PSNR, SSIM, VMAF visual quality metrics
- Processing up to 12 files in one go
- No limitations on frame size for PSNR/SSIM, Full HD/4K for VMAF
- Brief media info for reference and distorted files
- Ref's thumbnail 
- Bad frames can be extracted as PNG images for further analisys
- Only parts of video files can be analyzed
- Easy to use UI: drag & drop files from Explorer onto Reference field and Files list or use file choosers 
- Frames graphs can be zoomed in/out with mouse wheel (try it over graph or axes), panned with right mouse button and saved as PNG
- Frames metrics can be saved as tab-delimited csv files and then opened in Excel
- FFMpeg commands can be saved to log file (FFMetrics.log)
- Average metrics, frames statistics, frame size, bitrate, date/time and file name can be saved to tab-delimited csv file (appended) and then opened in Excel
- Proper VMAF model selected automatically based on reference media info, but can be changed using UI
- Supported VMAF model type (pkl or json) detected automatically
- Most program options could be supplyed as command line parameters



## Latest version: [0.9.7 Beta](https://github.com/fifonik/FFMetrics/releases/tag/v0.9.7)



## Requirements
- .NET Framework 4.7.2+. Program should notify if you need to install it.
  The framework is already included in Windows 10 1803 and above, but if you use earlier versions of Windows 10 or Windows 7/8, you may be asked to [download](https://dotnet.microsoft.com/download/dotnet-framework/net472) and install it.
- FFMpeg.exe. You need to download it from [official web site](https://ffmpeg.org/download.html) (choose static build for simplicity).
- VMAF metric require special FFMpeg's build. It is supported since version 4.3 (stable).
  In addition, VMAF model files must be in sub-folder "vmaf-models". The most common models are already included in archive. You can get other models from [Netflix VMAF project](https://github.com/Netflix/vmaf/)



## How to use
- Unpack into a folder
- Put FFMpeg.exe (and accompanied dll files if you use dynamic build) into the program folder or make it available through system %PATH%
- Run the program
- Use UI to add reference file and at least one distorted file (you can drag & drop files from Explorer or use file choosers).
- Click "Start" button


## How to run with command line options
**FFMetrics.exe \[options\] ref.mp4 file1.mp4 \[file2.mp4\] \[file3.mp4\] \[...\]**

### Accepted options
    -duration=<seconds>                    Duration of video stream to be processed
                                           Default: 0 (whole stream used)
    -log-commands                          Log ffmpeg commands
    -log-frames                            Log frames' metrics in csv files
    -log-frames-dir=C:\path\               Folder where frame's metrics will be stored
    -log-level=DEBUG|ERROR|INFO            Default: INFO
    -metric=PSNR|SSIM|VMAF                 Default: all (-metric=PSNR -metric=SSIM -metric=VMAF)
    -project=C:\path\to\project.ffmproj    Read project options from specified file
    -run                                   Run calculation when program started
    -save-results                          After calculation save results to log
    -save-results-file=C:\path\file.csv
    -scaling-method=NEIGHBOR|GAUSS|BILINEAR|BICUBIC|LANCZOS|SINC|SPLINE
                                           Default: BICUBIC
    -vmaf-model=filename.pkl               Default: vmaf_v0.6.1.pkl
    -vmaf-pool=MEAN|HARMONIC_MEAN          Default: MEAN
    -vmaf-phone-model

#### Examples
`FFMetrics.exe \\server\path\to\ref.mp4 "c:\path\to\my file.mp4"`<br />
`FFMetrics.exe -log-frames -metric=SSIM -metric=VMAF -run c:\to\ref.mp4 c:\to1\file1.avi c:\to2\file2.avs`<br />
`FFMetrics.exe -project=c:\path\to\project.ffmproj -vmaf-pool=harmonic_mean -run`<br />


## Limitations
- No MSE
- No libvmaf's PSNR & SSIM (ffmpeg can calculate PSNR & SSIM in two different ways and values that you can get using different methods are not exactly the same)
- You have to be careful and supply video files in the same colour range or with correct meta with the colour range. Otherwise ffmpeg.exe could make incorrect transformation and give you incorrect results ([more details](https://www.vegascreativesoftware.info/us/forum/magicyuv-2-20-released--117638/?page=3#ca772279)). I do have plans to improve the program to prevent/minimize this happen.



## Author
fifonik



## Discussions
- [Discussion in Vegas forum](https://www.vegascreativesoftware.info/us/forum/ffmetrics-yet-another-program-for-quality-metrics-calculation--122246/) (in English)
- [Discussion in IXBT forum](https://forum.ixbt.com/topic.cgi?id=29:36847) (in Russian)
