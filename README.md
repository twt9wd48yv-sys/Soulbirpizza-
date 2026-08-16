<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>SOULBIR — Сол бір пицца</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,500;1,500&display=swap');

:root{
--green:#244936;
--dark:#182f22;
--cream:#f5f1e7;
--card:#fffdf8;
--text:#18221c;
--gray:#747a74;
}

*{box-sizing:border-box;margin:0;padding:0}

body{
background:#dce4dc;
font-family:"DM Sans",sans-serif;
color:var(--text)
}

.site{
max-width:600px;
margin:auto;
background:var(--cream);
min-height:100vh
}

header{
height:70px;
padding:14px 20px;
display:flex;
align-items:center;
justify-content:space-between;
position:sticky;
top:0;
z-index:20;
background:rgba(245,241,231,.94);
backdrop-filter:blur(15px)
}

.logo strong{font-size:21px}
.logo small{
display:block;
font-size:8px;
letter-spacing:2px;
color:var(--gray)
}

.cartBtn{
border:0;
background:var(--green);
color:white;
padding:11px 17px;
border-radius:30px;
font-size:15px;
cursor:pointer
}

.hero{
min-height:570px;
padding:30px 25px 50px;
display:flex;
align-items:flex-end;
color:white;
background:
linear-gradient(180deg,rgba(0,0,0,.1),rgba(0,0,0,.75)),
url("https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=1000&q=85");
background-size:cover;
background-position:center
}

.tag{
font-size:10px;
letter-spacing:2px
}

.hero h1{
font-size:68px;
line-height:.85;
letter-spacing:-5px;
margin:18px 0
}

.hero em{
font-family:"Playfair Display",serif;
font-weight:500
}

.hero p{
line-height:1.5;
margin-bottom:24px
}

.hero a{
display:inline-block;
background:white;
color:var(--green);
padding:14px 20px;
border-radius:30px;
text-decoration:none;
font-weight:600
}

.intro{padding:60px 22px 25px}

.intro span{
font-size:10px;
letter-spacing:2px;
color:var(--green)
}

.intro h2{
font-size:38px;
letter-spacing:-2px;
margin:7px 0
}

.intro p{
color:var(--gray);
line-height:1.5
}

.categories{
display:flex;
gap:8px;
overflow-x:auto;
padding:15px 20px 28px;
scrollbar-width:none
}

.categories::-webkit-scrollbar{display:none}

.category{
flex-shrink:0;
padding:11px 16px;
border:1px solid #ccd3ca;
background:transparent;
border-radius:30px;
font-family:inherit;
cursor:pointer
}

.category.active{
background:var(--green);
color:white;
border-color:var(--green)
}

.menu{padding:0 20px 70px}

.products{
display:flex;
flex-direction:column;
gap:18px
}

.product{
background:var(--card);
border-radius:24px;
padding:20px;
box-shadow:0 8px 25px rgba(30,50,35,.07);
animation:show .25s ease
}

@keyframes show{
from{opacity:0;transform:translateY(10px)}
to{opacity:1;transform:none}
}

