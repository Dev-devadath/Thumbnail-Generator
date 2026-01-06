# YouTube Thumbnail Generator

An AI-powered tool that generates YouTube thumbnails using multiple specialized agents working together. The system analyzes video content, processes images, and generates engaging thumbnails using OpenAI's gpt-image1 model.


## Architecture

The system consists of several specialized agents:

### 1. Summary Agent (`summaryAgent.py`)

- Analyzes YouTube videos using the YouTube Transcript API
- Extracts video content and generates concise summaries
- Uses Google's Gemini AI for intelligent content analysis
- Handles various video formats and transcript availability

### 2. Classification Agent (`classificationAgent.py`)

- Analyzes input images using Google's Gemini Vision
- Identifies image types (person, logo, background, etc.)
- Provides detailed descriptions and usage suggestions
- Helps in determining how images can be used in thumbnails

### 3. Prompt Agent (`promptAgent.py`)

- Generates detailed prompts for image generation
- Combines video summary and image analysis
- Incorporates brand themes and styling preferences
- Creates optimized prompts for gpt-image-1

### 4. Image Generation Agent (`imageGen.py`)

- Handles image generation and editing using gpt-image-1
- Supports both text-to-image and image-to-image generation
- Manages image quality and size parameters
- Saves generated thumbnails with timestamps

### 5. Main Orchestrator (`main.py`)

- Coordinates all agents in a logical workflow
- Manages user input and agent interactions
- Handles the complete thumbnail generation process
- Provides a user-friendly command-line interface

<img width="1903" height="910" alt="image" src="https://github.com/user-attachments/assets/be6bbfd5-7c41-4615-9e64-4e68dcf0fc69" />

## Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file with your API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   GOOGLE_API_KEY=your_google_api_key_here
   ```

## Usage

Run the main orchestrator:

```bash
python main.py
```

The tool will guide you through the following steps:

1. **Video Analysis**

   - Enter a YouTube URL
   - System analyzes video content and generates a summary

2. **Image Processing**

   - Choose to use existing images or generate new ones
   - If using existing images, provide image paths
   - System analyzes images and suggests usage

3. **Prompt Generation**

   - Optionally provide brand theme
   - System generates optimized prompt for thumbnail

4. **Thumbnail Generation**
   - System generates or edits images based on the prompt
   - Saves the final thumbnail with timestamp

## Features

- **Intelligent Video Analysis**

  - Automatic transcript extraction
  - Smart content summarization
  - Fallback options for videos without transcripts

- **Advanced Image Processing**

  - Multi-image analysis
  - Intelligent image classification
  - Usage suggestions for thumbnail composition

- **Smart Prompt Generation**

  - Context-aware prompt creation
  - Brand theme integration
  - Style and composition suggestions

- **Flexible Image Generation**
  - Text-to-image generation
  - Image-to-image editing
  - High-quality output
  - Customizable parameters

## Requirements

- Python 3.8+
- OpenAI API key
- Google API key
- Required Python packages (see requirements.txt)

## Error Handling

The system includes robust error handling for:

- Invalid YouTube URLs
- Missing transcripts
- Image processing errors
- API limitations
- Network issues

## Output

Generated thumbnails are saved as PNG files with timestamps in the format:

```
thumbnail_[timestamp].png
```


