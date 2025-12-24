# Ex.07 Restaurant Website
## Date:30//2025

## AIM:
To develop a static Restaurant website to display the food items and services provided by them.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS.

### Step 3:
Updating the sample content.

### Step 4:
Choose the appropriate style and color scheme.

### Step 5:
Validate the layout in various browsers.

### Step 6:
Validate the HTML code.

### Step 7:
Publish the website in the given URL.

## PROGRAM:
```<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Deliou - Fine Dining Experience</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica', Arial, sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #f5f5f5;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            background: rgba(26, 26, 46, 0.95);
            padding: 20px 50px;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid #d4af37;
            backdrop-filter: blur(10px);
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 50px;
            align-items: center;
        }

        nav ul li a {
            color: #d4af37;
            text-decoration: none;
            font-size: 18px;
            font-weight: 600;
            letter-spacing: 2px;
            transition: all 0.3s ease;
            text-transform: uppercase;
        }

        nav ul li a:hover {
            color: #ffd700;
            text-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        /* Pages */
        .page {
            display: none;
            padding-top: 100px;
            min-height: 100vh;
        }

        .page.active {
            display: block;
        }

        /* Home Page */
        .hero {
            text-align: center;
            padding: 100px 20px;
            background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
                url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><rect fill="%23533d1a" width="1200" height="600"/><circle fill="%236b4e23" cx="200" cy="100" r="80"/><circle fill="%236b4e23" cx="800" cy="400" r="100"/><circle fill="%23533d1a" cx="1000" cy="200" r="60"/></svg>');
            background-size: cover;
            background-position: center;
            border-bottom: 3px solid #d4af37;
        }

        .hero h1 {
            font-size: 72px;
            color: #ffd700;
            margin-bottom: 20px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.8);
            letter-spacing: 3px;
        }

        .hero p {
            font-size: 24px;
            color: #e8e8e8;
            margin-bottom: 40px;
            font-style: italic;
        }

        .cta-button {
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            color: #1a1a2e;
            padding: 18px 45px;
            font-size: 18px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(212, 175, 55, 0.5);
        }

        .features {
            display: flex;
            justify-content: center;
            gap: 40px;
            padding: 80px 50px;
            flex-wrap: wrap;
        }

        .feature-card {
            background: linear-gradient(135deg, #2a2a4e 0%, #1f1f3a 100%);
            padding: 40px;
            border-radius: 20px;
            width: 300px;
            text-align: center;
            border: 2px solid #d4af37;
            transition: all 0.4s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(212, 175, 55, 0.3);
            border-color: #ffd700;
        }

        .feature-card h3 {
            color: #ffd700;
            font-size: 26px;
            margin-bottom: 15px;
            letter-spacing: 1px;
        }

        .feature-card p {
            color: #c0c0c0;
            font-size: 16px;
            line-height: 1.6;
        }

        /* Menu Page */
        .menu-container {
            padding: 50px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .menu-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .menu-header h2 {
            font-size: 56px;
            color: #ffd700;
            margin-bottom: 15px;
            letter-spacing: 2px;
        }

        .menu-header p {
            font-size: 20px;
            color: #c0c0c0;
            font-style: italic;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .menu-item {
            background: linear-gradient(135deg, #2a2a4e 0%, #1f1f3a 100%);
            border-radius: 15px;
            overflow: hidden;
            border: 2px solid #d4af37;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .menu-item:hover {
            transform: scale(1.03);
            box-shadow: 0 12px 35px rgba(212, 175, 55, 0.4);
        }

        .menu-item-image {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #8b6914 0%, #d4af37 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            border-bottom: 2px solid #d4af37;
        }

        .menu-item-content {
            padding: 25px;
        }

        .menu-item-content h3 {
            color: #ffd700;
            font-size: 24px;
            margin-bottom: 10px;
            letter-spacing: 1px;
        }

        .menu-item-content p {
            color: #b0b0b0;
            font-size: 15px;
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .menu-item-content .price {
            color: #d4af37;
            font-size: 22px;
            font-weight: bold;
        }

        /* Contact Page */
        .contact-container {
            padding: 50px;
            max-width: 900px;
            margin: 0 auto;
        }

        .contact-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .contact-header h2 {
            font-size: 56px;
            color: #ffd700;
            margin-bottom: 15px;
            letter-spacing: 2px;
        }

        .contact-form {
            background: linear-gradient(135deg, #2a2a4e 0%, #1f1f3a 100%);
            padding: 50px;
            border-radius: 20px;
            border: 2px solid #d4af37;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .form-group {
            margin-bottom: 30px;
        }

        .form-group label {
            display: block;
            color: #ffd700;
            font-size: 16px;
            margin-bottom: 10px;
            font-weight: 600;
            letter-spacing: 1px;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border: 2px solid #d4af37;
            border-radius: 10px;
            color: #f5f5f5;
            font-size: 16px;
            font-family: 'Helvetica', Arial, sans-serif;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ffd700;
            background: rgba(255, 255, 255, 0.08);
            box-shadow: 0 0 15px rgba(212, 175, 55, 0.2);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }

        .submit-button {
            background: linear-gradient(135deg, #d4af37 0%, #ffd700 100%);
            color: #1a1a2e;
            padding: 18px 50px;
            font-size: 18px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            width: 100%;
            transition: all 0.3s ease;
            box-shadow: 0 8px 20px rgba(212, 175, 55, 0.3);
        }

        .submit-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(212, 175, 55, 0.5);
        }

        .contact-info {
            margin-top: 50px;
            text-align: center;
            color: #c0c0c0;
            font-size: 18px;
        }

        .contact-info p {
            margin: 15px 0;
        }

        .contact-info strong {
            color: #ffd700;
        }

        footer {
            text-align: center;
            padding: 30px;
            background: rgba(26, 26, 46, 0.95);
            color: #d4af37;
            margin-top: 50px;
            border-top: 2px solid #d4af37;
        }
    </style>
</head>

<body>
    <nav>
        <ul>
            <li><a href="#" onclick="showPage('home')">Home</a></li>
            <li><a href="#" onclick="showPage('menu')">Menu</a></li>
            <li><a href="#" onclick="showPage('contact')">Contact</a></li>
        </ul>
    </nav>

    <!-- HOME PAGE -->
    <div id="home" class="page active">
        <div class="hero">
            <h1>Deliou</h1>
            <p>Where Culinary Art Meets Royal Elegance</p>
            <button class="cta-button" onclick="showPage('menu')">Explore Menu</button>
        </div>

        <div class="features">
            <div class="feature-card">
                <h3>Exquisite Cuisine</h3>
                <p>Experience the finest culinary creations prepared by our world-class chefs using the freshest
                    ingredients and time-honored techniques.</p>
            </div>
            <div class="feature-card">
                <h3>Elegant Ambiance</h3>
                <p>Dine in a sophisticated atmosphere that combines classic luxury with modern comfort, perfect for any
                    special occasion.</p>
            </div>
            <div class="feature-card">
                <h3>Impeccable Service</h3>
                <p>Our dedicated staff ensures every moment of your dining experience is memorable, with attention to
                    every detail.</p>
            </div>
        </div>
    </div>

    <!-- MENU PAGE -->
    <div id="menu" class="page">
        <div class="menu-container">
            <div class="menu-header">
                <h2>Our Menu</h2>
                <p>A Symphony of Flavors</p>
            </div>

            <div class="menu-grid">
                <div class="menu-item">
                    <div class="menu-item-image"><img src="beefwellinton.jpg"></div>
                    <div class="menu-item-content">
                        <h3>Wagyu Beef Wellington</h3>
                        <p>Premium Wagyu beef wrapped in golden puff pastry with mushroom duxelles and foie gras</p>
                        <div class="price">$125</div>
                    </div>
                </div>

                <div class="menu-item">
                    <div class="menu-item-image"><img src="MaineLobsterThermidor.jpg"></div>
                    <div class="menu-item-content">
                        <h3>Maine Lobster Thermidor</h3>
                        <p>Fresh Atlantic lobster in a rich brandy cream sauce, gratinated to perfection</p>
                        <div class="price">$95</div>
                    </div>
                </div>

                <div class="menu-item">
                    <div class="menu-item-image"><img src="trufflerisssotoo.jpg"></div>
                    <div class="menu-item-content">
                        <h3>Truffle Risotto Royale</h3>
                        <p>Creamy Arborio rice infused with black truffle, aged parmesan, and butter</p>
                        <div class="price">$68</div>
                    </div>
                </div>

                <div class="menu-item">
                    <div class="menu-item-image"><img src="Pan-SearedSeaBass.jpg"></div>
                    <div class="menu-item-content">
                        <h3>Pan-Seared Sea Bass</h3>
                        <p>Mediterranean sea bass with saffron beurre blanc and seasonal vegetables</p>
                        <div class="price">$82</div>
                    </div>
                </div>

                <div class="menu-item">
                    <div class="menu-item-image"><img src="operacakess.jpg"></div>
                    <div class="menu-item-content">
                        <h3>Opera Cake Classique</h3>
                        <p>Layers of almond sponge, coffee buttercream, and chocolate ganache</p>
                        <div class="price">$28</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- CONTACT PAGE -->
    <div id="contact" class="page">
        <div class="contact-container">
            <div class="contact-header">
                <h2>Reserve Your Table</h2>
            </div>

            <form class="contact-form" onsubmit="handleSubmit(event)">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" name="name" required>
                </div>

                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" name="email" required>
                </div>

                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone" required>
                </div>

                <div class="form-group">
                    <label for="date">Reservation Date</label>
                    <input type="date" id="date" name="date" required>
                </div>

                <div class="form-group">
                    <label for="message">Special Requests</label>
                    <textarea id="message" name="message"
                        placeholder="Any dietary restrictions or special occasions?"></textarea>
                </div>

                <button type="submit" class="submit-button">Confirm Reservation</button>
            </form>

            <div class="contact-info">
                <p><strong>Address:</strong> 123 Royal Boulevard, Luxury District</p>
                <p><strong>Phone:</strong> +1 (555) 123-4567</p>
                <p><strong>Hours:</strong> Tuesday - Sunday, 6:00 PM - 11:00 PM</p>
                <p><strong>Email:</strong> reservations@deliou.com</p>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2025 Deliou. All Rights Reserved.</p>
    </footer>

    <script>
        function showPage(pageId) {
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => page.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            window.scrollTo(0, 0);
        }

        function handleSubmit(e) {
            e.preventDefault();
            alert('Thank you for your reservation! We will contact you shortly to confirm.');
            e.target.reset();
        }
    </script>
</body>

</html>
```

## OUTPUT:
HOMEPAGE

<img width="1920" height="969" alt="image" src="https://github.com/user-attachments/assets/3e2b2b85-4552-42db-ad47-30ed74ac9175" />


MENU

<img width="1915" height="953" alt="image" src="https://github.com/user-attachments/assets/ef1675f7-d197-4397-8f6e-da5cde4b7b51" />


<img width="1919" height="955" alt="image" src="https://github.com/user-attachments/assets/b79f8a23-3145-4f3c-8a8c-91e083bb7b92" />


CONTACT

<img width="1916" height="897" alt="image" src="https://github.com/user-attachments/assets/b246a551-6f7d-44dc-814d-74e20085f463" />


<img width="1920" height="972" alt="image" src="https://github.com/user-attachments/assets/155ce738-2e1c-4fd0-84ab-e4ade9e920f4" />



## RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
