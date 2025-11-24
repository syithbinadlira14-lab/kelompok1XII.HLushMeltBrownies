# kelompok1XII.HLushMeltBrownies

<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LushMelt Brownies - Kelompok 1 XII.H</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Quicksand:wght@300;400;500;600;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Tailwind Config for Custom Colors -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brown: {
                            100: '#EFEBE9', // Very Light
                            200: '#D7CCC8',
                            300: '#A1887F',
                            400: '#8D6E63', // Light Brown (Button)
                            500: '#6D4C41',
                            800: '#4E342E', // Dark Brown (Text/Footer)
                            900: '#3E2723',
                        },
                        cream: {
                            50: '#FDFCF5',
                            100: '#FAF3E0', // Soft Cream
                            200: '#F5E6CA',
                        },
                        gold: {
                            400: '#D4AF37', // Gold Accent
                            500: '#C5A028',
                        }
                    },
                    fontFamily: {
                        serif: ['"Playfair Display"', 'serif'],
                        sans: ['"Quicksand"', 'sans-serif'],
                        body: ['"Poppins"', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Quicksand', sans-serif;
            background-color: #FAF3E0; /* Soft Cream Background */
            color: #4E342E;
            overflow-x: hidden;
        }
        
        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
        }

        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #FAF3E0;
        }
        ::-webkit-scrollbar-thumb {
            background: #8D6E63;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #4E342E;
        }
        
        .glass-effect {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.5);
        }
    </style>