.productIcon{
height:150px;
border-radius:18px;
background:linear-gradient(135deg,#dce5d9,#edf0e7);
display:flex;
align-items:center;
justify-content:center;
font-size:60px;
margin-bottom:18px
}

.productTop{
display:flex;
justify-content:space-between;
gap:10px
}

.product h3{font-size:21px}
.price{font-weight:700;white-space:nowrap}

.desc{
font-size:13px;
line-height:1.5;
color:var(--gray);
margin:8px 0 17px
}

.optionTitle{
font-size:11px;
color:var(--gray);
margin-bottom:7px
}

.options{
display:flex;
gap:7px;
overflow-x:auto;
margin-bottom:14px
}

.option{
flex-shrink:0;
padding:9px 13px;
border:1px solid #d1d6d0;
background:transparent;
border-radius:30px;
font-family:inherit;
cursor:pointer
}

.option.selected{
background:var(--green);
color:white
}

.add{
width:100%;
border:0;
padding:15px;
border-radius:30px;
background:var(--green);
color:white;
font-size:15px;
font-weight:600;
cursor:pointer
}

.about{
background:var(--green);
color:white;
padding:65px 25px
}

.about span{
font-size:10px;
letter-spacing:2px
}

.about h2{
font-size:42px;
line-height:.95;
margin:15px 0 25px;
letter-spacing:-2px
}

.about em{
font-family:"Playfair Display",serif
}

.about p{
opacity:.8;
line-height:1.5
}

footer{
background:var(--dark);
color:white;
padding:45px 25px
}

footer p{
opacity:.75;
margin-top:7px
}

.footerBtns{
display:flex;
gap:10px;
margin:25px 0
}

.footerBtns a{
color:white;
text-decoration:none;
border:1px solid rgba(255,255,255,.25);
padding:11px 15px;
border-radius:30px
}

.modal{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,.5);
z-index:100;
align-items:flex-end
}

.modal.open{display:flex}

.cart{
width:100%;
max-width:600px;
margin:auto;
background:var(--cream);
border-radius:28px 28px 0 0;
padding:28px 20px;
max-height:92vh;
overflow:auto;
position:relative
}

.close{
position:absolute;
right:18px;
top:15px;
width:38px;
height:38px;
border:0;
border-radius:50%;
font-size:22px;
cursor:pointer
}

.cart h2{
font-size:30px;
margin-bottom:22px
}

.cartItem{
background:white;
border-radius:16px;
padding:14px;
margin-bottom:9px;
display:flex;
justify-content:space-between;
gap:10px
}

.cartItem small{color:var(--gray)}

.qty{
display:flex;
align-items:center;
gap:7px;
margin-top:7px
}

.qty button{
width:28px;
height:28px;
border:0;
border-radius:50%;
background:#e6e9e3;
cursor:pointer
}

.remove{
border:0;
background:none;
cursor:pointer;
margin-left:5px
}

.total{
display:flex;
justify-content:space-between;
font-size:20px;
padding:20px 0;
border-bottom:1px solid #ddd8ce
}

.checkout{
padding-top:20px;
display:flex;
flex-direction:column;
gap:9px
}

.checkout input,
.checkout textarea{
width:100%;
border:0;
padding:15px;
border-radius:14px;
background:white;
font:inherit;
outline:none
}

.checkout textarea{
height:80px;
resize:none
}

.delivery{
display:flex;
gap:8px
}

.delivery button{
flex:1;
padding:13px 8px;
border:1px solid #ccd3ca;
background:transparent;
border-radius:14px;
font-family:inherit;
cursor:pointer
}

.delivery button.active{
background:var(--green);
color:white;
border-color:var(--green)
}

.order{
border:0;
padding:17px;
border-radius:30px;
background:var(--green);
color:white;
font-size:15px;
font-weight:600;
cursor:pointer;
margin-top:5px
}
</style>
</head>

<body>

<div class="site">

<header>
<div class="logo">
<strong>SOULBIR 🍕</strong>
<small>СОЛ БІР ПИЦЦА</small>
</div>

<button class="cartBtn" onclick="openCart()">
🛒 <span id="count">0</span>
</button>
</header>


<section class="hero">
<div>
<span class="tag">АСТАНА · PIZZA · COFFEE</span>

<h1>
Сол бір<br>
<em>пицца.</em>
</h1>

<p>
Те самые муж и жена.<br>
Пицца, кофе и завтраки.
</p>

<a href="#menu">Смотреть меню</a>
</div>
</section>


<section class="intro">
<span>OUR MENU</span>
<h2>Выбирай своё</h2>
<p>Пицца, завтраки, сэндвичи, кофе и напитки.</p>
</section>


<div class="categories">

