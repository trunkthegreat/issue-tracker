# Issue Tracker - Complete GitHub Integration Solution

A comprehensive, modern issue tracking and resolution management system with GitHub integration, featuring glassmorphic UI design, voice recording capabilities, and multi-language support.

## 🌟 Features

### Core Functionality
- **Complete CRUD Operations** - Create, Read, Update, Delete issues with full data persistence
- **GitHub Integration** - Seamless sync with GitHub repositories using Personal Access Tokens
- **Media Attachments** - Support for images (JPEG, PNG, GIF, WebP) and voice recordings
- **Voice Recording** - Direct browser-based voice recording with playback controls
- **Multi-language Search** - Fuzzy search supporting English, Vietnamese, Chinese, Japanese, and more
- **Real-time Filtering** - Advanced filtering by status, category, date ranges
- **Comprehensive Reports** - Analytics dashboard with charts and performance metrics

### User Interface
- **Glassmorphic Design** - Modern translucent UI with backdrop blur effects
- **Forest Theme** - Lush deep forest greens with split-complementary color palette
- **Responsive Layout** - Mobile-first design that works on all devices
- **Accessibility** - High contrast text and semantic markup for screen readers
- **Interactive Elements** - Smooth animations and hover effects

### Technical Features
- **Offline Capability** - Works without internet connection using local storage
- **Unicode Support** - Full support for non-Latin characters and international text
- **File Management** - Drag-and-drop file uploads with size validation
- **Data Export** - Export reports in CSV, JSON, and PDF formats
- **Category Management** - Hierarchical category system with custom colors

## 📁 Project Structure

```
github.com/trunkthegreat/issue-tracker/
├── index.html              # Main dashboard and entry point
├── issuelogger.html         # Issue creation and management interface
├── issueviewer.html         # Detailed issue viewer and editor
├── report.html              # Analytics and reporting dashboard
├── main.css                 # Shared styles with glassmorphic forest theme
├── database.json            # Hierarchical category structure and routing
├── records/                 # Directory for issue data storage
│   ├── issue_[id].json     # Individual issue files
│   └── media/              # Media files (images, audio)
│       ├── images/
│       └── audio/
└── README.md               # This documentation file
```

## 🚀 Quick Start

### 1. Repository Setup

1. **Create GitHub Repository**
   ```bash
   # Create a new repository on GitHub
   Repository name: issue-tracker
   Owner: trunkthegreat
   Visibility: Public or Private (as needed)
   ```

2. **Clone and Setup**
   ```bash
   git clone https://github.com/trunkthegreat/issue-tracker.git
   cd issue-tracker
   ```

3. **Deploy Files**
   - Copy all HTML, CSS, and JSON files to your repository
   - Ensure the `records/` directory exists
   - Push to GitHub Pages or your hosting solution

### 2. GitHub Token Setup

1. **Generate Personal Access Token**
   - Go to GitHub Settings → Developer settings → Personal access tokens
   - Click "Generate new token (classic)"
   - Select scopes: `repo`, `read:user`
   - Copy the generated token

2. **Configure Application**
   - Open the application in your browser
   - Enter your GitHub token when prompted
   - The app will validate and store the token locally

### 3. First Use

1. **Access Dashboard** - Open `index.html` in your browser
2. **Create Categories** - Set up your issue categories in the Issue Logger
3. **Log Your First Issue** - Use the Issue Logger to create your first issue
4. **Explore Reports** - Check the Reports section for analytics

## 🛠️ Configuration

### GitHub Integration

The application integrates with GitHub through the REST API. Configure settings in `database.json`:

```json
{
  "settings": {
    "githubIntegration": {
      "enabled": true,
      "repository": "trunkthegreat/issue-tracker",
      "syncInterval": 300,
      "createIssues": true,
      "updateIssues": true,
      "closeIssues": true
    }
  }
}
```

### Media Settings

Configure file upload limits and supported formats:

```json
{
  "mediaSettings": {
    "maxImageSize": 5242880,
    "maxAudioDuration": 300,
    "allowedImageTypes": ["image/jpeg", "image/png", "image/gif", "image/webp"],
    "allowedAudioTypes": ["audio/wav", "audio/mp3", "audio/m4a", "audio/ogg"]
  }
}
```

### Search Configuration

Customize search behavior:

```json
{
  "searchSettings": {
    "fuzzyMatchingEnabled": true,
    "fuzzyThreshold": 0.2,
    "maxSearchResults": 100,
    "searchFields": ["title", "content", "tags", "category"]
  }
}
```

## 📋 Issue Management

### Issue Lifecycle

Issues follow a comprehensive workflow:

1. **Creation** - New issues start as "ongoing"
2. **Assignment** - Assign to categories and set priorities
3. **Resolution** - Track resolution methods and dates
4. **Completion** - Mark as "finished" with actual resolution date

### Data Structure

Each issue contains:

