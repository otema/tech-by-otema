[index.html.txt](https://github.com/user-attachments/files/27640022/index.html.txt)
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TECHLAB</title>

<!-- FONTS -->
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans&display=swap" rel="stylesheet">

<style>
/* GLOBAL */
body {
  margin: 0;
  background: #0a0a0a;
  color: white;
  font-family: 'DM Sans', sans-serif;
}

/* NAV */
.nav {
  display: flex;
  justify-content: space-between;
  padding: 15px 30px;
  background: #111;
  position: sticky;
  top: 0;
}

.nav h1 {
  font-family: 'Bebas Neue';
  letter-spacing: 2px;
}

.nav ul {
  display: flex;
  list-style: none;
  gap: 20px;
}

/* HERO */
.hero {
  text-align: center;
  padding: 100px 20px;
}

.hero h1 {
  font-size: 60px;
  font-family: 'Bebas Neue';
}

.hero p {
  color: #aaa;
}

/* FILTER */
.filter {
  text-align: center;
}

button {
  background: #e8ff35;
  border: none;
  padding: 10px 15px;
  margin: 5px;
  cursor: pointer;
  font-weight: bold;
}

/* GRID */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  padding: 20px;
  gap: 20px;
}

/* CARD */
.card {
  background: #111;
  padding: 20px;
  border-radius: 10px;
  transition: 0.3s;
}

.card:hover {
  transform: scale(1.05);
}

/* FOOTER */
footer {
  text-align: center;
  padding: 20px;
  background: #111;
  margin-top: 30px;
}

/* ANIMATION */
.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: 0.6s;
}
.reveal.active {
  opacity: 1;
  transform: translateY(0);
}

/* MOBILE */
@media (max-width: 600px) {
  .hero h1 {
    font-size: 40px;
  }
}
</style>
</head>

<body>

<!-- NAV -->
<nav class="nav">
  <h1>TECHLAB</h1>
  <ul>
    <li>Home</li>
    <li>Reviews</li>
    <li>Compare</li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero reveal">
  <h1>Future Tech Reviews</h1>
  <p>Phones • Laptops • Gadgets</p>
</section>

<!-- FILTER -->
<section class="filter reveal">
  <button onclick="filterBrand('all')">All</button>
  <button onclick="filterBrand('apple')">Apple</button>
  <button onclick="filterBrand('samsung')">Samsung</button>
  <button onclick="filterBrand('google')">Google</button>
</section>

<!-- PRODUCTS -->
<section class="grid">

  <div class="card apple reveal">
    <h2>iPhone 15</h2>
    <p>Score: 9.2</p>
    <p>$999</p>
  </div>

  <div class="card samsung reveal">
    <h2>Galaxy S24</h2>
    <p>Score: 9.0</p>
    <p>$899</p>
  </div>

  <div class="card google reveal">
    <h2>Pixel 9</h2>
    <p>Score: 8.8</p>
    <p>$799</p>
  </div>

  <div class="card apple reveal">
    <h2>MacBook Pro</h2>
    <p>Score: 9.5</p>
    <p>$1999</p>
  </div>

</section>

<!-- FOOTER -->
<footer>
  <p>© 2026 TECHLAB | Tech Reviews Website</p>
</footer>

<script>
// FILTER
function filterBrand(brand) {
  let cards = document.querySelectorAll('.card');

  cards.forEach(card => {
    if (brand === 'all' || card.classList.contains(brand)) {
      card.style.display = 'block';
    } else {
      card.style.display = 'none';
    }
  });
}

// SCROLL ANIMATION
function reveal() {
  let reveals = document.querySelectorAll('.reveal');

  reveals.forEach(el => {
    let windowHeight = window.innerHeight;
    let top = el.getBoundingClientRect().top;

    if (top < windowHeight - 50) {
      el.classList.add('active');
    }
  });
}

window.addEventListener('scroll', reveal);
reveal();
</script>

</body>
</html>
