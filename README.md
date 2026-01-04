# Year Progress Bar

A single-page web application that visualizes the passing of time with a beautiful, brutalist design. Track your year's progress with an animated progress bar, daily statistics, and multilingual support.

![Year Progress](https://img.shields.io/badge/year-2026-orange)
![License](https://img.shields.io/badge/license-MIT-blue)

## Features

- **Animated Progress Bar** - Smooth, real-time visualization of year completion
- **Multi-language Support** - 11 languages including English, Chinese (Simplified/Traditional), Japanese, Korean, Spanish, French, German, Arabic, Hindi, and Portuguese
- **Persistent Language Preferences** - Your language choice is saved in localStorage
- **Download Progress Image** - Export your progress as a beautifully designed PNG image
- **Responsive Design** - Works seamlessly on desktop and mobile devices
- **Brutalist Aesthetic** - Bold typography, thick borders, and accent colors
- **Social Link** - Connect on X (Twitter) [@xcm0215](https://x.com/xcm0215)

## Live Demo

Open `index.html` directly in your web browser - no server required.

## Usage

Simply open the `index.html` file in any modern web browser. The application will:

1. Display the current year's progress as a percentage
2. Show days passed and days remaining
3. Display the current date in your selected language
4. Update hourly to reflect time passage

### Language Selection

Use the dropdown menu at the top to switch between supported languages. Your preference will be automatically saved.

### Download Progress Image

Click the "Download Image" button to save a high-resolution PNG of your current progress, perfect for sharing on social media.

## Development

### Project Structure

The entire application is self-contained in `index.html`:

- **CSS (lines 10-428)**: Inline styles with CSS variables, animations, and responsive layouts
- **HTML (lines 430-516)**: Semantic structure with progress display and controls
- **JavaScript (lines 518-877)**: All logic including i18n, date calculations, and canvas rendering

### Local Development

For live reloading during development:

```bash
# Python 3
python3 -m http.server 8000

# Node.js
npx http-server
```

### Adding New Languages

1. Add a translation entry to the `translations` object in the JavaScript section:

```javascript
'xx': {
    title: 'YOUR TITLE',
    labelCurrentDate: 'CURRENT DATE',
    labelDaysPassed: 'DAYS PASSED',
    labelDaysRemaining: 'DAYS REMAINING',
    labelCompleted: 'COMPLETED',
    labelToGo: 'TO GO',
    progressLabel: 'COMPLETE',
    shareButton: 'DOWNLOAD IMAGE',
    footer: '// YOUR FOOTER TEXT //',
    locale: 'xx-XX'
}
```

2. Add an option to the language selector:

```html
<option value="xx">XX / Your Language</option>
```

## Design System

- **Typography**: Google Fonts (Space Mono for UI, Playfair Display for headlines)
- **Colors**:
  - Black: `#0a0a0a`
  - White: `#f5f5f5`
  - Accent: `#ff6b35` (orange)
  - Gray: `#8a8a8a`
- **Border**: 4px thick borders for brutalist effect
- **Animations**: CSS transitions with cubic-bezier easing

## Browser Support

Works in all modern browsers that support:
- CSS Grid
- CSS Variables
- ES6 JavaScript
- Canvas API

## License

MIT License - feel free to use this project for personal or commercial purposes.

## Connect

Find me on X (Twitter): [@xcm0215](https://x.com/xcm0215)

---

*Time passes, nothing lasts.*
