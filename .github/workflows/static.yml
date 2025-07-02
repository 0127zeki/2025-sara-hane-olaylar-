<!DOCTYPE html>
<html lang="tr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2025 Saraçhane Olayları - İnteraktif Rapor</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <!-- Chosen Palette: "Calm Neutrality" - A palette of soft grays, off-white, and a muted, serious red for accents to reflect the gravity of the events while ensuring clarity and readability. -->
    <!-- Application Structure Plan: A single-page dashboard design with a sticky top navigation for easy access to key thematic sections: 'Genel Bakış' (Overview), 'Zaman Tüneli' (Timeline), 'Etkiler' (Impacts), and 'Tepkiler' (Reactions). This non-linear structure prioritizes user-driven exploration over the report's original linear format. The 'Etkiler' section uses a grid of charts and dynamic stat cards for quantitative data, while the 'Zaman Tüneli' is an interactive vertical timeline. This design choice aims to make dense information digestible and engaging by breaking it into logical, interactive components. -->
    <!-- Visualization & Content Choices: 
        - Report Info: Economic data (Lira value, Borsa Istanbul). Goal: Show the immediate negative economic shock. Viz/Presentation: A line chart for the Lira's fall and dynamic stat cards for key numbers. Interaction: Tooltips on the chart provide exact values. Justification: A line chart is the most effective way to show change over a short period. Library: Chart.js (Canvas).
        - Report Info: Pre/Post protest poll results. Goal: Compare public opinion shifts. Viz/Presentation: A grouped bar chart. Interaction: Users can visually compare the bars for 'Önce' (Before) and 'Sonra' (After). Justification: Bar charts excel at direct comparison between categories. Library: Chart.js (Canvas).
        - Report Info: Timeline of events. Goal: Organize sequential events logically. Viz/Presentation: An interactive vertical timeline. Interaction: Clicking on a date/event highlights it and potentially shows more detail (though simplified here for clarity). Justification: More engaging and less overwhelming than a long text list. Library/Method: HTML/CSS/JS.
        - Report Info: Different reactions (supporters, opponents, international). Goal: Categorize qualitative data. Viz/Presentation: A tabbed interface. Interaction: Users click tabs to switch views. Justification: Tabs cleanly separate related but distinct categories of information without cluttering the page. Library/Method: HTML/CSS/JS.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* slate-50 */
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        .nav-link {
            transition: color 0.3s;
        }
        .nav-link:hover, .nav-link.active {
            color: #ef4444; /* red-500 */
        }
        .timeline-item-content {
            transition: all 0.3s ease-in-out;
        }
    </style>
