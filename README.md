# Video Batcher

A modern Python desktop application for batch processing videos with randomized effects. Perfect for creating hundreds of variations with subtle alterations—ideal for content creators who need multiple unique versions of the same video.

## ⚡ New in v2.0

- **GPU Acceleration**: Automatic detection and support for NVIDIA, AMD, and Intel hardware encoders
- **Parallel Processing**: Process multiple variations simultaneously (up to 8 workers)
- **New Effects**: Saturation and Hue adjustments
- **Metadata Randomization**: Each video gets unique metadata for platform uniqueness
- **Smart Audio Sync**: Intelligent audio stream handling prevents sync issues
- **Progress Estimation**: Real-time calculation of remaining processing time
- **Detailed Logging**: Export comprehensive JSON logs with processing statistics

## Features

- **Batch Video Processing**: Generate hundreds of variations from a single video
- **Multiple Video Support**: Process multiple videos at once
- **GPU Acceleration**: Automatic hardware encoder detection (NVIDIA/AMD/Intel)
- **Parallel Processing**: Configure 1-8 workers for concurrent video processing
- **Randomized Effects**: Apply random adjustments within user-defined ranges
  - Brightness adjustment (%)
  - Contrast adjustment (%)
  - Saturation adjustment (%) - NEW!
  - Hue shift (degrees) - NEW!
  - Zoom effect (%)
  - Frame trimming (start and end)
  - Volume adjustment (dB)
- **Metadata Randomization**: Each video gets unique metadata (title, encoder info) for platform uniqueness
- **Smart Audio Handling**: Stream copying when possible for perfect audio sync
- **Real-Time Progress**: Progress bar with estimated time remaining
- **Processing Logs**: Export detailed JSON reports of all variations
- **User-Friendly GUI**: Clean, scrollable Tkinter interface
- **Local Processing**: Uses your computer's hardware—no cloud costs
- **Efficient Rendering**: Powered by FFmpeg for fast, high-quality video processing

## Requirements

### System Requirements
- Python 3.7 or higher
- FFmpeg (must be installed separately)
- Optional: NVIDIA/AMD/Intel GPU for hardware acceleration

### Python Dependencies
- tkinter (built-in with Python)
- All other dependencies are part of Python's standard library

## Installation

