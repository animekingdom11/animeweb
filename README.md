<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NexVerse | Your Anime Universe</title>
    <style>
        :root {
            --primary: #6a00f4;
            --secondary: #ff00a0;
            --dark: #0a0a1a;
            --light: #f0f0ff;
            --accent: #00f0ff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            overflow-x: hidden;
        }
        
        /* Glow Effects */
        .glow {
            text-shadow: 0 0 10px var(--accent), 0 0 20px var(--primary);
        }
        
        .gradient-text {
            background: linear-gradient(45deg, var(--primary), var(--secondary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        /* Header Styles */
        header {
            background: rgba(10, 10, 26, 0.8);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            z-index: 100;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .logo {
            font-size: 2rem;
            font-weight: 800;
            text-decoration: none;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        nav a {
            color: var(--light);
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            position: relative;
        }
        
        nav a:hover {
            color: var(--accent);
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: 0.3s;
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        .cta-button {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            transition: 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(106, 0, 244, 0.3);
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 5%;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(106, 0, 244, 0.2), transparent 50%);
            z-index: -1;
        }
        
        .hero-content {
            max-width: 600px;
        }
        
        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        .hero-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .secondary-button {
            background: transparent;
            color: var(--light);
            padding: 0.8rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            transition: 0.3s;
            border: 2px solid var(--accent);
        }
        
        .secondary-button:hover {
            background: rgba(0, 240, 255, 0.1);
        }
        
        .hero-image {
            position: absolute;
            right: 5%;
            bottom: 0;
            height: 90%;
            z-index: -1;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        /* Sections */
        section {
            padding: 5rem 5%;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .section-header p {
            max-width: 700px;
            margin: 0 auto;
            opacity: 0.8;
        }
        
        /* Comics Grid */
        .comics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        .comic-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            overflow: hidden;
            transition: 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .comic-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(106, 0, 244, 0.2);
            border-color: var(--accent);
        }
        
        .comic-cover {
            width: 100%;
            height: 350px;
            object-fit: cover;
        }
        
        .comic-info {
            padding: 1.5rem;
        }
        
        .comic-info h3 {
            margin-bottom: 0.5rem;
        }
        
        .comic-info .price {
            color: var(--accent);
            font-weight: 700;
            margin: 1rem 0;
            display: block;
        }
        
        /* Anime Teaser */
        .anime-teaser {
            background: linear-gradient(135deg, rgba(106, 0, 244, 0.1), rgba(0, 240, 255, 0.1));
            border-radius: 20px;
            padding: 3rem;
            display: flex;
            align-items: center;
            gap: 3rem;
            margin-top: 3rem;
        }
        
        .anime-teaser video {
            width: 50%;
            border-radius: 10px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
        
        .anime-teaser-content {
            flex: 1;
        }
        
        .anime-teaser-content h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }
        
        /* Merchandise */
        .merch-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 2rem;
        }
        
        .merch-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            padding: 1.5rem;
            text-align: center;
            transition: 0.3s;
        }
        
        .merch-item:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 20px rgba(106, 0, 244, 0.2);
        }
        
        .merch-item img {
            width: 100%;
            height: 200px;
            object-fit: contain;
            margin-bottom: 1rem;
        }
        
        /* Newsletter */
        .newsletter {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 4rem;
            border-radius: 20px;
            text-align: center;
        }
        
        .newsletter h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 2rem;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-form input {
            flex: 1;
            padding: 1rem;
            border: none;
            border-radius: 50px 0 0 50px;
            font-size: 1rem;
        }
        
        .newsletter-form button {
            padding: 0 2rem;
            border-radius: 0 50px 50px 0;
            border: none;
            background: var(--dark);
            color: white;
            font-weight: 700;
            cursor: pointer;
        }
        
        /* Footer */
        footer {
            background: rgba(0, 0, 0, 0.3);
            padding: 3rem 5%;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h4 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column a {
            color: var(--light);
            text-decoration: none;
            opacity: 0.7;
            transition: 0.3s;
        }
        
        .footer-column a:hover {
            opacity: 1;
            color: var(--accent);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            transition: 0.3s;
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            opacity: 0.7;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .hero {
                text-align: center;
                padding-top: 100px;
            }
            
            .hero-content {
                margin: 0 auto;
            }
            
            .hero-buttons {
                justify-content: center;
            }
            
            .hero-image {
                display: none;
            }
            
            .anime-teaser {
                flex-direction: column;
            }
            
            .anime-teaser video {
                width: 100%;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 50px;
                margin-bottom: 1rem;
            }
            
            .newsletter-form button {
                border-radius: 50px;
                padding: 1rem;
            }
        }
    </style>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <header>
        <a href="#" class="logo gradient-text">NexVerse</a>
        <nav>
            <ul>
                <li><a href="#comics">Comics</a></li>
                <li><a href="#anime">Anime</a></li>
                <li><a href="#merch">Merch</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
        <a href="#" class="cta-button">Join the Fandom</a>
    </header>
    
    <section class="hero">
        <div class="hero-content">
            <h1 class="glow">Enter the <span class="gradient-text">NexVerse</span></h1>
            <p>Where comics come to life and anime dreams become reality. Explore our universe of original stories, characters, and merchandise that will ignite your imagination.</p>
            <div class="hero-buttons">
                <a href="#comics" class="cta-button">Read Comics</a>
                <a href="#anime" class="secondary-button">Watch Teaser</a>
            </div>
        </div>
        <img src="https://i.imgur.com/8mQxL2p.jpg" alt="Hero Character" class="hero-image">
    </section>
    
    <section id="comics">
        <div class="section-header">
            <h2>Latest <span class="gradient-text">Comics</span></h2>
            <p>Dive into our original comic series available now on Gumroad. Each issue expands the NexVerse universe.</p>
        </div>
        <div class="comics-grid">
            <div class="comic-card">
                <img src="https://i.imgur.com/5xQ3b9j.jpg" alt="Cyber Samurai Cover" class="comic-cover">
                <div class="comic-info">
                    <h3>Cyber Samurai #1</h3>
                    <p>A lone warrior battles in neon-lit future Tokyo.</p>
                    <span class="price">$4.99</span>
                    <a href="#" class="cta-button" style="display: block; text-align: center;">Buy Now</a>
                </div>
            </div>
            <div class="comic-card">
                <img src="https://i.imgur.com/JKvkW3D.png" alt="Stellar Wanderers Cover" class="comic-cover">
                <div class="comic-info">
                    <h3>Stellar Wanderers #1</h3>
                    <p>Space explorers discover a galaxy of wonders.</p>
                    <span class="price">$4.99</span>
                    <a href="#" class="cta-button" style="display: block; text-align: center;">Buy Now</a>
                </div>
            </div>
            <div class="comic-card">
                <img src="https://i.imgur.com/3tQYV9F.jpg" alt="Shadow Protocol Cover" class="comic-cover">
                <div class="comic-info">
                    <h3>Shadow Protocol #1</h3>
                    <p>Covert ops team battles interdimensional threats.</p>
                    <span class="price">$4.99</span>
                    <a href="#" class="cta-button" style="display: block; text-align: center;">Buy Now</a>
                </div>
            </div>
            <div class="comic-card">
                <img src="https://i.imgur.com/7pNqB2W.jpg" alt="NexVerse Chronicles Cover" class="comic-cover">
                <div class="comic-info">
                    <h3>NexVerse Chronicles</h3>
                    <p>Short stories from across the multiverse.</p>
                    <span class="price">$3.99</span>
                    <a href="#" class="cta-button" style="display: block; text-align: center;">Buy Now</a>
                </div>
            </div>
        </div>
    </section>
    
    <section id="anime">
        <div class="section-header">
            <h2>Coming Soon: <span class="gradient-text">Anime Adaptation</span></h2>
            <p>Our comics are leaping from the page to the screen. Be the first to see the animated adventures of your favorite characters.</p>
        </div>
        <div class="anime-teaser">
            <video controls poster="https://i.imgur.com/mX5D4pP.png">
                <source src="teaser.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
            <div class="anime-teaser-content">
                <h3>NexVerse: The Animation</h3>
                <p>Witness the stunning anime adaptation of our hit comic series, coming soon exclusively to our platform. The animation brings the vibrant world of NexVerse to life with breathtaking action, emotional depth, and visual splendor.</p>
                <p>Sign up for updates to get early access and exclusive behind-the-scenes content.</p>
                <a href="#" class="cta-button">Notify Me</a>
            </div>
        </div>
    </section>
    
    <section id="merch">
        <div class="section-header">
            <h2>Official <span class="gradient-text">Merchandise</span></h2>
            <p>Wear your fandom with pride. High-quality merchandise featuring your favorite NexVerse characters.</p>
        </div>
        <div class="merch-grid">
            <div class="merch-item">
                <img src="https://i.imgur.com/Q9W3XpY.png" alt="Cyber Samurai T-Shirt">
                <h3>Cyber Samurai Tee</h3>
                <p>$24.99</p>
                <a href="#" class="cta-button">Add to Cart</a>
            </div>
            <div class="merch-item">
                <img src="https://i.imgur.com/v7QY9Jx.png" alt="Anime Poster">
                <h3>Limited Edition Poster</h3>
                <p>$14.99</p>
                <a href="#" class="cta-button">Add to Cart</a>
            </div>
            <div class="merch-item">
                <img src="https://i.imgur.com/8KQ3Y9x.png" alt="Action Figure">
                <h3>Hero Action Figure</h3>
                <p>$39.99</p>
                <a href="#" class="cta-button">Add to Cart</a>
            </div>
            <div class="merch-item">
                <img src="https://i.imgur.com/mX5D4pP.png" alt="Art Book">
                <h3>Art Book Collection</h3>
                <p>$29.99</p>
                <a href="#" class="cta-button">Add to Cart</a>
            </div>
            <div class="merch-item">
                <img src="https://i.imgur.com/5xQ3b9j.jpg" alt="Sticker Pack">
                <h3>Character Stickers</h3>
                <p>$7.99</p>
                <a href="#" class="cta-button">Add to Cart</a>
            </div>
        </div>
    </section>
    
    <section class="newsletter">
        <h3>Join the NexVerse Community</h3>
        <p>Get exclusive updates, early access to new releases, and special discounts for our subscribers.</p>
        <form class="newsletter-form">
            <input type="email" placeholder="Enter your email address">
            <button type="submit">Subscribe</button>
        </form>
    </section>
    
    <footer>
        <div class="footer-grid">
            <div class="footer-column">
                <h4>NexVerse</h4>
                <p>Creating immersive worlds and unforgettable stories through comics, animation, and merchandise.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-tiktok"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                </div>
            </div>
            <div class="footer-column">
                <h4>Explore</h4>
                <ul>
                    <li><a href="#comics">Comics</a></li>
                    <li><a href="#anime">Anime</a></li>
                    <li><a href="#merch">Merchandise</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Events</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Company</h4>
                <ul>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#">Careers</a></li>
                    <li><a href="#">Press</a></li>
                    <li><a href="#">Partners</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4>Support</h4>
                <ul>
                    <li><a href="#">Help Center</a></li>
                    <li><a href="#contact">Contact Us</a></li>
                    <li><a href="#">Shipping</a></li>
                    <li><a href="#">Returns</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 NexVerse. All rights reserved. | <a href="#">Privacy Policy</a> | <a href="#">Terms of Service</a></p>
        </div>
    </footer>
    
    <!-- Video teaser placeholder script -->
    <script>
        // This would be replaced with your actual video player implementation
        document.querySelector('video').addEventListener('click', function() {
            this.play();
        });
    </script>
</body>
</html>
# animeweb
