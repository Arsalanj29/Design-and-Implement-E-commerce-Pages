# Design-and-Implement-E-commerce-Pages
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Shop | Modern E-Commerce</title>
    <link rel="stylesheet" href="styles.css">
    <script defer src="script.js"></script>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">E-Shop</div>
            <input type="text" id="search-bar" placeholder="Search for products" oninput="searchProducts()">
            <div class="nav-icons">
                <a href="#cart" class="cart">🛒 Cart (<span id="cart-count">0</span>)</a>
                <a href="#account" class="account">👤 Account</a>
            </div>
        </nav>
    </header>

    <!-- Product Listing Section -->
    <section id="product-listing" class="active">
        <main class="filters">
            <h2>Filters</h2>
            <div>
                <label for="category">Category</label>
                <select id="category" onchange="filterProducts()">
                    <option value="All">All</option>
                    <option value="electronics">Electronics</option>
                    <option value="clothing">Clothing</option>
                    <option value="home">Home Appliances</option>
                </select>
            </div>
            <div>
                <label for="price-range">Price Range</label>
                <input type="range" id="price-range" min="0" max="1000" oninput="updatePriceRange()">
                <span id="price-range-value">$500</span>
            </div>
        </main>
        <main class="product-listing">
            <div class="product-grid" id="product-grid">
                <!-- Example Product Card -->
                <div class="product-card" onclick="showDetails()">
                    <img src="https://via.placeholder.com/200" alt="Product Image">
                    <h3>Magoooo</h3>
                    <p class="price">$99.99</p>
                    <p class="rating">⭐⭐⭐⭐☆</p>
                    <button class="btn-add-to-cart" onclick="addToCart(event)">Add to Cart</button>
                </div>
                <!-- Add more products as needed -->
            </div>
            <div class="pagination">
                <button class="btn-pagination">Previous</button>
                <button class="btn-pagination">Next</button>
            </div>
        </main>
    </section>

    <!-- Product Details Section -->
    <section id="product-details" class="hidden">
        <div class="details-container">
            <div class="product-image">
                <img src="https://via.placeholder.com/400" alt="Product Image">
            </div>
            <div class="product-info">
                <h1>Product Title</h1>
                <h2 class="price">$99.99</h2>
                <p class="description">
                    This is a detailed description of the product. It highlights features, materials, and usage.
                </p>
                <ul>
                    <li>Specification 1</li>
                    <li>Specification 2</li>
                    <li>Specification 3</li>
                </ul>
                <div class="actions">
                    <button class="btn-add-to-cart" onclick="addToCart(event)">Add to Cart</button>
                    <button class="btn-buy-now">Buy Now</button>
                </div>
            </div>
        </div>
        <button class="btn-back" onclick="showListing()">← Back to Listing</button>
    </section>

    <!-- User Authentication Section -->
    <section id="auth-section" class="hidden">
        <div class="auth-container">
            <h2>Account</h2>
            <div id="login-form">
                <h3>Login</h3>
                <input type="email" id="login-email" placeholder="Email">
                <input type="password" id="login-password" placeholder="Password">
                <button onclick="login()">Login</button>
            </div>
            <div id="signup-form">
                <h3>Signup</h3>
                <input type="email" id="signup-email" placeholder="Email">
                <input type="password" id="signup-password" placeholder="Password">
                <button onclick="signup()">Signup</button>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 E-Shop. All rights reserved.</p>
    </footer>

    <script>
        // Add JavaScript functions for search, filter, cart, and authentication
        function searchProducts() {
            // Implement product search functionality
        }

        function filterProducts() {
            // Implement product filtering functionality
        }

        function updatePriceRange() {
            // Update price range display
        }

        function addToCart(event) {
            event.stopPropagation();
            // Implement add to cart functionality
        }

        function showDetails() {
            // Show product details section
        }

        function showListing() {
            // Show product listing section
        }

        function login() {
            // Implement login functionality
        }

        function signup() {
            // Implement signup functionality
        }
    </script>