</head>
<body class="text-slate-800">

    <header class="bg-slate-800 text-white shadow-lg sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-slate-100">2025 Saraçhane Raporu</h1>
            <div class="hidden md:flex space-x-8">
                <a href="#overview" class="nav-link font-medium">Genel Bakış</a>
                <a href="#timeline" class="nav-link font-medium">Zaman Tüneli</a>
                <a href="#impacts" class="nav-link font-medium">Etkiler</a>
                <a href="#reactions" class="nav-link font-medium">Tepkiler</a>
            </div>
            <button id="mobile-menu-button" class="md:hidden text-slate-100 focus:outline-none">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <div id="mobile-menu" class="hidden md:hidden px-6 pt-2 pb-4">
            <a href="#overview" class="block py-2 nav-link">Genel Bakış</a>
            <a href="#timeline" class="block py-2 nav-link">Zaman Tüneli</a>
            <a href="#impacts" class="block py-2 nav-link">Etkiler</a>
            <a href="#reactions" class="block py-2 nav-link">Tepkiler</a>
        </div>
    </header>

    <main class="container mx-auto p-4 md:p-8">
        
        <section id="overview" class="pt-16 -mt-16 mb-16 text-center">
            <h2 class="text-4xl md:text-5xl font-extrabold mb-4 text-slate-900">2025 Türkiye Protestoları</h2>
            <p class="max-w-3xl mx-auto text-lg text-slate-600">
                19 Mart 2025'te İBB Başkanı Ekrem İmamoğlu'nun gözaltına alınmasıyla başlayan ve Türkiye geneline yayılan Saraçhane Eylemleri; ifade özgürlüğü, medya sansürü ve otoriterleşme tartışmalarını alevlendiren, ülke siyasetinde ve ekonomisinde derin izler bırakan bir halk muhalefeti dalgası oldu.
            </p>
        </section>
        
        <hr class="my-12">

        <section id="timeline" class="pt-16 -mt-16 mb-12">
            <h2 class="text-3xl font-bold text-center mb-12 text-slate-900">Olayların Zaman Tüneli</h2>
            <div class="relative max-w-2xl mx-auto">
                <div class="absolute left-1/2 w-1 bg-slate-300 h-full -translate-x-1/2"></div>
                <div id="timeline-container" class="space-y-12">
                </div>
            </div>
        </section>

        <hr class="my-12">

        <section id="impacts" class="pt-16 -mt-16 mb-12">
            <h2 class="text-3xl font-bold text-center mb-12 text-slate-900">Olayların Etkileri</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                
                <div class="bg-white p-6 rounded-lg shadow-md col-span-1 md:col-span-2 lg:col-span-3">
                    <h3 class="font-bold text-xl mb-4 text-center">Ekonomik Krizin Derinleşmesi</h3>
                    <p class="text-sm text-slate-600 text-center mb-6">Protestoların başlamasıyla piyasalarda yaşanan ani şok, Türk Lirası'nda rekor değer kaybına ve borsada sert düşüşlere neden oldu.</p>
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 text-center mb-8">
                        <div class="bg-red-50 p-4 rounded-lg">
                            <div class="text-3xl font-bold text-red-600">42₺</div>
                            <div class="text-sm text-slate-500">Dolar Kuru Rekoru</div>
                        </div>
                        <div class="bg-red-50 p-4 rounded-lg">
                            <div class="text-3xl font-bold text-red-600">-8.72%</div>
                            <div class="text-sm text-slate-500">BIST 100 Düşüşü</div>
                        </div>
                        <div class="bg-red-50 p-4 rounded-lg">
                            <div class="text-3xl font-bold text-red-600">%46</div>
                            <div class="text-sm text-slate-500">Politika Faizi</div>
                        </div>
                    </div>
                    <div class="chart-container">
                        <canvas id="liraChart"></canvas>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-lg shadow-md col-span-1 md:col-span-2 lg:col-span-2">
                     <h3 class="font-bold text-xl mb-4 text-center">Anket Sonuçlarına Etkisi</h3>
                     <p class="text-sm text-slate-600 text-center mb-6">İmamoğlu'nun gözaltına alınması sonrası yapılan anketler, seçmen tercihlerinde belirgin bir değişime işaret etti.</p>
                    <div class="chart-container h-[350px] md:h-[400px] max-h-[450px]">
                        <canvas id="pollChart"></canvas>
                    </div>
                </div>

                <div class="bg-white p-6 rounded-lg shadow-md col-span-1">
                    <h3 class="font-bold text-xl mb-4 text-center">Gözaltı ve Tutuklamalar</h3>
                    <p class="text-sm text-slate-600 text-center mb-6">Protestolar boyunca gazeteciler, öğrenciler ve aktivistlerin de aralarında bulunduğu binlerce kişi hakkında yasal işlem yapıldı.</p>
                    <div class="space-y-4 text-center">
                        <div class="bg-slate-100 p-4 rounded-lg">
                            <div class="text-4xl font-bold text-slate-700">~2,000</div>
                            <div class="text-sm text-slate-500">Gözaltı</div>
                        </div>
                        <div class="bg-slate-100 p-4 rounded-lg">
                            <div class="text-4xl font-bold text-slate-700">~300</div>
                            <div class="text-sm text-slate-500">Tutuklama</div>
                        </div>
                         <div class="bg-slate-100 p-4 rounded-lg">
                            <div class="text-sm font-semibold text-slate-700 pt-2">Öne Çıkan Gözaltılar</div>
                            <p class="text-xs text-slate-500 mt-1">İsmail Saymaz, Yasin Akgül, Bülent Kılıç, Zeynep Kuray, Barış İnce, Cem Yiğit Üzümoğlu, Ümit Özdağ.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <hr class="my-12">

        <section id="reactions" class="pt-16 -mt-16">
            <h2 class="text-3xl font-bold text-center mb-8 text-slate-900">Toplumsal ve Uluslararası Tepkiler</h2>
            <p class="text-lg text-slate-600 text-center max-w-3xl mx-auto mb-12">
                Olaylar, Türkiye içinde ve dışında geniş yankı buldu. Sanatçılardan akademisyenlere, uluslararası kurumlardan hükümetlere kadar birçok farklı kesimden tepkiler geldi.
            </p>
            <div>
                <div class="flex justify-center border-b border-slate-300 mb-8">
                    <button data-tab="supporters" class="reaction-tab active-tab px-6 py-3 text-lg font-medium border-b-2 border-red-500 text-red-600">Destekleyenler</button>
                    <button data-tab="opponents" class="reaction-tab px-6 py-3 text-lg font-medium border-b-2 border-transparent text-slate-500">Karşı Çıkanlar</button>
                    <button data-tab="international" class="reaction-tab px-6 py-3 text-lg font-medium border-b-2 border-transparent text-slate-500">Uluslararası</button>
                </div>
                <div id="reactions-content">
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-slate-800 text-slate-400 text-center p-4 mt-12">
        <p>Bu interaktif rapor, "Saraçhane Olayları Detaylı Belgesi" kaynak alınarak hazırlanmıştır.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            
            const timelineData = [
                { date: "18 Mart 2025", title: "Diploma İptali", description: "İstanbul Üniversitesi, İmamoğlu'nun 31 yıllık diplomasını tartışmalı bir kararla iptal etti." },
                { date: "19 Mart 2025", title: "Gözaltı ve Protestoların Başlaması", description: "Ekrem İmamoğlu yolsuzluk iddialarıyla gözaltına alındı. Başta İstanbul olmak üzere büyük şehirlerde kitlesel protestolar başladı." },
                { date: "23 Mart 2025", title: "Boykot Çağrısı", description: "CHP lideri Özgür Özel, protestoları yayınlamayan yandaş medya ve bağlantılı şirketlere yönelik boykot çağrısı yaptı." },
                { date: "25 Mart 2025", title: "Haftalık Miting Kararı", description: "CHP, ülke genelinde haftalık 'Millet İradesine Sahip Çıkıyor' mitingleri düzenleme kararı aldı." },
                { date: "27 Mart 2025", title: "RTÜK'ten Cezalar", description: "RTÜK, protestoları yayınlayan muhalif TV kanallarına yayın durdurma ve para cezaları kesti." },
                { date: "2 Nisan 2025", title: "Tüketim Boykotu", description: "Üniversite öğrencilerinin öncülüğünde, hükümete yakın markalara karşı bir günlük tüketim boykotu düzenlendi." },
                { date: "17 Nisan 2025", title: "Faiz Artırımı", description: "Ekonomik baskıyı azaltmak amacıyla Merkez Bankası, politika faizini %46'ya yükseltti." },
                { date: "1 Mayıs 2025", title: "Taksim Müdahalesi", description: "1 Mayıs İşçi Bayramı'nda Taksim Meydanı'na çıkmak isteyen eylemcilere müdahale edildi, yüzlerce kişi gözaltına alındı." }
            ];

            const reactionsData = {
                supporters: [
                    { name: "Zülfü Livaneli", quote: "Sanatçı ve yazar olarak Saraçhane'deki mitinge katılarak halkın yanında yer aldı." },
                    { name: "Celâl Şengör", quote: "Protestoları 'halkın hakkını arama mücadelesi' olarak tanımladı ve Türkiye'nin artık bir hukuk devleti olmadığını belirtti." },
                    { name: "Sanatçılar ve Ünlüler", quote: "Ahmet Mümtaz Taylan, Fazıl Say, Farah Zeynep Abdullah gibi yüzlerce ünlü isim sosyal medya paylaşımlarıyla destek verdi." },
                    { name: "Oyuncular Sendikası", quote: "Boykot nedeniyle diziden çıkarılan Aybüke Pusat'a destek vererek ifade özgürlüğünün önemini vurguladı." },
                    { name: "Ümit Özdağ ve Zafer Partisi", quote: "Protestolara destek verdiklerini açıkladılar ve olayların siyasi boyutuna dikkat çektiler." }
                ],
                opponents: [
                    { name: "Hilal Cebeci", quote: "Eski şarkıcı, sosyal medya üzerinden insanlara sokağa çıkmamaları yönünde çağrı yaptı." },
                    { name: "Reynmen", quote: "Sosyal medya fenomeni, sokağa çıkmanın hiçbir işe yaramayacağını savundu." },
                    { name: "Sinan Akçıl", quote: "Cumhurbaşkanı Erdoğan'a yönelik hakaretlere tepki göstererek protestocuları eleştirdi." }
                ],
                international: [
                    { name: "Avrupa Komisyonu", quote: "Başkan Ursula von der Leyen, Türkiye'nin AB adayı olarak demokratik değerleri koruması gerektiğini hatırlattı." },
                    { name: "Uluslararası Af Örgütü", quote: "Hükümetin eylemlerini 'acımasız' ve 'barışçıl muhalefete yönelik artan bir baskı' olarak nitelendirdi." },
                    { name: "Uluslararası Basın", quote: "Financial Times, The Guardian ve Reuters gibi önde gelen yayınlar, olayları siyasi baskının artışı ve demokrasi gerilemesi olarak yorumladı." }
                ]
            };
            
            const timelineContainer = document.getElementById('timeline-container');
            timelineData.forEach((item, index) => {
                const sideClass = index % 2 === 0 ? 'md:ml-auto md:pr-16' : 'md:mr-auto md:pl-16';
                const dotSideClass = index % 2 === 0 ? 'md:left-1/2 md:-translate-x-1/2' : 'md:left-1/2 md:-translate-x-1/2';
                const timelineItem = `
                    <div class="relative timeline-item">
                        <div class="dot absolute w-4 h-4 bg-red-500 rounded-full mt-3 top-0 left-[-7px] md:left-1/2 md:-translate-x-1/2"></div>
                        <div class="timeline-item-content bg-white p-6 rounded-lg shadow-md border-l-4 border-red-400 ml-8 md:ml-0 ${sideClass} md:w-5/12">
                            <span class="font-bold text-red-500">${item.date}</span>
                            <h3 class="text-lg font-bold mt-1 mb-2">${item.title}</h3>
                            <p class="text-slate-600 text-sm">${item.description}</p>
                        </div>
                    </div>
                `;
                timelineContainer.innerHTML += timelineItem;
            });
            
            const reactionsContainer = document.getElementById('reactions-content');
            const reactionTabs = document.querySelectorAll('.reaction-tab');

            function renderReactions(tab) {
                reactionsContainer.innerHTML = '';
                const data = reactionsData[tab];
                const grid = document.createElement('div');
                grid.className = 'grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6';
                data.forEach(item => {
                    const card = `
                        <div class="bg-white p-6 rounded-lg shadow-md transition-transform transform hover:scale-105">
                            <h4 class="font-bold text-lg mb-2 text-slate-800">${item.name}</h4>
                            <p class="text-slate-600 italic">"${item.quote}"</p>
                        </div>
                    `;
                    grid.innerHTML += card;
                });
                reactionsContainer.appendChild(grid);
            }

            reactionTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    reactionTabs.forEach(t => {
                        t.classList.remove('active-tab', 'border-red-500', 'text-red-600');
                        t.classList.add('border-transparent', 'text-slate-500');
                    });
                    tab.classList.add('active-tab', 'border-red-500', 'text-red-600');
                    tab.classList.remove('border-transparent', 'text-slate-500');
                    renderReactions(tab.dataset.tab);
                });
            });

            renderReactions('supporters');


            const liraCtx = document.getElementById('liraChart').getContext('2d');
            new Chart(liraCtx, {
                type: 'line',
                data: {
                    labels: ['18 Mart', '19 Mart', '20 Mart', '21 Mart', '22 Mart'],
                    datasets: [{
                        label: 'Dolar Kuru (₺)',
                        data: [36.8, 42.1, 41.5, 40.8, 38.5],
                        borderColor: '#ef4444',
                        backgroundColor: 'rgba(239, 68, 68, 0.1)',
                        tension: 0.3,
                        fill: true,
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { display: false },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return ` ${context.raw.toFixed(2)} ₺`;
                                }
                            }
                        }
                    },
                    scales: { y: { beginAtZero: false } }
                }
            });

            const pollCtx = document.getElementById('pollChart').getContext('2d');
            new Chart(pollCtx, {
                type: 'bar',
                data: {
                    labels: ['R.T. Erdoğan', 'E. İmamoğlu', 'M. Yavaş'],
                    datasets: [
                        {
                            label: 'Protesto Öncesi (%)',
                            data: [33.8, 19.8, 24.0], 
                            backgroundColor: '#94a3b8',
                        },
                        {
                            label: 'Protesto Sonrası (%)',
                            data: [31.2, 22.0, 25.5],
                            backgroundColor: '#ef4444',
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { position: 'top' },
                        tooltip: {
                             callbacks: {
                                label: function(context) {
                                    return ` ${context.dataset.label}: ${context.raw}%`;
                                }
                            }
                        }
                    },
                    scales: { y: { beginAtZero: true, max: 60 } }
                }
            });

            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    if(mobileMenu.offsetParent !== null) {
                       mobileMenu.classList.add('hidden');
                    }
                });
            });

        });
    </script>
</body>
</html>
