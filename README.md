<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <base target="_self">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>المتجر الإلكتروني - الجزائر</title>
    <meta name="description" content="متجر إلكتروني مدعوم بالذكاء الاصطناعي مع دعم الدينار الجزائري">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: "#006633",
                        secondary: "#FFFFFF",
                        accent: "#D21034"
                    },
                    fontFamily: {
                        arabic: ["Tajawal", "sans-serif"]
                    }
                }
            }
        }
    </script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700&display=swap');
        body {
            font-family: 'Tajawal', sans-serif;
        }
    </style>
</head>
<body class="min-h-screen bg-gray-50">
    <!-- Algerian Flag Banner -->
    <div class="w-full h-2 bg-gradient-to-r from-green-600 via-white to-red-600"></div>

    <!-- Header -->
    <header class="bg-white shadow-md">
        <div class="container mx-auto px-4 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <img src="https://picsum.photos/50?random=1" alt="شعار المتجر" class="w-12 h-12 rounded-full">
                    <h1 class="text-xl font-bold text-primary">المتجر الإلكتروني</h1>
                </div>
                <div class="flex items-center space-x-4">
                    <span class="text-lg font-bold text-accent">د.ج</span>
                    <button id="cartBtn" class="relative">
                        <i class="fas fa-shopping-cart text-2xl text-primary"></i>
                        <span id="cartCount" class="absolute -top-2 -right-2 bg-accent text-white text-xs rounded-full h-5 w-5 flex items-center justify-center">0</span>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
        <!-- Store Management Section -->
        <section class="mb-12">
            <div class="bg-white rounded-lg shadow-md p-6">
                <h2 class="text-xl font-bold text-primary mb-4">إدارة المتجر</h2>
                
                <!-- Product Management -->
                <div class="mb-6">
                    <h3 class="text-lg font-semibold mb-2">إدارة المنتجات</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <!-- Add Product Form -->
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-medium mb-2">إضافة منتج جديد</h4>
                            <form id="addProductForm" class="space-y-3">
                                <input type="text" placeholder="اسم المنتج" class="w-full px-3 py-2 border rounded-lg" required>
                                <textarea placeholder="وصف المنتج" class="w-full px-3 py-2 border rounded-lg" rows="2"></textarea>
                                <input type="number" placeholder="السعر (د.ج)" class="w-full px-3 py-2 border rounded-lg" required>
                                <input type="text" placeholder="رابط الصورة" class="w-full px-3 py-2 border rounded-lg">
                                <button type="submit" class="w-full bg-primary text-white py-2 rounded-lg hover:bg-green-800 transition">إضافة المنتج</button>
                            </form>
                        </div>
                        
                        <!-- Product List -->
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-medium mb-2">قائمة المنتجات</h4>
                            <div id="productList" class="space-y-2 max-h-60 overflow-y-auto">
                                <!-- Products will be added here dynamically -->
                                <div class="text-center text-gray-500 py-4">لا توجد منتجات متوفرة</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Social Media Integration -->
                <div class="mb-6">
                    <h3 class="text-lg font-semibold mb-2">ربط وسائل التواصل الاجتماعي</h3>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                        <div class="bg-gray-50 p-4 rounded-lg text-center">
                            <i class="fab fa-facebook text-blue-600 text-3xl mb-2"></i>
                            <button class="bg-blue-600 text-white px-4 py-1 rounded-lg text-sm hover:bg-blue-700 transition">ربط الفيسبوك</button>
                        </div>
                        <div class="bg-gray-50 p-4 rounded-lg text-center">
                            <i class="fab fa-instagram text-pink-600 text-3xl mb-2"></i>
                            <button class="bg-pink-600 text-white px-4 py-1 rounded-lg text-sm hover:bg-pink-700 transition">ربط الإنستغرام</button>
                        </div>
                        <div class="bg-gray-50 p-4 rounded-lg text-center">
                            <i class="fab fa-whatsapp text-green-500 text-3xl mb-2"></i>
                            <button class="bg-green-500 text-white px-4 py-1 rounded-lg text-sm hover:bg-green-600 transition">ربط الواتساب</button>
                        </div>
                    </div>
                </div>
                
                <!-- Store Video -->
                <div>
                    <h3 class="text-lg font-semibold mb-2">فيديو توضيحي للمتجر</h3>
                    <div class="bg-gray-200 rounded-lg aspect-video flex items-center justify-center">
                        <i class="fas fa-play-circle text-4xl text-gray-400"></i>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Product Showcase -->
        <section class="mb-12">
            <h2 class="text-xl font-bold text-primary mb-4">منتجاتنا</h2>
            <div id="productsGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Products will be added here dynamically -->
                <div class="text-center py-8 text-gray-500 col-span-3">قم بإضافة منتجاتك لتبدأ البيع</div>
            </div>
        </section>
        
        <!-- Download Section -->
        <section class="bg-white rounded-lg shadow-md p-6">
            <h2 class="text-xl font-bold text-primary mb-4">تحميل المتجر</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="bg-gray-50 p-6 rounded-lg text-center">
                    <i class="fas fa-download text-4xl text-primary mb-4"></i>
                    <h3 class="text-lg font-semibold mb-2">تحميل المتجر النهائي</h3>
                    <p class="text-gray-600 mb-4">احصل على نسخة كاملة من متجرك جاهزة للنشر</p>
                    <button id="downloadBtn" class="bg-primary text-white px-6 py-2 rounded-lg hover:bg-green-800 transition">تحميل الآن</button>
                </div>
                <div class="bg-gray-50 p-6 rounded-lg text-center">
                    <i class="fas fa-book text-4xl text-primary mb-4"></i>
                    <h3 class="text-lg font-semibold mb-2">دليل الاستخدام</h3>
                    <p class="text-gray-600 mb-4">تعرف على كيفية إدارة متجرك ونشره</p>
                    <button class="bg-secondary text-primary border border-primary px-6 py-2 rounded-lg hover:bg-gray-100 transition">تحميل الدليل</button>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-primary text-white py-8">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div>
                    <h3 class="text-lg font-bold mb-4">عن المتجر</h3>
                    <p>متجر إلكتروني مدعوم بالذكاء الاصطناعي مع دعم كامل للدينار الجزائري ووسائل التواصل الاجتماعي.</p>
                </div>
                <div>
                    <h3 class="text-lg font-bold mb-4">روابط سريعة</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-gray-300 transition">الصفحة الرئيسية</a></li>
                        <li><a href="#" class="hover:text-gray-300 transition">المنتجات</a></li>
                        <li><a href="#" class="hover:text-gray-300 transition">اتصل بنا</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-bold mb-4">تواصل معنا</h3>
                    <div class="flex space-x-4">
                        <a href="#" class="text-2xl hover:text-gray-300 transition"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="text-2xl hover:text-gray-300 transition"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="text-2xl hover:text-gray-300 transition"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>
            <div class="border-t border-gray-600 mt-8 pt-6 text-center">
                <p>© 2023 المتجر الإلكتروني. جميع الحقوق محفوظة.</p>
            </div>
        </div>
    </footer>

    <!-- Shopping Cart Modal -->
    <div id="cartModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden">
        <div class="absolute top-0 right-0 h-full w-full md:w-1/3 bg-white shadow-lg overflow-y-auto">
            <div class="p-4">
                <div class="flex justify-between items-center mb-4">
                    <h3 class="text-lg font-bold">سلة التسوق</h3>
                    <button id="closeCartBtn" class="text-gray-500 hover:text-gray-700">
                        <i class="fas fa-times"></i>
                    </button>
                </div>
                <div id="cartItems" class="space-y-4">
                    <!-- Cart items will be added here dynamically -->
                    <div class="text-center py-8 text-gray-500">سلة التسوق فارغة</div>
                </div>
                <div class="border-t pt-4 mt-4">
                    <div class="flex justify-between mb-2">
                        <span>المجموع:</span>
                        <span id="cartTotal" class="font-bold">0 د.ج</span>
                    </div>
                    <button class="w-full bg-accent text-white py-2 rounded-lg hover:bg-red-800 transition">إتمام الشراء</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Download Confirmation Modal -->
    <div id="downloadModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden">
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-white p-6 rounded-lg w-11/12 md:w-1/2">
            <h3 class="text-lg font-bold mb-4">تأكيد التحميل</h3>
            <p class="mb-6">هل أنت متأكد أنك تريد تحميل نسخة نهائية من متجرك؟ سيتم تنزيل ملف ZIP يحتوي على جميع الملفات اللازمة.</p>
            <div class="flex justify-end space-x-3">
                <button id="cancelDownloadBtn" class="px-4 py-2 border rounded-lg hover:bg-gray-100">إلغاء</button>
                <button id="confirmDownloadBtn" class="px-4 py-2 bg-primary text-white rounded-lg hover:bg-green-800">تأكيد التحميل</button>
            </div>
        </div>
    </div>

    <script>
        // Algerian Dinar Formatter
        const formatDZD = (amount) => {
            return new Intl.NumberFormat('ar-DZ', {
                style: 'decimal',
                minimumFractionDigits: 2,
                maximumFractionDigits: 2
            }).format(amount) + ' د.ج';
        };

        // Store Data
        let products = [];
        let cart = [];

        // DOM Elements
        const productList = document.getElementById('productList');
        const productsGrid = document.getElementById('productsGrid');
        const addProductForm = document.getElementById('addProductForm');
        const cartBtn = document.getElementById('cartBtn');
        const cartModal = document.getElementById('cartModal');
        const closeCartBtn = document.getElementById('closeCartBtn');
        const cartItems = document.getElementById('cartItems');
        const cartCount = document.getElementById('cartCount');
        const cartTotal = document.getElementById('cartTotal');
        const downloadBtn = document.getElementById('downloadBtn');
        const downloadModal = document.getElementById('downloadModal');
        const cancelDownloadBtn = document.getElementById('cancelDownloadBtn');
        const confirmDownloadBtn = document.getElementById('confirmDownloadBtn');

        // Event Listeners
        addProductForm.addEventListener('submit', addProduct);
        cartBtn.addEventListener('click', openCart);
        closeCartBtn.addEventListener('click', closeCart);
        downloadBtn.addEventListener('click', showDownloadModal);
        cancelDownloadBtn.addEventListener('click', hideDownloadModal);
        confirmDownloadBtn.addEventListener('click', downloadStore);

        // Functions
        function addProduct(e) {
            e.preventDefault();
            const inputs = e.target.elements;
            
            const newProduct = {
                id: Date.now(),
                name: inputs[0].value,
                description: inputs[1].value,
                price: parseFloat(inputs[2].value),
                image: inputs[3].value || `https://picsum.photos/400?random=${Math.floor(Math.random() * 1000)}`
            };
            
            products.push(newProduct);
            renderProducts();
            inputs[0].value = '';
            inputs[1].value = '';
            inputs[2].value = '';
            inputs[3].value = '';
        }

        function renderProducts() {
            // Clear existing products
            productList.innerHTML = '';
            productsGrid.innerHTML = '';
            
            if (products.length === 0) {
                productList.innerHTML = '<div class="text-center text-gray-500 py-4">لا توجد منتجات متوفرة</div>';
                productsGrid.innerHTML = '<div class="text-center py-8 text-gray-500 col-span-3">قم بإضافة منتجاتك لتبدأ البيع</div>';
                return;
            }
            
            // Render in management list
            products.forEach(product => {
                const productItem = document.createElement('div');
                productItem.className = 'flex justify-between items-center bg-white p-2 rounded border';
                productItem.innerHTML = `
                    <div class="flex items-center space-x-2">
                        <img src="${product.image}" alt="${product.name}" class="w-10 h-10 rounded">
                        <span>${product.name}</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <span class="text-sm">${formatDZD(product.price)}</span>
                        <button onclick="removeProduct(${product.id})" class="text-red-500 hover:text-red-700">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                `;
                productList.appendChild(productItem);
            });
            
            // Render in products grid
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition';
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="w-full h-48 object-cover" loading="lazy">
                    <div class="p-4">
                        <h3 class="font-bold text-lg mb-1">${product.name}</h3>
                        <p class="text-gray-600 text-sm mb-3">${product.description || 'لا يوجد وصف'}</p>
                        <div class="flex justify-between items-center">
                            <span class="font-bold text-primary">${formatDZD(product.price)}</span>
                            <button onclick="addToCart(${product.id})" class="bg-primary text-white px-3 py-1 rounded-lg text-sm hover:bg-green-800 transition">
                                أضف للسلة
                            </button>
                        </div>
                    </div>
                `;
                productsGrid.appendChild(productCard);
            });
        }

        function removeProduct(id) {
            products = products.filter(product => product.id !== id);
            renderProducts();
        }

        function addToCart(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;
            
            const existingItem = cart.find(item => item.id === id);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...product,
                    quantity: 1
                });
            }
            
            updateCart();
        }

        function updateCart() {
            // Update cart count
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart modal
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<div class="text-center py-8 text-gray-500">سلة التسوق فارغة</div>';
                cartTotal.textContent = '0 د.ج';
                return;
            }
            
            let total = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItem = document.createElement('div');
                cartItem.className = 'flex justify-between items-center border-b pb-3';
                cartItem.innerHTML = `
                    <div class="flex items-center space-x-3">
                        <img src="${item.image}" alt="${item.name}" class="w-12 h-12 rounded">
                        <div>
                            <h4 class="font-medium">${item.name}</h4>
                            <div class="flex items-center space-x-2 mt-1">
                                <button onclick="updateQuantity(${item.id}, -1)" class="w-6 h-6 flex items-center justify-center border rounded">
                                    <i class="fas fa-minus text-xs"></i>
                                </button>
                                <span>${item.quantity}</span>
                                <button onclick="updateQuantity(${item.id}, 1)" class="w-6 h-6 flex items-center justify-center border rounded">
                                    <i class="fas fa-plus text-xs"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="text-right">
                        <span class="block font-medium">${formatDZD(itemTotal)}</span>
                        <button onclick="removeFromCart(${item.id})" class="text-red-500 text-sm mt-1">إزالة</button>
                    </div>
                `;
                cartItems.appendChild(cartItem);
            });
            
            cartTotal.textContent = formatDZD(total);
        }

        function updateQuantity(id, change) {
            const item = cart.find(item => item.id === id);
            if (!item) return;
            
            item.quantity += change;
            
            if (item.quantity <= 0) {
                cart = cart.filter(item => item.id !== id);
            }
            
            updateCart();
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCart();
        }

        function openCart() {
            cartModal.classList.remove('hidden');
        }

        function closeCart() {
            cartModal.classList.add('hidden');
        }

        function showDownloadModal() {
            downloadModal.classList.remove('hidden');
        }

        function hideDownloadModal() {
            downloadModal.classList.add('hidden');
        }

        function downloadStore() {
            hideDownloadModal();
            alert('سيتم تحميل ملفات المتجر. في بيئة حقيقية، سيتم تنزيل ملف ZIP يحتوي على جميع الملفات.');
            // In a real implementation, you would generate a ZIP file with:
            // 1. This HTML file
            // 2. Any additional CSS/JS files
            // 3. Documentation files
            // Then trigger the download
        }

        // Initialize
        renderProducts();
        updateCart();
    </script>
</body>
</html>
