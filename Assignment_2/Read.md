<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AuraWear - Fashion for Everyone</title>
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            overflow-x: hidden;
        }

        /* Sidebar Navigation */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            height: 100%;
            width: 80px;
            background-color: #222;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding-top: 20px;
            z-index: 100;
        }

        .sidebar a {
            margin: 15px 0;
            color: white;
            font-size: 20px;
            text-decoration: none;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 40px;
            height: 40px;
        }

        .sidebar-logo {
            margin-top: auto;
            margin-bottom: 20px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #48a7a0;
        }

        .sidebar-logo img {
            width: 80%;
            height: auto;
        }

        /* Main Content */
        .main-content {
            margin-left: 80px;
            width: calc(100% - 80px);
            min-height: 100vh;
            position: relative;
        }

        /* Hero Section */
        .hero {
            display: flex;
            height: 100vh;
            background-color: #f5f5f5;
        }

        .hero-left {
            flex: 1;
            background-color: #f9f9f9;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 50px;
        }

        .hero-right {
            flex: 1;
            background-image: url('attached_assets/1.jpg');
            background-size: cover;
            background-position: center;
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 30px;
            line-height: 1.2;
            color: #222;
        }

        .brand-name {
            font-size: 2.5rem;
            font-style: italic;
            font-weight: bold;
            margin-bottom: 20px;
            color: #222;
        }

        .cta-buttons {
            margin-top: 20px;
        }

        .cta-btn {
            display: inline-block;
            padding: 12px 25px;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            text-decoration: none;
            margin-right: 10px;
            margin-bottom: 10px;
            transition: background-color 0.3s;
        }

        .cta-btn:hover {
            background-color: black;
        }

        /* Category Sections */
        .category-section {
            padding: 80px 50px;
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 40px;
            text-align: center;
            font-weight: bold;
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }

        .category-card {
            position: relative;
            height: 400px;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .category-card:hover {
            transform: translateY(-10px);
        }

        .category-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .category-info {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 20px;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
            color: white;
        }

        .category-name {
            font-size: 1.5rem;
            margin-bottom: 5px;
        }

        .category-description {
            font-size: 0.9rem;
            margin-bottom: 10px;
        }

        .category-link {
            display: inline-block;
            padding: 8px 15px;
            background-color: #48a7a0;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            font-size: 0.9rem;
            transition: background-color 0.3s;
        }

        .category-link:hover {
            background-color: #3a857f;
        }

        /* Product List Styles */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .product-card {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            background-color: white;
            margin-bottom: 20px;
        }

        .product-card:hover {
            transform: translateY(-10px);
        }

        .product-image {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.1);
        }

        .product-info {
            padding: 15px;
            background-color: white;
        }

        .product-name {
            font-size: 1.1rem;
            margin-bottom: 5px;
            font-weight: bold;
        }

        .product-price {
            color: #48a7a0;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .product-actions {
            display: flex;
            justify-content: space-between;
        }

        .product-btn {
            padding: 8px 12px;
            background-color: #48a7a0;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .product-btn:hover {
            background-color: #3a857f;
        }

        .wishlist-btn {
            background-color: transparent;
            color: #666;
            padding: 8px 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .wishlist-btn:hover {
            background-color: #f8f8f8;
            color: #48a7a0;
            border-color: #48a7a0;
        }
        
        /* Category Pages Specific Styles (Men/Women/Kids) */
        .category-page {
            display: none;
            padding: 0;
            background-color: #f9f9f9;
        }
        
        .category-header {
            margin-bottom: 30px;
        }
        
        .category-header h2 {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        .category-types {
            display: flex;
            justify-content: flex-start;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 40px;
        }
        
        .category-type {
            text-align: center;
            width: 100px;
        }
        
        .category-type img {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 10px;
        }
        
        .category-type p {
            font-size: 0.9rem;
            text-transform: uppercase;
            font-weight: bold;
        }
        
        /* Left Sidebar - AuraWear specific */
        .left-sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 250px;
            height: 100%;
            background-color: #48a7a0;
            color: white;
            padding: 50px 30px;
            z-index: 100;
        }
        
        .left-sidebar-content {
            display: flex;
            flex-direction: column;
            height: 100%;
        }
        
        .left-intro {
            margin-bottom: 30px;
        }
        
        .left-intro h2 {
            font-style: italic;
            margin-bottom: 15px;
        }
        
        .left-intro p {
            line-height: 1.6;
            font-size: 0.95rem;
        }
        
        .left-sidebar-logo {
            margin-top: auto;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            align-self: center;
            overflow: hidden;
        }
        
        .left-sidebar-logo img {
            width: 70%;
            height: auto;
        }
        
        /* Auth Pages Styles */
        .auth-container {
            display: flex;
            min-height: 100vh;
        }
        
        .auth-content {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 50px;
            background-color: rgba(72, 167, 160, 0.1);
            margin-left: 250px;
            background-image: url('attached_assets/2.jpg');
            background-size: cover;
            background-position: center;
        }
        
        .auth-form {
            width: 100%;
            max-width: 450px;
            background-color: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .auth-form h2 {
            font-size: 1.8rem;
            margin-bottom: 30px;
            text-align: center;
        }
        
        .auth-social {
            display: flex;
            gap: 15px;
            margin-bottom: 25px;
        }
        
        .auth-social-btn {
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 0.9rem;
            cursor: pointer;
            transition: all 0.3s;
            background-color: white;
        }
        
        .auth-social-btn:hover {
            border-color: #48a7a0;
        }
        
        .auth-social-btn img {
            width: 20px;
            height: 20px;
            margin-right: 10px;
        }
        
        .auth-divider {
            text-align: center;
            position: relative;
            margin: 20px 0;
        }
        
        .auth-divider::before, .auth-divider::after {
            content: '';
            position: absolute;
            top: 50%;
            width: 40%;
            height: 1px;
            background-color: #ddd;
        }
        
        .auth-divider::before {
            left: 0;
        }
        
        .auth-divider::after {
            right: 0;
        }
        
        .auth-divider span {
            background-color: white;
            padding: 0 10px;
            position: relative;
            z-index: 1;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-size: 0.9rem;
            color: #555;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            transition: border-color 0.3s;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: #48a7a0;
        }
        
        .auth-btn {
            width: 100%;
            padding: 12px;
            background-color: #48a7a0;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .auth-btn:hover {
            background-color: #3a857f;
        }
        
        .auth-footer {
            text-align: center;
            margin-top: 20px;
            font-size: 0.9rem;
        }
        
        .auth-footer a {
            color: #48a7a0;
            text-decoration: none;
        }
        
        .auth-footer a:hover {
            text-decoration: underline;
        }
        
        /* Product List Page Styles */
        .product-list-container {
            margin-left: 250px;
            padding: 50px;
            background-color: #f9f9f9;
        }
        
        .product-list-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }
        
        .product-list-title {
            font-size: 2.5rem;
            font-weight: bold;
        }
        
        .back-btn {
            display: flex;
            align-items: center;
            font-size: 1rem;
            color: #333;
            text-decoration: none;
        }
        
        .back-btn:hover {
            color: #48a7a0;
        }
        
        .back-btn i {
            margin-right: 10px;
        }
        
        .product-list-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }
        
        .product-list-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            position: relative;
        }
        
        .product-list-image {
            height: 350px;
            overflow: hidden;
        }
        
        .product-list-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product-list-card:hover .product-list-image img {
            transform: scale(1.1);
        }
        
        .product-list-info {
            padding: 20px;
            border-top: 1px solid #f1f1f1;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .product-list-price {
            font-size: 1.2rem;
            font-weight: bold;
            color: #333;
        }
        
        .product-list-btn {
            padding: 8px 20px;
            background-color: #333;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .product-list-btn:hover {
            background-color: #48a7a0;
        }

        /* Back Button for Category/Product Pages */
        .back-btn {
            display: inline-block;
            margin-bottom: 30px;
            padding: 10px 15px;
            background-color: #f0f0f0;
            color: #333;
            text-decoration: none;
            border-radius: 4px;
            transition: background-color 0.3s;
        }

        .back-btn:hover {
            background-color: #ddd;
        }

        /* Responsive Styles */
        @media (max-width: 1200px) {
            .category-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .product-grid, 
            .product-list-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .left-sidebar {
                width: 220px;
            }
            
            .auth-content, 
            .product-list-container {
                margin-left: 220px;
            }
        }

        @media (max-width: 992px) {
            .hero {
                flex-direction: column;
                height: auto;
            }
            
            .hero-left, .hero-right {
                height: 50vh;
            }
            
            .category-types {
                gap: 10px;
            }
            
            .category-type {
                width: 80px;
            }
            
            .category-type img {
                width: 60px;
                height: 60px;
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 60px;
            }
            
            .main-content {
                margin-left: 60px;
                width: calc(100% - 60px);
            }
            
            .category-grid {
                grid-template-columns: 1fr;
            }
            
            .product-grid,
            .product-list-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .left-sidebar {
                width: 100%;
                height: auto;
                position: relative;
                padding: 30px;
            }
            
            .auth-content, 
            .product-list-container {
                margin-left: 0;
            }
            
            .auth-container {
                flex-direction: column;
            }
            
            .product-list-title {
                font-size: 2rem;
            }
            
            .category-section {
                padding: 50px 20px;
            }
        }

        @media (max-width: 576px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .brand-name {
                font-size: 2rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .auth-form {
                padding: 30px 20px;
            }
            
            .product-list-grid {
                gap: 15px;
            }
            
            .product-list-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
            }
        }

        /* Special category pages like men, women, kids */
        #men-page, #women-page, #kids-page {
            background-color: #e8f2f9;
        }

        #men-page .left-sidebar {
            background-color: #c2e6d3;
        }

        #women-page .left-sidebar {
            background-color: #48a7a0;
        }

        #kids-page .left-sidebar {
            background-color: #c2e6d3;
        }

        /* Special category layouts */
        #sarees-page, #winter-page {
            background-color: #f0f0f0;
        }

        #sarees-page .product-list-container, #winter-page .product-list-container {
            background-color: #f9f9f9;
        }
    </style>
