<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Commerce Website</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            color: #fff;
            background: url('https://via.placeholder.com/1920x1080?text=Galaxy+Background') no-repeat center center fixed;
            background-size: cover;
        }
        header {
            background-color: rgba(0, 0, 128, 0.8);
            padding: 1em;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: center;
            gap: 1em;
        }
        nav a {
            color: #fff;
            text-decoration: none;
            padding: 0.5em 1em;
            border: 1px solid #fff;
            border-radius: 5px;
            background-color: rgba(255, 255, 255, 0.2);
        }
        nav a:hover {
            background-color: rgba(255, 255, 255, 0.4);
        }
        .content {
            padding: 2em;
            text-align: center;
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1em;
            padding: 2em;
        }
        .product {
            background-color: rgba(255, 255, 255, 0.2);
            border: 1px solid #fff;
            border-radius: 10px;
            padding: 1em;
            text-align: center;
        }
        .product img {
            max-width: 100%;
            border-radius: 10px;
        }
        .cart {
            background-color: rgba(0, 0, 128, 0.8);
            padding: 1em;
            margin: 2em;
            border-radius: 10px;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            margin: 1em 0;
        }
        footer {
            background-color: rgba(0, 0, 128, 0.8);
            text-align: center;
            padding: 1em;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Galaxy Shop</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#shop">Shop</a>
            <a href="#about">About Us</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <div id="home" class="content">
        <h2>Explore the Universe of Products</h2>
        <p>Your one-stop shop for stellar items!</p>
    </div>

    <div id="shop" class="content">
        <h2>Shop Our Collection</h2>
        <div class="product-grid">
            <div class="product">
                <img src="https://via.placeholder.com/200" alt="Product 1">
                <h3>Galaxy Mug</h3>
                <p>$15.99</p>
                <button onclick="addToCart('Galaxy Mug', 15.99)">Add to Cart</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/200" alt="Product 2">
                <h3>Starry Night Lamp</h3>
                <p>$29.99</p>
                <button onclick="addToCart('Starry Night Lamp', 29.99)">Add to Cart</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/200" alt="Product 3">
                <h3>Space Notebook</h3>
                <p>$9.99</p>
                <button onclick="addToCart('Space Notebook', 9.99)">Add to Cart</button>
            </div>
            <div class="product">
                <img src="https://via.placeholder.com/200" alt="Product 4">
                <h3>Cosmic T-Shirt</h3>
                <p>$19.99</p>
                <button onclick="addToCart('Cosmic T-Shirt', 19.99)">Add to Cart</button>
            </div>
        </div>
    </div>

    <div id="cart" class="content">
        <h2>Your Cart</h2>
        <div class="cart" id="cart-items">
            <p>Your cart is empty.</p>
        </div>
    </div>

    <div id="about" class="content">
        <h2>About Us</h2>
        <p>We bring the galaxy closer to you through our products.</p>
    </div>

    <div id="contact" class="content">
        <h2>Contact Us</h2>
        <form>
            <input type="text" placeholder="Your Name" required><br>
            <input type="email" placeholder="Your Email" required><br>
            <textarea placeholder="Your Message" required></textarea><br>
            <button type="submit">Send Message</button>
        </form>
    </div>

    <footer>
        <p>&copy; 2024 Galaxy Shop. All Rights Reserved.</p>
    </footer>

    <script>
        let cart = [];

        function addToCart(product, price) {
            cart.push({ product, price });
            displayCart();
        }

        function displayCart() {
            const cartItems = document.getElementById('cart-items');
            if (cart.length === 0) {
                cartItems.innerHTML = '<p>Your cart is empty.</p>';
                return;
            }

            cartItems.innerHTML = cart.map((item, index) => `
                <div class="cart-item">
                    <span>${item.product} - $${item.price.toFixed(2)}</span>
                    <button onclick="removeFromCart(${index})">Remove</button>
                </div>
            `).join('');
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            displayCart();
        }
    </script>
</body>
</html>
