# 💻 Lab: Design & Build a Fake E-Commerce Website

---

## ✅ Objectives

- Practice **UX design process** from sketch to hi-fi prototype.
- Implement a real UI using **HTML/CSS/Bootstrap/JavaScript**.
- Consume a public API using `fetch` or `axios`.
- Add interactivity, animations, icons, charts, and responsive UI elements.
- Learn **separation of concerns** between layout, style, and behavior.

---

## 🧹 Part 1: UX Design Process (Figma + Sketches)

### 📌 Goal: Design a fake eCommerce website selling products using [Fake Store API](https://fakestoreapi.com/)

### 1.1 🔍 Requirements Gathering

Students should answer:

- Who is the user?
- What problem are we solving?
- What pages are needed? (Landing Page, Cart Page, Dashboard)
- What interactions do we expect? (Add to cart, View cart, Sort/filter/search)

### 1.2 ✏️ Sketches (Paper or Tablet)

- Sketch a rough **user flow** (Landing → Cart → Dashboard)
- Sketch layout for:
  - Landing Page
  - Cart Page
  - Dashboard Page

### 1.3 🧱 Low-Fidelity Wireframes

- Use Figma or any tool to draw:
  - Layout structure (header, card grid, cart layout, footer)

### 1.4 🎨 High-Fidelity Designs

Create a clickable prototype in Figma:

- Use realistic images and text
- Add buttons, colors, fonts
- Link navigation between pages
- Use **Roboto** from Google Fonts

---

## 🧪 Part 2: Frontend Implementation

Use **HTML + CSS + JS + Bootstrap**.

---

### 2.1 📁 Folder Structure

```bash
ecommerce-lab/
│
├── index.html
├── cart.html
├── dashboard.html
├── css/
│   └── styles.css
├── js/
│   ├── main.js
│   ├── cart.js
│   └── dashboard.js
├── assets/
│   └── (icons, images if needed)
```

---

### 2.2 🩰 Header (on all pages)

- Use Bootstrap `navbar`
- Add links to: Home | Cart | Dashboard
- Add site logo or name

**Example:**

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">FakeShop</a>
  <div class="collapse navbar-collapse">
    <ul class="navbar-nav">
      <li class="nav-item"><a class="nav-link" href="index.html">Home</a></li>
      <li class="nav-item"><a class="nav-link" href="cart.html">Cart</a></li>
      <li class="nav-item"><a class="nav-link" href="dashboard.html">Dashboard</a></li>
    </ul>
  </div>
</nav>
```

---

### 2.3 📦 Product Cards (index.html)

- Fetch products from [https://fakestoreapi.com/products](https://fakestoreapi.com/products)
- Use `<template>` tag for product card
- Use Bootstrap Card component:
  - Image
  - Title
  - Price
  - Short Description
  - “Add to Cart” button
- Add hover animation:

```css
.card:hover {
  transform: scale(1.03);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
  transition: 0.3s ease;
}
```

**Example Bootstrap Card Template:**

```html
<template id="product-template">
  <div class="col-md-4">
    <div class="card mb-4">
      <img class="card-img-top" src="" alt="Product Image">
      <div class="card-body">
        <h5 class="card-title"></h5>
        <p class="card-text"></p>
        <p class="card-price fw-bold text-success"></p>
        <button class="btn btn-primary add-to-cart">Add to Cart</button>
      </div>
    </div>
  </div>
</template>
```

---

### 2.4 🛒 Cart Page (cart.html)

- Show list of products added to cart
- Display:
  - Product Title
  - Price
  - Quantity
- On right side, show **Price Summary**:
  - Subtotal
  - Tax (fake)
  - Total

---

### 2.5 📊 Dashboard (dashboard.html)

- Use `Chart.js` or `Echarts.js`
- Fetch products and group by `category`
- Display **Bar Chart**: "Number of Products by Category"

**Chart.js Example:**

```html
<canvas id="categoryChart"></canvas>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  const ctx = document.getElementById('categoryChart').getContext('2d');
  const chart = new Chart(ctx, {
    type: 'bar',
    data: {
      labels: ['electronics', 'jewelery', "men's clothing", "women's clothing"],
      datasets: [{
        label: 'Number of Products',
        data: [5, 3, 7, 6],
        backgroundColor: '#0d6efd'
      }]
    }
  });
</script>
```

---

## 🌟 Optional Enhancements

### (1) 🕽️ Category Filter

- Add a `select` dropdown on index.html
- Only show products from selected category

**Example:**

```html
<select id="categoryFilter" class="form-select">
  <option value="all">All Categories</option>
  <option value="electronics">Electronics</option>
  <option value="jewelery">Jewelery</option>
</select>
```

### (2) 🔍 Search Box

- Add input field to filter products by title/description

**Example:**

```html
<input type="text" id="searchInput" class="form-control" placeholder="Search products...">
```

### (3) 🍿 Category Icons

- Add icons using FontAwesome/Iconify for each category

**Example:**

```html
<script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
<i class="fas fa-laptop"></i> Electronics
```

### (4) 🔄 Sort Feature

- Dropdown to sort by:
  - Title (A-Z)
  - Price (Low to High, High to Low)

**Example:**

```html
<select id="sortOptions" class="form-select">
  <option value="title">Sort by Title</option>
  <option value="priceLow">Price: Low to High</option>
  <option value="priceHigh">Price: High to Low</option>
</select>
```

---

## 🎨 Styling & Fonts

- Use Google Fonts `Roboto`
- Use consistent colors and spacing
- Footer should contain:
  - Social media icons (FontAwesome)
  - Copyright

**Include Roboto Font:**

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
<style>
  body {
    font-family: 'Roboto', sans-serif;
  }
</style>
```

**Example Footer with Icons:**

```html
<footer class="text-center p-3">
  <p>Follow us:</p>
  <a href="#"><i class="fab fa-facebook fa-lg mx-2"></i></a>
  <a href="#"><i class="fab fa-twitter fa-lg mx-2"></i></a>
  <a href="#"><i class="fab fa-instagram fa-lg mx-2"></i></a>
  <p class="mt-3">&copy; 2025 FakeShop. All rights reserved.</p>
</footer>
```

---

## 🚀 Bonus Challenges

- Add a loading spinner while fetching data
- Add animations when cards are added to cart
- Use localStorage to persist cart items across page reloads

---

## 🔍 Submission Requirements

Students should submit:

- Link to Figma Design
- Source code on GitHub
- Live hosted site (Netlify, Vercel, GitHub Pages, etc.)

---

## 🔍 Evaluation Rubric

| Category             | Points |
| -------------------- | ------ |
| UX Design (Figma)    | 20     |
| Responsive Layout    | 15     |
| API Integration      | 20     |
| Functionality (Cart) | 15     |
| Dashboard Chart      | 10     |
| Code Structure/Clean | 10     |
| Bonus Features       | 10     |