### 1. Install Python
Download and install Python from [python.org](https://www.python.org/downloads/)

Make sure to check "Add Python to PATH" during installation.

### 2. Install FFmpeg

FFmpeg is required for video processing. Choose your operating system:

#### Windows
**Easiest Method:**
1. Go to: https://www.gyan.dev/ffmpeg/builds/
2. Download: **ffmpeg-release-essentials.zip**
3. Extract to `C:\ffmpeg`
4. Add `C:\ffmpeg\bin` to your system PATH:
   - Press Windows key → type "environment variables"
   - Click "Edit the system environment variables"
   - Click "Environment Variables" → Select "Path" → Click "Edit"
   - Click "New" → Add `C:\ffmpeg\bin`
   - Click OK on all windows
5. Verify: Open new Command Prompt and run `ffmpeg -version`

#### macOS
Using Homebrew (recommended):
```bash
brew install ffmpeg
```

Verify installation:
```bash
ffmpeg -version
```

#### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install ffmpeg
```

Verify installation:
```bash
ffmpeg -version
```

### 3. Download This Application
1. Download all files from this repository
2. Keep all files in the same folder

## Usage

### Running the Application

1. Open a terminal/command prompt in the application folder
2. Run the application:
```bash
python main.py
```

### Using the Application

1. **Select Videos**: Click "Select Video Files (MP4/MOV)" to choose one or more videos
2. **Choose Output Folder**: Click "Select Output Folder" where variations will be saved
3. **Configure Processing Settings**:
   - **Variations per video**: Number of variations to generate (e.g., 10, 100, 500)
   - **Parallel workers**: Number of simultaneous processing threads (1-8)
     - Higher = faster processing, but more CPU/GPU usage
     - Recommended: 2-4 workers for most systems
   - **Use GPU Acceleration**: Enable/disable hardware encoding
     - App automatically detects available GPU encoders
     - GPU encoding is typically 3-5x faster than CPU
4. **Configure Master Controls**: Set min/max ranges for each effect:
   - **Brightness (%)**: -100 to 100 (default: -10 to 10)
   - **Contrast (%)**: -100 to 100 (default: -10 to 10)
   - **Saturation (%)**: -100 to 100 (default: -10 to 10) - For color intensity
   - **Hue (degrees)**: -180 to 180 (default: -15 to 15) - For color shifting
   - **Zoom (%)**: 0 to 50 (default: 0 to 10)
   - **Cut Start (frames)**: Frames to randomly trim from beginning
   - **Cut End (frames)**: Frames to randomly trim from end
   - **Volume (dB)**: -20 to 20 (default: -5 to 5)
   - **Note**: Metadata is automatically randomized for each video
5. **Start Processing**: Click "Start Batch Processing"
6. **Monitor Progress**: 
   - Watch the progress bar
   - See estimated time remaining
   - View current processing status
7. **Save Log** (optional): After processing, click "Save Log" to export detailed statistics
8. **Find Your Videos**: Variations will be saved in your output folder with names like:
   - `original_name_var_001.mp4`
   - `original_name_var_002.mp4`
   - etc.

## Example Settings

### Subtle Variations (for platform diversity)
Perfect for uploading to multiple platforms without detection:
- Brightness: -5% to 5%
- Contrast: -5% to 5%
- Saturation: -3% to 3%
- Hue: -5° to 5°
- Zoom: 0% to 3%
- Cut Start: 0 to 5 frames
- Cut End: 0 to 5 frames
- Volume: -2dB to 2dB
- **Workers**: 2-4
- **Note**: Metadata is automatically randomized

### Noticeable Variations (for testing/creative)
More dramatic differences between variations:
- Brightness: -15% to 15%
- Contrast: -15% to 15%
- Saturation: -20% to 20%
- Hue: -30° to 30°
- Zoom: 0% to 15%
- Cut Start: 0 to 15 frames
- Cut End: 0 to 15 frames
- Volume: -5dB to 5dB
- **Workers**: 2-4

### Maximum Speed Configuration
For fastest processing:
- **Workers**: 4-6 (adjust based on your CPU cores)
- **GPU Acceleration**: Enabled
- **Effects**: Minimal (fewer effects = faster processing)

## Tips

- **Start Small**: Test with 5-10 variations first to verify your settings
- **Disk Space**: Each variation will be roughly the same size as the original
  - Example: 50MB video × 100 variations = ~5GB of disk space needed
- **Processing Time**: 
  - **With GPU**: 30-second video = ~2-4 seconds per variation
  - **With CPU**: 30-second video = ~5-10 seconds per variation
  - **Parallel processing (4 workers)**: Can reduce total time by 3-4x
- **Quality**: Output uses H.264 video codec with AAC audio at good quality settings
- **Audio Sync**: App automatically uses stream copying when no volume changes are made, ensuring perfect audio sync
- **GPU Detection**: App will display detected GPU encoder on startup

## GPU Acceleration

### Supported GPUs
- **NVIDIA**: GTX 600 series and newer (uses h264_nvenc)
- **AMD**: Radeon RX 400 series and newer (uses h264_amf)
- **Intel**: 6th gen Core and newer with Quick Sync (uses h264_qsv)

### Performance Comparison
| Hardware | 30-sec Video | 100 Variations | 4 Workers |
|----------|-------------|----------------|-----------|
| CPU Only | ~8s each | ~13 minutes | ~3.5 minutes |
| NVIDIA GPU | ~2s each | ~3 minutes | ~45 seconds |
| AMD GPU | ~3s each | ~5 minutes | ~1.2 minutes |

*Times are approximate and vary by CPU/GPU model*

## Processing Logs

After batch processing, click "Save Log" to export a detailed JSON file containing:
- Total videos processed
- Success/failure counts
- Processing time per variation
- Applied settings for each variation
- GPU encoder used
- Error details (if any)

Log files are saved as: `processing_log_YYYYMMDD_HHMMSS.json`

## Troubleshooting

### "FFmpeg is not installed or not in PATH"
- Make sure FFmpeg is installed correctly
- Verify it's in your system PATH by running `ffmpeg -version` in terminal
- Restart your terminal/command prompt after installing FFmpeg

### Application won't start
- Make sure Python 3.7+ is installed: `python --version`
- Try running with: `python3 main.py` on macOS/Linux

### "No module named tkinter"
- On Linux, install: `sudo apt-get install python3-tk`
- On macOS/Windows, tkinter should be included with Python

### Variations look identical
- Increase the min/max ranges in Master Controls
- Verify FFmpeg is processing correctly by checking file sizes vary slightly
- Check the processing log for applied settings

### GPU acceleration not working
- Verify GPU encoder is detected (shown at top of app window)
- Update GPU drivers to latest version
- Try disabling GPU toggle and use CPU encoding

### Audio is out of sync
- v2.0 includes smart audio handling that prevents sync issues
- Audio is stream-copied when no volume changes are made
- When volume is adjusted, audio is re-encoded with proper sync flags

### Processing is too slow
- Enable GPU acceleration if available
- Increase parallel workers (try 4-6)
- Reduce number of applied effects
- Use a faster preset (note: app uses balanced settings by default)

### Application crashes during processing
- Reduce parallel workers to 1-2
- Check available RAM (video processing is memory-intensive)
- Try processing one video at a time
- Check FFmpeg error messages in terminal

## Performance Notes

- **GPU vs CPU**: GPU encoding is 3-5x faster but may have slightly different quality characteristics
- **Parallel Processing**: More workers = faster total time, but higher CPU/GPU/RAM usage
- **Stream Copying**: Audio is copied (not re-encoded) when no volume changes are applied, ensuring perfect sync
- **Memory Usage**: Each worker process uses memory; reduce workers if running low on RAM
- **Disk I/O**: Processing speed can be limited by hard drive speed (SSD recommended for best performance)

## File Formats

**Supported Input Formats:**
- MP4 (.mp4)
- MOV (.mov)

**Output Format:**
- MP4 with H.264 video and AAC audio
- Configurable quality (CRF 23 by default for good quality/size balance)

## Technical Details

### Video Processing Pipeline
1. Input video analysis (duration, FPS, codec info)
2. Random parameter generation within user-defined ranges
3. FFmpeg command construction with appropriate filters
4. GPU/CPU encoding based on settings
5. Smart audio handling (stream copy vs re-encode)
6. Output validation and logging

### FFmpeg Filters Used
- `eq`: Brightness, contrast, saturation adjustments
- `hue`: Hue shifting for color variations
- `scale` + `crop`: Zoom effect implementation
- `volume`: Audio volume adjustment
- Metadata handling: `-map_metadata -1` (strips original metadata) + random metadata injection
- Proper sync flags: `-async 1`, `-vsync cfr`, `-avoid_negative_ts make_zero`

## Credits

Built with:
- Python 3
- Tkinter (GUI framework)
- FFmpeg (video processing engine)
- ThreadPoolExecutor (parallel processing)

## Version History

**v2.0** (November 2025)
- Added GPU hardware acceleration with auto-detection
- Implemented parallel processing (1-8 workers)
- New effects: saturation, hue
- Metadata stripping and randomization for video uniqueness
- Smart audio sync with conditional stream copying
- Real-time progress estimation
- Detailed JSON logging system
- Enhanced scrollable GUI
- PyInstaller build system for .exe distribution

**v1.0** (November 2025)
- Initial release
- Basic video variation generation
- Effects: brightness, contrast, zoom, trim, volume

## License

This software is provided as-is for personal and commercial use.
