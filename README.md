# 🛒 Grocery Mart

A modern e-commerce frontend UI project for an online grocery/coffee store. Built with pure HTML, SCSS (using the 7-1 architecture pattern), and vanilla JavaScript — no frameworks required.

---

## 📸 Pages

| Page | File |
|------|------|
| Home (Guest) | `index.html` |
| Home (Logged in) | `index-logined.html` |
| Product Detail | `product-detail.html` |
| Checkout | `checkout.html` |
| Payment | `payment.html` |
| Shipping | `shipping.html` |
| Favourites | `favourite.html` |
| Profile | `profile.html` |
| Edit Profile | `edit-personal-info.html` |
| Add New Card | `add-new-card.html` |
| Sign In | `sign-in.html` |
| Sign Up | `sign-up.html` |
| Reset Password | `reset-password.html` |
| Reset Password (Emailed) | `reset-password-emailed.html` |
| New Password | `new-password.html` |

---

## ✨ Features

- 🌙 **Dark / Light mode** toggle with `localStorage` persistence
- 🧩 **Template loading system** — header & footer are loaded dynamically via `fetch()` and cached in `localStorage`
- 🔍 **Product filter** panel with price range, size/weight, and brand filters
- ❤️ **Favourite / like button** toggle on product cards
- 🗂️ **Category browsing** with visual category cards
- 📦 **Product detail page** with image gallery, tabs (Description, Reviews), and related products
- 🛍️ **Cart / Checkout / Payment / Shipping** flow pages
- 👤 **User profile** management pages
- 📱 **Fully responsive** — adapts to desktop, tablet, and mobile
- 🔽 **Mega dropdown navigation** with animated arrow positioning
- 🔁 **Tab switching** system for product detail content sections

---

## 🗂️ Project Structure

```
Grocery_Mart/
├── index.html                   # Home page (guest)
├── index-logined.html           # Home page (logged in)
├── product-detail.html          # Product detail page
├── checkout.html                # Checkout page
├── payment.html                 # Payment page
├── shipping.html                # Shipping page
├── favourite.html               # Favourites list
├── profile.html                 # User profile
├── edit-personal-info.html      # Edit profile info
├── add-new-card.html            # Add payment card
├── sign-in.html                 # Login page
├── sign-up.html                 # Register page
├── reset-password.html          # Password reset
├── new-password.html            # Set new password
│
├── template/
│   ├── header.html              # Shared header (guest)
│   ├── header-logined.html      # Shared header (logged in)
│   └── footer.html              # Shared footer
│
├── assets/
│   ├── css/                     # Compiled CSS output
│   ├── js/
│   │   └── script.js            # All JS logic
│   ├── img/                     # Images (products, categories, slideshow, etc.)
│   ├── icons/                   # SVG & PNG icon assets
│   ├── fonts/                   # Custom web fonts
│   └── favicon/                 # Favicon files
│
└── scss/                        # SCSS source (7-1 architecture)
    ├── main.scss                # Entry point
    ├── abstracts/               # Mixins, variables
    ├── base/                    # Reset, grid, typography
    ├── components/              # Reusable UI components
    │   ├── _buttons.scss
    │   ├── _dropdown.scss
    │   ├── _forms.scss
    │   ├── _modal.scss
    │   ├── _product-card.scss
    │   ├── _slideshow.scss
    │   └── ...
    ├── layout/                  # Header, footer, navbar
    ├── pages/                   # Page-specific styles
    │   ├── _home.scss
    │   ├── _auth.scss
    │   ├── _checkout.scss
    │   ├── _product-details.scss
    │   └── ...
    └── themes/                  # Dark/light theme variables
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (for compiling SCSS)
- A local server (e.g. [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) VS Code extension)

> ⚠️ This project uses `fetch()` to load templates. You **must** open it via a local server (not by double-clicking the HTML file), otherwise the header/footer will not load.

### Installation

```bash
# Clone the repository
git clone https://github.com/minhchuong32/grocery_mart.git
cd grocery_mart

# Install dependencies
npm install
```

### Watch SCSS (auto-compile on save)

```bash
npm run sass
```

This runs:
```
sass scss:assets/css -w
```

It compiles `scss/main.scss` → `assets/css/main.css` and watches for changes automatically.

### Run locally

Open the project with **Live Server** in VS Code, or use any local HTTP server:

```bash
# Using npx serve
npx serve .
```

Then open `http://localhost:3000` (or the port shown) in your browser.

---

## 🛠️ Tech Stack

| Technology | Usage |
|------------|-------|
| **HTML5** | Semantic page structure |
| **SCSS** | Styling with 7-1 architecture |
| **Vanilla JavaScript** | UI interactions, template loading, theme toggle |
| **CSS Custom Properties** | Theme variables (dark/light mode) |
| **LocalStorage** | Theme preference, template caching |
| **Fetch API** | Dynamic header/footer loading |

---

## 🎨 SCSS Architecture (7-1 Pattern)

The project follows the **7-1 SCSS pattern** for maintainability:

- `abstracts/` — Mixins, functions, variables (no output CSS)
- `base/` — Reset styles, grid system, typography
- `components/` — Reusable standalone UI pieces
- `layout/` — Structural layout (header, footer, navbar)
- `pages/` — Styles scoped to specific pages
- `themes/` — Dark/light mode CSS custom properties

---

## 🌙 Dark Mode

The theme is toggled via a button in the header and stored in `localStorage`:

```js
switchBtn.onclick = function () {
    const isDark = localStorage.dark === "true";
    document.querySelector("html").classList.toggle("dark", !isDark);
    localStorage.setItem("dark", !isDark);
};
```

The CSS leverages `:root` and `.dark` class selectors with CSS custom properties for seamless theming.

---

## 📄 License

This project is for educational/portfolio purposes.
