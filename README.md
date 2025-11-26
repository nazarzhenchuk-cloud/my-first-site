<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CityCarWash – Резервації</title>
<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f2f2f2;
  color: #222;
  transition: background 0.3s, color 0.3s;
}
/* HEADER */
header {
  background: #000;
  padding: 30px 20px;
  text-align: center;
  color: #fff;
}
header img {
  height: 110px;
  margin-bottom: 10px;
}
header h1 {
  margin: 0;
  font-size: 2.4rem;
}
header p {
  color: #ff002b;
  font-weight: bold;
  text-shadow: 0 0 10px rgba(255,0,50,0.4);
}

/* Кнопка теми */
#themeBtn {
  position: fixed;
  top: 10px;
  right: 10px;
  z-index: 1001;
  padding: 8px 12px;
  border-radius: 6px;
  background: #ff002b;
  color: #fff;
  font-weight: 900;
  cursor: pointer;
}
#themeBtn:hover { background: #d10081; }

/* Секції */
.section {
  background: #fff;
  width: 90%;
  max-width: 900px;
  margin: 25px auto;
  padding: 25px;
  border-radius: 15px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.15);
  transition: background 0.3s, color 0.3s;
}
.section h2 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 1.8rem;
  color: #ff002b;
  border-bottom: 2px solid #ff002b;
  padding-bottom: 8px;
  font-weight: 900;
}

/* Таблиці прайсу */
.price-table {
  width: 100%;
  border-collapse: collapse;
  background: #000;
}
.price-table th, .price-table td {
  padding: 12px;
  text-align: center;
  color: white;
}
.price-table th {
  font-weight: 900;
}
.price-table th:nth-child(n+2) {
  color: #d10081;
}

/* Форма */
label {
  font-weight: bold;
  margin-top: 10px;
  display: block;
}
input, select, textarea {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  border-radius: 8px;
  border: 2px solid #ccc;
}
button {
  width: 100%;
  padding: 14px;
  margin-top: 20px;
  background: linear-gradient(90deg,#ff002b,#d10081);
  color: #fff;
  border: none;
  font-weight: 900;
  cursor: pointer;
  font-size: 1.2rem;
}
button:hover { background: linear-gradient(90deg,#d10081,#ff002b); }
#successMessage {
  display: none;
  margin-top: 15px;
  background: #2ecc71;
  color: #fff;
  padding: 15px;
  border-radius: 10px;
  text-align: center;
}

/* Меню праве */
#sideMenuBtn {
  position: fixed;
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  background: #ff002b;
  color: #fff;
  padding: 12px 16px;
  cursor: pointer;
  font-weight: 900;
  border-radius: 8px 0 0 8px;
  z-index: 1000;
}
#sideMenuBtn:hover { background: #d10081; }

#sideMenu {
  position: fixed;
  top: 0;
  right: -100%;
  width: 300px;
  height: 100%;
  background: #000;
  color: white;
  padding: 20px;
  box-shadow: -4px 0 15px rgba(0,0,0,0.3);
  transition: right 0.3s;
  z-index: 999;
  overflow-y: auto;
}
#sideMenuClose {
  cursor: pointer;
  text-align: right;
  color: #ff002b;
  font-size: 1.2rem;
  margin-bottom: 20px;
}
#sideMenu a {
  display: block;
  color: #fff;
  text-decoration: none;
  margin: 10px 0;
  padding: 8px;
  border-radius: 5px;
}
#sideMenu a:hover { background: #ff002b; }

/* Відгуки */
.review {
  background: #000;
  color: #fff;
  padding: 15px;
  border-radius: 10px;
  margin: 10px 0;
}

