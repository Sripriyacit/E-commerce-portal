THIS IS MY E-COMMERCE WEBSITE WITH HTML
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>VOXCART - Large Colorful E-Commerce Portal</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap');

  body {
    margin: 0; font-family: 'Montserrat', sans-serif; background: #f4faff; color: #333;
  }
  nav {
    background:pink; padding: 15px 40px; display: flex; align-items: center; justify-content: space-between; position: sticky; top: 0; z-index: 1000;
  }
  .logo {
    font-size: 28px; font-weight: 700; color: white; cursor: pointer;
  }
  .nav-links {
    display: flex; list-style: none; gap: 25px; margin: 0; padding: 0;
  }
  .nav-links li a {
    color: white; text-decoration: none; font-weight: 600; font-size: 18px;
  }
  .nav-links li a:hover {
    text-decoration: underline;
  }
  
  .container {
    max-width: 1200px; margin: 30px auto; padding: 20px;
  }
  h2.section-title {
    color: violet; margin-bottom: 20px;
  }
  
  .product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(230px,1fr));
    gap: 25px;
  }
  .product-card {
    background: white; border-radius: 12px;
    box-shadow: 0 2px 15px rgba(0,0,0,0.05);
    padding: 15px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .product-card img {
    max-width: 100%; border-radius: 8px;
    object-fit: contain; height: 160px;
  }
  .product-name {
    margin-top: 12px; font-weight: 700; font-size: 18px; color: #444;
  }
  .product-price {
    color: #0073e6; font-weight: 700; margin-top: 6px; font-size: 16px;
  }
  .btn {
    background: #0073e6; color: white; cursor: pointer;
    border: none; padding: 10px 12px; border-radius: 6px;
    font-weight: 600; margin-top: 12px;
  }
  .btn:hover {
    background: #005bb5;
  }
  
  form {
    max-width: 450px; background: white; padding: 25px; border-radius: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); margin-bottom: 40px;
  }
  label {
    font-weight: 600; margin-top: 15px; display: block;
  }
  input[type="text"], input[type="email"], input[type="password"] {
    width: 100%; padding: 10px; margin-top: 6px; border-radius: 6px; border: 1px solid #ccc; font-size: 16px;
  }
  span.error {
    color: #e94e4e; font-size: 14px; font-weight: 600;
  }

  ul.list {
    list-style: none; padding: 0;
    max-width: 600px;
    background: white;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  }
  ul.list li {
    padding: 12px 8px;
    border-bottom: 1px solid #ccc;
    font-weight: 600;
  }
  ul.list li:last-child {
    border-bottom: none;
  }

    .comments-box {
    max-width: 700px;
    background: white;
    padding: 15px 20px;
    border-radius: 12px;
    box-shadow: 0 0 13px rgba(0,0,0,0.1);
    margin-bottom: 30px;
  }
  .comments-box form {
    margin-bottom: 15px;
  }
  .comments-box ul {
    list-style: disc; padding-left: 20px;
  }
  .comments-box ul li {
    margin-bottom: 10px;
    font-weight: 500;
  }

    .section-box {
    background: white;
    margin-bottom: 40px;
    padding: 25px 30px;
    border-radius: 12px;
    box-shadow: 0 2px 20px rgba(0,0,0,0.05);
  }

  
  @media (max-width: 768px) {
      nav {
          flex-direction: column;
          gap: 15px;
      }
      .nav-links {
          flex-wrap: wrap;
          justify-content: center;
      }
      .product-grid {
          grid-template-columns: repeat(auto-fill,minmax(160px,1fr));
      }
  }
</style>
</head>
<body>

<nav>
  <div class="logo" onclick="showSection('home')">VOXCART</div>
  <ul class="nav-links">
    <li><a href="#home" onclick="showSection('home')">Home</a></li>
    <li><a href="#products" onclick="showSection('products')">Products</a></li>
    <li><a href="#wishlist" onclick="showSection('wishlist')">Wishlist</a></li>
    <li><a href="#orders" onclick="showSection('orders')">Orders</a></li>
    <li><a href="#reviews" onclick="showSection('reviews')">Comments & Reviews</a></li>
    <li><a href="#contact" onclick="showSection('contact')">Customer Care</a></li>
    <li><a href="#register" onclick="showSection('register')">Register/Login</a></li>
  </ul>
</nav>

