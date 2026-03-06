# 📚 Reference Storage — M7 Course Presentation References

![Web App Screenshot](web-app-screnshoot.png)

A minimalist, elegant web application for storing and managing academic presentation references. Built for the **M7: Human Resources Management and Leadership** course at **HTW Berlin**.

## 📖 About

This application serves as a dedicated reference management tool for the course presentation titled:

> **"Leading Minds, Not Just Tasks: Transformational Leadership and Effective Communication in Life Sciences"**
> *(with reflections from BioNTech's COVID-19 mRNA vaccine case)*

It provides a clean, intuitive interface to add, view, and manage all the academic sources and references used in the presentation, sorted by page number for easy navigation.

## ✨ Features

- **Add References** — Store reference details including title, author, page number, and optional URL
- **Auto-Sort by Page** — References are automatically sorted by page number for quick lookup
- **Editable Headers** — Click on course title, university, or presentation title to customize them inline
- **Delete with Confirmation** — Remove references with a custom confirmation modal (no browser alerts)
- **Dual Storage System** — Supports Firebase Firestore for cloud persistence with automatic localStorage fallback
- **Responsive Design** — Fully responsive layout optimized for desktop, tablet, and mobile devices
- **Modern UI** — Clean, minimalist design with Inter font, smooth hover animations, and custom scrollbar styling

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5** | Semantic page structure |
| **Tailwind CSS** (CDN) | Utility-first styling |
| **Vanilla JavaScript** (ES Modules) | Application logic & DOM manipulation |
| **Firebase Firestore** | Cloud database (optional) |
| **localStorage** | Offline/fallback data persistence |
| **Google Fonts (Inter)** | Typography |

## 🚀 Getting Started

### Quick Start (No Setup Required)

Simply open `index.html` in any modern web browser:

```bash
# Clone the repository
git clone https://github.com/project-sync/hr-leadership.git
cd hr-leadership

# Open in browser
start index.html        # Windows
open index.html         # macOS
xdg-open index.html     # Linux
```

> **Note:** The app works fully offline using `localStorage`. No server or build tools required.

### With Firebase (Optional)

To enable cloud persistence with Firebase:

1. Create a [Firebase project](https://console.firebase.google.com/)
2. Enable **Firestore Database** and **Anonymous Authentication**
3. Define the Firebase config as a global variable before the app script:

```html
<script>
  const __firebase_config = JSON.stringify({
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
  });
  const __app_id = "your-app-id";
</script>
```

If Firebase is not configured or unavailable, the app automatically falls back to `localStorage`.

## 📁 Project Structure

```
hr-leadership/
├── index.html                 # Main application (HTML + CSS + JS)
├── backend_test.py            # Placeholder test suite (Python/unittest)
├── web-app-screnshoot.png     # Application screenshot
├── LICENSE                    # License file
└── README.md                  # This file
```

## 🧪 Testing

The project includes a Python test file for documentation purposes:

```bash
python backend_test.py
```

> **Note:** Since this is a frontend-only application using localStorage/Firebase, the test suite contains placeholder tests. Functional testing is best performed through browser automation tools like Selenium or Playwright.

## 📱 How It Works

1. **Adding a Reference** — Fill in the form on the left panel with the reference title, author name, page number, and an optional link. Click "Add Reference" to save.

2. **Viewing References** — All saved references appear on the right panel, automatically sorted by page number. Each card displays the title, author, date added, and a link button if a URL was provided.

3. **Deleting a Reference** — Click the trash icon on any reference card. A custom confirmation modal will appear to prevent accidental deletions.

4. **Editing Headers** — Click on the main title, course name, or university fields to edit them inline. Changes are persisted in localStorage.

## 🎨 Design

The application features a warm, academic aesthetic:

- **Primary Color**: `#94B43B` (olive green)
- **Background**: `#F8F7F2` (warm off-white)
- **Font**: Inter (300–700 weights)
- **Cards**: White with subtle shadows and rounded corners
- **Animations**: Smooth hover scale transforms on reference cards

## 👨‍💻 Developer

**Uğur Ersöz**

## 📄 License

This project is licensed under the terms included in the [LICENSE](LICENSE) file.