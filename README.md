<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Login & Sign Up | CSC Vle</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', sans-serif;
    }
    body {
      background-color: #f0f2f5;
    }
    header {
      width: 100%;
      padding: 15px 40px;
      background: #fff;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 1px 5px rgba(0,0,0,0.1);
      position: fixed;
      top: 0;
      z-index: 10;
    }
    .logo {
      font-size: 22px;
      font-weight: bold;
      color: #2c3e50;
    }
    nav a {
      margin-left: 20px;
      color: #333;
      text-decoration: none;
      font-size: 14px;
    }
    nav a i {
      margin-right: 6px;
    }

    .container {
      display: flex;
      margin-top: 80px;
      min-height: 100vh;
    }

    .form-section {
      flex: 1;
      padding: 50px 40px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .form-section h2 {
      font-size: 28px;
      margin-bottom: 10px;
      color: #1a202c;
    }

    .form-section p {
      margin-bottom: 30px;
      color: #555;
    }

    .form-group {
      margin-bottom: 20px;
    }

    label {
      display: block;
      margin-bottom: 5px;
      color: #333;
    }

    input[type="text"],
    input[type="email"],
    input[type="password"] {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 14px;
    }

    .options {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 13px;
      margin: 15px 0;
    }

    .btn {
      width: 100%;
      padding: 12px;
      background: #1f2937;
      color: #fff;
      border: none;
      border-radius: 6px;
      font-weight: bold;
      cursor: pointer;
      margin-bottom: 10px;
    }

    .btn-google {
      background: #fff;
      color: #444;
      border: 1px solid #ccc;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .btn-google img {
      width: 18px;
      margin-right: 8px;
    }

    .form-toggle {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }

    .form-toggle button {
      padding: 10px 20px;
      border: none;
      background: #e0e0e0;
      cursor: pointer;
      font-weight: bold;
      color: #444;
    }

    .form-toggle .active {
      background: #1f2937;
      color: #fff;
    }

    .image-section {
      flex: 1;
      background: #e6f0ff;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 30px;
      position: relative;
    }

    .image-section img {
      max-width: 100%;
      height: auto;
    }

    .footer {
      position: absolute;
      bottom: 20px;
      width: 100%;
      text-align: center;
      font-size: 13px;
      color: #555;
    }

    @media(max-width: 768px) {
      .container {
        flex-direction: column;
      }
      .image-section {
        order: -1;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">CSC Vle</div>
    <nav>
      <a href="#"><i class="fa-solid fa-house"></i> Home</a>
      <a href="#"><i class="fa-solid fa-shield-halved"></i> Privacy</a>
      <a href="#"><i class="fa-solid fa-file-lines"></i> Terms</a>
      <a href="#"><i class="fa-solid fa-phone"></i> Contact</a>
    </nav>
  </header>

  <div class="container">
    <div class="form-section">
      <div class="form-toggle">
        <button id="loginBtn" class="active" onclick="showForm('login')">Login</button>
        <button id="signupBtn" onclick="showForm('signup')">Sign Up</button>
      </div>

      <!-- Login Form -->
      <form id="loginForm">
        <h2>Welcome Back</h2>
        <p>Please login to your account</p>
        <div class="form-group">
          <label for="email">Email ID *</label>
          <input type="text" id="email" placeholder="Enter your email" required />
        </div>
        <div class="form-group">
          <label for="password">Password *</label>
          <input type="password" id="password" placeholder="Enter your password" required />
        </div>
        <div class="options">
          <label><input type="checkbox" /> Remember me</label>
          <a href="#">Forgot password?</a>
        </div>
        <button class="btn" type="submit">Login</button>
        <button class="btn btn-google" type="button">
          <img src="https://cdn-icons-png.flaticon.com/512/281/281764.png" alt="Google" />
          Sign in with Google
        </button>
      </form>

      <!-- Signup Form -->
      <form id="signupForm" style="display: none;" onsubmit="return validateSignupForm()">
        <h2>Create Account</h2>
        <div class="form-group">
          <label for="name">Full Name *</label>
          <input type="text" id="name" placeholder="Your full name" required />
        </div>
        <div class="form-group">
          <label for="signupEmail">Email ID *</label>
          <input type="email" id="signupEmail" placeholder="Enter your email" required />
        </div>
        <div class="form-group">
          <label for="signupPassword">Password *</label>
          <input type="password" id="signupPassword" placeholder="Create a password" required />
        </div>
        <div class="form-group">
          <label for="confirmPassword">Confirm Password *</label>
          <input type="password" id="confirmPassword" placeholder="Re-enter password" required />
        </div>
        <button class="btn" type="submit">Register</button>
      </form>
    </div>

    <div class="image-section">
      <img src="https://assets-v2.lottiefiles.com/a/8e2c08a2-116f-11ee-a8fc-87919b0b746b/6L2iZkKDPz.gif" alt="Animation" />
      <div class="footer">© 2024 Your System | No Copyright</div>
    </div>
  </div>

  <script>
    function showForm(form) {
      document.getElementById('loginForm').style.display = (form === 'login') ? 'block' : 'none';
      document.getElementById('signupForm').style.display = (form === 'signup') ? 'block' : 'none';
      document.getElementById('loginBtn').classList.toggle('active', form === 'login');
      document.getElementById('signupBtn').classList.toggle('active', form === 'signup');
    }

    function validateSignupForm() {
      const password = document.getElementById("signupPassword").value;
      const confirm = document.getElementById("confirmPassword").value;

      if (password !== confirm) {
        alert("Password and Confirm Password do not match!");
        return false;
      }

      return true;
    }
  </script>

</body>
</html>