</head>
<body>
    <!-- Sidebar Navigation -->
    <div class="sidebar">
        <a href="#" title="Profile">👤</a>
        <a href="#" title="Search">🔍</a>
        <a href="#" title="Social Media">📱</a>
        <div class="sidebar-logo">
            <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
        </div>
    </div>

    <!-- Main Content -->
    <div class="main-content">
        <!-- Home Page Hero Section -->
        <section class="hero">
            <div class="hero-left">
                <div class="brand-name">AuraWear</div>
                <h1 class="hero-title">THE OUTFITS<br>THAT YOU ARE<br>LOOKING FOR</h1>
                <div class="cta-buttons">
                    <a href="#signup-page" class="cta-btn">Sign up</a>
                    <a href="#login-page" class="cta-btn">Log in</a>
                </div>
            </div>
            <div class="hero-right">
                <!-- The background image is set in CSS -->
            </div>
        </section>

        <!-- Categories Section -->
        <section class="category-section">
            <h2 class="section-title">Categories</h2>
            <div class="category-grid">
                <!-- Men's Category -->
                <div class="category-card">
                    <img src="attached_assets/4.jpg" alt="Men's Fashion">
                    <div class="category-info">
                        <h3 class="category-name">Men</h3>
                        <p class="category-description">Discover our latest collection for men including casual wear, formal attire, and accessories.</p>
                        <a href="#men-page" class="category-link">Shop Now</a>
                    </div>
                </div>
                
                <!-- Women's Category -->
                <div class="category-card">
                    <img src="attached_assets/4.jpg" alt="Women's Fashion">
                    <div class="category-info">
                        <h3 class="category-name">Women</h3>
                        <p class="category-description">Explore our diverse range of women's clothing from everyday essentials to statement pieces.</p>
                        <a href="#women-page" class="category-link">Shop Now</a>
                    </div>
                </div>
                
                <!-- Kids' Category -->
                <div class="category-card">
                    <img src="attached_assets/4.jpg" alt="Kids' Fashion">
                    <div class="category-info">
                        <h3 class="category-name">Kids</h3>
                        <p class="category-description">Cute and comfortable clothing for children of all ages from infants to teenagers.</p>
                        <a href="#kids-page" class="category-link">Shop Now</a>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Men's Category Page -->
    <div id="men-page" class="category-page">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>AuraWear</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion.</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="product-list-container">
            <div class="product-list-header">
                <h1 class="product-list-title">Men's Collection</h1>
                <a href="#" class="back-btn">← Back to Home</a>
            </div>
            
            <div class="category-types">
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="Winter">
                    <p>WINTER</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="T-Shirt">
                    <p>T-SHIRT</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="Shirts">
                    <p>SHIRTS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="Jeans">
                    <p>JEANS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="Trousers">
                    <p>TROUSERS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/5.png" alt="Ethnic">
                    <p>ETHNIC SETS</p>
                </div>
            </div>
            
            <div class="product-grid">
                <!-- Product cards from the images -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/5.png" alt="Hoodie">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Basic Hoodie</h3>
                        <p class="product-price">$49.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/5.png" alt="Winter Scarf">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Warm Winter Scarf</h3>
                        <p class="product-price">$24.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/5.png" alt="Formal Shirt">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Classic Formal Shirt</h3>
                        <p class="product-price">$39.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Women's Category Page -->
    <div id="women-page" class="category-page">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>AuraWear</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion.</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="product-list-container">
            <div class="product-list-header">
                <h1 class="product-list-title">Women's Collection</h1>
                <a href="#" class="back-btn">← Back to Home</a>
            </div>
            
            <div class="category-types">
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Winter">
                    <p>WINTER</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Kurtas">
                    <p>KURTAS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Tops">
                    <p>TOPS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Dresses">
                    <p>DRESSES</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Sarees">
                    <p>SAREES</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Suit">
                    <p>SUITS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/6.jpg" alt="Bottom">
                    <p>BOTTOMS</p>
                </div>
            </div>
            
            <div class="product-grid">
                <!-- Product cards from the images -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/6.jpg" alt="Trousers">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Bootcut Trousers</h3>
                        <p class="product-price">$49.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/6.jpg" alt="Striped Pants">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Striped Pants</h3>
                        <p class="product-price">$39.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/6.jpg" alt="Cargo Jeans">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Cargo Jeans</h3>
                        <p class="product-price">$59.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Kids' Category Page -->
    <div id="kids-page" class="category-page">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>AuraWear</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion.</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="product-list-container">
            <div class="product-list-header">
                <h1 class="product-list-title">Kids' Collection</h1>
                <a href="#" class="back-btn">← Back to Home</a>
            </div>
            
            <div class="category-types">
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Winter">
                    <p>WINTER</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="T-Shirt">
                    <p>T-SHIRT</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Shirts">
                    <p>SHIRTS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Frocks">
                    <p>FROCKS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Twin Sets">
                    <p>TWIN SETS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Twin Sets">
                    <p>TWIN SETS</p>
                </div>
                <div class="category-type">
                    <img src="attached_assets/7.jpg" alt="Tops">
                    <p>TOPS</p>
                </div>
            </div>
            
            <div class="product-grid">
                <!-- Product cards from the images -->
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/7.jpg" alt="Hoodie">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Kids Hoodie</h3>
                        <p class="product-price">$29.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/7.jpg" alt="Party Dress">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Plum Berry Fit Dress</h3>
                        <p class="product-price">$39.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
                
                <div class="product-card">
                    <div class="product-image">
                        <img src="attached_assets/7.jpg" alt="Dress">
                    </div>
                    <div class="product-info">
                        <h3 class="product-name">Playful Minimalism Dress</h3>
                        <p class="product-price">$34.99</p>
                        <div class="product-actions">
                            <button class="product-btn">Add to Cart</button>
                            <button class="wishlist-btn">♡</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Sarees Product List Page -->
    <div id="sarees-page" class="category-page">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>AuraWear</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion.</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="product-list-container">
            <div class="product-list-header">
                <h1 class="product-list-title">SAREES</h1>
                <a href="#women-page" class="back-btn">← Back to Women's Collection</a>
            </div>
            
            <div class="product-list-grid">
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Pink Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹699</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Light Pink Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹999</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Pink Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹849</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Lavender Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹799</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Red Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹1299</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/8.jpg" alt="Maroon Saree">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹1199</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Winter Wear Product List Page -->
    <div id="winter-page" class="category-page">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>AuraWear</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion.</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="product-list-container">
            <div class="product-list-header">
                <h1 class="product-list-title">WINTER WEAR</h1>
                <a href="#men-page" class="back-btn">← Back to Men's Collection</a>
            </div>
            
            <div class="product-list-grid">
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Scarf">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹399</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Scarf">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹999</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Scarf">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹599</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Black Scarf">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹499</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Winter Jacket">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹1499</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
                
                <div class="product-list-card">
                    <div class="product-list-image">
                        <img src="attached_assets/9.png" alt="Muffler">
                    </div>
                    <div class="product-list-info">
                        <div class="product-list-price">₹899</div>
                        <button class="product-list-btn">Buy</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Login Page -->
    <div id="login-page" class="auth-container" style="display: none;">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>Welcome Back!</h2>
                    <p>Discover Your Style at AuraWear. Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion. Join us today and redefine your wardrobe with our exclusive collections!</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="auth-content">
            <div class="auth-form">
                <h2>Log In</h2>
                <div class="auth-social">
                    <div class="auth-social-btn">
                        <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBmaWxsPSIjRUE0MzM1IiBkPSJNNS42NCA3LjY0Yy43OS0uNzggMS44NC0xLjE4IDIuOS0xLjE4IDEuMTEgMCAyLjIuNDQgMyAxLjNjLjc0Ljg1LjU3IDIuMTguLTU0IDIuNmExLjQzIDEuNDMgMCAwIDEgMC0yLjhjLS44IDAtMS41Ni4zLTIuMTMuODYtMS41MyAxLjUzLTEuNDQgNC4zLjIzIDUuOTcuODkuODkgMi4wOSAxLjMzIDMuMjcgMS4zM3YxLjQ5YTYuMDEgNi4wMSAwIDAgMS00LjI3LTEuNjdBNi4wMSA2LjAxIDAgMCAxIDUuNjQgNy42NHoiLz48cGF0aCBmaWxsPSIjRkJCQzA1IiBkPSJNMTIgNS4zOHYzLjZoLTEuNnYtMy42SDE2Yy4yMiAwIC40LjE4LjQuNHYxNmEuNCAwIDAgMC0uNC40SDhjLS4yMiAwLS40LS4xOC0uNC0uNHYtNC4yaDEuNnYzLjZIMTRWNi4xOGgtMnoiLz48cGF0aCBmaWxsPSIjMzRBODUzIiBkPSJNMTUuNiAxNy42djEuNmgtNC44di0xLjZoNC44eiIvPjxwYXRoIGZpbGw9IiM0Mjg1RjQiIGQ9Ik0xMi44IDcuNnYxLjZoLTEuNlY3LjZoMS42eiIvPjwvc3ZnPg==" alt="Google">
                        Sign In With Google
                    </div>
                </div>
                <div class="auth-social">
                    <div class="auth-social-btn">
                        <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBmaWxsPSIjMzk3OUY2IiBkPSJNMjIuNjc1IDBoLTIxLjM1Qy41ODUgMCAwIC41ODUgMCAxLjMyNXYyMS4zNTFDMCAyMy40MTUuNTg1IDI0IDEuMzI1IDI0SDEyLjgydi05LjI5NEg5LjY5MnYtMy42MjJoMy4xMjhWOC40MTNjMC0zLjEgMS44OTMtNC43ODggNC42NTktNC43ODggMS4zMjUgMCAyLjQ2My4wOTkgMi43OTUuMTQzdjMuMjRsLTEuOTE4LjAwMWMtMS41MDQgMC0xLjc5NS43MTUtMS43OTUgMS43NjN2Mi4zMTNoMy41ODdsLS40NjcgMy42MjJoLTMuMTJWMjRoNi4xMTZjLjczIDAgMS4zMjMtLjU4NSAxLjMyMy0xLjMyNVYxLjMyNUMyNCAuNTg1IDIzLjQxNSAwIDIyLjY3NSAweiIvPjwvc3ZnPg==" alt="Facebook">
                        Sign In With Facebook
                    </div>
                </div>
                <div class="auth-divider">
                    <span>OR</span>
                </div>
                <form onsubmit="event.preventDefault(); window.location.href='#';">
                    <div class="form-group">
                        <input type="email" placeholder="Email Address" required>
                    </div>
                    <div class="form-group">
                        <input type="password" placeholder="Password" required>
                    </div>
                    <button type="submit" class="auth-btn">Login Account</button>
                </form>
                <div class="auth-footer">
                    Already have an account? <a href="#login-page">Log In</a>
                </div>
            </div>
        </div>
    </div>

    <!-- Signup Page -->
    <div id="signup-page" class="auth-container" style="display: none;">
        <div class="left-sidebar">
            <div class="left-sidebar-content">
                <div class="left-intro">
                    <h2>Discover Your Style at AuraWear</h2>
                    <p>Shop unique, high-quality clothing that blends fashion with comfort. From trendy pieces to timeless essentials, we've got something for every occasion. Join us today and redefine your wardrobe with our exclusive collections!</p>
                </div>
                <div class="left-sidebar-logo">
                    <img src="data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGcgZmlsbD0ibm9uZSIgZmlsbC1ydWxlPSJldmVub2RkIj48cGF0aCBkPSJNMzAgMGMxNi41NjkgMCAzMCAxMy40MzEgMzAgMzBTNDYuNTY5IDYwIDMwIDYwIDAgNDYuNTY5IDAgMzAgMTMuNDMxIDAgMzAgMHoiIGZpbGw9IiM0OEE3QTAiLz48cGF0aCBkPSJNNDAgMjBIMjBjLTEuMTA1IDAtMiAuODk1LTIgMnYyMGMwIDEuMTA1Ljg5NSAyIDIgMmgyMGMxLjEwNSAwIDItLjg5NSAyLTJWMjJjMC0xLjEwNS0uODk1LTItMi0yem0tNiA3YTEgMSAwIDAwMCAyaDR2NmEzIDMgMCAwMS0zIDNIMjVhMyAzIDAgMDEtMy0zVjI1YTMgMyAwIDAxMy0zaDZ2MmgtNGExIDEgMCAwMC0xIDF2MTBhMSAxIDAgMDAxIDFoMTBhMSAxIDAgMDAxLTF2LTRhMSAxIDAgMDAtMS0xaC0ydi0zeiIgZmlsbD0iI0ZGRiIvPjwvZz48L3N2Zz4=" alt="AuraWear Logo">
                </div>
            </div>
        </div>
        
        <div class="auth-content">
            <div class="auth-form">
                <h2>Create Account</h2>
                <div class="auth-social">
                    <div class="auth-social-btn">
                        <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBmaWxsPSIjRUE0MzM1IiBkPSJNNS42NCA3LjY0Yy43OS0uNzggMS44NC0xLjE4IDIuOS0xLjE4IDEuMTEgMCAyLjIuNDQgMyAxLjNjLjc0Ljg1LjU3IDIuMTguLTU0IDIuNmExLjQzIDEuNDMgMCAwIDEgMC0yLjhjLS44IDAtMS41Ni4zLTIuMTMuODYtMS41MyAxLjUzLTEuNDQgNC4zLjIzIDUuOTcuODkuODkgMi4wOSAxLjMzIDMuMjcgMS4zM3YxLjQ5YTYuMDEgNi4wMSAwIDAgMS00LjI3LTEuNjdBNi4wMSA2LjAxIDAgMCAxIDUuNjQgNy42NHoiLz48cGF0aCBmaWxsPSIjRkJCQzA1IiBkPSJNMTIgNS4zOHYzLjZoLTEuNnYtMy42SDE2Yy4yMiAwIC40LjE4LjQuNHYxNmEuNCAwIDAgMC0uNC40SDhjLS4yMiAwLS40LS4xOC0uNC0uNHYtNC4yaDEuNnYzLjZIMTRWNi4xOGgtMnoiLz48cGF0aCBmaWxsPSIjMzRBODUzIiBkPSJNMTUuNiAxNy42djEuNmgtNC44di0xLjZoNC44eiIvPjxwYXRoIGZpbGw9IiM0Mjg1RjQiIGQ9Ik0xMi44IDcuNnYxLjZoLTEuNlY3LjZoMS42eiIvPjwvc3ZnPg==" alt="Google">
                        Sign Up With Google
                    </div>
                </div>
                <div class="auth-social">
                    <div class="auth-social-btn">
                        <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48cGF0aCBmaWxsPSIjMzk3OUY2IiBkPSJNMjIuNjc1IDBoLTIxLjM1Qy41ODUgMCAwIC41ODUgMCAxLjMyNXYyMS4zNTFDMCAyMy40MTUuNTg1IDI0IDEuMzI1IDI0SDEyLjgydi05LjI5NEg5LjY5MnYtMy42MjJoMy4xMjhWOC40MTNjMC0zLjEgMS44OTMtNC43ODggNC42NTktNC43ODggMS4zMjUgMCAyLjQ2My4wOTkgMi43OTUuMTQzdjMuMjRsLTEuOTE4LjAwMWMtMS41MDQgMC0xLjc5NS43MTUtMS43OTUgMS43NjN2Mi4zMTNoMy41ODdsLS40NjcgMy42MjJoLTMuMTJWMjRoNi4xMTZjLjczIDAgMS4zMjMtLjU4NSAxLjMyMy0xLjMyNVYxLjMyNUMyNCAuNTg1IDIzLjQxNSAwIDIyLjY3NSAweiIvPjwvc3ZnPg==" alt="Facebook">
                        Sign Up With Facebook
                    </div>
                </div>
                <div class="auth-divider">
                    <span>OR</span>
                </div>
                <form onsubmit="event.preventDefault(); window.location.href='#';">
                    <div class="form-group">
                        <input type="text" placeholder="Full Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" placeholder="Email Address" required>
                    </div>
                    <div class="form-group">
                        <input type="password" placeholder="Password" required>
                    </div>
                    <button type="submit" class="auth-btn">Create Account</button>
                </form>
                <div class="auth-footer">
                    Already have an account? <a href="#login-page">Log In</a>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Show/hide pages based on hash
        function navigate() {
            const pages = ['men-page', 'women-page', 'kids-page', 'sarees-page', 'winter-page', 'login-page', 'signup-page'];
            
            // Hide all pages first
            pages.forEach(page => {
                document.getElementById(page).style.display = 'none';
            });
            
            // Show main content by default
            document.querySelector('.main-content').style.display = 'block';
            
            // Get the current hash
            const hash = window.location.hash.substring(1);
            
            if (hash && pages.includes(hash)) {
                // Hide main content
                document.querySelector('.main-content').style.display = 'none';
                
                // Show the requested page
                document.getElementById(hash).style.display = 'flex';
            }
        }
        
        // Run navigation on load and hash change
        window.addEventListener('load', navigate);
        window.addEventListener('hashchange', navigate);
        
        // Log when the page loads
        console.log("AuraWear website loaded");
    </script>
</body>
</html>
