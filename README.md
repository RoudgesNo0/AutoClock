# AutoClock - Global Time Synchronizer

<div align="center">

![AutoClock Logo](https://img.shields.io/badge/AutoClock-Global%20Time%20Synchronizer-black?style=for-the-badge&logo=clock)

**Synchronize meetings across timezones with shareable time codes**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)]

</div>

---

## 🌍 Overview

AutoClock is a modern web application that solves the global meeting coordination problem. Create a meeting time in your timezone, get a compact code, and share it with anyone worldwide. They can instantly see when the meeting is in their local timezone.

### ✨ Key Features

- **🕐 Smart Time Code Generation** - Convert any meeting time into a compact, shareable code
- **🌐 Global Timezone Support** - Automatic conversion across 15+ major timezones
- **📱 Mobile-Friendly** - Responsive design that works on all devices
- **🔗 Shareable Links** - Generate direct links that auto-decode when opened
- **⚡ Real-time Updates** - Live current time display with automatic timezone detection
- **🎨 Modern UI** - Clean, professional interface with dark theme

## 🚀 Live Demo

**[Try AutoClock Now](https://autoclock.roudges.de)**

## 📋 Table of Contents

- [How It Works](#-how-it-works)
- [Features](#-features)
- [Usage](#-usage)
- [Technology Stack](#-technology-stack)
- [Installation](#-installation)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [License](#-license)

## 🔧 How It Works

### Time Code Generation
1. **Input**: User selects a meeting date, time, and their timezone
2. **Processing**: System converts the local time to UTC timestamp
3. **Encoding**: Creates a compact base36 code combining timestamp and timezone index
4. **Output**: Generates a short code (8-10 characters) and shareable URL

### Time Code Decoding
1. **Input**: User enters a time code or opens a shareable link
2. **Parsing**: System extracts timestamp and timezone information
3. **Conversion**: Converts UTC time to user's local timezone
4. **Display**: Shows both original and converted times

### Supported Timezones
- Europe: Berlin, London, Paris, Rome
- Americas: New York, Los Angeles, Chicago, Toronto, Mexico City
- Asia: Tokyo, Shanghai, Dubai, Kolkata
- Oceania: Sydney, Auckland

## ✨ Features

### Core Functionality
- **Compact Time Codes**: 8-10 character codes for easy sharing
- **Automatic Timezone Detection**: Uses browser's timezone by default
- **Backward Compatibility**: Supports legacy base64 encoded codes
- **URL Parameters**: Direct links with auto-decoding (`?c=CODE`)

### User Experience
- **Real-time Clock**: Live current time display
- **Auto-generation**: Codes update automatically when inputs change
- **Copy to Clipboard**: One-click copying of codes and links
- **Error Handling**: Clear error messages and validation
- **Responsive Design**: Works seamlessly on desktop and mobile

### Technical Features
- **Efficient Encoding**: Base36 encoding for shorter codes
- **Local Storage**: Handles custom timezones not in the standard list
- **Cross-browser Compatibility**: Works in all modern browsers
- **No Dependencies**: Pure HTML, CSS, and JavaScript

## 📖 Usage

### Creating a Time Code

1. **Set Meeting Details**
   - Choose your meeting date
   - Select the meeting time
   - Confirm your timezone (auto-detected)

2. **Generate Code**
   - Click "Generate Time Code"
   - Copy the generated code or shareable link

3. **Share Globally**
   - Send the code to team members worldwide
   - They can decode it instantly in their timezone

### Decoding a Time Code

1. **Enter Code**
   - Paste the time code in the decode section
   - Or open a shareable link directly

2. **View Results**
   - See the meeting time in your local timezone
   - View the original time and timezone

### Example Workflow

```
Meeting Creator (Berlin):
- Sets meeting: March 15, 2025 at 14:00 (2 PM)
- Gets code: "ABC123XY"

Team Member (Tokyo):
- Enters code: "ABC123XY"
- Sees: March 15, 2025 at 22:00 (10 PM) in Tokyo
```

## 🛠 Technology Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Custom CSS with modern design patterns
- **Encoding**: Base36 for compact time codes
- **Timezone Handling**: Intl.DateTimeFormat API
- **Storage**: LocalStorage for custom timezone support
- **Deployment**: Static hosting ready

### Browser Support
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 🚀 Installation

### Quick Start
1. Clone the repository:
   ```bash
   git clone https://github.com/RoudgesNo0/autoclock.git
   cd autoclock
   ```

2. Open `index.html` in your browser:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Or simply open index.html directly
   ```

3. Visit `http://localhost:8000` in your browser

### Deployment
AutoClock is a static web application that can be deployed to any web hosting service:

- **GitHub Pages**: Push to main branch
- **Netlify**: Drag and drop the folder
- **Vercel**: Connect your repository
- **AWS S3**: Upload files to a bucket
- **Any web server**: Copy files to web root

## 📚 API Reference

### Time Code Format

#### New Compact Format (8-10 characters)
```
[timestamp_base36][timezone_index_base36]
```

**Example**: `ABC123XY`
- `ABC123` = timestamp in base36
- `XY` = timezone index in base36

#### Legacy Format (base64)
```
base64({"t": timestamp, "z": timezone})
```

### Supported Timezone Indices
| Index | Timezone |
|-------|----------|
| 0 | Europe/Berlin |
| 1 | Europe/London |
| 2 | America/New_York |
| 3 | America/Los_Angeles |
| 4 | America/Chicago |
| 5 | Asia/Tokyo |
| 6 | Asia/Shanghai |
| 7 | Australia/Sydney |
| 8 | Europe/Paris |
| 9 | Europe/Rome |
| 10 | Asia/Dubai |
| 11 | Asia/Kolkata |
| 12 | Pacific/Auckland |
| 13 | America/Toronto |
| 14 | America/Mexico_City |
| 99 | Custom timezone (stored in localStorage) |

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Development Setup
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Test thoroughly across different browsers
5. Commit your changes: `git commit -m 'Add amazing feature'`
6. Push to the branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

### Areas for Contribution
- **New Timezones**: Add support for additional timezones
- **UI/UX Improvements**: Enhance the user interface
- **Performance**: Optimize code generation and decoding
- **Accessibility**: Improve accessibility features
- **Documentation**: Enhance documentation and examples
- **Testing**: Add comprehensive test coverage

### Code Style
- Follow existing code formatting
- Use meaningful variable and function names
- Add comments for complex logic
- Ensure cross-browser compatibility

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Timezone Data**: Based on IANA timezone database
- **Icons**: Using emoji for visual elements
- **Design Inspiration**: Modern web design principles
- **Community**: Thanks to all contributors and users

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/RoudgesNo0/autoclock/issues)
- **Discussions**: [GitHub Discussions](https://github.com/RoudgesNo0/autoclock/discussions)
- **Email**: leon@roudges.de

---

<div align="center">

**Made with ❤️ by Leon Schmidt for GermanSocialNetwork, now freely available on GitHub**

[![GitHub stars](https://img.shields.io/github/stars/RoudgesNo0/autoclock?style=social)](https://github.com/RoudgesNo0/autoclock/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/RoudgesNo0/autoclock?style=social)](https://github.com/RoudgesNo0/autoclock/network/members)

</div> 