</head>
<body class="flex flex-col min-h-screen">

    <!-- Navbar -->
    <nav class="fixed w-full z-50 glass-effect shadow-sm transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center cursor-pointer" onclick="router('home')">
                    <span class="text-2xl font-bold text-brown-800 font-serif tracking-wider">LushMelt<span class="text-gold-400">.</span></span>
                </div>

                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-8 items-center">
                    <a href="#" onclick="router('home')" class="text-brown-800 hover:text-gold-400 transition font-medium">Beranda</a>
                    <a href="#" onclick="router('shop')" class="text-brown-800 hover:text-gold-400 transition font-medium">Produk</a>
                    <a href="#" onclick="router('about')" class="text-brown-800 hover:text-gold-400 transition font-medium">Tentang Kami</a>
                    <a href="#" onclick="router('blog')" class="text-brown-800 hover:text-gold-400 transition font-medium">Blog</a>
                </div>

                <!-- Icons -->
                <div class="flex items-center space-x-4">
                    <button class="relative p-2 text-brown-800 hover:text-gold-400 transition" onclick="toggleCart()">
                        <i data-lucide="shopping-bag"></i>
                        <span id="cart-count" class="absolute top-0 right-0 inline-flex items-center justify-center px-1.5 py-0.5 text-xs font-bold leading-none text-white transform translate-x-1/4 -translate-y-1/4 bg-gold-400 rounded-full hidden">0</span>
                    </button>
                    <!-- Mobile menu button -->
                    <button class="md:hidden p-2 text-brown-800" onclick="document.getElementById('mobile-menu').classList.toggle('hidden')">
                        <i data-lucide="menu"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div class="hidden md:hidden bg-cream-100 absolute w-full shadow-md" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 text-center">
                <a href="#" onclick="router('home'); document.getElementById('mobile-menu').classList.add('hidden')" class="block px-3 py-2 text-brown-800 hover:bg-brown-200 rounded">Beranda</a>
                <a href="#" onclick="router('shop'); document.getElementById('mobile-menu').classList.add('hidden')" class="block px-3 py-2 text-brown-800 hover:bg-brown-200 rounded">Produk</a>
                <a href="#" onclick="router('about'); document.getElementById('mobile-menu').classList.add('hidden')" class="block px-3 py-2 text-brown-800 hover:bg-brown-200 rounded">Tentang Kami</a>
            </div>
        </div>
    </nav>

    <!-- Main Content Container -->
    <main id="app" class="flex-grow pt-20">
        
        <!-- HOME PAGE -->
        <section id="home" class="page fade-in">
            <!-- Hero Section -->
            <div class="relative w-full h-[600px] flex items-center justify-center overflow-hidden">
                <!-- Background Image Overlay -->
                <div class="absolute inset-0 z-0">
                    <img src="https://akcdn.detik.net.id/visual/2021/04/21/brownies_169.jpeg?w=720&q=90" alt="Brownies Background" class="w-full h-full object-cover opacity-90">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-brown-900/30"></div>
                </div>
                
                <div class="relative z-10 text-center px-4 max-w-4xl mx-auto text-white">
                    <p class="text-lg md:text-xl font-light mb-2 tracking-[0.2em] uppercase text-gold-400">Kelompok 1 XII.H</p>
                    <h1 class="text-5xl md:text-7xl font-bold mb-6 font-serif leading-tight">Brownis Lumer<br><span class="italic font-light text-cream-200">LushMelt</span></h1>
                    <p class="text-xl mb-8 font-light text-gray-200 max-w-2xl mx-auto">Rasakan sensasi cokelat premium yang meleleh di mulut dengan topping keju dan coklat pilihan.</p>
                    <div class="space-x-4">
                        <button onclick="router('shop')" class="bg-brown-400 hover:bg-gold-400 text-white font-semibold py-3 px-8 rounded-full transition duration-300 transform hover:scale-105 shadow-lg">
                            Belanja Sekarang
                        </button>
                    </div>
                </div>
            </div>

            <!-- Highlights / Features -->
            <div class="py-16 bg-white">
                <div class="max-w-7xl mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
                    <div class="p-6">
                        <div class="w-16 h-16 bg-cream-100 rounded-full flex items-center justify-center mx-auto mb-4 text-brown-800">
                            <i data-lucide="award" size="32"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Bahan Premium</h3>
                        <p class="text-gray-600 text-sm">Menggunakan coklat dan keju berkualitas tinggi untuk rasa terbaik.</p>
                    </div>
                    <div class="p-6">
                        <div class="w-16 h-16 bg-cream-100 rounded-full flex items-center justify-center mx-auto mb-4 text-brown-800">
                            <i data-lucide="droplet" size="32"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Tekstur Lumer</h3>
                        <p class="text-gray-600 text-sm">Lembut di luar, meleleh sempurna di dalam saat gigitan pertama.</p>
                    </div>
                    <div class="p-6">
                        <div class="w-16 h-16 bg-cream-100 rounded-full flex items-center justify-center mx-auto mb-4 text-brown-800">
                            <i data-lucide="heart" size="32"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Dibuat dengan Cinta</h3>
                        <p class="text-gray-600 text-sm">Produksi rumahan yang higienis dan penuh kasih sayang.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SHOP PAGE -->
        <section id="shop" class="page hidden fade-in py-12 px-4 sm:px-6 lg:px-8 bg-cream-50">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-brown-800 mb-4">Katalog Kami</h2>
                    <p class="text-brown-500">Pilih varian rasa dan ukuran favoritmu.</p>
                </div>

                <!-- Filters -->
                <div class="flex justify-center gap-4 mb-10 flex-wrap">
                    <button class="filter-btn active px-6 py-2 rounded-full border border-brown-400 bg-brown-400 text-white hover:bg-brown-500 transition" onclick="filterProducts('all', this)">Semua</button>
                    <button class="filter-btn px-6 py-2 rounded-full border border-brown-400 text-brown-800 hover:bg-brown-400 hover:text-white transition" onclick="filterProducts('Keju', this)">Topping Keju</button>
                    <button class="filter-btn px-6 py-2 rounded-full border border-brown-400 text-brown-800 hover:bg-brown-400 hover:text-white transition" onclick="filterProducts('Coklat', this)">Topping Coklat</button>
                </div>

                <!-- Product Grid -->
                <div id="product-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Products injected by JS -->
                </div>
            </div>
        </section>

        <!-- ABOUT PAGE -->
        <section id="about" class="page hidden fade-in py-12 px-4 bg-white">
            <div class="max-w-5xl mx-auto">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold text-brown-800 mb-6 font-serif">Tentang LushMelt</h2>
                    <div class="w-24 h-1 bg-gold-400 mx-auto mb-8"></div>
                </div>

                <div class="grid md:grid-cols-2 gap-12 items-center mb-16">
                    <div class="relative">
                        <img src="https://images.unsplash.com/photo-1515037893149-de7f840978e2?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Brownies" class="rounded-lg shadow-xl w-full h-80 object-cover">
                        <div class="absolute -bottom-4 -right-4 bg-gold-400 w-24 h-24 -z-10 rounded-br-3xl"></div>
                        <div class="absolute -top-4 -left-4 border-4 border-brown-400 w-full h-full -z-10 rounded-lg"></div>
                    </div>
                    <div class="text-brown-800">
                        <h3 class="text-2xl font-bold mb-4 font-serif">Cerita Kami</h3>
                        <p class="text-gray-600 leading-relaxed mb-4 text-justify">
                            Brownies lumer adalah varian brownies yang memiliki tekstur lembut di luar namun tetap lumer dan meleleh di bagian dalam. Cokelatnya terasa pekat dan rich, menghasilkan sensasi manis yang pas dan tidak berlebihan.
                        </p>
                        <p class="text-gray-600 leading-relaxed mb-4 text-justify">
                            Saat dipotong, bagian tengah brownies akan mengeluarkan lelehan cokelat yang menggoda. Aromanya harum khas cokelat premium, ditambah permukaan yang sedikit glossy memberikan tampilan yang menggugah selera. Cocok disajikan hangat dengan taburan topping keju dan coklat, brownies lumer menjadi pilihan dessert favorit pecinta cokelat.
                        </p>
                    </div>
                </div>

                <div class="bg-cream-100 rounded-2xl p-8 md:p-12 text-center">
                    <h3 class="text-2xl font-bold mb-8 font-serif text-brown-800">Tim Kami</h3>
                    <div class="flex flex-wrap justify-center gap-8 md:gap-16">
                        <div class="text-center group">
                            <div class="w-32 h-32 bg-white rounded-full mx-auto mb-4 overflow-hidden border-4 border-white shadow-md group-hover:border-gold-400 transition">
                                <img src="https://ui-avatars.com/api/?name=Dhiya+Haura&background=8D6E63&color=fff" alt="Dhiya" class="w-full h-full object-cover">
                            </div>
                            <h4 class="font-bold text-lg">Dhiya Haura</h4>
                            <span class="text-sm text-gold-500 font-semibold">Anggota Tim</span>
                        </div>
                        <div class="text-center group">
                            <div class="w-32 h-32 bg-white rounded-full mx-auto mb-4 overflow-hidden border-4 border-white shadow-md group-hover:border-gold-400 transition">
                                <img src="https://ui-avatars.com/api/?name=Syithbi+Nadlira&background=8D6E63&color=fff" alt="Syithbi" class="w-full h-full object-cover">
                            </div>
                            <h4 class="font-bold text-lg">Syithbi Nadlira Putri</h4>
                            <span class="text-sm text-gold-500 font-semibold">Anggota Tim</span>
                        </div>
                        <div class="text-center group">
                            <div class="w-32 h-32 bg-white rounded-full mx-auto mb-4 overflow-hidden border-4 border-white shadow-md group-hover:border-gold-400 transition">
                                <img src="https://ui-avatars.com/api/?name=Alfan+Widi&background=8D6E63&color=fff" alt="Alfan" class="w-full h-full object-cover">
                            </div>
                            <h4 class="font-bold text-lg">Alfan Widi</h4>
                            <span class="text-sm text-gold-500 font-semibold">Anggota Tim</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- BLOG PAGE (Optional) -->
        <section id="blog" class="page hidden fade-in py-12 px-4">
             <div class="max-w-6xl mx-auto">
                <div class="text-center mb-12">
                    <h2 class="text-3xl font-bold text-brown-800 font-serif">Blog & Inspirasi</h2>
                    <p class="text-gray-500 mt-2">Tips menikmati brownies dan ulasan pelanggan.</p>
                </div>
                <div class="grid md:grid-cols-3 gap-8">
                    <!-- Article 1: Cara Menghangatkan Brownies -->
                    <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition">
                        <img src="https://www.cravebyleena.com/cdn/shop/articles/Brown-in-oven.jpg?v=1727439651&width=1600" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <span class="text-xs text-gold-500 font-bold uppercase">Tips</span>
                            <h3 class="text-lg font-bold mt-2 text-brown-800">Cara Menghangatkan Brownies</h3>
                            <p class="text-gray-600 text-sm mt-2">Agar tetap lumer, hangatkan brownies selama 10 detik di microwave.</p>
                            <a href="#" class="inline-block mt-4 text-brown-500 text-sm font-semibold hover:text-gold-400">Baca Selengkapnya &rarr;</a>
                        </div>
                    </div>
                    <!-- Article 2: Brownies & Kopi -->
                    <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition">
                        <img src="https://i.gojekapi.com/darkroom/gofood-indonesia/v2/images/uploads/66890769-08f9-4e3a-8076-1de2047672c6_Go-Biz_20220119_155238.jpeg?auto=format" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <span class="text-xs text-gold-500 font-bold uppercase">Inspirasi</span>
                            <h3 class="text-lg font-bold mt-2 text-brown-800">Brownies & Kopi</h3>
                            <p class="text-gray-600 text-sm mt-2">Paduan sempurna menikmati sore hari dengan LushMelt dan secangkir kopi pahit.</p>
                            <a href="#" class="inline-block mt-4 text-brown-500 text-sm font-semibold hover:text-gold-400">Baca Selengkapnya &rarr;</a>
                        </div>
                    </div>
                </div>
             </div>
        </section>

        <!-- CHECKOUT FORM PAGE -->
        <section id="checkout" class="page hidden fade-in py-12 px-4 bg-cream-100 min-h-screen">
            <div class="max-w-3xl mx-auto">
                <div class="bg-white rounded-2xl shadow-xl overflow-hidden">
                    <div class="bg-brown-400 p-6 text-center">
                        <h2 class="text-2xl text-white font-serif">Formulir Pemesanan</h2>
                        <p class="text-cream-100 text-sm">Lengkapi data untuk menyelesaikan pesanan.</p>
                    </div>
                    
                    <div class="p-8">
                        <form onsubmit="handleOrderSubmit(event)" class="space-y-6">
                            <div>
                                <label class="block text-brown-800 font-bold mb-2">Nama Lengkap</label>
                                <input type="text" id="order-name" required class="w-full px-4 py-2 border border-brown-200 rounded-lg focus:outline-none focus:ring-2 focus:ring-gold-400 bg-cream-50" placeholder="Masukkan nama Anda">
                            </div>
                            
                            <div>
                                <label class="block text-brown-800 font-bold mb-2">Alamat / Kelas</label>
                                <input type="text" id="order-address" required class="w-full px-4 py-2 border border-brown-200 rounded-lg focus:outline-none focus:ring-2 focus:ring-gold-400 bg-cream-50" placeholder="Contoh: XII.H">
                            </div>

                            <div class="p-4 bg-cream-50 rounded-lg border border-brown-100">
                                <h4 class="font-bold text-brown-800 mb-2">Metode Pembayaran</h4>
                                <p class="text-sm text-gray-600 mb-4">Transfer atau Cash</p>
                                
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                    <div class="text-center p-4 border border-gray-200 rounded bg-white">
                                        <div class="text-lg font-bold text-blue-600 mb-2">QR DANA</div>
                                        <!-- Gambar QR DANA -->
                                        <img src="https://api.qrserver.com/v1/create-qr-code/?size=128x128&data=https%3A%2F%2Flink.dana.id%2Fminta%3Ffull_url%3Dhttps%3A%2F%2Fqr.dana.id%2Fv1%2F281012012022112679774170" alt="QR Code DANA" class="w-32 h-32 object-contain mx-auto mb-2">
                                        <p class="text-xs text-gray-500">Scan untuk bayar via Dana</p>
                                    </div>
                                    <div class="text-center p-4 border border-gray-200 rounded bg-white">
                                        <div class="text-lg font-bold text-gray-800 mb-2">QRIS</div>
                                        <!-- Placeholder QR -->
                                        <img src="https://api.qrserver.com/v1/create-qr-code/?size=128x128&data=https%3A%2F%2Flink.dana.id%2Fminta%3Ffull_url%3Dhttps%3A%2F%2Fqr.dana.id%2Fv1%2F281012012022112679774170" alt="QR Code QRIS" class="w-32 h-32 object-contain mx-auto mb-2">
                                        <p class="text-xs text-gray-500">Scan semua e-wallet</p>
                                    </div>
                                </div>
                                
                                <div class="mt-4 text-center">
                                    <p class="font-bold text-brown-800">Nomor WhatsApp / Cash</p>
                                    <p class="text-gold-500 font-mono text-lg">081387386531</p>
                                </div>
                            </div>

                            <!-- Order Summary in Form -->
                            <div class="border-t pt-4">
                                <h4 class="font-bold text-brown-800 mb-2">Ringkasan Pesanan</h4>
                                <div id="checkout-summary" class="text-sm text-gray-600 space-y-1 mb-2">
                                    <!-- Populated by JS -->
                                </div>
                                <div class="flex justify-between font-bold text-lg text-brown-800 border-t border-dashed border-brown-300 pt-2">
                                    <span>Total Pembayaran:</span>
                                    <span id="checkout-total">Rp 0</span>
                                </div>
                            </div>

                            <div class="flex gap-4 pt-4">
                                <button type="button" onclick="router('shop')" class="w-1/3 py-3 border border-brown-400 text-brown-400 rounded-lg hover:bg-brown-50 transition">Kembali</button>
                                <button type="submit" class="w-2/3 py-3 bg-brown-800 text-white rounded-lg hover:bg-brown-900 transition font-bold shadow-lg">Konfirmasi Pesanan</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Product Detail Modal -->
    <div id="product-modal" class="fixed inset-0 z-[60] hidden overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="flex items-center justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <div class="fixed inset-0 bg-gray-900 bg-opacity-75 transition-opacity" aria-hidden="true" onclick="closeModal()"></div>
            <span class="hidden sm:inline-block sm:align-middle sm:h-screen" aria-hidden="true">&#8203;</span>
            <div class="inline-block align-bottom bg-white rounded-xl text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg w-full">
                <div class="relative">
                     <button onclick="closeModal()" class="absolute top-4 right-4 bg-white rounded-full p-2 shadow-md hover:bg-gray-100 z-10"><i data-lucide="x"></i></button>
                     <img id="modal-img" src="" class="w-full h-64 object-cover">
                </div>
                <div class="px-6 pt-6 pb-8">
                    <div class="flex justify-between items-start mb-4">
                        <div>
                             <h3 class="text-2xl font-bold text-brown-800 font-serif" id="modal-title">Product Name</h3>
                             <p class="text-gold-500 font-semibold text-xl mt-1" id="modal-price">Rp 0</p>
                        </div>
                        <span class="px-3 py-1 bg-cream-100 text-brown-800 text-xs rounded-full uppercase font-bold tracking-wide" id="modal-category">Category</span>
                    </div>
                    <p class="text-gray-600 text-sm leading-relaxed mb-6" id="modal-desc">
                        Deskripsi produk...
                    </p>
                    <button id="modal-add-btn" class="w-full bg-brown-400 text-white font-bold py-3 rounded-lg hover:bg-brown-500 transition shadow-md flex justify-center items-center gap-2">
                        <i data-lucide="shopping-cart" size="18"></i> Tambah ke Keranjang
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Cart Sidebar/Modal -->
    <div id="cart-sidebar" class="fixed inset-0 z-[70] hidden">
        <div class="absolute inset-0 bg-black bg-opacity-50 transition-opacity" onclick="toggleCart()"></div>
        <div class="absolute inset-y-0 right-0 max-w-sm w-full bg-white shadow-xl flex flex-col transform transition-transform duration-300 translate-x-full" id="cart-panel">
            <div class="flex items-center justify-between p-4 border-b border-gray-200 bg-cream-50">
                <h2 class="text-lg font-bold text-brown-800 font-serif">Keranjang Belanja</h2>
                <button onclick="toggleCart()" class="text-gray-500 hover:text-brown-800"><i data-lucide="x"></i></button>
            </div>
            
            <div class="flex-1 overflow-y-auto p-4 space-y-4" id="cart-items">
                <!-- Cart items injected here -->
                <div class="text-center text-gray-500 mt-10">
                    <i data-lucide="shopping-bag" class="mx-auto mb-2 opacity-50" size="48"></i>
                    <p>Keranjang masih kosong.</p>
                </div>
            </div>

            <div class="border-t border-gray-200 p-6 bg-cream-50">
                <div class="flex justify-between text-base font-bold text-brown-800 mb-4">
                    <p>Total</p>
                    <p id="cart-total">Rp 0</p>
                </div>
                <button onclick="proceedToCheckout()" class="w-full flex justify-center items-center px-6 py-3 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-brown-800 hover:bg-brown-900 transition">
                    Pesan Sekarang
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-brown-800 text-cream-100 pt-12 pb-6">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-8">
                <div>
                    <h3 class="text-2xl font-serif font-bold mb-4 text-white">LushMelt<span class="text-gold-400">.</span></h3>
                    <p class="text-sm opacity-80 leading-relaxed">
                        Nikmati kelezatan brownies lumer premium buatan Kelompok 1 XII.H. Manisnya pas, lumernya bikin nagih.
                    </p>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4 text-white">Navigasi</h4>
                    <ul class="space-y-2 text-sm opacity-80">
                        <li><a href="#" onclick="router('home')" class="hover:text-gold-400 transition">Beranda</a></li>
                        <li><a href="#" onclick="router('shop')" class="hover:text-gold-400 transition">Belanja</a></li>
                        <li><a href="#" onclick="router('about')" class="hover:text-gold-400 transition">Tentang Kami</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4 text-white">Kontak</h4>
                    <p class="text-sm opacity-80 flex items-center gap-2 mb-2">
                        <i data-lucide="message-circle" size="16"></i> 081387386531
                    </p>
                    <p class="text-sm opacity-80 flex items-center gap-2">
                        <i data-lucide="map-pin" size="16"></i> Kelas XII.H, SMAN ...
                    </p>
                </div>
            </div>
            <div class="border-t border-brown-500 pt-6 text-center text-xs opacity-60">
                &copy; 2023 Kelompok 1 XII.H LushMelt Brownies. All rights reserved.
            </div>
        </div>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // Initialize Icons
        lucide.createIcons();

        // --- Data ---
        const products = [
            {
                id: 1,
                name: "Brownis Lumer Topping Keju",
                size: "200 ml",
                price: 7000,
                category: "Keju",
                image: "https://cf.shopee.co.id/file/1ca2533cb1a9a08daa4ca025705c6d49",
                description: "Brownies lembut ukuran besar (200ml) dengan limpahan saus cokelat dan parutan keju gurih yang melimpah."
            },
            {
                id: 2,
                name: "Brownis Lumer Topping Coklat",
                size: "200 ml",
                price: 7000,
                category: "Coklat",
                image: "https://filebroker-cdn.lazada.co.id/kf/Se2979a6533da4295b068691c1742fd49m.jpg",
                description: "Brownies ukuran besar (200ml) untuk pecinta cokelat sejati. Double chocolate, double happiness."
            },
            {
                id: 3,
                name: "Brownis Lumer Topping Keju",
                size: "100 ml",
                price: 5000,
                category: "Keju",
                image: "https://cf.shopee.co.id/file/1ca2533cb1a9a08daa4ca025705c6d49",
                description: "Versi mini (100ml) yang pas untuk camilan ringan. Perpaduan manis brownies dan gurihnya keju."
            },
            {
                id: 4,
                name: "Brownis Lumer Coklat",
                size: "100 ml",
                price: 5000,
                category: "Coklat",
                image: "https://filebroker-cdn.lazada.co.id/kf/Se2979a6533da4295b068691c1742fd49m.jpg",
                description: "Versi mini (100ml) dengan rasa cokelat klasik yang lumer di mulut. Hemat dan lezat."
            }
        ];

        let cart = [];

        // --- Initialization ---
        document.addEventListener('DOMContentLoaded', () => {
            renderProducts(products);
            updateCartUI();
        });

        // --- Routing System ---
        function router(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.add('hidden');
            });
            // Show selected page
            const selectedPage = document.getElementById(pageId);
            selectedPage.classList.remove('hidden');
            
            // Scroll to top
            window.scrollTo(0, 0);

            // Re-render icons just in case
            lucide.createIcons();
        }

        // --- Shop Functions ---
        function renderProducts(items) {
            const grid = document.getElementById('product-grid');
            grid.innerHTML = items.map(product => `
                <div class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition duration-300 transform hover:-translate-y-1 group">
                    <div class="relative h-48 overflow-hidden cursor-pointer" onclick="openProductModal(${product.id})">
                        <img src="${product.image}" alt="${product.name}" class="w-full h-full object-cover transition duration-500 group-hover:scale-110">
                        <div class="absolute top-2 right-2 bg-white/90 px-2 py-1 rounded text-xs font-bold text-brown-800 uppercase tracking-wide">
                            ${product.size}
                        </div>
                    </div>
                    <div class="p-5">
                        <div class="text-xs text-gold-500 font-bold mb-1 uppercase tracking-wider">${product.category}</div>
                        <h3 class="text-lg font-bold text-brown-800 mb-2 font-serif cursor-pointer hover:text-gold-400" onclick="openProductModal(${product.id})">${product.name}</h3>
                        <p class="text-gray-500 text-sm mb-4 line-clamp-2">${product.description}</p>
                        <div class="flex items-center justify-between">
                            <span class="text-lg font-bold text-brown-800">Rp ${product.price.toLocaleString('id-ID')}</span>
                            <button onclick="addToCart(${product.id})" class="bg-brown-400 hover:bg-brown-800 text-white p-2 rounded-full transition shadow-md">
                                <i data-lucide="plus" size="20"></i>
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
            lucide.createIcons();
        }

        function filterProducts(category, btn) {
            // Update button styles
            document.querySelectorAll('.filter-btn').forEach(b => {
                b.classList.remove('bg-brown-400', 'text-white');
                b.classList.add('text-brown-800', 'hover:bg-brown-400', 'hover:text-white');
            });
            btn.classList.remove('text-brown-800', 'hover:bg-brown-400');
            btn.classList.add('bg-brown-400', 'text-white');

            // Filter logic
            if (category === 'all') {
                renderProducts(products);
            } else {
                const filtered = products.filter(p => p.category === category);
                renderProducts(filtered);
            }
        }

        // --- Modal System ---
        function openProductModal(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;

            document.getElementById('modal-img').src = product.image;
            document.getElementById('modal-title').innerText = product.name;
            document.getElementById('modal-price').innerText = `Rp ${product.price.toLocaleString('id-ID')}`;
            document.getElementById('modal-category').innerText = product.category + ' - ' + product.size;
            document.getElementById('modal-desc').innerText = product.description;
            
            // Re-bind onclick for the button inside modal
            const btn = document.getElementById('modal-add-btn');
            btn.onclick = function() { addToCart(product.id); closeModal(); };

            document.getElementById('product-modal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('product-modal').classList.add('hidden');
        }

        // --- Cart Logic ---
        function addToCart(id) {
            const product = products.find(p => p.id === id);
            const existingItem = cart.find(item => item.id === id);

            if (existingItem) {
                existingItem.qty++;
            } else {
                cart.push({ ...product, qty: 1 });
            }

            updateCartUI();
            
            // Simple visual feedback
            const cartBtn = document.querySelector('button[onclick="toggleCart()"]');
            cartBtn.classList.add('text-gold-400');
            setTimeout(() => cartBtn.classList.remove('text-gold-400'), 200);
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCartUI();
        }

        function updateQty(id, change) {
            const item = cart.find(item => item.id === id);
            if (item) {
                item.qty += change;
                if (item.qty <= 0) removeFromCart(id);
                else updateCartUI();
            }
        }

        function updateCartUI() {
            const cartContainer = document.getElementById('cart-items');
            const countBadge = document.getElementById('cart-count');
            const totalEl = document.getElementById('cart-total');
            
            // Calculate totals
            const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

            // Update badge
            countBadge.innerText = totalQty;
            countBadge.classList.toggle('hidden', totalQty === 0);

            // Update Total Price Text
            totalEl.innerText = `Rp ${totalPrice.toLocaleString('id-ID')}`;

            // Render Items
            if (cart.length === 0) {
                cartContainer.innerHTML = `
                    <div class="text-center text-gray-400 mt-10">
                        <i data-lucide="shopping-bag" class="mx-auto mb-2" size="48"></i>
                        <p>Keranjang kosong</p>
                    </div>
                `;
            } else {
                cartContainer.innerHTML = cart.map(item => `
                    <div class="flex items-center justify-between bg-cream-50 p-3 rounded-lg border border-brown-100">
                        <div class="flex items-center gap-3">
                            <img src="${item.image}" class="w-12 h-12 rounded object-cover">
                            <div>
                                <h4 class="text-sm font-bold text-brown-800 line-clamp-1">${item.name}</h4>
                                <p class="text-xs text-gold-500">Rp ${item.price.toLocaleString('id-ID')}</p>
                            </div>
                        </div>
                        <div class="flex items-center gap-2">
                            <button onclick="updateQty(${item.id}, -1)" class="w-6 h-6 rounded-full bg-white border border-brown-200 flex items-center justify-center text-xs hover:bg-brown-100">-</button>
                            <span class="text-sm font-semibold w-4 text-center">${item.qty}</span>
                            <button onclick="updateQty(${item.id}, 1)" class="w-6 h-6 rounded-full bg-white border border-brown-200 flex items-center justify-center text-xs hover:bg-brown-100">+</button>
                            <button onclick="removeFromCart(${item.id})" class="ml-2 text-red-400 hover:text-red-600">
                                <i data-lucide="trash-2" size="14"></i>
                            </button>
                        </div>
                    </div>
                `).join('');
            }
            lucide.createIcons();
        }

        function toggleCart() {
            const sidebar = document.getElementById('cart-sidebar');
            const panel = document.getElementById('cart-panel');
            
            if (sidebar.classList.contains('hidden')) {
                sidebar.classList.remove('hidden');
                setTimeout(() => panel.classList.remove('translate-x-full'), 10);
            } else {
                panel.classList.add('translate-x-full');
                setTimeout(() => sidebar.classList.add('hidden'), 300);
            }
        }

        // --- Checkout Logic ---
        function proceedToCheckout() {
            if (cart.length === 0) {
                // Using console.log instead of alert for better UI experience
                console.log("Keranjang belanja Anda masih kosong!"); 
                return;
            }
            toggleCart(); // Close cart
            
            // Populate summary in form
            const summaryContainer = document.getElementById('checkout-summary');
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            
            summaryContainer.innerHTML = cart.map(item => `
                <div class="flex justify-between">
                    <span>${item.name} (${item.qty}x)</span>
                    <span>Rp ${(item.price * item.qty).toLocaleString('id-ID')}</span>
                </div>
            `).join('');
            
            document.getElementById('checkout-total').innerText = `Rp ${totalPrice.toLocaleString('id-ID')}`;

            router('checkout');
        }

        function handleOrderSubmit(e) {
            e.preventDefault();
            const name = document.getElementById('order-name').value;
            const address = document.getElementById('order-address').value;
            
            // Construct WhatsApp Message
            let message = `Halo Kak, saya mau pesan Brownis Lumer LushMelt.%0A%0A`;
            message += `*Nama:* ${name}%0A`;
            message += `*Alamat/Kelas:* ${address}%0A`;
            message += `*Pesanan:*%0A`;
            
            cart.forEach(item => {
                message += `- ${item.name} (${item.qty}x) : Rp ${(item.price * item.qty).toLocaleString('id-ID')}%0A`;
            });
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            message += `*Total Pembayaran:* Rp ${total.toLocaleString('id-ID')}%0A`;
            message += `*Metode:* Transfer/Cash`;

            // Open WhatsApp
            window.open(`https://wa.me/6281387386531?text=${message}`, '_blank');
            
            // Reset Cart
            cart = [];
            updateCartUI();
            router('home');
        }

    </script>
</body>
</html>
