<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ROM — Real Orders More | متجرك الذكي</title>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{--bg:#000;--bg-soft:#f5f5f7;--text:#1d1d1f;--text-soft:#86868b;--accent:#0071e3;--accent-hover:#0077ed;--radius:18px;--max:1200px;--danger:#ff375f;--success:#34c759}
html{scroll-behavior:smooth}
body{font-family:"SF Pro Display","Segoe UI",Tahoma,Arial,sans-serif;background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased;overflow-x:hidden}
a{text-decoration:none;color:inherit}
button{font-family:inherit;cursor:pointer;border:none;background:none}
img{max-width:100%;display:block}
input,select,textarea{font-family:inherit}

</style>
</head>
<body>

<!-- ============ STORE VIEW ============ -->
<div id="storeView">
<nav>
  <div class="nav-inner">
    <a href="#" class="logo">ROM</a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#home">الرئيسية</a></li>
      <li><a href="#products">المنتجات</a></li>
      <li><a href="#features">المميزات</a></li>
      <li><a href="#contact">تواصل</a></li>
    </ul>
    <div class="nav-icons">
      <button class="nav-icon" onclick="toggleSearch()" title="بحث">🔍</button>
      <button class="nav-icon" onclick="toggleCart(true)" title="السلة">🛒<span class="cart-badge" id="cartBadge">0</span></button>
      <button class="hamburger" onclick="document.getElementById('navLinks').classList.toggle('mobile-open')">☰</button>
    </div>
  </div>
</nav>
<div class="search-bar" id="searchBar">
  <input type="text" id="searchInput" placeholder="ابحث عن منتج..." oninput="renderProducts()">
</div>

<header class="hero" id="home">
  <h1>المستقبل بين يديك.</h1>
  <p>اكتشف أحدث الأجهزة والإلكترونيات بأفضل الأسعار. جودة عالمية، توصيل سريع، وضمان حقيقي.</p>
  <div class="hero-btns">
    <a href="#products" class="btn btn-primary">تسوق الآن</a>
    <a href="#features" class="btn btn-ghost">تعرف على المميزات</a>
  </div>
  <div class="hero-visual">🎧⌚💻</div>
</header>

<section id="products">
  <div class="container">
    <h2 class="section-title reveal">تسوق حسب الفئة</h2>
    <p class="section-sub reveal">اختر ما يناسبك من تشكيلتنا الواسعة</p>
    <div class="filters reveal" id="filters"></div>
    <div class="grid" id="productGrid"></div>
  </div>
</section>

<section id="features" class="band">
  <div class="container">
    <h2 class="section-title reveal">لماذا تختارنا؟</h2>
    <p class="section-sub reveal">نلتزم بتقديم أفضل تجربة تسوق</p>
    <div class="band-grid">
      <div class="band-card reveal"><div class="ic">🚚</div><h4>شحن سريع مجاني</h4><p>توصيل خلال 24-48 ساعة لجميع المدن دون رسوم إضافية.</p></div>
      <div class="band-card reveal"><div class="ic">🛡️</div><h4>ضمان سنتان</h4><p>ضمان شامل على جميع المنتجات مع إمكانية الاستبدال.</p></div>
      <div class="band-card reveal"><div class="ic">💳</div><h4>دفع آمن</h4><p>ادفع بأمان عبر مدى، Apple Pay، أو البطاقات البنكية.</p></div>
      <div class="band-card reveal"><div class="ic">🔄</div><h4>إرجاع مجاني</h4><p>غير راضٍ عن المنتج؟ أرجعه مجاناً خلال 30 يوماً.</p></div>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="footer-grid">
    <div>
      <h5 style="font-size:18px;font-weight:900;background:linear-gradient(135deg,#7d7aff,#0071e3);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent">ROM</h5>
      <p style="color:var(--text-soft);font-size:13px;line-height:1.7;margin-bottom:10px">Real Orders More.<br>طلبات حقيقية، مبيعات أكثر.</p>
    </div>
    <div><h5>تسوق</h5><a href="#products">الهواتف الذكية</a><a href="#products">اللابتوبات</a><a href="#products">السماعات</a><a href="#products">الساعات</a></div>
    <div><h5>خدمة العملاء</h5><a href="#">تتبع الطلب</a><a href="#">الشحن والتوصيل</a><a href="#">الإرجاع والاستبدال</a><a href="#">الأسئلة الشائعة</a></div>
    <div><h5>عن المتجر</h5><a href="#">من نحن</a><a href="#">الأخبار</a><a href="#" onclick="showAdminLogin();return false;">لوحة التحكم 🔐</a></div>
  </div>
  <div class="footer-bottom"><b style="color:var(--text)">ROM</b> — Real Orders More.<br>© 2026 ROM. جميع الحقوق محفوظة. | صُنع بشغف 🖤</div>
</footer>
</div>

<!-- ============ ADMIN LOGIN VIEW ============ -->
<div id="adminLoginView" class="admin-login hidden">
  <div class="login-box">
    <span class="logo">ROM</span>
    <p>لوحة تحكم المتجر — Real Orders More</p>
    <form onsubmit="adminLogin(event)">
      <div class="form-group"><label>اسم المستخدم</label><input id="adminUser" required placeholder="admin" autocomplete="username"></div>
      <div class="form-group"><label>كلمة المرور</label><input id="adminPass" type="password" required placeholder="••••••••" autocomplete="current-password"></div>
      <button class="btn btn-primary" style="width:100%;text-align:center">تسجيل الدخول 🔐</button>
    </form>
    <div class="login-hint">للتجربة: المستخدم <b>admin</b> — كلمة المرور <b>rom2026</b></div>
    <p style="text-align:center;margin-top:14px"><a href="#" onclick="showStore();return false;" style="color:var(--accent);font-size:13px">← العودة للمتجر</a></p>
  </div>
</div>

<!-- ============ ADMIN PANEL VIEW ============ -->
<div id="adminView" class="hidden">
  <div class="admin-mobile-bar"><button class="nav-icon" onclick="document.getElementById('adminSide').classList.toggle('open')">☰</button><b>ROM لوحة التحكم</b></div>
  <div class="admin-layout">
    <aside class="admin-side" id="adminSide">
      <span class="logo">ROM</span>
      <nav class="admin-nav">
        <a href="#" class="active" data-tab="dashboard" onclick="adminTab('dashboard',this)">📊 لوحة المعلومات</a>
        <a href="#" data-tab="products" onclick="adminTab('products',this)">📦 المنتجات</a>
        <a href="#" data-tab="orders" onclick="adminTab('orders',this)">🧾 الطلبات</a>
        <a href="#" onclick="showStore();return false;">🛍️ عرض المتجر</a>
        <a href="#" onclick="adminLogout();return false;">🚪 تسجيل الخروج</a>
      </nav>
    </aside>
    <main class="admin-main">
      <!-- DASHBOARD -->
      <div id="tab-dashboard">
        <div class="admin-top"><h2>لوحة المعلومات</h2><span style="color:var(--text-soft);font-size:13px" id="todayDate"></span></div>
        <div class="stats-grid" id="statsGrid"></div>
        <h3 style="margin-bottom:14px;font-size:18px">أحدث الطلبات</h3>
        <div style="overflow-x:auto"><table class="admin-table"><thead><tr><th>رقم الطلب</th><th>العميل</th><th>الإجمالي</th><th>الحالة</th><th>التاريخ</th></tr></thead><tbody id="recentOrders"></tbody></table></div>
      </div>
      <!-- PRODUCTS -->
      <div id="tab-products" class="hidden">
        <div class="admin-top">
          <h2>إدارة المنتجات</h2>
          <button class="btn btn-primary btn-small" onclick="openProductForm()">+ إضافة منتج</button>
        </div>
        <div style="overflow-x:auto"><table class="admin-table"><thead><tr><th></th><th>المنتج</th><th>الفئة</th><th>السعر</th><th>المخزون</th><th>الحالة</th><th>إجراءات</th></tr></thead><tbody id="adminProducts"></tbody></table></div>
      </div>
      <!-- ORDERS -->
      <div id="tab-orders" class="hidden">
        <div class="admin-top"><h2>الطلبات</h2></div>
        <div style="overflow-x:auto"><table class="admin-table"><thead><tr><th>رقم الطلب</th><th>العميل</th><th>الجوال</th><th>المدينة</th><th>المنتجات</th><th>الإجمالي</th><th>الدفع</th><th>الحالة</th><th>إجراءات</th></tr></thead><tbody id="adminOrders"></tbody></table></div>
      </div>
    </main>
  </div>
</div>

<!-- CART DRAWER -->
<div class="overlay" id="overlay" onclick="toggleCart(false)"></div>
<aside class="drawer" id="cartDrawer">
  <div class="drawer-head"><h3>🛍️ سلة التسوق</h3><button class="drawer-close" onclick="toggleCart(false)">✕</button></div>
  <div class="cart-items" id="cartItems"></div>
  <div class="drawer-foot">
    <div class="total-row"><span>الإجمالي</span><span id="cartTotal">0 ر.س</span></div>
    <button class="checkout-btn" id="checkoutBtn" onclick="startCheckout()">إتمام الشراء 💳</button>
  </div>
</aside>

<!-- MODAL -->
<div class="modal" id="productModal">
  <div class="modal-bg" onclick="closeModal()"></div>
  <div class="modal-box" id="modalBox"></div>
</div>

<div class="toast" id="toast"></div>

<script>
/* ============================================================
   ROM — Real Orders More
   قاعدة البيانات (Database Layer) — localStorage
============================================================ */
const DB = {
  get(key, fallback){ try{ const v = localStorage.getItem('rom_'+key); return v ? JSON.parse(v) : fallback; }catch(e){ return fallback; } },
  set(key, val){ localStorage.setItem('rom_'+key, JSON.stringify(val)); }
};

const DEFAULT_PRODUCTS = [
  {id:1, name:"آيفون 17 برو ماكس", cat:"هواتف", price:5299, oldPrice:null, stock:25, emoji:"📱", isNew:true, rating:5, desc:"شريحة A19 Pro، كاميرا 48MP، شاشة ProMotion 120Hz، وتصميم من التيتانيوم.", specs:{"الشاشة":"6.9 بوصة OLED","التخزين":"256GB","الكاميرا":"48MP ثلاثية","البطارية":"30 ساعة"}},
  {id:2, name:"ماك بوك برو 16", cat:"لابتوبات", price:9499, oldPrice:null, stock:12, emoji:"💻", isNew:true, rating:5, desc:"شريحة M5 Pro مع ذاكرة 36GB وشاشة Liquid Retina XDR مذهلة.", specs:{"المعالج":"M5 Pro","الذاكرة":"36GB","التخزين":"512GB SSD","البطارية":"22 ساعة"}},
  {id:3, name:"سماعات AirPods Max", cat:"سماعات", price:1999, oldPrice:2499, stock:40, emoji:"🎧", isNew:false, rating:4, desc:"إلغاء ضوضاء نشط، صوت فضائي، وبطارية تدوم حتى 20 ساعة.", specs:{"إلغاء الضوضاء":"نشط","البطارية":"20 ساعة","الاتصال":"Bluetooth 5.3","الوزن":"385 جم"}},
  {id:4, name:"ساعة Apple Watch Ultra 3", cat:"ساعات", price:3299, oldPrice:null, stock:18, emoji:"⌚", isNew:true, rating:5, desc:"مصنوعة من التيتانيوم، مقاومة للماء حتى 100 متر، وبطارية 72 ساعة.", specs:{"المعالج":"S11","البطارية":"72 ساعة","المقاومة":"100 متر","GPS":"مزدوج التردد"}},
  {id:5, name:"آيباد برو 13 بوصة", cat:"هواتف", price:4599, oldPrice:4999, stock:15, emoji:"📲", isNew:false, rating:4, desc:"أنحف آيباد على الإطلاق مع شريحة M5 وشاشة Ultra Retina XDR.", specs:{"الشاشة":"13 بوصة XDR","المعالج":"M5","التخزين":"256GB","القلم":"مدعوم"}},
  {id:6, name:"سماعات AirPods Pro 3", cat:"سماعات", price:949, oldPrice:null, stock:60, emoji:"🎵", isNew:false, rating:4, desc:"إلغاء ضوضاء مضاعف، وضع الشفافية التكيفية، وصوت مخصص.", specs:{"إلغاء الضوضاء":"2x أقوى","البطارية":"30 ساعة","الشحن":"MagSafe","الصندوق":"USB-C"}},
  {id:7, name:"آيفون 16", cat:"هواتف", price:3699, oldPrice:null, stock:30, emoji:"📱", isNew:false, rating:5, desc:"التوازن المثالي بين الأداء والسعر مع شريحة A18.", specs:{"الشاشة":"6.1 بوصة","المعالج":"A18","الكاميرا":"48MP","البطارية":"27 ساعة"}},
  {id:8, name:"ماك بوك Air 15", cat:"لابتوبات", price:5899, oldPrice:null, stock:20, emoji:"💻", isNew:false, rating:4, desc:"أخف وأنحف ماك بوك مع شريحة M4 وألوان مبهجة.", specs:{"المعالج":"M4","الذاكرة":"16GB","التخزين":"512GB","الوزن":"1.51 كجم"}},
  {id:9, name:"ساعة Apple Watch SE", cat:"ساعات", price:1249, oldPrice:1399, stock:35, emoji:"⌚", isNew:false, rating:4, desc:"ساعة ذكية مثالية للمبتدئين مع تتبع الصحة واللياقة.", specs:{"المعالج":"S9","البطارية":"18 ساعة","المقاومة":"50 متر","المقاسات":"40/44mm"}},
  {id:10, name:"سماعات Beats Studio Pro", cat:"سماعات", price:1349, oldPrice:null, stock:22, emoji:"🎶", isNew:false, rating:4, desc:"صوت احترافي مع إلغاء ضوضاء وتشغيل 40 ساعة.", specs:{"البطارية":"40 ساعة","الشحن":"USB-C","الكودك":"Lossless","الألوان":"4 خيارات"}},
  {id:11, name:"آيباد ميني 7", cat:"هواتف", price:2099, oldPrice:null, stock:28, emoji:"📲", isNew:true, rating:5, desc:"قوة A17 Pro بحجم الجيب، مثالي للقراءة والرسم.", specs:{"الشاشة":"8.3 بوصة","المعالج":"A17 Pro","القلم":"Apple Pencil Pro","الوزن":"297 جم"}},
  {id:12, name:"ماك ستوديو", cat:"لابتوبات", price:12499, oldPrice:null, stock:8, emoji:"🖥️", isNew:true, rating:5, desc:"وحش الأداء الإبداعي مع شريحة M5 Ultra للمحترفين.", specs:{"المعالج":"M5 Ultra","الذاكرة":"96GB","التخزين":"1TB SSD","المنافذ":"12 منفذ"}},
];
const CATS = ["الكل","هواتف","لابتوبات","سماعات","ساعات"];
const ADMIN_CRED = {user:"admin", pass:"rom2026"};

/* تهيئة قاعدة البيانات */
let PRODUCTS = DB.get('products', null);
if(!PRODUCTS){ PRODUCTS = DEFAULT_PRODUCTS; DB.set('products', PRODUCTS); }
let cart = DB.get('cart', []);
let activeCat = "الكل";

/* ================= VIEWS ================= */
function showStore(){ hideAllViews(); document.getElementById('storeView').classList.remove('hidden'); renderProducts(); renderFilters(); window.scrollTo(0,0); }
function showAdminLogin(){ hideAllViews(); document.getElementById('adminLoginView').classList.remove('hidden'); }
function showAdminPanel(){ hideAllViews(); document.getElementById('adminView').classList.remove('hidden'); renderAdmin(); }
function hideAllViews(){ ['storeView','adminLoginView','adminView'].forEach(id=>document.getElementById(id).classList.add('hidden')); }

/* ================= AUTH ================= */
function adminLogin(e){
  e.preventDefault();
  const u = document.getElementById('adminUser').value.trim();
  const p = document.getElementById('adminPass').value;
  if(u===ADMIN_CRED.user && p===ADMIN_CRED.pass){
    sessionStorage.setItem('rom_admin','1');
    showAdminPanel(); showToast('✅ مرحباً بك في لوحة التحكم','success');
  } else showToast('❌ بيانات الدخول غير صحيحة','error');
}
function adminLogout(){ sessionStorage.removeItem('rom_admin'); showStore(); }

/* ================= ADMIN TABS ================= */
function adminTab(tab, el){
  ['dashboard','products','orders'].forEach(t=>document.getElementById('tab-'+t).classList.add('hidden'));
  document.getElementById('tab-'+tab).classList.remove('hidden');
  document.querySelectorAll('.admin-nav a[data-tab]').forEach(a=>a.classList.remove('active'));
  el.classList.add('active');
  document.getElementById('adminSide').classList.remove('open');
}

function renderAdmin(){
  const orders = DB.get('orders', []);
  const revenue = orders.filter(o=>o.status!=='ملغي').reduce((s,o)=>s+o.total,0);
  const lowStock = PRODUCTS.filter(p=>p.stock<10).length;
  document.getElementById('todayDate').textContent = new Date().toLocaleDateString('ar-SA',{weekday:'long',year:'numeric',month:'long',day:'numeric'});
  document.getElementById('statsGrid').innerHTML = `
    <div class="stat-card"><div class="si">🧾</div><div class="sv">${orders.length}</div><div class="sl">إجمالي الطلبات</div></div>
    <div class="stat-card"><div class="si">💰</div><div class="sv">${revenue.toLocaleString()} <small style="font-size:14px">ر.س</small></div><div class="sl">إجمالي المبيعات</div></div>
    <div class="stat-card"><div class="si">📦</div><div class="sv">${PRODUCTS.length}</div><div class="sl">عدد المنتجات</div></div>
    <div class="stat-card"><div class="si">⚠️</div><div class="sv" style="color:${lowStock?'var(--danger)':'inherit'}">${lowStock}</div><div class="sl">منتجات مخزون منخفض</div></div>`;
  document.getElementById('recentOrders').innerHTML = orders.length ? orders.slice(-5).reverse().map(o=>`
    <tr><td><b>#${o.id}</b></td><td>${o.customer.name}</td><td>${o.total.toLocaleString()} ر.س</td><td>${statusPill(o.status)}</td><td style="color:var(--text-soft);font-size:12px">${o.date}</td></tr>`).join('')
    : '<tr><td colspan="5" style="text-align:center;color:var(--text-soft);padding:30px">لا توجد طلبات بعد</td></tr>';
  renderAdminProducts();
  renderAdminOrders();
}

function statusPill(s){
  const map = {"جديد":"status-new","تم الشحن":"status-shipped","مكتمل":"status-done","ملغي":"status-cancel"};
  return `<span class="status-pill ${map[s]||'status-new'}">${s}</span>`;
}

function renderAdminProducts(){
  document.getElementById('adminProducts').innerHTML = PRODUCTS.map(p=>`
    <tr>
      <td><span class="pe">${p.emoji}</span></td>
      <td><b>${p.name}</b>${p.isNew?' <span class="new-badge" style="position:static;display:inline-block">جديد</span>':''}</td>
      <td>${p.cat}</td>
      <td><b>${p.price.toLocaleString()}</b> ر.س${p.oldPrice?`<br><small style="text-decoration:line-through;color:var(--text-soft)">${p.oldPrice.toLocaleString()}</small>`:''}</td>
      <td style="color:${p.stock<10?'var(--danger)':'inherit'};font-weight:${p.stock<10?'700':'400'}">${p.stock}</td>
      <td>${statusPill(p.stock>0?'مكتمل':'ملغي').replace('مكتمل','متوفر').replace('ملغي','نفد')}</td>
      <td><div class="admin-actions">
        <button class="icon-btn" onclick="openProductForm(${p.id})" title="تعديل">✏️</button>
        <button class="icon-btn danger" onclick="deleteProduct(${p.id})" title="حذف">🗑</button>
      </div></td>
    </tr>`).join('');
}

function renderAdminOrders(){
  const orders = DB.get('orders', []);
  document.getElementById('adminOrders').innerHTML = orders.length ? orders.slice().reverse().map(o=>`
    <tr>
      <td><b>#${o.id}</b></td>
      <td>${o.customer.name}</td>
      <td style="direction:ltr;text-align:right">${o.customer.phone}</td>
      <td>${o.customer.city}</td>
      <td>${o.items.map(i=>`${i.emoji}×${i.qty}`).join(' ')}</td>
      <td><b>${o.total.toLocaleString()}</b> ر.س</td>
      <td>${o.payment}</td>
      <td>${statusPill(o.status)}</td>
      <td><div class="admin-actions">
        ${o.status==='جديد'?`<button class="icon-btn" onclick="updateOrder(${o.id},'تم الشحن')" title="شحن">🚚</button>`:''}
        ${o.status==='تم الشحن'?`<button class="icon-btn" onclick="updateOrder(${o.id},'مكتمل')" title="إكمال">✅</button>`:''}
        ${o.status!=='ملغي'&&o.status!=='مكتمل'?`<button class="icon-btn danger" onclick="updateOrder(${o.id},'ملغي')" title="إلغاء">✕</button>`:''}
      </div></td>
    </tr>`).join('')
    : '<tr><td colspan="9" style="text-align:center;color:var(--text-soft);padding:30px">لا توجد طلبات بعد — الطلبات الجديدة ستظهر هنا</td></tr>';
}

function updateOrder(id, status){
  const orders = DB.get('orders', []);
  const o = orders.find(x=>x.id===id);
  if(o){ o.status = status; DB.set('orders', orders); renderAdmin(); showToast(`تم تحديث الطلب #${id} → ${status}`,'success'); }
}

/* ================= PRODUCT CRUD ================= */
function openProductForm(id){
  const p = id ? PRODUCTS.find(x=>x.id===id) : null;
  document.getElementById('modalBox').innerHTML = `
    <button class="modal-close" onclick="closeModal()">✕</button>
    <h2>${p?'✏️ تعديل منتج':'➕ إضافة منتج جديد'}</h2>
    <form onsubmit="saveProduct(event,${p?p.id:'null'})" style="margin-top:20px">
      <div class="form-group"><label>اسم المنتج *</label><input id="fName" required value="${p?p.name:''}"></div>
      <div class="form-row">
        <div class="form-group"><label>الفئة *</label><select id="fCat">${CATS.slice(1).map(c=>`<option ${p&&p.cat===c?'selected':''}>${c}</option>`).join('')}</select></div>
        <div class="form-group"><label>الأيقونة (Emoji)</label><input id="fEmoji" value="${p?p.emoji:'📦'}" maxlength="4"></div>
      </div>
      <div class="form-row">
        <div class="form-group"><label>السعر (ر.س) *</label><input id="fPrice" type="number" min="1" required value="${p?p.price:''}"></div>
        <div class="form-group"><label>السعر قبل الخصم</label><input id="fOld" type="number" min="0" value="${p&&p.oldPrice?p.oldPrice:''}"></div>
      </div>
      <div class="form-row">
        <div class="form-group"><label>المخزون *</label><input id="fStock" type="number" min="0" required value="${p?p.stock:20}"></div>
        <div class="form-group"><label>التقييم (1-5)</label><input id="fRating" type="number" min="1" max="5" value="${p?p.rating:5}"></div>
      </div>
      <div class="form-group"><label>الوصف</label><textarea id="fDesc" rows="3">${p?p.desc:''}</textarea></div>
      <div class="form-group"><label style="display:flex;align-items:center;gap:8px"><input type="checkbox" id="fNew" style="width:auto" ${p&&p.isNew?'checked':''}> منتج جديد (شارة)</label></div>
      <button class="btn btn-primary" style="width:100%;text-align:center">${p?'حفظ التعديلات 💾':'إضافة المنتج ➕'}</button>
    </form>`;
  document.getElementById('productModal').classList.add('open');
}

function saveProduct(e, id){
  e.preventDefault();
  const data = {
    name: document.getElementById('fName').value.trim(),
    cat: document.getElementById('fCat').value,
    emoji: document.getElementById('fEmoji').value || '📦',
    price: +document.getElementById('fPrice').value,
    oldPrice: +document.getElementById('fOld').value || null,
    stock: +document.getElementById('fStock').value,
    rating: Math.min(5,Math.max(1,+document.getElementById('fRating').value||5)),
    desc: document.getElementById('fDesc').value.trim(),
    isNew: document.getElementById('fNew').checked,
  };
  if(id){
    const i = PRODUCTS.findIndex(x=>x.id===id);
    PRODUCTS[i] = {...PRODUCTS[i], ...data};
  } else {
    data.id = Math.max(0,...PRODUCTS.map(p=>p.id))+1;
    data.specs = {"الضمان":"سنتان","التوصيل":"مجاني"};
    PRODUCTS.push(data);
  }
  DB.set('products', PRODUCTS);
  closeModal(); renderAdmin(); renderProducts(); renderFilters();
  showToast(id?'✅ تم حفظ التعديلات':'✅ تمت إضافة المنتج','success');
}

function deleteProduct(id){
  if(!confirm('هل أنت متأكد من حذف هذا المنتج؟')) return;
  PRODUCTS = PRODUCTS.filter(p=>p.id!==id);
  DB.set('products', PRODUCTS);
  cart = cart.filter(i=>i.id!==id); saveCart();
  renderAdmin(); renderProducts();
  showToast('🗑 تم حذف المنتج','success');
}

/* ================= STORE RENDER ================= */
function renderFilters(){
  document.getElementById('filters').innerHTML = CATS.map(c=>
    `<button class="chip ${c===activeCat?'active':''}" onclick="setCat('${c}')">${c}</button>`).join('');
}
function setCat(c){ activeCat=c; renderFilters(); renderProducts(); }
function starStr(n){ return "★".repeat(n)+"☆".repeat(5-n); }

function renderProducts(){
  const q = (document.getElementById('searchInput').value||'').trim();
  const list = PRODUCTS.filter(p =>
    (activeCat==="الكل"||p.cat===activeCat) &&
    (!q || p.name.includes(q)||(p.desc||'').includes(q)||p.cat.includes(q))
  );
  document.getElementById('productGrid').innerHTML = list.length ? list.map(p=>`
    <div class="card reveal visible" onclick="openProduct(${p.id})">
      ${p.isNew?'<span class="new-badge">جديد</span>':''}
      ${p.oldPrice?`<span class="sale-badge">خصم ${Math.round((1-p.price/p.oldPrice)*100)}%</span>`:''}
      <div class="emoji">${p.emoji}</div>
      <span class="cat-tag">${p.cat}</span>
      <h3>${p.name}</h3>
      <p>${p.desc||''}</p>
      <div class="stars">${starStr(p.rating)}</div>
      <div class="price">${p.oldPrice?`<span class="old-price">${p.oldPrice.toLocaleString()}</span>`:''}${p.price.toLocaleString()} <small>ر.س</small></div>
      ${p.stock<=0?'<button class="btn-add" style="background:#d2d2d7;cursor:not-allowed;margin-top:18px;width:100%">نفد المخزون</button>':`
      <div class="actions">
        <button class="btn-add" onclick="event.stopPropagation();addToCart(${p.id})">أضف للسلة</button>
        <button class="btn-view" onclick="event.stopPropagation();openProduct(${p.id})">عرض</button>
      </div>`}
    </div>`).join('')
  : '<p style="grid-column:1/-1;text-align:center;color:#86868b;font-size:18px;padding:40px">لا توجد نتائج مطابقة 😕</p>';
}

/* ================= CART ================= */
function saveCart(){ DB.set('cart', cart); updateCartUI(); }

function addToCart(id){
  const p = PRODUCTS.find(x=>x.id===id);
  if(!p || p.stock<=0){ showToast('⚠️ نفد المخزون','error'); return; }
  const item = cart.find(i=>i.id===id);
  const inCart = item ? item.qty : 0;
  if(inCart+1 > p.stock){ showToast(`⚠️ المتوفر فقط ${p.stock} قطعة`,'error'); return; }
  if(item) item.qty++;
  else cart.push({id:p.id, name:p.name, price:p.price, emoji
