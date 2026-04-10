# Interview AI Interview Assistant

An AI-powered interview assistant with a stealth overlay that helps you during technical interviews. The app provides real-time AI-generated responses, transcription, and practice mode.

## Features

- 🎯 **Real-time AI Assistance**: Get instant AI-generated responses during interviews
- 🎤 **Audio Transcription**: Automatic transcription of interview conversations
- 👁️ **Stealth Mode**: Window excluded from screen capture (Windows only)
- 🎓 **Practice Mode**: Practice interview questions with AI feedback
- 📊 **Conversation History**: Track all questions and responses
- ⚙️ **Multiple AI Providers**: Support for Gemini, OpenAI, Claude, and custom providers
- 🔒 **Secure API Key Storage**: Encrypted storage using Windows Credential Manager

## Quick Start

### 1. Installation

```bash
npm install
```

### 2. Configure API Keys

Create a `.env` file in the root directory (copy from `.env.example`):

```bash
cp .env.example .env
```

Edit `.env` and add your API keys:

```env
# Google Gemini API Key (Recommended - Free tier available)
GEMINI_API_KEY=your_gemini_api_key_here

# Optional: Other providers
OPENAI_API_KEY=your_openai_api_key_here
CLAUDE_API_KEY=your_claude_api_key_here
```

**Get API Keys:**
- **Gemini (Free)**: https://makersuite.google.com/app/apikey
- **OpenAI**: https://platform.openai.com/api-keys
- **Claude**: https://console.anthropic.com/

### 3. Build and Run

```bash
# Build the application
npm run build

# Start the application
npm start
```

## Usage

### Window Controls

The overlay window appears at the top-center of your screen with the following controls:

- **⚙️ Settings**: Configure AI provider, profile, and preferences
- **👁️ Transcription Toggle** (Ctrl+Shift+T): Cycle through transcription modes (Full/Questions Only/Off)
- **🙈 Hide** (Ctrl+Shift+H): Hide/show the overlay window
- **⏸️ Pause** (Ctrl+Shift+P): Pause/resume AI responses
- **📌 Pin**: Keep window always on top
- **❌ Close**: Close the application

### Window Resizing

- **Minimum Size**: 400x300 pixels
- **Maximum Size**: 1400x1000 pixels
- **Default Size**: 800x600 pixels
- Drag from any edge or corner to resize
- Window snaps to screen edges automatically

### Keyboard Shortcuts

- `Ctrl+Shift+H`: Toggle window visibility
- `Ctrl+Shift+T`: Cycle transcription mode
- `Ctrl+Shift+P`: Pause/Resume

#### Response Navigation
- `Alt+←`: Previous response
- `Alt+→`: Next response
- `Alt+R`: Regenerate response
- `Alt+C`: Collapse/Uncollapse AI response
- `Alt+Space`: Scroll up response
- `Alt+Shift+Space`: Scroll down response

#### Audio Controls
- `Alt+U`: Toggle user audio (microphone)
- `Alt+I`: Toggle interviewer audio (system audio)
- `Alt+T`: Clear transcripts

#### AI Actions
- `Alt+B`: Brainstorm answer (auto-answer based on last conversation)
- `Alt+S`: Analyze screen (for coding problems, MCQs, etc.)
- `Alt+H`: Toggle context history (counter questions)
- `Alt+A`: Ask last question
- `Alt+E`: Edit and ask last question

#### Response Modes
- `Alt+1`: Switch to Concise mode
- `Alt+2`: Switch to Explain mode
- `Alt+3`: Switch to Story mode
- `Alt+Q`: Toggle auto-answer mode (automatic question detection)

#### Window Navigation
- `Alt+M`: Minimize/Maximize window
- `Shift+Tab`: Switch tabs (Answers/Transcripts)
- `Ctrl+Shift+F`: Focus manual input bar

#### Window Positioning
- `Ctrl+Shift+←`: Move window left
- `Ctrl+Shift+→`: Move window right
- `Ctrl+Shift+↑`: Move window up
- `Ctrl+Shift+↓`: Move window down

