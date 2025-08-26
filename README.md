# Text to PowerPoint Generator

A web application that transforms bulk text, markdown, or prose into fully formatted PowerPoint presentations using AI and custom templates.

## 🚀 Demo

**Live Demo:** [https://24f2009046.github.io/tds-ppt-generator/](https://24f2009046.github.io/tds-ppt-generator/)

## ✨ Features

- **AI-Powered Content Structuring**: Uses OpenAI, Anthropic Claude, or Google Gemini to intelligently break down text into slides
- **Template Style Matching**: Automatically applies colors, fonts, and layouts from uploaded PowerPoint templates
- **Flexible Input**: Supports markdown, plain text, and long-form prose
- **Privacy First**: API keys are never stored or logged - all processing happens client-side when possible
- **Multiple LLM Support**: Choose from OpenAI GPT-4, Anthropic Claude, or Google Gemini
- **Professional Output**: Generates downloadable .pptx files with proper formatting

## 🎯 How It Works

### Input Text Parsing and Slide Mapping

The application uses a multi-step process to transform your text into structured slides:

1. **Content Analysis**: The selected LLM analyzes your input text to understand structure, key topics, and logical flow
2. **Intelligent Segmentation**: Content is automatically segmented based on:
   - Natural topic boundaries
   - Header structures (if markdown is used)
   - Content density and complexity
   - User-provided guidance (e.g., "investor pitch deck")
3. **Slide Type Assignment**: Each segment is classified as:
   - **Title slides**: For main presentation title and section headers
   - **Content slides**: For bullet points, lists, and detailed information
   - **Section slides**: For topic transitions and chapter breaks

The AI considers factors like content length, complexity, and presentation context to determine optimal slide count (typically 5-12 slides).

### Visual Style and Asset Application

The template processing system extracts and applies visual elements through:

1. **Theme Extraction**: Parses the uploaded PowerPoint template to extract:
   - Color schemes (primary, accent, background colors)
   - Font families (major/minor fonts)
   - Layout structures and placeholder positions
2. **Asset Reuse**: Identifies and catalogues existing images from the template for potential reuse
3. **Style Application**: Applies extracted theme elements to generated slides:
   - Uses template color schemes for text and backgrounds
   - Applies template fonts to headings and body text
   - Maintains consistent spacing and layout patterns
4. **Smart Formatting**: Preserves template's visual hierarchy while adapting to new content structure

## 🛠️ Setup and Usage

### Prerequisites

- Modern web browser with JavaScript enabled
- API key from one of the supported LLM providers:
  - **OpenAI**: Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
  - **Anthropic**: Get your API key from [Anthropic Console](https://console.anthropic.com/)
  - **Google Gemini**: Get your API key from [Google AI Studio](https://makersuite.google.com/)

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/text-to-ppt-generator.git
   cd text-to-ppt-generator
   ```

2. **Serve the application:**
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Using PHP
   php -S localhost:8000
   ```

3. **Open in browser:**
   Navigate to `http://localhost:8000`

### Using the Application

1. **Prepare Your Content:**
   - Write or paste your text content (supports markdown formatting)
   - Optionally add guidance like "investor pitch deck" or "technical presentation"

2. **Configure AI Settings:**
   - Select your preferred LLM provider
   - Enter your API key (never stored)

3. **Upload Template:**
   - Upload a PowerPoint template (.pptx or .potx file)
   - The app will analyze and extract the visual style

4. **Generate Presentation:**
   - Click "Generate PowerPoint Presentation"
   - Wait for processing (typically 30-60 seconds)
   - Download your generated presentation

## 📋 Example Usage

### Input Text Example:
```markdown
# Company Overview
We are revolutionizing the tech industry with AI-powered solutions.

## Market Analysis
- Current market size: $50B
- Growth rate: 25% annually
- Key competitors: Company A, B, C

## Our Solution
Our innovative approach solves three key problems:
1. Efficiency bottlenecks in enterprise workflows
2. Data integration challenges across platforms
3. Scalability issues with traditional architectures

## Financial Projections
Expected revenue growth over next 3 years...
```

### Generated Output:
- **Slide 1**: Title slide with "Company Overview"
- **Slide 2**: Market Analysis with bullet points
- **Slide 3**: Our Solution with numbered list
- **Slide 4**: Financial Projections with detailed content
- **Slide 5**: Conclusion/next steps

## 🔧 Technical Architecture

### Frontend Technologies
- **HTML5/CSS3**: Modern responsive design with glassmorphism effects
- **Vanilla JavaScript**: No framework dependencies for maximum compatibility
- **JSZip**: PowerPoint file creation and manipulation
- **File APIs**: Template upload and analysis

### PowerPoint Generation
- **XML Processing**: Direct manipulation of PowerPoint's XML structure
- **Theme Parsing**: Extraction of colors, fonts, and layouts from templates
- **Content Mapping**: Intelligent placement of content into slide structures

### LLM Integration
- **Multi-Provider Support**: Unified interface for different AI APIs
- **Secure Processing**: API keys used only for session, never stored
- **Error Handling**: Robust fallback mechanisms for API failures

## 🔒 Privacy and Security

- **No Data Storage**: All processing happens client-side
- **API Key Security**: Keys are never stored, logged, or transmitted to our servers
- **Template Privacy**: Uploaded templates are processed locally and never saved
- **HTTPS Only**: All API communications use secure connections

## 🚫 Limitations

- **File Size**: Template uploads limited to 50MB
- **API Costs**: Users responsible for LLM API usage costs
- **Template Complexity**: Some advanced PowerPoint features may not be perfectly replicated
- **Image Generation**: Does not generate new images - only reuses existing template images

## 📊 Supported File Formats

### Input Formats
- Plain text
- Markdown (.md)
- Long-form prose

### Template Formats
- PowerPoint Presentation (.pptx)
- PowerPoint Template (.potx)

### Output Formats
- PowerPoint Presentation (.pptx)

### Development Guidelines
1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Submit a pull request with a clear description

---

Made with ❤️ for the open source community