</body>
</html>


/* General Styles */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  background-color: #e525ef;
  color: #333;
  box-sizing: border-box;
}

.hidden {
  display: none;
}

.active {
  display: block;
}

/* Header Styles */
header {
  background-color: #d98f28;
  color: #fff;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

header .logo {
  font-size: 1.8rem;
  font-weight: bold;
}

header input {
  width: 40%;
  padding: 0.6rem;
  border: none;
  border-radius: 20px;
  font-size: 1rem;
}

header input:focus {
  outline: 2px solid #0056b3;
}

header .nav-icons a {
  margin-left: 1rem;
  color: #fff;
  text-decoration: none;
  font-size: 1.2rem;
  position: relative;
}

header .nav-icons a:hover {
  color: #ffd700;
}

header .cart span {
  position: absolute;
  top: -10px;
  right: -10px;
  background-color: #dc3545;
  color: #fff;
  font-size: 0.8rem;
  width: 18px;
  height: 18px;
  text-align: center;
  border-radius: 50%;
}

/* Filters Section */
.filters {
  position: fixed;
  top: 0; /* Leave space for the header */
  left: 0;
  width: 20%;
  background: #e0c512;
  padding: 1.5rem;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: sticky; /* Change from fixed to sticky */
  
}

.filters h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  border-bottom: 2px solid #007bff;
  padding-bottom: 0.5rem;
  color: #007bff;
}

.filters label {
  display: block;
  margin: 1rem 0 0.5rem;
  font-weight: bold;
}

.filters select, .filters input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
}

.filters input[type="range"] {
  background-color: transparent;
}

#price-range-value {
  display: block;
  text-align: center;
  font-weight: bold;
  margin-top: 0.5rem;
}

/* Product Listing */
.product-listing {
  margin-left: 22%; /* Adjust to leave space for the fixed filter sidebar */
  padding: 2rem;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.product-card {
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  text-align: center;
  transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
}

.product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.product-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  margin-bottom: 1rem;
}

.product-card h3 {
  font-size: 1.2rem;
  margin: 0.5rem 0;
}

.product-card .price {
  font-size: 1.5rem;
  color: #007bff;
  font-weight: bold;
}

.product-card .rating {
  font-size: 1.2rem;
  color: #ffc107;
}

.product-card button {
  margin-top: 1rem;
  padding: 0.5rem 1.5rem;
  font-size: 1rem;
  color: #fff;
  background-color: #007bff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.product-card button:hover {
  background-color: #0056b3;
}

/* Pagination */
.pagination {
  text-align: center;
  margin-top: 2rem;
}

.pagination .btn-pagination {
  padding: 0.5rem 1.5rem;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  margin: 0 0.5rem;
}

.pagination .btn-pagination:hover {
  background-color: #0056b3;
}

/* Product Details */
.details-container {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  padding: 2rem;
  background: #fff;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
  border-radius: 10px;
  margin: 2rem auto;
  width: 80%;
}

.product-image img {
  max-width: 100%;
  border-radius: 10px;
}

.product-info {
  flex: 1;
}

.product-info h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

.product-info .price {
  font-size: 1.8rem;
  color: #007bff;
  font-weight: bold;
  margin-bottom: 1rem;
}

.product-info .description {
  margin-bottom: 1rem;
  line-height: 1.5;
}

.product-info ul {
  list-style-type: disc;
  padding-left: 1rem;
  margin-bottom: 1rem;
}