### First-Time Setup

1. Click the **Settings** button (⚙️)
2. Go to **AI Provider** tab
3. Select your preferred provider (Gemini recommended for free tier)
4. Enter your API key if not using .env file
5. Go to **Profile & Resume** tab
6. Fill in your information and upload your resume
7. Paste the job description for the role you're interviewing for
8. Click **Save Changes**

### During an Interview

1. The app will automatically transcribe the conversation
2. When a question is detected, AI will generate a response
3. View the response in the right panel
4. Use manual input bar to trigger custom responses
5. All conversations are saved in history

### Practice Mode

1. Click the practice mode button
2. Answer generated interview questions
3. Get AI-powered feedback on your responses
4. Track your improvement over time

## Configuration

### AI Provider Settings

Configure in Settings > AI Provider:

- **Provider**: Choose between Gemini, OpenAI, Claude, or Custom
- **Model**: Select the AI model to use
- **Temperature**: Control response randomness (0-1)
- **Max Tokens**: Maximum response length
- **Response Mode**: Concise, Detailed, Technical, or Story (STAR method)

### Audio Settings

Configure in Settings > Audio:

- Select system audio device
- Select microphone device
- Adjust audio capture settings

### Privacy Settings

Configure in Settings > Privacy:

- Enable/disable stealth mode
- Clear conversation history
- Export data

## Troubleshooting

### Microphone Permission

If the app doesn't have microphone access:

1. Windows Settings > Privacy > Microphone
2. Enable "Allow apps to access your microphone"
3. Restart the application

### API Key Issues

If AI responses aren't working:

1. Check your `.env` file has the correct API key
2. Or add the key in Settings > AI Provider
3. Test the provider connection in settings
4. Check your API key has sufficient credits/quota

### Window Not Resizing

If the window gets stuck:

1. Close and restart the application
2. Delete `%APPDATA%/interviewace` folder
3. Restart the application

### Stealth Mode Not Working

Stealth mode (screen capture exclusion) only works on Windows 10/11. On other platforms, the feature is disabled but the app works normally.

## Development

```bash
# Development mode with hot reload
npm run dev

# Run tests
npm test

# Run property-based tests
npm run test:pbt

# Package for distribution
npm run package
```

## Project Structure

```
interview-interviewace/
├── src/
│   ├── main/           # Electron main process
│   │   ├── main.ts           # Application entry point
│   │   ├── WindowManager.ts  # Window management
│   │   ├── IPCHandler.ts     # IPC communication
│   │   └── preload.ts        # Preload script
│   ├── renderer/       # React UI components
│   │   ├── App.tsx           # Main app component
│   │   ├── components/       # UI components
│   │   └── styles.css        # Tailwind styles
│   ├── services/       # Business logic services
│   │   ├── AIService.ts      # AI provider management
│   │   ├── AudioManager.ts   # Audio capture
│   │   ├── ConversationManager.ts
│   │   ├── StorageService.ts
│   │   └── ...
│   ├── types/          # TypeScript type definitions
│   └── tests/          # Unit and property-based tests
├── dist/               # Build output
├── .env                # Environment variables (API keys)
├── .env.example        # Example environment file
└── .kiro/              # Kiro spec files
```

## Architecture

- **Main Process**: Electron main process handles window management, IPC, and system integration
- **Renderer Process**: React UI for the overlay window
- **Services**: Audio capture, transcription, AI providers, conversation management
- **Storage**: Encrypted local storage using electron-store

## Security

- API keys are encrypted using AES-256-CBC
- Windows Credential Manager integration for secure storage
- No data sent to external servers except AI provider APIs
- All conversation data stored locally

## Requirements

- Windows 10/11 (stealth mode requires Windows)
- Node.js 18+
- npm or yarn

## License

MIT

## Support

For issues and feature requests, please open an issue on GitHub.
