<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KiraSTORE - Zapatillas y Ropa Deportiva</title>
<style>
body{font-family:Arial;margin:0;background:#111;color:#fff}
header{background:#000;padding:20px;text-align:center}
h1{margin:0}
.container{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px;padding:20px}
.card{background:#1c1c1c;padding:15px;border-radius:10px;text-align:center}
.card img{width:100%;border-radius:10px}
button{background:#00c853;color:#fff;border:none;padding:10px 15px;border-radius:5px;cursor:pointer}
button:hover{background:#00a844}
#cart{position:fixed;right:0;top:0;background:#000;width:300px;height:100%;padding:20px;overflow:auto}
#cart h2{text-align:center}
.cart-item{border-bottom:1px solid #333;padding:10px 0}
.total{font-size:20px;margin-top:10px}
</style>
</head>
<body>

<header>
<h1>KiraSTORE</h1>
<p>Zapatillas y Ropa Deportiva</p>
</header>

<div class="container">

<div class="card">
<img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff">
<h3>Nike Air Force 1</h3>
<p>$120000</p>
<button onclick="addToCart('Nike Air Force 1',120000)">Agregar al carrito</button>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1600185365483-26d7a4cc7519">
<h3>Adidas Superstar</h3>
<p>$110000</p>
<button onclick="addToCart('Adidas Superstar',110000)">Agregar al carrito</button>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1595950653106-6c9ebd614d3a">
<h3>Puma RS-X</h3>
<p>$100000</p>
<button onclick="addToCart('Puma RS-X',100000)">Agregar al carrito</button>
</div>

</div>

<div id="cart">
<h2>Carrito</h2>
<div id="cart-items"></div>
<div class="total">Total: $<span id="total">0</span></div>
</div>

<script>
let cart=[];

function addToCart(name,price){
cart.push({name,price});
renderCart();
}

function renderCart(){
const cartItems=document.getElementById('cart-items');
cartItems.innerHTML='';
let total=0;

cart.forEach(item=>{
const div=document.createElement('div');
div.className='cart-item';
div.innerHTML=`${item.name} - $${item.price}`;
cartItems.appendChild(div);

total+=item.price;
});

document.getElementById('total').textContent=total;
}
</script>

</body>
</html>
