### 0.7.0b
- New:    Calculation can be cancelled
- New:    UI: VMAF model can be selected
- New:    UI: Only small part of video can be processed (pre-defined set on options: 5, 10, 30, 60 seconds, whole file)
- New:    New command line option "-log-level-debug" added (can be useful for investigating issues)
- New:    Error (if any) is shown in tooltip
- Change: UI: slightly re-designed
- Change: UNC paths should be supported now
- Change: VMAF model files now should be in "vmaf-model" sub-folder
- Change: Files limit increased from 10 to 12
- Change: Target changed back to .NET 4.7.2 (included in Windows 10 1803+, older versions of Windows will require .NET 4.7.2 installation)
- Change: Internal changes and optimizations
- Bugfix: Race conditions while working with external process in background thread should be fixed


### 0.6.5b
- Change: Warnings written in log
- Change: Improved ffmpeg.exe version detection routine
- Bugfix: Unhandled exception when model file(s) were missing


### 0.6.4b
- Change: Target changed from .NET 4.7.2 to .NET 4.5.2 (included in Windows 10, Windows 7/8 will require .NET 4.5.2 installation)


### 0.6.3b
- New:    Selected files on a list can be excluded from analyzing / graphs


### 0.6.2b
- New:    Added ability to select metrics for processing
- Change: Program do not even trying to create FFMetrics.log until it is really needed
- Bugfix: Clear button did not work correctly
- Bugfix: Program was not shown in taskbar


### 0.6.1b
- Initial public release