<button class="category active" onclick="setCat('pizza',this)">🍕 Пицца</button>
<button class="category" onclick="setCat('breakfast',this)">🍳 Завтраки</button>
<button class="category" onclick="setCat('sandwich',this)">🥪 Сэндвичи</button>
<button class="category" onclick="setCat('coffee',this)">☕ Кофе</button>
<button class="category" onclick="setCat('drinks',this)">🥤 Напитки</button>
<button class="category" onclick="setCat('dessert',this)">🍰 Десерты</button>

</div>


<section id="menu" class="menu">
<div id="products" class="products"></div>
</section>


<section class="about">
<span>SOULBIR</span>

<h2>
Место,<br>
<em>куда хочется</em><br>
вернуться.
</h2>

<p>
Спокойная атмосфера, горячая пицца,
кофе и завтраки.
</p>
</section>


<footer>

<h2>SOULBIR</h2>

<p>Сол бір пицца Астанада</p>
<p>Те самые муж и жена ❤️</p>

<div class="footerBtns">

<a href="https://www.instagram.com/soulbirpizza/" target="_blank">
Instagram
</a>

<a href="https://wa.me/77479881805" target="_blank">
WhatsApp
</a>

</div>

<small>© 2026 Soulbir Pizza</small>

</footer>


<div id="modal" class="modal">

<div class="cart">

<button class="close" onclick="closeCart()">×</button>

<h2>Ваш заказ 🛒</h2>

<div id="cartItems"></div>

<div class="total">
<span>Итого</span>
<strong id="total">0 ₸</strong>
</div>


<div class="checkout">

<h3>Оформление</h3>

<input id="name" placeholder="Ваше имя">

<input id="phone" type="tel" placeholder="Номер телефона">


<div class="delivery">

<button id="deliveryBtn" class="active" onclick="setDelivery('delivery')">
🚗 Доставка
</button>

<button id="pickupBtn" onclick="setDelivery('pickup')">
🏠 Самовывоз
</button>

</div>


<div id="addressBox">
<input id="address" placeholder="Адрес доставки">
</div>


<textarea id="comment" placeholder="Комментарий к заказу"></textarea>


<button class="order" onclick="sendOrder()">
Заказать через WhatsApp →
</button>

</div>

</div>
</div>

</div>


<script>

