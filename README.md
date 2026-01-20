# E-commerce-coffee-shop
website 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brew&Bean - Karachi's Favourite Coffee House</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #6F4E37;
            --secondary-color: #D4A574;
            --accent-color: #8B4513;
            --text-light: #333;
            --text-dark: #fff;
            --bg-light: #FFF8F0;
            --bg-dark: #1a1a1a;
            --card-light: #fff;
            --card-dark: #2d2d2d;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        body.light-mode {
            background-color: var(--bg-light);
            color: var(--text-light);
        }

        body.dark-mode {
            background-color: var(--bg-dark);
            color: var(--text-dark);
        }

        /* Header */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 50px;
            background-color: var(--primary-color);
            color: white;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 32px;
            font-weight: 700;
            animation: fadeInLeft 1s ease;
        }

        nav {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease, transform 0.3s ease;
            padding: 8px 15px;
        }

        nav a:hover {
            color: var(--secondary-color);
            transform: translateY(-2px);
        }

        .login-button {
            background-color: var(--secondary-color);
            color: var(--primary-color);
            border: none;
            padding: 10px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .login-button:hover {
            background-color: white;
            transform: scale(1.05);
        }

        .theme-toggle {
            background-color: var(--secondary-color);
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
            color: var(--primary-color);
        }

        .theme-toggle:hover {
            background-color: var(--accent-color);
            color: white;
            transform: scale(1.05);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            color: white;
            padding: 100px 50px;
            text-align: center;
            animation: fadeIn 1.5s ease;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 56px;
            margin-bottom: 20px;
            animation: slideInDown 1s ease;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            animation: slideInUp 1s ease;
        }

        .cta-button {
            background-color: var(--secondary-color);
            color: var(--primary-color);
            padding: 15px 40px;
            border: none;
            border-radius: 30px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }

        .cta-button:hover {
            background-color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        /* Features Section - Flexbox */
        .features {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            padding: 80px 50px;
            gap: 30px;
            margin: 40px 0;
        }

        .feature-card {
            flex: 1;
            min-width: 250px;
            max-width: 350px;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease;
        }

        body.light-mode .feature-card {
            background-color: var(--card-light);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        body.dark-mode .feature-card {
            background-color: var(--card-dark);
            box-shadow: 0 5px 15px rgba(255,255,255,0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }

        .feature-icon {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            color: var(--primary-color);
            margin-bottom: 15px;
            font-size: 24px;
        }

        body.dark-mode .feature-card h3 {
            color: var(--secondary-color);
        }

        /* Menu Section - Grid */
        .menu-section {
            padding: 80px 50px;
        }

        .section-title {
            font-family: 'Playfair Display', serif;
            font-size: 42px;
            text-align: center;
            margin-bottom: 50px;
            color: var(--primary-color);
        }

        body.dark-mode .section-title {
            color: var(--secondary-color);
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .menu-item {
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            animation: zoomIn 0.8s ease;
        }

        body.light-mode .menu-item {
            background-color: var(--card-light);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        body.dark-mode .menu-item {
            background-color: var(--card-dark);
            box-shadow: 0 5px 15px rgba(255,255,255,0.1);
        }

        .menu-item:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .menu-item img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .menu-item:hover img {
            transform: scale(1.1);
        }

        .menu-content {
            padding: 25px;
        }

        .menu-content h3 {
            color: var(--primary-color);
            margin-bottom: 10px;
            font-size: 22px;
        }

        body.dark-mode .menu-content h3 {
            color: var(--secondary-color);
        }

        .menu-content p {
            margin-bottom: 15px;
            font-size: 14px;
        }

        .price {
            font-size: 24px;
            font-weight: 700;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .order-button {
            width: 100%;
            padding: 12px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .order-button:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        /* Gallery Section */
        .gallery {
            padding: 80px 50px;
            text-align: center;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.2) rotate(2deg);
        }

        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(111, 78, 55, 0.8);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }

        .gallery-overlay h4 {
            color: white;
            font-size: 24px;
        }

        /* Contact Section */
        .contact {
            padding: 80px 50px;
            text-align: center;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 50px;
            flex-wrap: wrap;
            margin-top: 40px;
        }

        .contact-item {
            flex: 1;
            min-width: 250px;
            padding: 30px;
            border-radius: 15px;
            transition: transform 0.3s ease;
        }

        body.light-mode .contact-item {
            background-color: var(--card-light);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        body.dark-mode .contact-item {
            background-color: var(--card-dark);
            box-shadow: 0 5px 15px rgba(255,255,255,0.1);
        }

        .contact-item:hover {
            transform: translateY(-5px);
        }

        .contact-item h4 {
            color: var(--primary-color);
            font-size: 20px;
            margin-bottom: 15px;
        }

        body.dark-mode .contact-item h4 {
            color: var(--secondary-color);
        }

        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 30px;
            margin-top: 50px;
        }

        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            animation: fadeIn 0.3s ease;
        }

        .modal-content {
            position: relative;
            margin: 5% auto;
            padding: 40px;
            width: 90%;
            max-width: 450px;
            max-height: 90vh;
            overflow-y: auto;
            border-radius: 20px;
            animation: slideInDown 0.5s ease;
        }

        body.light-mode .modal-content {
            background-color: var(--card-light);
        }

        body.dark-mode .modal-content {
            background-color: var(--card-dark);
        }

        .close {
            position: absolute;
            right: 20px;
            top: 15px;
            font-size: 35px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close:hover {
            color: var(--accent-color);
        }

        .login-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .login-header h2 {
            font-family: 'Playfair Display', serif;
            font-size: 32px;
            color: var(--primary-color);
            margin-bottom: 10px;
        }

        body.dark-mode .login-header h2 {
            color: var(--secondary-color);
        }

        .login-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .form-group label {
            font-weight: 600;
            font-size: 14px;
            color: var(--primary-color);
        }

        body.dark-mode .form-group label {
            color: var(--secondary-color);
        }

        .form-group input {
            padding: 12px 15px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 16px;
            transition: all 0.3s ease;
        }

        body.dark-mode .form-group input {
            background-color: var(--bg-dark);
            border-color: #444;
            color: white;
        }

        .form-group input:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(111, 78, 55, 0.1);
        }

        .login-submit {
            background-color: var(--primary-color);
            color: white;
            padding: 14px;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
        }

        .login-submit:hover {
            background-color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .login-footer {
            text-align: center;
            margin-top: 20px;
            font-size: 14px;
        }

        .login-footer a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
        }

        body.dark-mode .login-footer a {
            color: var(--secondary-color);
        }

        .login-footer a:hover {
            text-decoration: underline;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes slideInUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes zoomIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                padding: 20px;
                gap: 20px;
            }

            nav {
                flex-direction: column;
                gap: 15px;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 16px;
            }

            .features {
                padding: 40px 20px;
            }

            .menu-section {
                padding: 40px 20px;
            }

            .section-title {
                font-size: 32px;
            }

            .gallery {
                padding: 40px 20px;
            }

            .contact {
                padding: 40px 20px;
            }

            .contact-info {
                flex-direction: column;
                gap: 20px;
            }

            .modal-content {
                margin: 5% auto;
                padding: 30px 20px;
                max-height: 85vh;
            }
        }
    </style>
</head>
<body class="light-mode">
    <header>
        <div class="logo">☕Brew&Bean</div>
        <nav>
            <a href="#home">Home</a>
            <a href="#menu">Menu</a>
            <a href="#gallery">Gallery</a>
            <a href="#contact">Contact</a>
            <button class="login-button" onclick="openLoginModal()">🔐 Login</button>
            <button class="theme-toggle" onclick="toggleTheme()">🌙 Dark Mode</button>
        </nav>
    </header>

    <section class="hero" id="home">
        <h1>Karachi's Favourite Coffee House</h1>
        <p>Premium coffee crafted with passion, served with love</p>
        <button class="cta-button" onclick="scrollToMenu()">Order Now</button>
    </section>

    <section class="features">
        <div class="feature-card">
            <div class="feature-icon">☕</div>
            <h3>Premium Coffee</h3>
            <p>Sourced from the finest coffee beans around the world</p>
        </div>
        <div class="feature-card">
            <div class="feature-icon">🚀</div>
            <h3>Fast Delivery</h3>
            <p>Quick delivery to your doorstep within 30 minutes</p>
        </div>
        <div class="feature-card">
            <div class="feature-icon">💳</div>
            <h3>Easy Payment</h3>
            <p>Multiple payment options available for your convenience</p>
        </div>
    </section>

    <section class="menu-section" id="menu">
        <h2 class="section-title">Our Special Menu</h2>
        <div class="menu-grid">
            <div class="menu-item">
                <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=600&h=400&fit=crop" alt="Cappuccino">
                <div class="menu-content">
                    <h3>Classic Cappuccino</h3>
                    <p>Rich espresso with steamed milk and foam</p>
                    <div class="price">Rs. 350</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
            <div class="menu-item">
                <img src="https://images.unsplash.com/photo-1485808191679-5f86510681a2?w=600&h=400&fit=crop" alt="Latte">
                <div class="menu-content">
                    <h3>Caramel Latte</h3>
                    <p>Smooth latte with sweet caramel drizzle</p>
                    <div class="price">Rs. 400</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
            <div class="menu-item">
                <img src="https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=600&h=400&fit=crop" alt="Espresso">
                <div class="menu-content">
                    <h3>Double Espresso</h3>
                    <p>Pure concentrated coffee shot for true lovers</p>
                    <div class="price">Rs. 250</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
            <div class="menu-item">
                <img src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=600&h=400&fit=crop" alt="Mocha">
                <div class="menu-content">
                    <h3>Chocolate Mocha</h3>
                    <p>Coffee meets chocolate in perfect harmony</p>
                    <div class="price">Rs. 450</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
            <div class="menu-item">
                <img src="https://images.unsplash.com/photo-1517487881594-2787fef5ebf7?w=600&h=400&fit=crop" alt="Iced Coffee">
                <div class="menu-content">
                    <h3>Iced Americano</h3>
                    <p>Refreshing cold coffee for hot days</p>
                    <div class="price">Rs. 380</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
            <div class="menu-item">
                <img src="https://plus.unsplash.com/premium_photo-1674327105076-36c4419864cf?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTd8fGZsYXQlMjB3aGl0ZXxlbnwwfHwwfHx8MA%3D%3D=crop" alt="Flat White">
                <div class="menu-content">
                    <h3>Flat White</h3>
                    <p>Velvety smooth espresso with microfoam</p>
                    <div class="price">Rs. 420</div>
                    <button class="order-button">Order Now</button>
                </div>
            </div>
        </div>
    </section>

    <section class="gallery" id="gallery">
        <h2 class="section-title">Our Atmosphere</h2>
        <div class="gallery-grid">
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348?w=500&h=400&fit=crop" alt="Coffee Shop">
                <div class="gallery-overlay">
                    <h4>Cozy Interior</h4>
                </div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1453614512568-c4024d13c247?w=500&h=400&fit=crop" alt="Barista">
                <div class="gallery-overlay">
                    <h4>Expert Baristas</h4>
                </div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=500&h=400&fit=crop" alt="Coffee Bar">
                <div class="gallery-overlay">
                    <h4>Premium Bar</h4>
                </div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1442512595331-e89e73853f31?w=500&h=400&fit=crop" alt="Cafe">
                <div class="gallery-overlay">
                    <h4>Relaxing Ambiance</h4>
                </div>
            </div>
        </div>
    </section>

    <section class="contact" id="contact">
        <h2 class="section-title">Get In Touch</h2>
        <div class="contact-info">
            <div class="contact-item">
                <h4>📞 Call Us</h4>
                <p>03053805691</p>
            </div>
            <div class="contact-item">
                <h4>📍 Visit Us</h4>
                <p>Multiple locations in Karachi</p>
            </div>
            <div class="contact-item">
                <h4>⏰ Working Hours</h4>
                <p>Mon - Sun: 8:00 AM - 11:00 PM</p>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2024 Brew&Bean. All rights reserved. | Karachi's Favourite Coffee House</p>
    </footer>

    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeLoginModal()">&times;</span>
            <div class="login-header">
                <h2>☕ Welcome Back!</h2>
                <p>Login to order your favourite coffee</p>
            </div>
            <form class="login-form" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" placeholder="your@email.com" required>
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" placeholder="Enter your password" required>
                </div>
                <button type="submit" class="login-submit">Login</button>
            </form>
            <div class="login-footer">
                <p>Don't have an account? <a href="#" onclick="openSignupModal()">Sign Up</a></p>
                <p><a href="#" onclick="alert('Password reset link sent to your email!')">Forgot Password?</a></p>
            </div>
        </div>
    </div>

    <!-- Signup Modal -->
    <div id="signupModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeSignupModal()">&times;</span>
            <div class="login-header">
                <h2>☕ Join Brew&Bean!</h2>
                <p>Create an account to start ordering</p>
            </div>
            <form class="login-form" onsubmit="handleSignup(event)">
                <div class="form-group">
                    <label for="signup-name">Full Name</label>
                    <input type="text" id="signup-name" placeholder="Enter your name" required>
                </div>
                <div class="form-group">
                    <label for="signup-email">Email Address</label>
                    <input type="email" id="signup-email" placeholder="your@email.com" required>
                </div>
                <div class="form-group">
                    <label for="signup-phone">Phone Number</label>
                    <input type="tel" id="signup-phone" placeholder="03XX-XXXXXXX" required>
                </div>
                <div class="form-group">
                    <label for="signup-password">Password</label>
                    <input type="password" id="signup-password" placeholder="Create a password" required>
                </div>
                <div class="form-group">
                    <label for="signup-confirm">Confirm Password</label>
                    <input type="password" id="signup-confirm" placeholder="Confirm your password" required>
                </div>
                <button type="submit" class="login-submit">Sign Up</button>
            </form>
            <div class="login-footer">
                <p>Already have an account? <a href="#" onclick="switchToLogin()">Login</a></p>
            </div>
        </div>
    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const button = document.querySelector('.theme-toggle');
            
            if (body.classList.contains('light-mode')) {
                body.classList.remove('light-mode');
                body.classList.add('dark-mode');
                button.textContent = '☀️ Light Mode';
            } else {
                body.classList.remove('dark-mode');
                body.classList.add('light-mode');
                button.textContent = '🌙 Dark Mode';
            }
        }

        function scrollToMenu() {
            document.getElementById('menu').scrollIntoView({ behavior: 'smooth' });
        }

        // Login Modal Functions
        function openLoginModal() {
            document.getElementById('loginModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        function closeLoginModal() {
            document.getElementById('loginModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        function handleLogin(event) {
            event.preventDefault();
            const email = document.getElementById('email').value;
            alert(🎉 Welcome back! Logged in as ${email});
            closeLoginModal();
            document.getElementById('email').value = '';
            document.getElementById('password').value = '';
        }

        // Signup Modal Functions
        function openSignupModal() {
            closeLoginModal();
            document.getElementById('signupModal').style.display = 'block';
            document.body.style.overflow = 'hidden';
        }

        function closeSignupModal() {
            document.getElementById('signupModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        function switchToLogin() {
            closeSignupModal();
            openLoginModal();
        }

        function handleSignup(event) {
            event.preventDefault();
            const name = document.getElementById('signup-name').value;
            const email = document.getElementById('signup-email').value;
            const password = document.getElementById('signup-password').value;
            const confirm = document.getElementById('signup-confirm').value;

            if (password !== confirm) {
                alert('⚠️ Passwords do not match!');
                return;
            }

            alert(🎉 Welcome ${name}! Your account has been created successfully!);
            closeSignupModal();
            
            // Clear form
            document.getElementById('signup-name').value = '';
            document.getElementById('signup-email').value = '';
            document.getElementById('signup-phone').value = '';
            document.getElementById('signup-password').value = '';
            document.getElementById('signup-confirm').value = '';
        }

        // Close modal when clicking outside
        window.onclick = function(event) {
            const loginModal = document.getElementById('loginModal');
            const signupModal = document.getElementById('signupModal');
            
            if (event.target == loginModal) {
                closeLoginModal();
            }
            if (event.target == signupModal) {
                closeSignupModal();
            }
        }

        // Order button functionality
        document.querySelectorAll('.order-button').forEach(button => {
            button.addEventListener('click', function() {
                const itemName = this.parentElement.querySelector('h3').textContent;
                alert(🎉 Great choice! ${itemName} has been added to your cart!);
            });
        });
    </script>
</body>
</html>
