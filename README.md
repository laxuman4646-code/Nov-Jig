html 
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Clothing Store</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; background-color: #f4f4f4; }
        header { background-color: #333; color: white; padding: 1rem; text-align: center; }
        nav { background-color: #444; padding: 0.5rem; }
        nav a { color: white; margin: 0 1rem; text-decoration: none; }
        .container { max-width: 1200px; margin: 0 auto; padding: 2rem; }
        .product-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1rem; }
        .product { background: white; padding: 1rem; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); text-align: center; }
        .product img { max-width: 100%; height: 200px; object-fit: cover; }
        button { background-color: #28a745; color: white; border: none; padding: 0.5rem 1rem; cursor: pointer; border-radius: 4px; }
        button:hover { background-color: #218838; }
        footer { background-color: #333; color: white; text-align: center; padding: 1rem; margin-top: 2rem; }
        @media (max-width: 768px) { .product-grid { grid-template-columns: 1fr; } }
    </style>
</head>
<body>
    <header>
        <h1>My Clothing Store</h1>
        <p>Stylish outfits for every occasion</p>
    </header>
    <nav>
        <a href="#home">Home</a>
        <a href="#products">Products</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
    </nav>
    <div class="container">
        <section id="products">
            <h2>Featured Clothing</h2>
            <div class="product-grid">
                <div class="product">
                    <img src="https://via.placeholder.com/250x200?text=T-Shirt" alt="T-Shirt">
                    <h3>Casual T-Shirt</h3>
                    <p>$19.99</p>
                    <button onclick="addToCart('Casual T-Shirt')">Add to Cart</button>
                </div>
                <div class="product">
                    <img src="https://via.placeholder.com/250x200?text=Jeans" alt="Jeans">
                    <h3>Denim Jeans</h3>
                    <p>$49.99</p>
                    <button onclick="addToCart('Denim Jeans')">Add to Cart</button>
                </div>
                <div class="product">
                    <img src="https://via.placeholder.com/250x200?text=Dress" alt="Dress">
                    <h3>Elegant Dress</h3>
                    <p>$79.99</p>
                    <button onclick="addToCart('Elegant Dress')">Add to Cart</button>
                </div>
                <!-- Add more products as needed -->
            </div>
        </section>
        <section id="cart">
            <h2>Shopping Cart</h2>
            <ul id="cart-items"></ul>
            <p>Total: $<span id="total">0.00</span></p>
            <button onclick="checkout()">Checkout</button>
        </section>
    </div>
    <footer>
        <p>&copy; 2023 My Clothing Store. All rights reserved.</p>
    </footer>
    <script>
        let cart = [];
        let total = 0;

        function addToCart(item) {
            cart.push(item);
            total += 19.99; // Simplified pricing; adjust per item
            updateCart();
        }

        function updateCart() {
            const cartList = document.getElementById('cart-items');
            cartList.innerHTML = '';
            cart.forEach(item => {
                const li = document.createElement('li');
                li.textContent = item;
                cartList.appendChild(li);
            });
            document.getElementById('total').textContent = total.toFixed(2);
        }

        function checkout() {
            alert('Checkout not implemented yet! In a real site, integrate with Stripe or PayPal.');
        }
    </script>
</body>
</html>