/* Темна тема */
body.dark { background:#121212; color:#eee; }
body.dark .section { background:#1e1e1e; color:#fff; }
body.dark input, body.dark select, body.dark textarea { background:#333; color:#fff; border-color:#555; }
body.dark .price-table td, body.dark .price-table th { background:#111; color:#eee; }

/* Знижки */
.discount-banner {
  background: #ff002b;
  color: #fff;
  text-align: center;
  font-weight: 900;
  padding: 12px;
  border-radius: 12px;
  margin: 20px auto;
  max-width: 900px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  font-size: 1.2rem;
}
.discount-banner span { font-size:1.3rem; }

/* FAQ */
.faq-item { margin-bottom:15px; }
.faq-item p { margin:5px 0 0 0; }

/* Подарункові сертифікати */
#gift-cards .choose-us div {
  background: #000;
  color: #fff;
  padding: 15px;
  border-radius: 12px;
  margin: 10px 0;
}
#gift-cards .choose-us span { display:block; color:#d10081; font-weight:600; margin-top:5px; }
</style>
</head>
<body>

<header>
  <img src="https://i.imgur.com/0fG0Pjc.png" alt="Logo">
  <h1>CityCarWash – Prešov</h1>
  <p>Преміальна ручна автомийка</p>
</header>

<div id="themeBtn">🌓</div>

<!-- Знижки -->
<div class="discount-banner" id="discountBanner">
25-30 листопада – знижки до <span>20%</span> на всі послуги!
</div>

<!-- Прайс -->
<div class="section" id="prices">
<h2>Прайс-лист</h2>
<table class="price-table">
<tr><th>Послуга</th><th>Мале</th><th>Середнє</th><th>Велике</th><th>Van</th></tr>
<tr><td>Екстер’єр</td><td>18,90€</td><td>21,90€</td><td>22,90€</td><td>29,90€</td></tr>
<tr><td>Інтер’єр</td><td>19,90€</td><td>22,90€</td><td>24,90€</td><td>29,90€</td></tr>
<tr><td>Комплет</td><td>34,90€</td><td>37,90€</td><td>39,90€</td><td>59,90€</td></tr>
<tr><td>Tepovanie сидінь</td><td>69,90€</td><td>74,90€</td><td>79,90€</td><td>119,90€</td></tr>
<tr><td>Tepovanie комплет</td><td>89,90€</td><td>94,90€</td><td>99,90€</td><td>149,90€</td></tr>
<tr><td>Clay Bar</td><td>69,90€</td><td>79,90€</td><td>89,90€</td><td>99,90€</td></tr>
</table>
</div>

<!-- Форма -->
<div class="section" id="booking">
<h2>Забронювати мийку</h2>
<form id="washForm">
<label>Ім'я</label>
<input id="name" required>
<label>Телефон</label>
<input id="phone" required>
<label>Розмір авто</label>
<select id="carSize" required>
<option value="small">Мале</option>
<option value="medium">Середнє</option>
<option value="large">Велике</option>
<option value="van">Van</option>
</select>
<label>Послуга</label>
<select id="serviceType" required>
<option value="exterior">Екстер’єр</option>
<option value="interior">Інтер’єр</option>
<option value="full">Комплет</option>
<option value="tepsits">Tepovanie сидінь</option>
<option value="tepfull">Tepovanie комплет</option>
<option value="clay">Clay Bar</option>
</select>
<p id="dynamicPrice" style="font-weight:bold; margin-top:10px; font-size:1.2rem;">Ціна: –</p>
<label>Дата та час</label>
<input type="datetime-local" id="date" required>
<label>Коментар</label>
<textarea id="comment"></textarea>
<button type="submit">Відправити</button>
<div id="successMessage">Заявку відправлено!</div>
</form>
</div>

<!-- FAQ -->
<div class="section" id="faq">
<h2>FAQ</h2>
<div class="faq-item"><strong>Години роботи?</strong><p>9:00 – 21:00 щодня</p></div>
<div class="faq-item"><strong>Коли можна записатись?</strong><p>В будь-який час</p></div>
<div class="faq-item"><strong>Оплата?</strong><p>Готівка, безготівка або подарунковий сертифікат</p></div>
<div class="faq-item"><strong>Якість мийки?</strong><p>Використовуємо тільки сертифіковану хімію від авторизованих представників у Словаччині (KochChemie, Mafra) та безпечні миючі засоби. Приходьте, а не приїжджайте!</p></div>
</div>

<!-- Подарункові сертифікати -->
<div class="section" id="gift-cards">
<h2>Подарункові сертифікати</h2>
<div class="choose-us">
  <div>Універсальні<span>Обирайте будь-яку послугу та будь-який розмір авто</span></div>
  <div>Дійсні 3 місяці<span>Сертифікат можна використати протягом 3 місяців з моменту покупки</span></div>
  <div>Ідеальний подарунок<span>Подаруйте чистоту та комфорт вашим близьким</span></div>
</div>
</div>

<!-- Відгуки -->
<div class="section" id="reviews">
<h2>Відгуки клієнтів</h2>
<div class="review">⭐️⭐️⭐️⭐️⭐️ «Дуже задоволений! Машина блищить як нова» – Андрій</div>
<div class="review">⭐️⭐️⭐️⭐️⭐️ «Швидко і якісно. Рекомендую всім» – Олена</div>
<div class="review">⭐️⭐️⭐️⭐️⭐️ «Професійна мийка, приємні ціни» – Ігор</div>
</div>

<!-- Локація -->
<div class="section" id="location">
<h2>Локація</h2>
<iframe src="https://maps.google.com/maps?q=Novum%20Pre%C5%A1ov&t=&z=15&ie=UTF8&iwloc=&output=embed"
width="100%" height="300" style="border:0; border-radius:12px;" loading="lazy"></iframe>
<a class="navigate-btn" href="https://www.google.com/maps/dir/?api=1&destination=OC+Novum+Presov" target="_blank">📍 Прокласти маршрут</a>
</div>

<!-- Меню -->
<div id="sideMenuBtn">Меню ☰</div>
<div id="sideMenu">
<span id="sideMenuClose">✖ Закрити</span>
<a href="#prices">Ціни</a>
<a href="#booking">Записатись</a>
<a href="#faq">FAQ</a>
<a href="#gift-cards">Подарункові сертифікати</a>
<a href="#reviews">Відгуки</a>
<a href="#location">Локація</a>
</div>

<script>
// Динамічний прайс + знижка
const prices = {
  exterior: { small:18.90, medium:21.90, large:22.90, van:29.90 },
  interior: { small:19.90, medium:22.90, large:24.90, van:29.90 },
  full: { small:34.90, medium:37.90, large:39.90, van:59.90 },
  tepsits: { small:69.90, medium:74.90, large:79.90, van:119.90 },
  tepfull: { small:89.90, medium:94.90, large:99.90, van:149.90 },
  clay: { small:69.90, medium:79.90, large:89.90, van:99.90 }
};

const serviceType = document.getElementById("serviceType");
const carSize = document.getElementById("carSize");
const priceDisplay = document.getElementById("dynamicPrice");

function isDiscountPeriod() {
  const now = new Date();
  const month = now.getMonth(); // 0-11
  const date = now.getDate();
  return month === 10 && date >= 25 && date <= 30; // Листопад 25-30
}

function updatePrice(){
  const s = serviceType.value;
  const c = carSize.value;
  let price = prices[s][c];
  if(isDiscountPeriod()) price *= 0.8; // -20%
  priceDisplay.textContent = "Ціна: " + price.toFixed(2) + "€" + (isDiscountPeriod()?" (знижка 20%)":"");
}
serviceType.addEventListener("change", updatePrice);
carSize.addEventListener("change", updatePrice);
updatePrice();

// Форма
const BOT_TOKEN = "8390723540:AAG5goKKUr6ZZrmUhbCqQtUJtslNf_pK-rA";
const CHAT_ID = "814894513";
const TG_URL = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;

document.getElementById("washForm").addEventListener("submit", function(e){
  e.preventDefault();
  const priceText = priceDisplay.textContent;
  const msg = `🔥 *Нове бронювання*\n👤 Ім’я: ${name.value}\n📞 Телефон: ${phone.value}\n🚘 Розмір авто: ${carSize.value}\n✨ Послуга: ${serviceType.value}\n📅 Дата: ${date.value}\n💬 Коментар: ${comment.value||"-"}\n💰 ${priceText}`;
  fetch(TG_URL,{
    method:"POST",
    headers:{"Content-Type":"application/json"},
    body:JSON.stringify({chat_id:CHAT_ID,text:msg,parse_mode:"Markdown"})
  }).then(()=>{
    document.getElementById("successMessage").style.display="block";
    document.getElementById("washForm").reset();
    updatePrice();
  });
});

// Меню
const menuBtn = document.getElementById("sideMenuBtn");
const sideMenu = document.getElementById("sideMenu");
const closeBtn = document.getElementById("sideMenuClose");
menuBtn.addEventListener("click", ()=>sideMenu.style.right="0");
closeBtn.addEventListener("click", ()=>sideMenu.style.right="-100%");

// Тема
const themeBtn = document.getElementById("themeBtn");
themeBtn.addEventListener("click", ()=>document.body.classList.toggle("dark"));

// Мінімальна дата
const today = new Date().toISOString().split('T')[0];
document.getElementById("date").setAttribute('min', today);
</script>
</body>
</html>
