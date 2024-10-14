<template>
    <footer>
        <div class="footer-content">
            <div class="newsletter">
                <img src="../assets/logo/logo.png" alt="Club-Logo" width="150px" height="150px">
                <p>Join our newsletter to stay up to date on features and releases.</p>
                <div class="newsform">
                    <p>By subscribing you agree to with our Privacy Policy and provide consent to receive updates from our company.</p>
                    <form action="">
                        <input type="email" placeholder="Enter your email" required>
                        <input type="submit" value="Subscribe">
                    </form>
                </div>
            </div>
            <div class="links">
                <div class="web-explore">
                    <h2>Explore More</h2>
                    <ul>
                        <li><a href="">Home</a></li>
                        <li><a href="">About</a></li>
                        <li><a href="">Pricing</a></li>
                        <li><a href="">Blog</a></li>
                        <li><a href="">Events</a></li>
                    </ul>
                </div>
                <div class="web-links">
                    <h2>Stay Connected</h2>
                    <ul>
                        <li><a href="">Subscribe</a></li>
                        <li><a href="">Member stories</a></li>
                        <li><a href="">Location</a></li>
                        <li><a href="">Write for us</a></li>
                    </ul>
                </div>
                <div class="social-media-links">
                    <h2>Follow Us</h2>
                    <ul>
                        <li><a href="">Facebook</a></li>
                        <li><a href="">Instagram</a></li>
                        <li><a href="">X</a></li>
                        <li><a href="">Linkedin</a></li>
                        <li><a href="">Youtube</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="footer-footer">
            <div class="credit">
                <p>&copy; 2024 Skikda i-tech club. All rights reserved.</p>
            </div>
             <div class="footer-links">
                <a href="#">Privacy Policy</a>
                <a href="#">Terms of Service</a>
                <a href="#">Cookies Settings</a>
            </div>
        </div>
    </footer>
</template>

<style>

footer {
    bottom: 0;
    margin-top: 100px;
    padding: 0 20px;
    background-color: #000; 
    color: #fff; 
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, auto)); /* Adjusts to available space */
    gap: 24px;
    padding: 20px 10px;
    border-radius: 10px;
    background-color: #7847ffe7;
    border: 2px solid #5E25FF;
}

/* Newsletter section - Adjust width for better grid fit */
.newsletter {
    grid-column: span 1; /* This will span across two columns on larger screens */
    max-width: 400px; /* To prevent it from being too wide */
}

.newsletter img {
    margin-bottom: 24px;
}

.newsletter p {
    font-size: 12px;
    font-weight: 100;
    margin-bottom: 24px;
}

.newsform p {
    font-size: 12px;
    font-weight: 100;
    margin-bottom: 24px;
}

.newsform input {
    padding: 12px;
    margin-right: 24px;
    background-color: #313131;
    color: #ffffff;
    border: none; 
    border-radius: 4px; 
}

.newsform input[type="submit"] {
    padding: 12px 24px;
    margin-top: 10px;
    border: 2px solid #5E25FF;
    border-radius: 42px;
    background-color: #ffffff;
    color: #5E25FF;
    cursor: pointer; 
}

/* Links section */
.links {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, auto)); /* Adaptable grid for links */
    gap: 32px;
}

/* Explore, Stay Connected, Social Media Links */
.web-explore, .web-links, .social-media-links {
    margin: 0;
}

.web-explore h2, .web-links h2, .social-media-links h2 {
    font-family: 'ItechFont';
    font-size: 24px;
    font-weight: regular;
    letter-spacing: 3px;
    margin-bottom: 30px;
}

.web-explore ul, .web-links ul, .social-media-links ul {
    list-style: none;
    padding: 0; 
}

.web-explore ul li, .web-links ul li, .social-media-links ul li {
    margin-bottom: 8px;
}

.web-explore ul li a, .web-links ul li a, .social-media-links ul li a {
    text-decoration: none;
    font-size: 14px; 
    font-weight: 100;
    color: #fff; 
}

.web-explore ul li a:hover, .web-links ul li a:hover, .social-media-links ul li a:hover {
    text-decoration: underline;
}

/* Footer footer - Aligns at the bottom */
.footer-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 24px auto 0; 
}

.credit p {
    margin: 0;
}

.footer-links {
    display: flex;
    gap: 20px;
}

.footer-links a {
    font-size: 12px;
    font-weight: 100;
    color: #fff;
    text-decoration: none;
}

.footer-links a:hover {
    text-decoration: underline;
}

@media (max-width: 768px) {
    .footer-content {
        grid-template-columns: 1fr; /* Stack content on smaller screens */
    }

    .newsletter {
        grid-column: span 1; /* Full-width on smaller screens */
    }
}
</style>
