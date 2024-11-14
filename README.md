Here’s how the README can be formatted for GitHub. You can copy and paste this directly into your `README.md` file:

```markdown
# Recipe App

This is a React Native app that allows users to view, like, comment on, and manage their favorite recipes. It supports filtering recipes by vegan or non-vegan, and offers features such as liking, commenting, and bookmarking favorite recipes. The app stores user interactions locally using `AsyncStorage` to persist likes, comments, and favorites across sessions.

## Features

- Recipe List: Display a list of recipes with details such as title, time to cook, and whether the recipe is vegan.
  - Allows users to like recipes and increase the like count.
  - Users can add comments to recipes.
- Favorite Recipes: Users can add recipes to their favorites list and remove them.
  - Display favorite recipes in a separate "Favorites" screen, where users can see and manage their favorites.
- Vegan/Non-Vegan Filter: Recipes can be filtered based on whether they are vegan or non-vegan.

## Components

### 1. App Component
The main screen of the app where users can:
- Search for recipes by title.
- Filter recipes by vegan/non-vegan categories.
- View recipe details and interact with them (like, comment, add to favorites).
- Each recipe has a like button, comment input, and favorite toggle.

Key Functions:
- Like a Recipe: Clicking the heart button increments the like count.
- Add Comments: Users can add comments on each recipe.
- Toggle Favorite: Star button allows users to add/remove recipes from their favorites list.

```javascript
const handleLike = (id) => { ... };
const handleAddComment = (id, comment) => { ... };
const handleToggleFavorite = (id) => { ... };
```

### 2. **Bookmark Component**
This screen displays a list of favorite recipes. Users can remove recipes from their favorites.

Key Functions:
- Remove from Favorites: Users can confirm and remove a recipe from the favorites list.
- Display Recipe: Each favorite recipe shows the title, image, and a "Remove" button.

```javascript
const handleRemoveRecipe = (id) => { ... };
```

### 3. **RecipeItem Component**
This is a reusable component that represents a single recipe item on both the main screen and the favorites screen. It displays the recipe image, title, and action buttons for liking, commenting, and toggling the favorite status.

**Key Props**:
- `recipe`: The recipe object containing details like title, likes, image, and whether it's a favorite.
- `onLike`: Function to increment the like count.
- `comments`: List of comments for the recipe.
- `onAddComment`: Function to add a new comment to the recipe.
- `onToggleFavorite`: Function to toggle the favorite status.

```javascript
<RecipeItem 
    recipe={item} 
    onLike={() => handleLike(item.id)} 
    comments={comments[item.id] || []} 
    onAddComment={handleAddComment} 
    onToggleFavorite={() => handleToggleFavorite(item.id)} 
/>
```

## Technologies

- **React Native**: Cross-platform mobile app development.
- **Expo**: Managed workflow for building and running React Native apps.
- **AsyncStorage**: Local storage for persisting likes, comments, and favorites.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/recipe-app.git
```

2. Install dependencies:

```bash
cd recipe-app
npm install
```

3. Run the app:

```bash
npx expo start
```

4. Open the app in the Expo Go app or in a simulator/emulator.

## Screenshots

### Recipe List Screen:
![WhatsApp Image 2024-11-14 at 9 52 37 PM](https://github.com/user-attachments/assets/c90ec960-87d8-498f-8c04-9779612a49a0)

### Jokes Screen:
![WhatsApp Image 2024-11-14 at 9 52 37 PM (1)](https://github.com/user-attachments/assets/b76df56d-3379-42fb-a4bc-0d49046333b3)

### Favorites Screen:
![WhatsApp Image 2024-11-14 at 9 52 36 PM](https://github.com/user-attachments/assets/bf34635e-d710-4d06-9a97-dfdb40ff5c94)

---

### Notes:

- **Assets**: Ensure that you have images for the recipes stored in the correct path (`../../assets/images/`) to display them properly.
- **State Persistence**: The app uses `AsyncStorage` to persist likes, comments, and favorites across sessions. The data is loaded when the app starts and saved when updated.

```
