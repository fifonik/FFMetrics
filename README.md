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
- Frames graphs can be zoomed in/out with mouse wheel (try it over graph or axes) and panned with right mouse button
- Frames metrics can be saved as tab-delimited csv files that can be opened in Excel. Files are created aside of analyzed files and named as filename.mp4.PSNR.csv.
- FFMpeg commands can be saved to log file (FFMetrics.log)
- Average metrics can be saved to tab-delimited csv file (FFMetrics.Results.csv) with date/time and file name included 
- VMAF model can be choosen from UI (4K videos require different model)
- Only parts of video files could be analyzed



## Latest version: [0.7.0 Beta](https://github.com/fifonik/FFMetrics/releases)



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
- Click "Calculate" button



## Limitations
- Slower than [similar program](https://tools4vegas.com/render-quality-metrics-ffmpeg/) from @wwaag
- No MSE, no libvmaf's PSNR & SSIM (ffmpeg can calculate PSNR & SSIM in two different ways and values that you can get using different methods are not the same)
- ffmpeg.exe sometimes gives too low results (to be investigated)



## ToDo
- Command line options
- Metrics configuration
- Visual controls for graphs manipulating & saving
- Allow to specify folder for logs
- Allow to process more files in one go
- Separates graphs from main program window
- Icon



## Author
fifonik



## Discussions
- [Thread in Vegas forum](https://www.vegascreativesoftware.info/us/forum/ffmetrics-yet-another-program-for-quality-metrics-calculation--122246/) (in English)
- [Thread in IXBT forum](https://forum.ixbt.com/topic.cgi?id=29:36847) (in Russian)
