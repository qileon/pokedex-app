# 🔴 Pokédex App

<div align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg" alt="Version">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/platform-Web%20%7C%20Desktop-lightgrey.svg" alt="Platform">
  <img src="https://img.shields.io/badge/JavaScript-ES6+-yellow.svg" alt="JavaScript">
  <img src="https://img.shields.io/badge/Electron-37.0.0-blue.svg" alt="Electron">
</div>


A modern and user-friendly Pokédex app. Search for any Pokémon, view their details, and explore evolution chains. Runs both in web browsers and as a desktop application.

## 📸 Screenshots

![{A95FD581-E0BF-4B4D-A915-23327FF7AFCC}](https://github.com/user-attachments/assets/e9ef6395-e2a5-456f-a437-b6a6ad2f3497)
![{8723611F-C36C-4FDD-A46D-F2A797A751BA}](https://github.com/user-attachments/assets/130d3ebf-9a72-49f5-8cc1-dee6947710c7)
![{8EF4491A-03D6-418E-904D-88B5B573C294}](https://github.com/user-attachments/assets/97ff372c-185e-4a2a-b152-d9eb0b478fa2)


## ✨ Features

### 🔍 Smart Search System

* **Search by name**: Just type the name of any Pokémon (e.g., `pikachu`) to fetch its data instantly.
* **Search by number**: Enter the Pokédex number (e.g., `25`) to look it up directly.
* **Random Pokémon**: Type `surprise me` in the search box to be shown a completely random Pokémon. Perfect for discovering new ones or challenging yourself.
* **Fuzzy matching**: Even if you misspell a name (like `pikacuh`), the app will suggest the closest valid matches.
* **Autocomplete suggestions**: While typing, a dropdown will offer matching Pokémon names in real-time.
* **Direct shiny search**: Type `shiny pikachu` to jump straight to its shiny version.

### ✨ Visual Features

* Toggle between **normal/shiny** sprites to compare color variants.
* Switch between **static** (non-moving) and **animated** sprites.
* Shiny Pokémon are highlighted with a ✨ sparkle effect.
* The UI is fully responsive and works on all screen sizes.
* Dark theme for comfortable browsing at night.

### 🧬 Evolution Chain

* Fully interactive evolution tree: click any stage to explore it.
* Supports branched evolution paths like Eevee's multiple forms.
* Arrows and lines visually show evolution progression.

### ⚔️ Type Interactions

* Clearly shows each Pokémon's **type weaknesses**, **resistances**, and **immunities**.
* Uses color-coded badges to make types visually distinct.

### 📊 Stats View

* Displays all base stats: HP, Attack, Defense, Special Attack, Special Defense, Speed.
* Each stat is represented as a color-coded bar graph.
* Helps you instantly see a Pokémon's strengths and weaknesses.

### 🔄 Navigation

* Navigate back to previously viewed Pokémon with a back button.
* A full search history is stored locally for quick access.
* Keyboard shortcuts: `Enter` to search, `Escape` to close suggestions, arrow keys to move through the list.

### 🎨 Accessibility

* Font size can be changed between 12px and 20px.
* High contrast dark theme improves readability.
* Fully navigable via keyboard for accessibility.

## 🛠️ Technologies

### Frontend

* **HTML5** with semantic layout.
* **CSS3**: Grid, Flexbox, animations, and custom properties.
* **Vanilla JavaScript (ES6+)** for logic and interactivity.
* **Fetch API**: Interacts with RESTful endpoints.
* **Local Storage**: Saves user preferences locally.

### Desktop

* **Electron 37.0.0** to build the desktop app.
* **Node.js** runtime for backend logic and scripting.

### External Services

* **PokéAPI**: For all core Pokémon data.
* **Pokémon Sprite Repository**: For fetching static and animated sprite images.

## 📊 Data & API Usage

### PokéAPI Endpoints

```js
GET https://pokeapi.co/api/v2/pokemon/{id-or-name}
GET https://pokeapi.co/api/v2/pokemon-species/{id}
GET https://pokeapi.co/api/v2/evolution-chain/{id}
GET https://pokeapi.co/api/v2/pokemon?limit=100000
```

### Data Structures Used

* Pokémon info: name, ID, types, base stats.
* Sprite URLs: standard, shiny, and animated.
* Type effectiveness data: weaknesses, resistances, immunities.
* Evolution chains with stages and branching conditions.

## 📁 Project Structure

```
pokedex-app/
├── index.html           # Main HTML file
├── main.js              # Electron main process
├── package.json         # Project configuration
└── README.md            # This file
```

### File Details

#### `index.html`

* UI layout with semantic tags.
* Embedded CSS for design.
* JavaScript for all interactive logic.
* All fetch/API code is centralized here.

#### `main.js`

* Creates Electron browser window.
* Handles lifecycle events like open/close.
* Ensures cross-platform support.

#### `package.json`

* Lists dependencies like `chalk` (future CLI) and `electron`.
* Includes scripts to run the app.

## 🚀 Installation & Run

### Requirements

* Node.js v14+
* NPM v6+
* Internet connection

### Web Version

```bash
git clone https://github.com/qileon/pokedex-app.git
cd pokedex-app
python -m http.server 8000
# Visit http://localhost:8000 in your browser
```

### Desktop Version

```bash
npm install
npm start
# or
npx electron .
```

## 🎮 User Guide

### Search Examples

* `pikachu` → Searches by name
* `25` → Searches by Pokédex number
* `surprise me` → Fetches a random Pokémon
* `shiny charizard` → Opens shiny version of Charizard

### Shortcuts

* `Enter` → Search
* `Escape` → Close suggestions
* `↑/↓` → Navigate suggestions

### Sprite Controls

* Toggle between normal and shiny
* Switch between static and animated

### Navigation

* Click on evolution sprites to explore their chains
* Back button to return to last viewed Pokémon
* Change font size with a slider in settings

## 🧩 Algorithms & Data Handling

### Fuzzy Search (Levenshtein)

```js
function levenshtein(a, b) {
  // Calculates edit distance for typo correction
}
```

### Type Effectiveness Calculation

```js
const typeChart = {
  fire: {
    weak: ['water', 'ground', 'rock'],
    resist: ['fire', 'grass', 'ice', 'bug', 'steel', 'fairy'],
    immune: []
  }
  // and other types...
}
```

### Evolution Chain Parser

```js
function buildEvolutionTree(current, level = 0) {
  // Recursively parses the evolution chain from API
}
```

## 🎨 Design System

### Color Palette

```css
--background: #202123;
--surface: #2d2f33;
--border: #555;
--text: #ffffff;
--accent: #bfae9f;
--fire: #F08030;
--water: #6890F0;
--grass: #78C850;
```

### Typography

* Font stack: system fonts
* Sizes: 12px to 20px
* Line height: 1.4 for readability

### Animations

```css
@keyframes sparkle {
  0%, 100% { opacity: 1; transform: scale(1) rotate(0deg); }
  50% { opacity: 0.5; transform: scale(1.2) rotate(180deg); }
}

.evolution-pokemon:hover {
  background-color: #3a3d42;
  transition: background-color 0.3s;
}
```

## 🔧 Technical Details

### API Rate Limits

* PokéAPI is free to use with no hard limits.
* Just avoid making excessive requests too quickly.
* No built-in caching or retry system yet.

### Compatibility

* Web: Chrome, Firefox, Safari, Edge
* Desktop: Windows 10+, macOS 10.12+, Ubuntu 16.04+

### Performance

* Evolution chains are lazy-loaded.
* Images are cached by the browser.
* Debounced inputs reduce redundant API calls.

### Error Handling

* Graceful fallback for network issues.
* Invalid names are fixed with fuzzy logic.

## 🐛 Known Limitations

### API Dependency

* Requires internet connection
* Will not work if PokéAPI is down

### Sprite Limitations

* Some older-gen Pokémon lack animated sprites
* Not all forms/variants are available

## 🤝 Contributing

### Development Setup

```bash
git clone https://github.com/qileon/pokedex-app.git
cd pokedex-app
git checkout -b feature/new-feature
npm start
```

### Guidelines

* Use ES6+ syntax
* Always use semicolons
* Use camelCase
* Comment important functions
* Handle all async errors

### Commit Format

```bash
feat: add new feature
fix: fix bug
docs: update docs
style: code style change
refactor: internal refactor
```

## 📄 License

This project is licensed under the **MIT License**.

```
✅ Free use
✅ Modification
✅ Redistribution
✅ Private/commercial use
⚠️ No warranty provided
```

## 🙏 Credits

### Data

* [PokéAPI](https://pokeapi.co/)
* [Pokémon Sprites](https://github.com/PokeAPI/sprites)
* [Pokémon Official](https://www.pokemon.com/)

### Tech Stack

* [Electron](https://electronjs.org/)
* [Node.js](https://nodejs.org/)
* Modern browser APIs

### Inspiration

* Official Pokédex apps
* Pokémon mainline games
* Suggestions from the community

## 📞 Contact

**Owner:** [@qileon](https://github.com/qileon)
**Project:** [github.com/qileon/pokedex-app](https://github.com/qileon/pokedex-app)

* Found a bug? Open an [issue](https://github.com/qileon/pokedex-app/issues)
* Have an idea or suggestion? Start a [discussion](https://github.com/qileon/pokedex-app/discussions)
* (P.S. I know it's not the most professional thing, but to be honest, it's more fun to keep building on existing projects)

<div align="center">
  <p><strong>⭐ If you like the project, leave a star!</strong></p>
  <p>Made with ❤️ by <a href="https://github.com/qileon">qileon</a></p>
</div>