.product-info .actions button {
  padding: 0.5rem 1.5rem;
  margin-right: 1rem;
  font-size: 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.btn-add-to-cart {
  background-color: #28a745;
  color: #fff;
}

.btn-add-to-cart:hover {
  background-color: #218838;
}

.btn-buy-now {
  background-color: #577359;
  color: #fff;
}

.btn-buy-now:hover {
  background-color: #c82333;
}

.btn-back {
  margin-top: 1rem;
  padding: 0.5rem 1.5rem;
  background: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.btn-back:hover {
  background-color: #0056b3;
}

/* Footer */
footer {
  text-align: center;
  padding: 1rem;
  background-color: #333;
  color: #fff;
  font-size: 0.9rem;
  position: relative;
}



// Global Variables
let cartCount = 0;
const products = [
    {
        id: 1,
        name: "Product 1",
        category: "electronics",
        price: 99.99,
        rating: 4,
        image: "https://via.placeholder.com/200",
    },
    {
        id: 2,
        name: "Product 2",
        category: "clothing",
        price: 49.99,
        rating: 5,
        image: "https://via.placeholder.com/200",
    },
    {
        id: 3,
        name: "Product 3",
        category: "home",
        price: 299.99,
        rating: 3,
        image: "https://via.placeholder.com/200",
    },
];

// Function to Render Products
function renderProducts(filterFn = () => true) {
    const productGrid = document.getElementById("product-grid");
    productGrid.innerHTML = ""; // Clear existing products
    const filteredProducts = products.filter(filterFn);

    filteredProducts.forEach((product) => {
        const productCard = `
            <div class="product-card" onclick="showDetails(${product.id})">
                <img src="${product.image}" alt="${product.name}">
                <h3>${product.name}</h3>
                <p class="price">$${product.price.toFixed(2)}</p>
                <p class="rating">${"⭐".repeat(product.rating)}</p>
                <button class="btn-add-to-cart" onclick="addToCart(event, ${product.id})">Add to Cart</button>
            </div>
        `;
        productGrid.innerHTML += productCard;
    });
}

// Initial Render
renderProducts();

// Search Products
function searchProducts() {
    const query = document.getElementById("search-bar").value.toLowerCase();
    renderProducts((product) =>
        product.name.toLowerCase().includes(query)
    );
}

// Filter Products by Category
function filterProducts() {
    const category = document.getElementById("category").value;
    renderProducts(
        (product) =>
            category === "all" || product.category === category
    );
}

// Update Price Range
function updatePriceRange() {
    const rangeValue = document.getElementById("price-range").value;
    document.getElementById("price-range-value").textContent = $${rangeValue};
    renderProducts((product) => product.price <= rangeValue);
}

// Add to Cart
function addToCart(event, productId) {
    event.stopPropagation(); // Prevent triggering showDetails
    cartCount++;
    document.getElementById("cart-count").textContent = cartCount;
    alert(Product ${productId} added to cart!);
}

// Show Product Details
function showDetails(productId) {
    const product = products.find((p) => p.id === productId);
    const detailsSection = document.getElementById("product-details");
    const listingSection = document.getElementById("product-listing");

    document.querySelector("#product-details .product-image img").src =
        product.image;
    document.querySelector("#product-details .product-info h1").textContent =
        product.name;
    document.querySelector("#product-details .product-info .price").textContent =
        $${product.price.toFixed(2)};
    document.querySelector(
        "#product-details .product-info .description"
    ).textContent = This is a detailed description of ${product.name}.;

    listingSection.classList.add("hidden");
    detailsSection.classList.remove("hidden");
}

// Back to Listing
function showListing() {
    const detailsSection = document.getElementById("product-details");
    const listingSection = document.getElementById("product-listing");
    detailsSection.classList.add("hidden");
    listingSection.classList.remove("hidden");
}

// Login Functionality
function login() {
    const email = document.getElementById("login-email").value;
    const password = document.getElementById("login-password").value;

    if (email === "user@example.com" && password === "password123") {
        alert("Login successful!");
        document.getElementById("auth-section").classList.add("hidden");
    } else {
        alert("Invalid credentials!");
    }
}

// Signup Functionality
function signup() {
    const email = document.getElementById("signup-email").value;
    const password = document.getElementById("signup-password").value;

    if (email && password) {
        alert("Signup successful! You can now log in.");
        document.getElementById("signup-email").value = "";
        document.getElementById("signup-password").value = "";
    } else {
        alert("Please fill in all fields.");
    }
}