<div class="container">

  <section id="home" class="section-box">
    <h2 class="section-title">Welcome to VOXCART
    <p>Your one-stop online shop with a rich variety of products and features to manage your shopping experience.</p>
  </section>

  <section id="products" class="section-box" style="display:none;">
    <h2 class="section-title">Our Products</h2>
    <div class="product-grid" id="productGrid">
      <!-- Products inserted by JS -->
    </div>
  </section>

  <section id="wishlist" class="section-box" style="display:none;">
    <h2 class="section-title">Your Wishlist</h2>
    <ul class="list" id="wishlistList">
      <li>No items in your wishlist yet.</li>
    </ul>
  </section>

  <section id="orders" class="section-box" style="display:none;">
    <h2 class="section-title">Orders List</h2>
    <ul class="list" id="ordersList">
      <li>You haven't placed any orders yet.</li>
    </ul>
  </section>

  <section id="reviews" class="section-box" style="display:none;">
    <h2 class="section-title">Comments & Reviews</h2>
    <div class="comments-box">
      <form id="commentForm">
        <input type="text" id="commentInput" placeholder="Write your comment here" required style="width:100%;padding:10px; border-radius:6px; border: 1px solid #ccc;"/>
        <button type="submit" class="btn" style="margin-top:10px;">Submit Comment</button>
      </form>
      <ul id="commentsList"></ul>
    </div>
  </section>

  <section id="contact" class="section-box" style="display:none;">
    <h2 class="section-title">Customer Care & Reporting</h2>
    <p>For queries, complaints, or support, contact us:</p>
    <ul>
      <li>Email: support@shopease.com</li>
      <li>Phone: +91 90001 11122</li>
      <li><a href="mailto:support@shopease.com">Send an Email</a></li>
    </ul>
    <p>Please fill out our contact form or reach out through phone anytime.</p>
  </section>

  <section id="register" class="section-box" style="display:none;">
    <h2 class="section-title">User Registration</h2>
    <form id="registerForm" autocomplete="off">
      <label for="regName">Name</label>
      <input type="text" id="regName" required/>
      <span class="error" id="regNameError"></span>

      <label for="regEmail">Email</label>
      <input type="email" id="regEmail" required/>
      <span class="error" id="regEmailError"></span>

      <label for="regPassword">Password</label>
      <input type="password" id="regPassword" required/>
      <span class="error" id="regPasswordError"></span>

      <button type="submit" class="btn">Register</button>
    </form>

    <h2 class="section-title" style="margin-top: 60px;">User Login</h2>
    <form id="loginForm" autocomplete="off">
      <label for="loginEmail">Email</label>
      <input type="email" id="loginEmail" required/>
      <span class="error" id="loginEmailError"></span>

      <label for="loginPassword">Password</label>
      <input type="password" id="loginPassword" required/>
      <span class="error" id="loginPasswordError"></span>

      <button type="submit" class="btn">Login</button>
    </form>
  </section>

</div>

