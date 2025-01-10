# Assignment: Responsive Web Design

## Objective:
Create a responsive webpage using modern CSS techniques, specifically Flexbox, Grid, and Media Queries. The goal is to ensure the webpage adapts gracefully to various screen sizes.

## Assignment Tasks

### Designing a Responsive Layout
a. Create a webpage with the following sections:

Header (including a logo and navigation links).
Main content area (with two columns: one for text content and the other for an image).
Footer (with links to social media and a copyright notice).
b. Use Flexbox to style the navigation menu in the header.
c. Use CSS Grid to structure the main content area.

### Creating Media Queries for Responsiveness
a. Implement media queries to ensure the webpage looks good on the following screen sizes:

Small screens (up to 600px): Stack all sections vertically.
Medium screens (601px to 1024px): Keep the header and footer horizontal, but stack the main content columns.
Large screens (above 1024px): Display the layout as designed with Flexbox and Grid.

### Bonus

Add animations or transitions when resizing the screen.
HTML FILE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Webpage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- Header Section -->
    <header class="header">
        <div class="logo">
            <img src="logo.png" alt="Logo" />
        </div>
        <nav class="navigation">
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Main Content Section -->
    <main class="main-content">
        <div class="text-content">
            <h2>Welcome to Our Website</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras sit amet ligula a augue volutpat tincidunt.</p>
        </div>
        <div class="image-content">
            <img src="image.jpg" alt="Image" />
        </div>
    </main>

    <!-- Footer Section -->
    <footer class="footer">
        <div class="social-media">
            <a href="#">Facebook</a>
            <a href="#">Twitter</a>
            <a href="#">Instagram</a>
        </div>
        <p>&copy; 2025 Company Name. All rights reserved.</p>
    </footer>

</body>
</html>

CSS FILE
/* General Styles */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

a {
    text-decoration: none;
    color: inherit;
}

header, main, footer {
    padding: 20px;
    margin: 0 auto;
}

/* Header Styles (Flexbox) */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #333;
    color: white;
}

.logo img {
    width: 100px;
}

.navigation ul {
    list-style: none;
    display: flex;
    gap: 20px;
}

.navigation li {
    display: inline-block;
}

.navigation a {
    color: white;
    font-size: 18px;
}

/* Main Content Styles (Grid) */
.main-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin: 20px 0;
}

.text-content h2 {
    font-size: 24px;
    margin-bottom: 10px;
}

.text-content p {
    font-size: 16px;
    line-height: 1.5;
}

.image-content img {
    max-width: 100%;
    height: auto;
}

/* Footer Styles */
.footer {
    text-align: center;
    background-color: #333;
    color: white;
    margin-top: 20px;
}

.social-media {
    margin-bottom: 10px;
}

.social-media a {
    margin: 0 10px;
    color: white;
    font-size: 18px;
}

/* Media Queries for Responsiveness */
@media screen and (max-width: 600px) {
    /* Small screens - Stack all sections vertically */
    .header {
        flex-direction: column;
        text-align: center;
    }

    .navigation ul {
        flex-direction: column;
        align-items: center;
    }

    .main-content {
        grid-template-columns: 1fr;
    }

    .footer {
        text-align: center;
    }
}

@media screen and (min-width: 601px) and (max-width: 1024px) {
    /* Medium screens - Stack main content columns */
    .main-content {
        grid-template-columns: 1fr;
    }

    .header {
        flex-direction: row;
    }

    .navigation ul {
        flex-direction: row;
        justify-content: center;
    }
}

@media screen and (min-width: 1025px) {
    /* Large screens - Display Flexbox and Grid layout */
    .main-content {
        grid-template-columns: 1fr 1fr;
    }
}

/* Bonus: Animations and Transitions */
* {
    transition: all 0.3s ease;
}

.header, .main-content, .footer {
    opacity: 0;
}

@media screen and (min-width: 601px) {
    .header, .main-content, .footer {
        opacity: 1;
    }
}
