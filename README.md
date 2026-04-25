# Bista-Natural-sweetness-
# Bista Natural Sweetness is A trusted jaggery and Sugarcane Farm. 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bista Natural Farm - Ultra Pro</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Poppins,sans-serif}
body{
background:linear-gradient(135deg,#e8f5e9,#c8e6c9);
color:#222;
scroll-behavior:smooth;
}

/* NAV */
nav{
position:fixed;top:0;width:100%;
display:flex;justify-content:space-between;align-items:center;
padding:15px 40px;
background:rgba(0,0,0,0.6);
backdrop-filter:blur(10px);
color:#fff;
z-index:1000;
animation:navDown 0.8s ease;
}
nav a{color:#fff;margin-left:20px;text-decoration:none;transition:.3s}
nav a:hover{color:#00e676}

/* HERO */
.hero{
height:100vh;
background:linear-gradient(rgba(0,0,0,.6),rgba(0,0,0,.6)),
url('https://images.unsplash.com/photo-1501004318641-b39e6451bec6') center/cover;
display:flex;align-items:center;justify-content:center;text-align:center;color:white;
}
.hero h1{
font-size:60px;
animation:zoomIn 1s ease;
}
.hero p{margin:15px 0;font-size:18px}

/* BUTTON */
.btn{
padding:12px 25px;
background:linear-gradient(45deg,#00c853,#64dd17);
border:none;border-radius:30px;
color:white;cursor:pointer;
transition:.3s;
position:relative;overflow:hidden;
}
.btn:hover{
transform:scale(1.1);
box-shadow:0 10px 25px rgba(0,0,0,0.3);
}
.btn::after{
content:"";
position:absolute;
width:0;height:0;
background:rgba(255,255,255,0.4);
border-radius:50%;
top:50%;left:50%;
transform:translate(-50%,-50%);
transition:.5s;
}
.btn:active::after{
width:300px;height:300px;
opacity:0;
}

/* SECTION */
.section,.cart,.order,.about{
padding:100px 20px;
text-align:center;
opacity:0;
transform:translateY(40px);
transition:all 0.8s ease;
}
.show{opacity:1;transform:translateY(0)}

/* PRODUCTS */
.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;margin-top:40px;
}
.card{
background:rgba(255,255,255,0.7);
backdrop-filter:blur(10px);
border-radius:20px;
overflow:hidden;
box-shadow:0 10px 25px rgba(0,0,0,0.15);
transition:.4s;
animation:floatCard 4s infinite ease-in-out;
}
.card:hover{
transform:translateY(-15px) scale(1.03);
box-shadow:0 20px 40px rgba(0,200,83,0.4);
}
.card img{width:100%;height:220px;object-fit:cover}
.card h3{padding:10px}

/* CART / ORDER */
.cart,.order,.about{
background:white;
margin:30px;
padding:25px;
border-radius:20px;
box-shadow:0 10px 30px rgba(0,0,0,0.2);
}

input,select{
width:80%;padding:12px;margin:10px;
border-radius:10px;border:1px solid #ccc;
}

/* WHATSAPP */
.whatsapp{
position:fixed;bottom:20px;right:20px;
background:#25D366;color:white;
padding:18px;border-radius:50%;
font-size:20px;
animation:float 2s infinite;
}

/* ABOUT */
.about-box{line-height:1.7}
.highlight{color:#00c853;font-weight:600}

/* FOOTER */
footer{
text-align:center;padding:20px;background:#111;color:white;
animation:fadeUp 1.5s ease;
}

/* ANIMATIONS */
@keyframes fadeUp{
from{opacity:0;transform:translateY(30px)}
to{opacity:1;transform:translateY(0)}
}
@keyframes navDown{
from{transform:translateY(-100%)}
to{transform:translateY(0)}
}
@keyframes zoomIn{
from{transform:scale(0.8);opacity:0}
to{transform:scale(1);opacity:1}
}
@keyframes float{
0%,100%{transform:translateY(0)}
50%{transform:translateY(-10px)}
}
@keyframes floatCard{
0%,100%{transform:translateY(0)}
50%{transform:translateY(-8px)}
}
</style>
</head>

<body>

<nav>
<h2>🌿 Bista Farm</h2>
<div>
<a href="#">Home</a>
<a href="#products">Products</a>
<a href="#cart">Cart</a>
<a href="#order">Order</a>
<a href="#about">About</a>
</div>
</nav>

<div class="hero">
<div>
<h1>Organic Farm Business</h1>
<p>Pure • Natural • Trusted • 30 Years Experience</p>
<a href="#products"><button class="btn">Explore Products</button></a>
</div>
</div>

<section class="section" id="products">
<h2>Our Products</h2>

<div class="products">

<div class="card">
<img src="https://images.unsplash.com/photo-1501004318641-b39e6451bec6">
<h3>Sugarcane - Rs 50</h3>
<button class="btn" onclick="add('Sugarcane',50)">🛒 Add</button>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1615485737459-8a2c81394b1e">
<h3>Jaggery - Rs 120</h3>
<button class="btn" onclick="add('Jaggery',120)">🛒 Add</button>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1604908177079-3fd36bbdbb6c">
<h3>Powder - Rs 110</h3>
<button class="btn" onclick="add('Powder',110)">🛒 Add</button>
</div>

</div>
</section>

<section id="cart" class="cart">
<h2>🛒 Cart</h2>
<div id="cartItems">Cart is empty</div>
<h3 id="total">Total Rs 0</h3>
</section>

<section id="order" class="order">
<h2>Order Now</h2>

<form onsubmit="sendOrder(event)">
<input id="name" placeholder="Name" required><br>
<input id="phone" placeholder="Phone" required><br>

<select id="payment">
<option>Cash</option>
<option>eSewa</option>
<option>Khalti</option>
</select><br>

<button class="btn">Place Order</button>
</form>
</section>

<section id="about" class="about">
<div class="about-box">
<h2>👨‍🌾 About Owner</h2>

<p>Welcome to <span class="highlight">Bista Natural Farm</span> — with <span class="highlight">30 years experience</span>.</p>

<p>📍 500 meters straight from Parashuram Municipality-08, Jamarani Bazar, Dadeldhura</p>

<p>🤝 Meet owner at <span class="highlight">Sudip Liquor Shop, Jamarani Bazar</span></p>

<p>🌿 Pure organic farming for healthy future</p>
</div>
</section>

<footer>© 2026 Bista Natural Farm</footer>

<a class="whatsapp" href="https://wa.me/9779865988080" target="_blank">💬</a>

<script>

// SCROLL ANIMATION
const observer=new IntersectionObserver(entries=>{
entries.forEach(entry=>{
if(entry.isIntersecting){
entry.target.classList.add("show");
}
});
},{threshold:0.2});

document.querySelectorAll(".section,.cart,.order,.about")
.forEach(el=>observer.observe(el));

// CART SYSTEM
let cart={};

function add(name,price){
if(cart[name]) cart[name].qty++;
else cart[name]={price:price,qty:1};
renderCart();
}

function renderCart(){
let html="";let total=0;

for(let item in cart){
let c=cart[item];
let sum=c.price*c.qty;
total+=sum;

html+=`
<div style="padding:10px;border-bottom:1px solid #ccc">
<b>${item}</b><br>
${c.qty} × Rs ${c.price} = <span style="color:#00c853">Rs ${sum}</span><br>
<button onclick="changeQty('${item}',-1)">➖</button>
<button onclick="changeQty('${item}',1)">➕</button>
</div>
`;
}

document.getElementById("cartItems").innerHTML=html||"Cart is empty";
document.getElementById("total").innerText="Total Rs "+total;
}

function changeQty(name,val){
cart[name].qty+=val;
if(cart[name].qty<=0) delete cart[name];
renderCart();
}

function sendOrder(e){
e.preventDefault();

let name=document.getElementById("name").value;
let phone=document.getElementById("phone").value;
let payment=document.getElementById("payment").value;

let msg=`Order:%0AName:${name}%0APhone:${phone}%0APayment:${payment}%0A`;

for(let item in cart){
let c=cart[item];
msg+=`${item} - ${c.qty} pcs = Rs ${c.price*c.qty}%0A`;
}

window.open("https://wa.me/9779865988080?text="+msg);

cart={};
renderCart();
}

</script>

</body>
</html>