const data={

pizza:[
["Пепперони","Томатный соус, моцарелла, пепперони, пармезан, базилик, оливковое масло.",3640,"🍕"],
["Маргарита Премиум","Томатный соус, моцарелла, пармезан, базилик, оливковое масло.",3840,"🍕"],
["Курица и грибы","Томатный соус, моцарелла, куриное филе, шампиньоны, пармезан, базилик, оливковое масло.",3940,"🍕"],
["Мортаделла и страчателла","Томатный соус, моцарелла, мортаделла, страчателла, пармезан, базилик, оливковое масло.",5290,"🍕"],
["Груша и сыр с плесенью","Моцарелла, груша, сыр с плесенью, пармезан, базилик, белый соус, оливковое масло.",null,"🍐"],
["Четыре сыра","Моцарелла, фета, сыр с плесенью, пармезан, белый соус, базилик, оливковое масло.",null,"🧀"],
["Курица Чили","Томатный соус, моцарелла, куриное филе, перец чили, красный лук, пармезан, базилик, оливковое масло.",3840,"🌶️"],
["Овощная","Томатный соус, моцарелла, сладкий перец, шампиньоны, красный лук, томаты, пармезан, базилик, оливковое масло.",3740,"🥬"],
["Карбонат и грибы","Томатный соус, моцарелла, карбонат из говядины, шампиньоны, пармезан, базилик, оливковое масло.",4040,"🍄"]
],

breakfast:[
["Завтрак с мортаделлой, фисташками и авокадо","Мортаделла с фисташками, авокадо, яйца, творожный крем, микс салата, томаты, оливковое масло.",3710,"🥑"],
["Завтрак с семгой и авокадо","Семга, авокадо, яйца, творожный крем, микс салата, томаты, оливковое масло.",3800,"🥑"],
["Завтрак с копченой говядиной и авокадо","Копченая говядина, авокадо, яйца, творожный крем, микс салата, томаты, оливковое масло.",3920,"🥑"],
["Дачный завтрак с колбасками","Колбаски, яйца, томаты, микс салата, сливочное масло, фирменная лепешка.",3790,"🍳"]
],

sandwich:[
["Сэндвич с мортаделлой и страчателлой","Хлеб, мортаделла, страчателла, рукола, томаты, базилик, оливковое масло.",3500,"🥪"],
["Сэндвич с курицей","Хлеб, куриное филе, творожный сыр, рукола, томаты, оливковое масло.",3000,"🥪"],
["Сэндвич с копченой говядиной","Хлеб, копченая говядина, творожный сыр, томаты, красный лук, рукола, оливковое масло.",4000,"🥪"],
["Сэндвич с семгой и авокадо","Хлеб, семга, авокадо, творожный сыр, рукола, стебулет, оливковое масло.",4000,"🥪"]
],

coffee:[
["Эспрессо","Классический эспрессо.",900,"☕"],
["Американо","Эспрессо с горячей водой.",1100,"☕"],
["Капучино","Эспрессо с молоком и нежной пенкой.",1300,"☕"],
["Латте","Эспрессо с большим количеством молока.",1400,"☕"],
["Флэт уайт","Крепкий кофе с бархатистым молоком.",1500,"☕"],
["Раф","Нежный сливочный кофейный напиток.",1600,"☕"],
["Какао","Горячий шоколадный напиток с молоком.",1400,"🍫"]
],

drinks:[
["Pepsi","Холодный газированный напиток.",700,"🥤"],
["Pepsi Max","Газированный напиток без сахара.",700,"🥤"],
["Mirinda","Апельсиновый газированный напиток.",700,"🥤"],
["7UP","Лимонно-лаймовый газированный напиток.",700,"🥤"],
["Вода без газа","Питьевая вода.",600,"💧"],
["Вода с газом","Газированная вода.",600,"💧"],
["Домашний лимонад","Освежающий домашний лимонад.",1400,"🍋"],
["Апельсиновый сок","Апельсиновый сок.",1400,"🍊"],
["Яблочный сок","Яблочный сок.",1400,"🍏"]
],

dessert:[
["Чизкейк","Нежный сливочный десерт.",1990,"🍰"],
["Тирамису","Классический итальянский десерт.",2190,"🍰"],
["Шоколадный десерт","Насыщенный шоколадный десерт.",1890,"🍫"]
]

};


let category="pizza";
let cart=[];
let delivery="delivery";


function money(n){
return n===null?"Уточнить":n.toLocaleString()+" ₸";
}


function setCat(cat,btn){

category=cat;

document.querySelectorAll(".category")
.forEach(x=>x.classList.remove("active"));

btn.classList.add("active");

render();

}


function render(){

const box=document.getElementById("products");

box.innerHTML="";

data[category].forEach((p,i)=>{

let price=p[2];

let options=[];

if(category==="pizza"){
options=[
["25 см",p[2]],
["30 см",p[2] ? p[2]+1000:null],
["35 см",p[2] ? p[2]+2000:null]
];
}else if(category==="coffee"){
options=[
["250 мл",p[2]],
["350 мл",p[2]+300]
];
}else{
options=[["Порция",p[2]]];
}


let selected=0;


const card=document.createElement("div");

card.className="product";

card.innerHTML=`

<div class="productIcon">${p[3]}</div>

<div class="productTop">
<h3>${p[0]}</h3>
<span class="price">${money(options[0][1])}</span>
</div>

<p class="desc">${p[1]}</p>

<div class="optionTitle">
${category==="pizza"?"Размер":category==="coffee"?"Объём":"Вариант"}
</div>

<div class="options">

${options.map((o,j)=>`
<button class="option ${j===0?"selected":""}" data-i="${j}">
${o[0]} · ${money(o[1])}
</button>
`).join("")}

</div>

<button class="add">
Добавить · <span>${money(options[0][1])}</span>
</button>

`;


const buttons=card.querySelectorAll(".option");
const priceEl=card.querySelector(".price");
const addPrice=card.querySelector(".add span");


buttons.forEach(b=>{

b.onclick=()=>{

buttons.forEach(x=>x.classList.remove("selected"));

b.classList.add("selected");

selected=Number(b.dataset.i);

price=options[selected][1];

priceEl.textContent=money(price);

addPrice.textContent=money(price);

};

});


card.querySelector(".add").onclick=()=>{

if(price===null){
alert("Цена этого блюда пока уточняется.");
return;
}

cart.push({
name:p[0],
option:options[selected][0],
price:price,
qty:1
});

updateCart();

};

box.appendChild(card);

});

}


