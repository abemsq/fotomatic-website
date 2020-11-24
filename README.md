# Project: Fotomatic

In this project you will fix a broken version of a responsive website called Fotomatic. You will update it to look and work exactly the same as the specs do. Download the broken code here and the specs here. You can also see a working version of the final product here.

As you fix Fotomatic’s bugs, remember to use the skills you acquired in the
Chrome DevTools article to help you decipher and update the site’s CSS. Chrome
DevTools are essential for debugging – they allow you to view current style
values, toggle rules, and test different rule values.

[!image](https://github.com/abemsq/fotomatic-website/blob/master/image.png)

## HTML
```
<!DOCTYPE html>
<html>
<head>
  <link href="https://fonts.googleapis.com/css?family=Damion" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css?family=Roboto:300,400,600,700" rel="stylesheet">
  <link rel="stylesheet" href="./resources/css/reset.css">
  <link rel="stylesheet" href="./resources/css/style.css">
  <title>Fotomatic</title>
</head>
<body>
  <!-- Header -->
  <header>
    <div class="content">
      <a href="index.html" class="desktop logo">Fotomatic</a>
      <nav class="desktop">
        <ul>
          <li><a href="#">Product detail</a></li>
          <li><a href="#">About us</a></li>
          <li><a href="https://www.instagram.com/" target="_blank">Follow us <img class="icon" src="./resources/images/instagram.png"></a></li>
          <li><a href="#" class="button">Join us</a></li>
        </ul>
      </nav>
      <nav class="mobile">
        <ul>
          <li><a href="#"><img src="./resources/images/ic-logo.svg"></a></li>
          <li><a href="#"><img src="./resources/images/ic-product-detail.svg"></a></li>
          <li><a href="#"><img src="./resources/images/ic-about-us.svg"></a></li>
          <li><a href="#" class="button">Join us</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <!-- Main Content -->
  <div class="main-content">

    <!-- Sign Up Section -->
    <div id="sign-up-section" class="banner">
      <div id="sign-up-cta">
        <div class="content center">
          <div class="header">
            <h2 class="cursive">Instant</h2>
            <h1 class="striking">FORMAT CAMERA</h1>
          </div>
          <div class="email">
            <span>
              Email us to request a demo and be in our waiting list for the <strong>Febuary 2017</strong> release!
            </span>
            <div class="button">Join the waiting list</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Features Section -->
    <div id="features-section">
      <div class="feature">
        <div class="center">
          <div class="image-container">
            <img src="./resources/images/feature-1.png" />
          </div>
          <div class="content">
            <h2>Advanced, automatic, instant</h2>
            <h3>Shutter speed, apperture and flash output adjust automatically</h3>
          </div>
        </div>
      </div>
      <div class="feature">
        <div class="center">
          <div class="image-container">
            <img src="./resources/images/feature-2.png" />
          </div>
          <div class="content">
            <h2>Beautifully crafted inside-out</h2>
            <h3>From the paint outside to the tiny screw inside, Fotomatic is crafted with love and 20-year of expertise</h3>
          </div>
        </div>
      </div>
    </div>

    <!-- Filters Section -->
    <div id="filters-section">
      <div class="content center">
        <h2>Over 20+ filters to choose from</h2>
        <h3>Feed your creativity with 20 different filter designed by our eclectic in-house photographers!</h3>
      </div>
      <div class="images-container">
        <div class="image-container">
          <img src="./resources/images/filter-1.png" />
        </div>
        <div class="image-container">
          <img src="./resources/images/filter-2.png" />
        </div>
        <div class="image-container">
          <img src="./resources/images/filter-3.png" />
        </div>
        <div class="image-container extra">
          <img src="./resources/images/filter-4.png" />
        </div>
      </div>
    </div>

    <!-- Quotes Section -->
    <div id="quotes-section">
      <div class="content center">
        <span class="quote">“It’s truly something that could create a brand new photography Renaissance”</span>
        <img class="quote-citation" src="./resources/images/photography-logo.png" />
      </div>
    </div>

    <!-- Footer -->
    <footer>
      <div class="content">
        <span class="copyright">© 2016  Fotomatic, All Rights Reserved</span>
        <span class="location">Designed in NYC</span>
      </div>
    </footer>

  </div>
</body>
</html>
```

## CSS
```
/* Universal Styles */

html {
  font-family: "Roboto", sans-serif;
  font-size: 16px;
}

.main-content {
  position: relative;
  top: 5.3125rem; /* To offset for fixed header. */
}

.center {
  text-align: center;
}

.button {
  border-radius: 4px;
  background-color: #4a4a4a;
  color: white;
}

.image-container {
  overflow: hidden;
}

.image-container img {
  display: block;
  max-width: 100%;
}

@media only screen and (max-width: 895px) {
  .main-content {
    top: 2.5625rem;
  }
}

/* Header */

header {
  position: fixed;
  z-index: 100;
  width: 100%;
  border-bottom: solid 1px #c6c1c1;
  background-color: white;
}

header .content {
  display: flex;
  align-items: center;
  padding: 1.875rem;
}

header .logo {
  flex: 1;
}

header nav ul {
  display: flex;
}

nav li {
  padding-left: 3.5rem;
}

nav a {
  vertical-align: bottom;
  line-height: 1.6;
  font-size: 1rem;
  color: #4a4a4a;
}

nav .button {
  padding: .1875rem .5rem;
  background-color: #9dc20b;
  line-height: 1.6;
  color: white;
}

nav li:last-child {
  display: none;
}

header .icon {
  width: 1rem;
  padding-left: .75rem;
}

header .mobile {
  display: none;
}

@media only screen and (max-width: 895px) {
  nav li:last-child {
    display: block;
  }

  header .content {
    padding: 1rem 1rem;
  }
}

@media only screen and (max-width: 600px) {
  header .desktop {
    display: none;
  }

  header .mobile {
    display: block;
    width: 100%;
  }

  header .content {
    padding: .5rem 0;
  }

  header .mobile ul {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
  }

  header .mobile li {
    padding: 0;
  }
}

/* Sign Up Section */

#sign-up-section {
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
  height: 43.5rem;
  background-image: url('../images/banner-landingpage.jpg');
  background-position: bottom;
  background-size: cover;
  background-repeat: no-repeat;
}

#sign-up-cta {
  position: relative;
  top: 171px;
  left: 10%;
  padding: 0 5rem 2.5rem 5rem;
  border: solid 1px #979797;
  border-radius: 4px;
  background-color: #9dc20b;
}

#sign-up-cta .content {
  width: 25.625rem;
  margin-top: 2rem;
  font-family: "Roboto", sans-serif;
  font-size: 1.25rem;
  line-height: 1.4;
  color: white;
}

#sign-up-cta h1 {
  font-size: 3.125rem;
}

#sign-up-cta h2 {
  font-size: 2.25rem;
}

#sign-up-cta span strong {
  font-weight: bold;
}

#sign-up-cta .cursive {
  font-family: "Damion", cursive;
}

#sign-up-cta .striking {
  font-family: "Rubik", sans-serif;
  padding-bottom: .75rem;
}

#sign-up-cta .button {
  margin-top: 1.625rem;
  padding: 1.25rem 7.25rem;
}

@media only screen and (max-width: 895px) {
  #sign-up-section {
    align-items: center;
    justify-content: center;
    height: 28rem;
  }

  #sign-up-cta {
    position: static;
    width: auto;
    height: auto;
    background-color: transparent;
    border: none;
  }

  #sign-up-cta .content {
    margin-top: 0;
  }

  #sign-up-cta .email {
    display: none;
  }

  #sign-up-cta h1 {
    font-size: 3.125rem;
  }

  #sign-up-cta h2 {
    font-size: 2.25rem;
  }
}

@media only screen and (max-width: 600px) {
  #sign-up-section {
    height: 20rem;
  }

  #sign-up-cta h1 {
    font-size: 2.25rem;
  }

  #sign-up-cta h2 {
    font-size: 2rem;
  }
}

/* Features Section */

#features-section {
  display: flex;
  justify-content: space-between;
  padding: 4rem 5%;
  background-color: #f3f3f3;
}

.feature {
  flex: 1;
  padding: 2rem;
  margin: 0px 1.25rem;
  background-color: white;
}

.feature .image-container {
  width: 90%;
  height: 65%;
  margin: 0 auto;
}

.feature .content {
  padding: 2.5rem 0;
}

.feature h2 {
  padding-bottom: .5rem;
  font-size: 2.25rem;
  font-weight: bold;
  color: #4a4a4a;
}

.feature h3 {
  font-size: 1rem;
  line-height: 1.2;
  font-weight: 300;
  color: #4a4a4a;
}

@media only screen and (max-width: 895px) {
  #features-section {
    padding: 1rem;
  }

  .feature {
    margin: 0px .5rem;
    padding: 1rem;
  }

  .feature h2 {
    font-size: 2rem;
    line-height: 1.3;
  }

  .feature h3 {
    font-size: .875rem;
    line-height: 1.4;
  }
}

@media only screen and (max-width: 600px) {
  #features-section {
    flex-flow: column;
    padding: 0;
  }

  .feature {
    margin: 0;
    padding: 1.25rem 1rem 0 1rem;
  }

  .feature .content {
    padding: 1.25rem 0 1.875rem 0;
  }
}

/* Filters Section */

#filters-section {
  padding: 4rem 0;
  background-color: #4a4a4a;
}

#filters-section .content {
  padding: 0 .625rem;
  margin-bottom: 5rem;
}

#filters-section .content h2 {
  font-size: 2.25rem;
  font-weight: bold;
  color: white;
}

#filters-section .content h3 {
  font-size: 1rem;
  line-height: 1.4;
  font-weight: 300;
  color: white;
}

#filters-section .images-container {
  display: flex;
  max-width: 100%;
  padding: 0 1%;
}

@media only screen and (max-width: 600px) {
  #filters-section {
    padding: 1.5rem 0 0 0;
  }

  #filters-section .content {
    margin-bottom: 1rem;
  }

  #filters-section .content h2 {
    padding-bottom: .625rem;
    font-size: 1.125rem;
    line-height: 1.3;
    font-weight: normal;
  }

  #filters-section .content h3 {
    font-size: .875rem;
    line-height: 1.4;
  }

  #filters-section .images-container {
    padding: 0;
  }

  #filters-section .extra {
    display: none;
  }
}

/* Quotes Section */

#quotes-section {
  background-color: #f3f3f3;
}

#quotes-section .content {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5rem 1.5rem;
}

#quotes-section .quote {
  padding-right: 1.875rem;
  font-family: "Palatino", serif;
  font-size: 1.875rem;
  line-height: 1.1;
  font-style: italic;
  color: #4a4a4a;
}

#quotes-section .quote-citation {
  height: 1.875rem;
}

@media only screen and (max-width: 895px) {
  #quotes-section .content {
    padding: 3rem 1.5rem;
  }
}

@media only screen and (max-width: 600px) {
  #quotes-section .content {
    flex-flow: column;
    padding: 1.875rem .625rem;
  }

  #quotes-section .quote {
    font-size: 1.5rem;
    line-height: 1.4;
  }

  #quotes-section .quote-citation {
    display: block;
    padding-top: 1rem;
    margin: auto;
  }
}

/* Footer */

footer {
  background-color: #9b9b9b;
  padding: 1.5rem 2rem;
}

footer .content {
  color: white;
  display: flex;
  font-size: .75rem;
}

footer .copyright {
  flex-grow: 1;
}

@media only screen and (max-width: 600px) {
  footer .content {
    font-size: .625rem;
  }
}
```