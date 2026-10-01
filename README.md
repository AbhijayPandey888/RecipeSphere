# 🍽️ RecipeSphere

RecipeSphere is a simple, responsive web app for searching recipes by meal name. Type a dish, browse the results as cards, and open any card to see its full ingredient list and cooking instructions in a pop-up.

Built with plain HTML, CSS and JavaScript (no frameworks, no build step) and powered by the free [TheMealDB API](https://www.themealdb.com/api.php).

## ✨ Features

- 🔍 Search recipes by meal name
- 🖼️ Recipe cards showing the photo, name, cuisine (area) and category
- 📖 "View Recipe" pop-up with the full ingredients list (with measurements) and step-by-step instructions
- ⏳ Loading message while recipes are being fetched
- ⚠️ Friendly messages for empty searches and for no results
- 📱 Fully responsive layout (desktop, tablet and mobile)
- 🎨 Dark, warm theme with smooth hover and modal animations
- ♿ Accessibility touches: focus outlines, labelled close button, and `prefers-reduced-motion` support

## 🛠️ Tech Stack

| Technology | Purpose |
| --- | --- |
| HTML5 | Page structure |
| CSS3 | Styling, CSS variables, Grid/Flexbox, animations, media queries |
| JavaScript (ES6+) | Fetch API, async/await, DOM manipulation |
| [TheMealDB API](https://www.themealdb.com/api.php) | Recipe data |
| [Font Awesome](https://fontawesome.com/) | Close (✕) icon |

## 📁 Project Structure

```
RecipeSphere/
├── index.html   # Page markup
├── style.css    # Styles and design tokens
├── script.js    # Search, fetch and modal logic
└── README.md
```

## 🚀 Getting Started

No installation is required.

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. **Open the app**
   - Double-click `index.html`, or
   - Use a local server such as the VS Code **Live Server** extension.
3. An internet connection is needed, since recipes come from TheMealDB and the icon from a CDN.

## 🧑‍🍳 How to Use

1. Enter a meal name (for example `Pasta`, `Chicken`, `Cake`) in the search box.
2. Click **Search**.
3. Browse the recipe cards that appear.
4. Click **View Recipe** on a card to open the details pop-up.
5. Click the red **✕** button to close it.

## ⚙️ How It Works

1. The search form calls `fetchRecipes(query)`, which requests:
   ```
   https://www.themealdb.com/api/json/v1/1/search.php?s=<query>
   ```
2. For every meal returned, a card is built dynamically and added to `.recipeContainer`.
3. Clicking **View Recipe** calls `openRecipePopup(meal)`, which fills the pop-up with the name, the ingredients (collected from `strIngredient1…20` and `strMeasure1…20` by `fetchIngredients`) and the instructions.
4. If the search box is empty, or the API returns no meals, a helpful message is shown instead.

## 🔮 Future Improvements

- Search by ingredient, category or cuisine
- Save favourite recipes (localStorage)
- Show recipe video and source links
- Dark/light theme toggle
- Escape key and outside-click to close the pop-up

## 🙏 Acknowledgements

- [TheMealDB](https://www.themealdb.com/) for the free recipe API
- [Font Awesome](https://fontawesome.com/) for icons
- [Google Fonts – Poppins](https://fonts.google.com/specimen/Poppins) for the typography style

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