function updateCart(){

document.getElementById("count").textContent=
cart.reduce((a,b)=>a+b.qty,0);

renderCart();

}


function renderCart(){

const box=document.getElementById("cartItems");

box.innerHTML="";

let total=0;

cart.forEach((item,i)=>{

total+=item.price*item.qty;

const div=document.createElement("div");

div.className="cartItem";

div.innerHTML=`

<div>

<strong>${item.name}</strong>

<br>

<small>${item.option}</small>

<div class="qty">

<button onclick="changeQty(${i},-1)">−</button>

<span>${item.qty}</span>

<button onclick="changeQty(${i},1)">+</button>

</div>

</div>

<div>

<strong>${money(item.price*item.qty)}</strong>

<button class="remove" onclick="removeItem(${i})">✕</button>

</div>

`;

box.appendChild(div);

});

document.getElementById("total").textContent=
money(total);

}


function changeQty(i,value){

cart[i].qty+=value;

if(cart[i].qty<=0){
cart.splice(i,1);
}

updateCart();

}


function removeItem(i){

cart.splice(i,1);

updateCart();

}


function openCart(){

document.getElementById("modal").classList.add("open");

}


function closeCart(){

document.getElementById("modal").classList.remove("open");

}


function setDelivery(type){

delivery=type;

document.getElementById("deliveryBtn")
.classList.toggle("active",type==="delivery");

document.getElementById("pickupBtn")
.classList.toggle("active",type==="pickup");

document.getElementById("addressBox").style.display=
type==="delivery"?"block":"none";

}


function sendOrder(){

if(!cart.length){
alert("Корзина пустая.");
return;
}


const name=document.getElementById("name").value.trim();

const phone=document.getElementById("phone").value.trim();

const address=document.getElementById("address").value.trim();

const comment=document.getElementById("comment").value.trim();


if(!name||!phone){

alert("Введите имя и номер телефона.");

return;

}


if(delivery==="delivery"&&!address){

alert("Введите адрес доставки.");

return;

}


let total=0;

let text="🍕 SOULBIR — НОВЫЙ ЗАКАЗ\n\n";


cart.forEach(item=>{

const sum=item.price*item.qty;

total+=sum;

text+=
`${item.name}\n`+
`${item.option} × ${item.qty} — ${sum.toLocaleString()} ₸\n\n`;

});


text+=`💰 Итого: ${total.toLocaleString()} ₸\n\n`;

text+=`👤 Имя: ${name}\n`;

text+=`📞 Телефон: ${phone}\n`;

text+=
delivery==="delivery"
?"🚗 Доставка\n"
:"🏠 Самовывоз\n";


if(delivery==="delivery"){
text+=`📍 Адрес: ${address}\n`;
}


if(comment){
text+=`💬 Комментарий: ${comment}\n`;
}


const whatsapp=
"https://wa.me/77479881805?text="+
encodeURIComponent(text);


window.open(whatsapp,"_blank");

}


render();
updateCart();

</script>

</body>
</html>
