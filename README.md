## FFMetrics — yet another program for video Visual Quality Metrics visualization

FFMpeg can be used for calculating different visual quality metrics (PSNR, SSIM, VMAF). 
FFMetrics is a FFMpeg GUI that purpose is to visualize the metrics calculated by FFMpeg.
The program allows you to select analyzed files without dealing with command line, calculate and visualize the quality metrics for all of them in one go.

Well, and build shiny interactive graphs of course:

<p align="center"><img src="screenshots/screenshot.png" width="919"/></p>



## Features
- PSNR, SSIM, VMAF visual quality metrics
- Easy to use UI: drag & drop files from Explorer onto Reference field and Files list or use file choosers
- Processing up to 12 files in one go
- No limitations on frame size for PSNR/SSIM, Full HD/4K for VMAF
- Frames graphs can be zoomed in/out with mouse wheel (try it over graph or axes), panned with right mouse button and saved as PNG
- Frames metrics can be saved as tab-delimited csv files that can be opened in Excel. Files are created aside of analyzed files and named as filename.mp4.PSNR.csv.
- FFMpeg commands can be saved to log file (FFMetrics.log)
- Average metrics can be saved to tab-delimited csv file (FFMetrics.Results.csv) with date/time and file name included 
- VMAF model can be choosen from UI (4K videos require different model)
- Only parts of video files could be analyzed
- You can run the program suppliying most options as command line parameters.



## Latest version: [0.8.1 Beta](https://github.com/fifonik/FFMetrics/releases/tag/v0.8.1)



## Requirements
- .NET Framework 4.7.2+. Program should notify if you need to install it.
  The framework is already included in Windows 10 1803 and above, but if you use earlier versions of Windows 10 or Windows 7/8, you will be asked to [download](https://dotnet.microsoft.com/download/dotnet-framework/net472) and install it.
- FFMpeg.exe. You need to download it from [official web site](https://ffmpeg.org/download.html) (choose static build for simplicity).
- VMAF metric require special FFMpeg's build. It is supported in stable version 4.3.
  In addition, VMAF model files must be in sub-folder "vmaf-models". Two the most common models are already included in archive. You can get other models from [Netflix VMAF project](https://github.com/Netflix/vmaf/)



## How to use
- Unpack into a folder
- Put FFMpeg.exe (and accompanied dll files if you use dynamic build) into the program folder or make it available through system %PATH%
- Run the program
- Use UI to add reference file and at least one processing file. You can drop files from Explorer or use file choosers.
- Click "Start" button


## How to run with command line options
**FFMetrics.exe \[options\] ref.mp4 file1.mp4 \[file2.mp4\] \[file3.mp4\] \[...\]**

### Accepted options
    -log-frames                    Log frames' metrics in csv files
    -log-frames-dir=C:\path\       Folder where frame's metrics will be stored
    -log-commands                  Log ffmpeg commands
    -run                           Run calculation when program started
    -save-results                  After calculation save results to log
    -save-results-file=C:\path\file.csv
    -metric=PSNR|SSIM|VMAF         Default: all
    -vmaf-model=filename.pkl       Default: vmaf_v0.6.1.pkl
    -vmaf-harmonic-mean
    -vmaf-phone-model
    -log-level=DEBUG|ERROR|INFO    Default: INFO

#### Examples
`FFMetrics.exe \\server\path\to\ref.mp4 "c:\path\to\my file.mp4"`<br />
`FFMetrics.exe -log-frames -metric=SSIM -metric=VMAF -run c:\path1\ref.mp4 c:\path2\file1.avi c:\path2\file2.avs`


## Limitations
- No MSE. No libvmaf's PSNR & SSIM (ffmpeg can calculate PSNR & SSIM in two different ways and values that you can get using different methods are not exactly the same)
- ffmpeg.exe sometimes gives too low results (to be investigated)



## Author
fifonik



## Discussions
- [Discussion in Vegas forum](https://www.vegascreativesoftware.info/us/forum/ffmetrics-yet-another-program-for-quality-metrics-calculation--122246/) (in English)
- [Discussion in IXBT forum](https://forum.ixbt.com/topic.cgi?id=29:36847) (in Russian)