<script>
  // Navigation: Show only selected section
  function showSection(id) {
    const sections = ['home','products','wishlist','orders','reviews','contact','register'];
    sections.forEach(section => {
      document.getElementById(section).style.display = (section === id) ? 'block' : 'none';
    });
  }
  showSection('home'); // default view

  // Sample Products Data (can be expanded)
  const products = [
    { id:1, name: "Smartphone X1", price: 15999, image: "https://fdn2.gsmarena.com/vv/pics/samsung/samsung-galaxy-m33-1.jpg"},
    { id:2, name: "Wireless Earbuds", price: 2999, image: "https://www.boat-lifestyle.com/cdn/shop/files/ACCG6DS7WDJHGWSH_0.png?v=1727669669" },
    { id:3, name: "Smartwatch Z3", price: 6999, image: "https://m.media-amazon.com/images/I/61-OGVGPEJL.jpg" },
    { id:4, name: "Laptop Pro 15", price: 58999, image: "https://images.unsplash.com/photo-1618424181497-157f25b6ddd5?ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8bGFwdG9wJTIwY29tcHV0ZXJ8ZW58MHx8MHx8fDA%3D&fm=jpg&q=60&w=3000" },
    { id:5, name: "Gaming Mouse G7", price: 1499, image: "https://m.media-amazon.com/images/I/61Ahjsi1iOL.jpg" },
    { id:6, name: "Bluetooth Speaker", price: 3999, image: "https://www.boat-lifestyle.com/cdn/shop/files/Stone_SpinXPro_1_b3503890-50f6-4cd1-9138-0bd90874391e_1300x.png?v=1709717442" },
    { id:7, name: "4K Monitor 24\"", price: 12999, image: "https://rukminim2.flixcart.com/image/480/640/l4oi4cw0/monitor/b/7/g/ls27b800pxwxxl-4k-ultra-hd-24-ls27b800pxwxxl-samsung-original-imagfgvdkqu5fubb.jpeg?q=20" },
    { id:8, name: "External HDD 2TB", price: 5799, image: "https://d2j6dbq0eux0bg.cloudfront.net/images/1107006/585164883.jpg" },
    { id:9, name: "Mechanical Keyboard", price: 4499, image: "https://www.thevaluestore.in/image/cache/catalog/2024/Zebronics/Keyboard/zeb-nitro-plus-1-1000x1000.jpeg" }
      ];

  // Populate Products Grid
  const productGrid = document.getElementById('productGrid');
  products.forEach(product => {
    const card = document.createElement('div');
    card.className = 'product-card';
    card.innerHTML = `
      <img src="${product.image}" alt="${product.name}"/>
      <div class="product-name">${product.name}</div>
      <div class="product-price">₹${product.price.toLocaleString()}</div>
      <button class="btn" onclick="addToWishlist(${product.id})">Add to Wishlist</button>
      <button class="btn" style="margin-top:6px; background:#28a745;" onclick="placeOrder(${product.id})">Order Now</button>
    `;
    productGrid.appendChild(card);
  });

  // Wishlist logic
  let wishlist = [];
  function addToWishlist(productId) {
    if (!wishlist.includes(productId)) {
      wishlist.push(productId);
      updateWishlist();
      alert("Added to Wishlist!");
    } else {
      alert("Item already in Wishlist.");
    }
  }
  function updateWishlist() {
    const list = document.getElementById('wishlistList');
    list.innerHTML = wishlist.length === 0 ? '<li>No items in your wishlist yet.</li>' : '';
    wishlist.forEach(id => {
      const product = products.find(p => p.id === id);
      const li = document.createElement('li');
      li.textContent = product.name + " - ₹" + product.price.toLocaleString();
      list.appendChild(li);
    });
  }

  // Orders logic
  let orders = [];
  function placeOrder(productId) {
    orders.push(productId);
    updateOrders();
    alert("Thank you for your order!");
  }
  function updateOrders() {
    const list = document.getElementById('ordersList');
    list.innerHTML = orders.length === 0 ? '<li>You haven\'t placed any orders yet.</li>' : '';
    orders.forEach(id => {
      const product = products.find(p => p.id === id);
      const li = document.createElement('li');
      li.textContent = product.name + " - ₹" + product.price.toLocaleString();
      list.appendChild(li);
    });
  }

  // Comments & Reviews logic
  const commentForm = document.getElementById('commentForm');
  const commentsList = document.getElementById('commentsList');
  commentForm.addEventListener('submit', e => {
    e.preventDefault();
    const commentInput = document.getElementById('commentInput');
    const val = commentInput.value.trim();
    if(val) {
      const li = document.createElement('li');
      li.textContent = val;
      commentsList.appendChild(li);
      commentInput.value = '';
    }
  });

  // Registration validation
  const registerForm = document.getElementById('registerForm');
  registerForm.addEventListener('submit', e => {
    e.preventDefault();
    clearRegisterErrors();
    let valid = true;
    const name = document.getElementById('regName').value.trim();
    const email = document.getElementById('regEmail').value.trim();
    const password = document.getElementById('regPassword').value;

    if(name.length < 3){
      showError('regNameError', 'Name must be at least 3 characters');
      valid = false;
    }
    if (!validateEmail(email)) {
      showError('regEmailError','Invalid email format');
      valid = false;
    }
    if(password.length < 6){
      showError('regPasswordError','Password must be at least 6 characters');
      valid = false;
    }
    if(valid){
      alert('Registration successful!');
      registerForm.reset();
    }
  });
  function clearRegisterErrors(){
    ['regNameError', 'regEmailError', 'regPasswordError'].forEach(id => document.getElementById(id).innerText = '');
  }

  // Login validation  
  const loginForm = document.getElementById('loginForm');
  loginForm.addEventListener('submit', e => {
    e.preventDefault();
    clearLoginErrors();
    let valid = true;
    const email = document.getElementById('loginEmail').value.trim();
    const password = document.getElementById('loginPassword').value;
    if (!validateEmail(email)) {
      showError('loginEmailError','Invalid email format');
      valid = false;
    }
    if(password.length < 6){
      showError('loginPasswordError','Password must be at least 6 characters');
      valid = false;
    }
    if(valid){
      alert('Login successful!');
      loginForm.reset();
    }
  });
  function clearLoginErrors(){
    ['loginEmailError','loginPasswordError'].forEach(id => document.getElementById(id).innerText = '');
  }

  // Helper functions
  function validateEmail(email) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email.toLowerCase());
  }
  function showError(id, message){
    document.getElementById(id).innerText = message;
  }

</script>
</body>
</html>