```json
{
  "id": "unique_timestamp_id",
  "title": "Issue title",
  "content": "Detailed description",
  "category": "bug|feature|improvement|question|other",
  "status": "ongoing|finished",
  "dateTime": "ISO_8601_timestamp",
  "expectedResolutionDate": "YYYY-MM-DD",
  "actualResolutionDate": "YYYY-MM-DD",
  "resolutionMethod": "How the issue was resolved",
  "pictures": [{"name": "file.jpg", "data": "base64_data"}],
  "voiceRecords": [{"name": "recording.wav", "data": "base64_data"}],
  "comments": [{"id": "id", "content": "note", "timestamp": "ISO_8601"}]
}
```

## 🎨 User Interface Guide

### Dashboard (index.html)
- **Overview Stats** - Total, ongoing, resolved, and overdue issues
- **Recent Issues** - Latest activity with quick access
- **Quick Actions** - Fast issue creation and data management
- **System Status** - GitHub connection and sync status

### Issue Logger (issuelogger.html)
- **Create Issues** - Full form with media attachments
- **Search & Filter** - Real-time search with multiple filters
- **Category Management** - Add, edit, and delete categories
- **Bulk Operations** - Export and import data

### Issue Viewer (issueviewer.html)
- **Detailed View** - Complete issue information
- **Edit Mode** - Modify all issue properties
- **Media Gallery** - View images in lightbox, play audio
- **Comments System** - Add notes and track activity
- **Activity Timeline** - Visual history of changes

### Reports (report.html)
- **Analytics Dashboard** - Charts and performance metrics
- **Detailed Reports** - Overdue issues, category performance
- **Export Options** - CSV, JSON, PDF export
- **Time-based Analysis** - Filter by various time periods

## 🔧 Advanced Features

### Voice Recording
- Click the microphone button to start recording
- Maximum duration: 5 minutes (configurable)
- Automatic conversion to WAV format
- Playback controls in issue viewer

### Image Management
- Drag-and-drop upload support
- Automatic thumbnail generation
- Lightbox viewer with navigation
- Size validation (5MB limit)

### Search Capabilities
- **Fuzzy Matching** - Handles typos and variations
- **Multi-keyword** - Comma-separated search terms
- **Unicode Support** - Works with any language
- **Real-time Results** - Instant filtering as you type

### GitHub Sync
- **Automatic Backup** - Issues saved to GitHub repository
- **Conflict Resolution** - Handles sync conflicts gracefully
- **Offline Mode** - Works without GitHub connection
- **Manual Sync** - Force sync when needed

## 🌐 Browser Compatibility

### Supported Browsers
- **Chrome/Chromium** 80+ (Recommended)
- **Firefox** 75+
- **Safari** 13+
- **Edge** 80+

### Required Features
- **Web Audio API** - For voice recording
- **File API** - For drag-and-drop uploads
- **Local Storage** - For offline functionality
- **Fetch API** - For GitHub integration

## 📱 Mobile Support

The application is fully responsive and supports:
- Touch navigation
- Mobile file selection
- Voice recording on mobile devices
- Responsive charts and tables
- Mobile-optimized forms

## 🔒 Security & Privacy

### Data Storage
- **Local Storage** - All data stored locally in browser
- **No Server Required** - Pure client-side application
- **GitHub Integration** - Optional, uses personal access tokens
- **No Tracking** - No analytics or external tracking

### Token Security
- Tokens stored in local storage only
- Never transmitted except to GitHub API
- Can be revoked at any time from GitHub settings
- Application works offline without tokens

## 📊 Performance

### Optimization Features
- **Lazy Loading** - Charts and media loaded on demand
- **Image Compression** - Automatic image optimization
- **Efficient Search** - Indexed search for large datasets
- **Minimal Dependencies** - Lightweight external libraries

### Recommended Limits
- **Maximum Issues** - 10,000 issues (browser dependent)
- **Image Size** - 5MB per image
- **Audio Duration** - 5 minutes per recording
- **Search Results** - 100 results displayed

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Code Style
- Follow existing naming conventions
- Use semantic HTML
- Maintain accessibility standards
- Comment complex functionality

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Support

### Common Issues

**Q: GitHub authentication fails**
A: Ensure your token has the correct scopes (`repo`, `read:user`) and hasn't expired.

**Q: Voice recording doesn't work**
A: Check browser permissions for microphone access. HTTPS is required for microphone API.

**Q: Images won't upload**
A: Verify file size is under 5MB and format is supported (JPEG, PNG, GIF, WebP).

**Q: Search not working with special characters**
A: The application supports Unicode; ensure your browser encoding is set to UTF-8.

### Getting Help
- Check the browser console for error messages
- Verify all files are properly uploaded to your repository
- Test with a fresh browser session
- Ensure JavaScript is enabled

## 🔄 Updates

The application automatically checks for updates and can import/export data for migration between versions.

### Backup Your Data
```javascript
// Export all data from browser console
const backup = {
  issues: JSON.parse(localStorage.getItem('issues') || '[]'),
  categories: JSON.parse(localStorage.getItem('categories') || '{}'),
  timestamp: new Date().toISOString()
};
console.log(JSON.stringify(backup, null, 2));
```

---

**Built with ❤️ for efficient issue tracking and resolution management**

For technical support or feature requests, please create an issue in this repository.
