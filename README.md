<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aroma Haven - Specialty Coffee Cafe</title>
    <style>
      /* Reset and basic styles */
      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

/* Problem: The horizontal scrollbar appears because some elements exceed the viewport width due to fixed
widths or margin/padding configurations.
Fix: Add overflow-x: hidden; to the body to prevent horizontal scrolling */
      body {
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        line-height: 1.6;
        color: #333;
        background-color: #f4f4f4;
        overflow-x: hidden; /*Prevent horizontal scroll*/
      }

      img {
        max-width: 100%;
        height: auto;
      }

      .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 0 20px;
      }

      /* Header styles */
      header {
        background-color: #2c3e50;
        color: #ecf0f1;
        padding: 1rem 0;
        position: sticky;
        top: 0;
        z-index: 1000;
      }

      .header-content {
        display: flex;
        justify-content: space-between;
        align-items: center;
      }

      .logo {
        font-size: 1.5rem;
        font-weight: bold;
      }

      nav ul {
        display: flex;
        gap: 1.5rem;
        list-style: none;
      }

      nav a {
        color: #ecf0f1;
        text-decoration: none;
        transition: color 0.3s ease;
      }

      nav a:hover {
        color: #3498db;
      }

      /* Hero section styles */
      .hero {
        background-image: url("/api/placeholder/1200/600");
        background-size: cover;
        background-position: center;
        height: 70vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        color: #fff;
      }

      .hero-content {
        background-color: rgba(0, 0, 0, 0.6);
        padding: 2rem;
        border-radius: 10px;
      }

      .hero h1 {
        font-size: 3rem;
        margin-bottom: 1rem;
      }

      .cta-button {
        display: inline-block;
        background-color: #e74c3c;
        color: #fff;
        padding: 0.8rem 1.5rem;
        border-radius: 5px;
        text-decoration: none;
        transition: background-color 0.3s ease;
      }

      .cta-button:hover {
        background-color: #c0392b;
      }

      /* Section styles */
      section {
        padding: 4rem 0;
      }

      .section-title {
        text-align: center;
        margin-bottom: 2rem;
        font-size: 2rem;
        color: #2c3e50;
      }

      /* Featured products styles */
      .featured-products {
        display: flex;
        flex-wrap: wrap;
        gap: 2rem;
        justify-content: center;
      }

      .product-card {
        flex: 0 1 calc(25% - 2rem);
        background-color: #fff;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        transition: transform 0.3s ease;
      }

      .product-card:hover {
        transform: translateY(-5px);
      }

      .product-image {
        height: 200px;
        background-size: cover;
        background-position: center;
      }

      .product-info {
        padding: 1rem;
      }

      .product-title {
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
      }

      .product-price {
        font-weight: bold;
        color: #e74c3c;
      }

      /* About section styles */
      .about {
        display: flex;
        align-items: center;
        gap: 4rem;
      }

      .about-content,
      .about-image {
        flex: 1;
      }

      .about-image img {
        border-radius: 10px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      }

      /* Menu section styles */
      .menu-categories {
        display: flex;
        justify-content: center;
        gap: 1rem;
        margin-bottom: 2rem;
      }

      .category-button {
        background-color: #3498db;
        color: #fff;
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease;
      }

      .category-button:hover {
        background-color: #2980b9;
      }

      .menu-items {
        display: flex;
        flex-wrap: wrap;
        gap: 2rem;
      }

      .menu-item {
        flex: 0 1 calc(33.333% - 2rem);
        background-color: #fff;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      }

      .menu-item-image {
        height: 200px;
        background-size: cover;
        background-position: center;
      }

      .menu-item-info {
        padding: 1rem;
      }

      .menu-item-title {
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
      }

      .menu-item-price {
        font-weight: bold;
        color: #e74c3c;
      }

      /* Testimonials section styles */
      .testimonials {
        display: flex;
        flex-wrap: wrap;
        gap: 2rem;
        justify-content: center;
      }

      .testimonial-card {
        flex: 0 1 calc(33.333% - 2rem);
        background-color: #fff;
        border-radius: 10px;
        padding: 2rem;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      }

      .testimonial-text {
        font-style: italic;
        margin-bottom: 1rem;
      }

      .testimonial-author {
        font-weight: bold;
        text-align: right;
      }

      /* Contact section styles */
      .contact-form {
        max-width: 600px;
        margin: 0 auto;
      }

      .form-group {
        margin-bottom: 1rem;
      }

      .form-group label {
        display: block;
        margin-bottom: 0.5rem;
      }

      .form-group input,
      .form-group textarea {
        width: 100%;
        padding: 0.5rem;
        border: 1px solid #ccc;
        border-radius: 5px;
      }

      .form-group textarea {
        height: 150px;
      }

      .submit-button {
        background-color: #2ecc71;
        color: #fff;
        border: none;
        padding: 0.8rem 1.5rem;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease;
      }

      .submit-button:hover {
        background-color: #27ae60;
      }

      /* Footer styles */
      footer {
        background-color: #34495e;
        color: #ecf0f1;
        padding: 2rem 0;
      }

      .footer-content {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 2rem;
      }

      .footer-section {
        flex: 1 1 300px;
      }

      .footer-section h3 {
        margin-bottom: 1rem;
      }

      .social-links {
        display: flex;
        gap: 1rem;
      }

      .social-links a {
        color: #ecf0f1;
        font-size: 1.5rem;
        transition: color 0.3s ease;
      }

      .social-links a:hover {
        color: #3498db;
      }

/* Problem: When the width is reduced, the header content (logo and navigation links) overflows.
Fix: Make the header content stack vertically on smaller screens. Additionally, adjust font sizes for better scaling. */
     /* Responsive design */
      @media (max-width: 768px) {
        .header-content {
          flex-direction: column;
          gap: 1rem;
        }

        nav ul {
          flex-direction: column; /*Align navigation vertically*/
          gap: 0.5rem; /*Reduce gap*/
        }

        .hero h1 {
          font-size: 2rem;
        }

        .about {
          flex-direction: column;
        }

        .product-card,
        .menu-item,
        .testimonial-card {
          flex: 0 1 calc(50% - 1rem);
        }
      }

/*Problem: On smaller screens, the .product-card, .menu-item, and .testimonial-card maintain their widths and don't adjust properly.
Fix: Use flex-basis to make the cards adjust based on screen size. I've added media queries to handle smaller screens for better alignment. */
      @media (max-width: 768px) {
        .product-card,
        .menu-item,
        .testimonial-card {
            flex: 0 1 calc(50% - 1rem); /* 50% width on medium screens */
  }
}


/* Problem: The featured-products, menu-items, and other flex containers were not wrapping properly on smaller screens.
Fix: Added flex-wrap: wrap; to handle wrapping of content in a more fluid way. */
      @media (max-width: 480px) {
        .product-card,
        .menu-item,
        .testimonial-card {
        flex: 0 1 100%; /* Full width on small screens */
  }
}

/* Problem: On smaller screens, the padding of .container could cause content to look squeezed.
Fix: Use padding: 0 in smaller viewports to avoid this */
@media (max-width: 768px) {
  .container {
    padding: 0 10px; /* Adjust padding for smaller screens */
  }
}

/* add 480px for the mobiles making it more responsive */

@media (max-width: 480px) {
  .hero h1 {
    font-size: 1.5rem;
  }
  
  .product-card,
  .menu-item,
  .testimonial-card {
    flex: 0 1 100%;
    margin-bottom: 1rem; /* Ensure proper spacing */
  }
  
  .cta-button {
    padding: 0.6rem 1rem;
    font-size: 0.9rem;
  }
  
  /* Adjust font size for small screens */
  body {
    font-size: 0.9rem;
  }
  
  header .logo {
    font-size: 1.2rem;
  }
}



.featured-products, .menu-items, .testimonials {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center; /* Ensure the content centers properly */
}


    </style>
  </head>
  <body>
    <header>
      <div class="container header-content">
        <div class="logo">Aroma Haven</div>
        <nav>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#testimonials">Testimonials</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <main>
      <section id="home" class="hero">
        <div class="hero-content">
          <h1>Welcome to Aroma Haven</h1>
          <p>Experience the perfect blend of flavor and ambiance</p>
          <a href="#menu" class="cta-button">Explore Our Menu</a>
        </div>
      </section>

      <section id="featured-products">
        <div class="container">
          <h2 class="section-title">Featured Products</h2>
          <div class="featured-products">
            <div class="product-card">
              <div
                class="product-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="product-info">
                <h3 class="product-title">Signature Blend</h3>
                <p class="product-price">$14.99</p>
              </div>
            </div>
            <div class="product-card">
              <div
                class="product-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="product-info">
                <h3 class="product-title">Espresso Roast</h3>
                <p class="product-price">$12.99</p>
              </div>
            </div>
            <div class="product-card">
              <div
                class="product-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="product-info">
                <h3 class="product-title">Cold Brew Kit</h3>
                <p class="product-price">$24.99</p>
              </div>
            </div>
            <div class="product-card">
              <div
                class="product-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="product-info">
                <h3 class="product-title">Pour Over Set</h3>
                <p class="product-price">$34.99</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="about">
        <div class="container about">
          <div class="about-content">
            <h2 class="section-title">Our Story</h2>
            <p>
              Aroma Haven was founded with a passion for serving the finest
              coffee in town. Our journey began with a simple idea: to create a
              warm and inviting space where coffee lovers could come together to
              enjoy exceptional brews and meaningful conversations.
            </p>
            <p>
              Today, we continue to source our beans from sustainable farms
              around the world, roasting them to perfection to bring out their
              unique flavors and aromas. Our dedicated team of baristas is
              committed to crafting each cup with care and precision, ensuring
              that every sip is a delightful experience.
            </p>
          </div>
          <div class="about-image">
            <img
              src="/api/placeholder/600/400"
              alt="Coffee beans being roasted"
            />
          </div>
        </div>
      </section>

      <section id="menu">
        <div class="container">
          <h2 class="section-title">Our Menu</h2>
          <div class="menu-categories">
            <button class="category-button">All</button>
            <button class="category-button">Hot Drinks</button>
            <button class="category-button">Cold Drinks</button>
            <button class="category-button">Pastries</button>
          </div>
          <div class="menu-items">
            <div class="menu-item">
              <div
                class="menu-item-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="menu-item-info">
                <h3 class="menu-item-title">Cappuccino</h3>
                <p class="menu-item-price">$3.99</p>
              </div>
            </div>
            <div class="menu-item">
              <div
                class="menu-item-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="menu-item-info">
                <h3 class="menu-item-title">Iced Latte</h3>
                <p class="menu-item-price">$4.49</p>
              </div>
            </div>
            <div class="menu-item">
              <div
                class="menu-item-image"
                style="background-image: url('/api/placeholder/300/200')"
              ></div>
              <div class="menu-item-info">
                <h3 class="menu-item-title">Croissant</h3>
                <p class="menu-item-price">$2.99</p>
              </div>
            </div>
            <!-- Add more menu items here -->
          </div>
        </div>
      </section>

      <section id="testimonials">
        <div class="container">
          <h2 class="section-title">What Our Customers Say</h2>
          <div class="testimonials">
            <div class="testimonial-card">
              <p class="testimonial-text">
                "Aroma Haven is my go-to spot for the perfect cup of coffee. The
                atmosphere is cozy, and the staff is always friendly and
                knowledgeable."
              </p>
              <p class="testimonial-author">- Sarah J.</p>
            </div>
            <div class="testimonial-card">
              <p class="testimonial-text">
                "I've tried coffee shops all over town, but none compare to the
                quality and consistency of Aroma Haven. Their pour-over is
                simply unmatched!"
              </p>
              <p class="testimonial-author">- Michael T.</p>
            </div>
            <div class="testimonial-card">
              <p class="testimonial-text">
                "As a freelancer, I spend a lot of time working from cafes.
                Aroma Haven provides the perfect environment with great coffee
                and reliable Wi-Fi."
              </p>
              <p class="testimonial-author">- Emily R.</p>
            </div>
          </div>
        </div>
      </section>

      <section id="contact">
        <div class="container">
          <h2 class="section-title">Get in Touch</h2>
          <form class="contact-form">
            <div class="form-group">
              <label for="name">Name</label>
              <input type="text" id="name" name="name" required />
            </div>
            <div class="form-group">
              <label for="email">Email</label>
              <input type="email" id="email" name="email" required />
            </div>
            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" name="message" required></textarea>
            </div>
            <button type="submit" class="submit-button">Send Message</button>
          </form>
        </div>
      </section>
    </main>

    <footer>
      <div class="container footer-content">
        <div class="footer-section">
          <h3>Aroma Haven</h3>
          <p>123 Coffee Street<br />Cityville, State 12345</p>
        </div>
        <div class="footer-section">
          <h3>Hours</h3>
          <p>Monday - Friday: 7am - 8pm<br />Saturday - Sunday: 8am - 7pm</p>
        </div>
        <div class="footer-section">
          <h3>Contact</h3>
          <p>Phone: (123) 456-7890<br />Email: info@aromahaven.com</p>
        </div>
        <div class="footer-section">
          <h3>Follow Us</h3>
          <div class="social-links">
            <a href="#" aria-label="Facebook">FB</a>
            <a href="#" aria-label="Instagram">IG</a>
            <a href="#" aria-label="Twitter">TW</a>
          </div>
        </div>
      </div>
    </footer>
  </body>
</html>

