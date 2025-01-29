<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Theme Android App</title>
    <link rel="stylesheet" href="styles.css">
    <script src="scripts.js" defer></script>
</head>
<body class="dark-theme">
    <!-- Header Section -->
    <header class="app-header">
        <div class="app-title">Demo Gold Battle</div>
        <div class="header-actions">
            <span class="notification">🔔</span>
            <span class="wallet">₹ 0</span>
        </div>
    </header>

    <!-- Welcome Section -->
    <section class="welcome-section">
        <marquee>WELCOME TO OUR APP</marquee>
    </section>

    <!-- Login/Register Section -->
    <section class="auth-section" id="auth-section">
        <div id="auth-container">
            <h2>Login</h2>
            <form id="login-form">
                <input type="text" id="username" placeholder="Username/Email/Mobile No" required>
                <input type="password" id="password" placeholder="Password" required>
                <button type="submit" onclick="login()">Login</button>
                <p>Forgot Password? <a href="#">Recover via Email/Mobile</a></p>
                <p>Don't have an account? <a href="#" onclick="toggleRegister()">Register</a></p>
            </form>

            <form id="register-form" style="display:none;">
                <h2>Register</h2>
                <input type="text" id="name" placeholder="Name" required>
                <input type="text" id="username-reg" placeholder="Username" required>
                <input type="text" id="phone" placeholder="India +91 Phone Number" required>
                <input type="email" id="email" placeholder="Email" required>
                <input type="password" id="password-reg" placeholder="Password" required>
                <input type="text" id="promo-code" placeholder="Promo Code (Optional)">
                <input type="file" id="image-upload" accept="image/*" required>
                <button type="submit">Register</button>
                <p>Or login with:</p>
                <button type="button" onclick="googleLogin()">Google Login</button>
                <button type="button" onclick="facebookLogin()">Facebook Login</button>
                <p>Already have an account? <a href="#" onclick="toggleLogin()">Login</a></p>
            </form>
        </div>
    </section>

    <!-- Account Details Section (Visible After Login) -->
    <section class="account-details" id="account-details" style="display:none;">
        <h2>Account Details</h2>
        <div class="details-icons">
            <button onclick="navigateTo('profile')">My Profile</button>
            <button onclick="navigateTo('wallet')">My Wallet</button>
            <button onclick="navigateTo('statistics')">My Statistics</button>
            <button onclick="navigateTo('settings')">Settings</button>
            <button onclick="navigateTo('notifications')">Notifications</button>
        </div>
    </section>

    <!-- Other Sections -->
    <section class="esports-games" style="display:none;">
        <h2>Esports Games</h2>
        <div class="game-cards">
            <div class="card" onclick="openGame('Mega BR')">Mega BR</div>
            <div class="card" onclick="openGame('CS 2v2')">CS 2v2</div>
            <div class="card" onclick="openGame('Battle Royal')">Battle Royal</div>
            <div class="card" onclick="openGame('Lone Wolf')">Lone Wolf</div>
            <div class="card" onclick="openGame('Lone 1v1')">Lone 1v1</div>
            <div class="card" onclick="openGame('CS 1v1')">CS 1v1</div>
        </div>
    </section>

    <section class="lucky-draw" style="display:none;">
        <h2>Lucky Draw</h2>
        <div class="draw-banner" onclick="participateLuckyDraw()">Participate Now!</div>
    </section>

    <section class="my-matches" style="display:none;">
        <h2>My Matches</h2>
        <div class="match-status">
            <button onclick="showMatches('upcoming')">Upcoming</button>
            <button onclick="showMatches('ongoing')">Ongoing</button>
            <button onclick="showMatches('completed')">Completed</button>
        </div>
    </section>

    <footer class="app-footer" style="display:none;">
        <button class="share-button" onclick="shareApp()">SHARE</button>
    </footer>

    <script>
        let isLoggedIn = false;

        function login() {
            // Perform login action (Add validation as needed)
            isLoggedIn = true;  // Assuming login is successful
            toggleSections();
            alert('Login Successful!');
        }

        function toggleSections() {
            if (isLoggedIn) {
                document.getElementById('auth-section').style.display = 'none';
                document.getElementById('account-details').style.display = 'block';
                document.querySelectorAll('.esports-games, .lucky-draw, .my-matches, .app-footer').forEach(section => {
                    section.style.display = 'block';
                });
            }
        }

        function navigateTo(section) {
            alert(`Navigating to ${section}`);
        }

        function openGame(game) {
            alert(`Opening ${game}`);
        }

        function participateLuckyDraw() {
            alert('Participating in Lucky Draw!');
        }

        function showMatches(status) {
            alert(`Showing ${status} matches`);
        }

        function shareApp() {
            alert('Sharing the app!');
        }

        function toggleRegister() {
            document.getElementById('login-form').style.display = 'none';
            document.getElementById('register-form').style.display = 'block';
        }

        function toggleLogin() {
            document.getElementById('register-form').style.display = 'none';
            document.getElementById('login-form').style.display = 'block';
        }

        function googleLogin() {
            alert('Google Login triggered!');
            // Implement Google login API here
        }

        function facebookLogin() {
            alert('Facebook Login triggered!');
            // Implement Facebook login API here
        }
    </script>
</body>
</html>
