# levetiracetam
Сравнение противоэпилептических препаратов
<!DOCTYPE html>
<html lang="ru" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Интерактивное сравнение противоэпилептических препаратов</title>
    <!-- Chosen Palette: Clinical Professional -->
    <!-- Application Structure Plan: A single-page, scrollable application with a sticky navigation bar for quick access to thematic sections. The structure follows a logical narrative: introduction, mechanism, spectrum, interactions, side effects, and special risks. This thematic, top-down approach was chosen over mirroring the report's linear slide structure to allow users to quickly jump to the information they need, facilitating easier comparison and better usability. Interactive charts and styled cards are used to make complex data digestible. -->
    <!-- Visualization & Content Choices: 1. Mechanism: Report Info -> How drugs work -> Goal: Organize -> Viz: HTML/CSS flow diagrams -> Interaction: Hover effects -> Justification: Visually separates and clarifies the multi-step process for each drug better than text. -> Method: Tailwind CSS. 2. Spectrum: Report Info -> Drug effectiveness range -> Goal: Compare -> Viz: Horizontal Bar Chart -> Interaction: Tooltips -> Justification: Immediately communicates the "broad" vs. "narrow" concept. -> Library: Chart.js. 3. Side Effects: Report Info -> Common adverse effects -> Goal: Compare/Relationships -> Viz: Radar Chart -> Interaction: Tooltips, legend filtering -> Justification: Best for multi-variate comparison, showing the unique "profile" of each drug's side effects. -> Library: Chart.js. 4. Risks: Report Info -> Major warnings -> Goal: Inform -> Viz: Styled "alert" cards -> Interaction: Hover effects -> Justification: Color and icons draw attention to critical safety information. -> Method: Tailwind CSS. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8FAFC;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
                max-height: 400px;
            }
        }
        .nav-link {
            transition: color 0.3s, border-color 0.3s;
        }
    </style>
</head>
<body class="text-slate-800">

    <header class="sticky top-0 bg-white/80 backdrop-blur-lg shadow-sm z-50">
        <nav class="container mx-auto px-6 py-3">
            <ul class="flex justify-center space-x-4 sm:space-x-8 text-sm sm:text-base">
                <li><a href="#mechanism" class="nav-link text-slate-600 hover:text-blue-600 border-b-2 border-transparent hover:border-blue-600 pb-1">Механизм</a></li>
                <li><a href="#spectrum" class="nav-link text-slate-600 hover:text-blue-600 border-b-2 border-transparent hover:border-blue-600 pb-1">Спектр</a></li>
                <li><a href="#interactions" class="nav-link text-slate-600 hover:text-blue-600 border-b-2 border-transparent hover:border-blue-600 pb-1">Взаимодействия</a></li>
                <li><a href="#side-effects" class="nav-link text-slate-600 hover:text-blue-600 border-b-2 border-transparent hover:border-blue-600 pb-1">Побочные эффекты</a></li>
                <li><a href="#risks" class="nav-link text-slate-600 hover:text-blue-600 border-b-2 border-transparent hover:border-blue-600 pb-1">Особые риски</a></li>
            </ul>
        </nav>
    </header>

    <main class="container mx-auto p-4 md:p-8">

        <section id="intro" class="text-center py-16">
            <h1 class="text-4xl md:text-5xl font-bold text-slate-900 mb-4">Сравнение противоэпилептических препаратов</h1>
            <p class="text-lg text-slate-600 max-w-3xl mx-auto">Интерактивный анализ ключевых различий между Леветирацетамом, Карбамазепином и Вальпроевой кислотой для более глубокого понимания их клинических профилей.</p>
        </section>

        <div id="mechanism" class="pt-16">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-900">Механизм действия</h2>
            <p class="text-center text-slate-600 mb-12 max-w-3xl mx-auto">Каждый препарат использует уникальную стратегию для стабилизации нейронной активности и предотвращения эпилептических приступов. Понимание этих механизмов является ключом к выбору правильной терапии.</p>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-white p-6 rounded-xl shadow-md border-t-4 border-blue-500">
                    <h3 class="text-xl font-bold mb-4 text-center text-blue-600">Леветирацетам</h3>
                    <p class="text-slate-600 text-sm text-center mb-4">Связывается с белком SV2A в синаптических везикулах, модулируя высвобождение нейротрансмиттеров и снижая избыточную нейронную активность.</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md border-t-4 border-red-500">
                    <h3 class="text-xl font-bold mb-4 text-center text-red-600">Карбамазепин</h3>
                    <p class="text-slate-600 text-sm text-center mb-4">Блокирует натриевые каналы, стабилизируя мембраны нейронов и предотвращая возникновение повторных высокочастотных разрядов.</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md border-t-4 border-amber-500">
                    <h3 class="text-xl font-bold mb-4 text-center text-amber-600">Вальпроевая кислота</h3>
                    <p class="text-slate-600 text-sm text-center mb-4">Обладает многофакторным действием: повышает уровень ГАМК (тормозящего нейротрансмиттера) и блокирует натриевые/кальциевые каналы.</p>
                </div>
            </div>
        </div>

        <div id="spectrum" class="pt-24">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-900">Спектр действия</h2>
            <p class="text-center text-slate-600 mb-12 max-w-3xl mx-auto">Эффективность препарата напрямую зависит от его спектра действия. Препараты широкого спектра эффективны против многих типов приступов, в то время как узкоспектральные препараты могут даже усугублять некоторые из них.</p>
            <div class="bg-white p-6 rounded-xl shadow-md">
                <div class="chart-container h-[250px] md:h-[300px]">
                    <canvas id="spectrumChart"></canvas>
                </div>
            </div>
        </div>

        <div id="interactions" class="pt-24">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-900">Лекарственные взаимодействия</h2>
            <p class="text-center text-slate-600 mb-12 max-w-3xl mx-auto">Взаимодействие с ферментами печени (система цитохрома P450) определяет, как препараты влияют на метаболизм других лекарств, что критически важно при сопутствующей терапии.</p>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-white p-6 rounded-xl shadow-md text-center">
                    <div class="text-5xl mb-4">🕊️</div>
                    <h3 class="text-xl font-bold mb-2 text-blue-600">Леветирацетам</h3>
                    <p class="font-semibold text-lg text-slate-800">Минимальные</p>
                    <p class="text-slate-500 mt-2">Не влияет на ферменты печени, что делает его наиболее безопасным для комбинированной терапии.</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md text-center">
                    <div class="text-5xl mb-4">⏩</div>
                    <h3 class="text-xl font-bold mb-2 text-red-600">Карбамазепин</h3>
                    <p class="font-semibold text-lg text-slate-800">Индуктор ферментов</p>
                    <p class="text-slate-500 mt-2">Ускоряет метаболизм других лекарств, снижая их эффективность.</p>
                </div>
                <div class="bg-white p-6 rounded-xl shadow-md text-center">
                    <div class="text-5xl mb-4">⏪</div>
                    <h3 class="text-xl font-bold mb-2 text-amber-600">Вальпроевая кислота</h3>
                    <p class="font-semibold text-lg text-slate-800">Ингибитор ферментов</p>
                    <p class="text-slate-500 mt-2">Замедляет метаболизм других препаратов, повышая их концентрацию и риск токсичности.</p>
                </div>
            </div>
        </div>

        <div id="side-effects" class="pt-24">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-900">Профиль побочных эффектов</h2>
            <p class="text-center text-slate-600 mb-12 max-w-3xl mx-auto">Каждый препарат имеет свой уникальный профиль побочных эффектов. Эта диаграмма сравнивает их относительную выраженность в ключевых категориях, помогая визуализировать потенциальные риски.</p>
            <div class="bg-white p-6 rounded-xl shadow-md">
                <div class="chart-container">
                    <canvas id="sideEffectsChart"></canvas>
                </div>
            </div>
        </div>

        <div id="risks" class="pt-24">
            <h2 class="text-3xl font-bold text-center mb-4 text-slate-900">Особые риски</h2>
            <p class="text-center text-slate-600 mb-12 max-w-3xl mx-auto">Помимо общих побочных эффектов, существуют специфические, серьезные риски, требующие особого внимания при назначении и приеме этих препаратов.</p>
            <div class="space-y-6">
                <div class="bg-blue-50 border-l-4 border-blue-500 p-6 rounded-r-lg">
                    <h4 class="font-bold text-lg text-blue-800">Леветирацетам: Психиатрические расстройства</h4>
                    <p class="text-blue-700 mt-2">Может вызывать или усугублять раздражительность, агрессию, депрессию и перепады настроения. Требует тщательного мониторинга психоэмоционального состояния пациента.</p>
                </div>
                <div class="bg-red-50 border-l-4 border-red-500 p-6 rounded-r-lg">
                    <h4 class="font-bold text-lg text-red-800">Карбамазепин: Синдром Стивенса-Джонсона</h4>
                    <p class="text-red-700 mt-2">Существует риск развития тяжелых, угрожающих жизни кожных реакций. Риск особенно высок у носителей гена HLA-B*1502 в азиатских популяциях.</p>
                </div>
                <div class="bg-amber-50 border-l-4 border-amber-500 p-6 rounded-r-lg">
                    <h4 class="font-bold text-lg text-amber-800">Вальпроевая кислота: Тератогенность</h4>
                    <p class="text-amber-700 mt-2">Высокий риск врожденных дефектов плода (особенно дефектов нервной трубки) при приеме во время беременности. Противопоказан женщинам репродуктивного возраста без надежной контрацепции.</p>
                </div>
            </div>
        </div>
    </main>

    <footer class="text-center mt-16 py-8 border-t border-slate-200">
        <p class="text-slate-500 text-sm max-w-4xl mx-auto px-4">Данная информация носит исключительно образовательный характер и не является медицинской рекомендацией. Выбор противоэпилептического препарата должен осуществляться только квалифицированным врачом на основе полной клинической картины и индивидуальных особенностей пациента.</p>
    </footer>

    <script>
        const tooltipTitleCallback = (tooltipItems) => {
            const item = tooltipItems[0];
            let label = item.chart.data.labels[item.dataIndex];
            if (Array.isArray(label)) {
                return label.join(' ');
            }
            return label;
        };

        const wrapLabel = (label) => {
            const max_width = 16;
            if (label.length <= max_width) {
                return label;
            }
            const words = label.split(' ');
            const lines = [];
            let currentLine = '';
            for (const word of words) {
                if ((currentLine + ' ' + word).trim().length > max_width) {
                    lines.push(currentLine.trim());
                    currentLine = word;
                } else {
                    currentLine = (currentLine + ' ' + word).trim();
                }
            }
            if (currentLine) {
                lines.push(currentLine.trim());
            }
            return lines;
        };

        const spectrumCtx = document.getElementById('spectrumChart').getContext('2d');
        new Chart(spectrumCtx, {
            type: 'bar',
            data: {
                labels: ['Леветирацетам', 'Карбамазепин', 'Вальпроевая кислота'],
                datasets: [{
                    data: [90, 50, 100],
                    backgroundColor: ['#3B82F6', '#EF4444', '#F59E0B'],
                    borderRadius: 4,
                    barPercentage: 0.6,
                }]
            },
            options: {
                indexAxis: 'y',
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    x: {
                        beginAtZero: true,
                        max: 100,
                        ticks: {
                            callback: (value) => {
                                if (value === 50) return 'Узкий';
                                if (value === 100) return 'Широкий';
                                return '';
                            },
                            font: { size: 12, weight: '600' },
                            color: '#475569'
                        },
                        grid: { color: '#E2E8F0' }
                    },
                    y: {
                        ticks: { font: { size: 14 }, color: '#1E293B' },
                        grid: { display: false }
                    }
                },
                plugins: {
                    legend: { display: false },
                    tooltip: {
                        callbacks: {
                            title: tooltipTitleCallback,
                            label: (context) => {
                                let val = context.raw;
                                let label = '';
                                if (val >= 90) label = 'Широкий спектр';
                                else label = 'Узкий спектр';
                                return label;
                            }
                        }
                    }
                }
            }
        });

        const sideEffectsCtx = document.getElementById('sideEffectsChart').getContext('2d');
        const sideEffectsLabels = [
            'Поведенческие эффекты', 'Неврологические эффекты', 'Метаболические эффекты', 
            'Системные риски', 'Лекарственные взаимодействия'
        ].map(wrapLabel);
        
        new Chart(sideEffectsCtx, {
            type: 'radar',
            data: {
                labels: sideEffectsLabels,
                datasets: [
                    {
                        label: 'Леветирацетам',
                        data: [5, 3, 1, 2, 1],
                        backgroundColor: 'rgba(59, 130, 246, 0.2)',
                        borderColor: '#3B82F6',
                        pointBackgroundColor: '#3B82F6',
                        borderWidth: 2
                    },
                    {
                        label: 'Карбамазепин',
                        data: [2, 5, 2, 4, 5],
                        backgroundColor: 'rgba(239, 68, 68, 0.2)',
                        borderColor: '#EF4444',
                        pointBackgroundColor: '#EF4444',
                        borderWidth: 2
                    },
                    {
                        label: 'Вальпроевая кислота',
                        data: [2, 3, 5, 5, 4],
                        backgroundColor: 'rgba(245, 158, 11, 0.2)',
                        borderColor: '#F59E0B',
                        pointBackgroundColor: '#F59E0B',
                        borderWidth: 2
                    }
                ]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                scales: {
                    r: {
                        angleLines: { color: '#CBD5E1' },
                        grid: { color: '#E2E8F0' },
                        pointLabels: { font: { size: 12 }, color: '#334155' },
                        suggestedMin: 0,
                        suggestedMax: 5,
                        ticks: { display: false, stepSize: 1 }
                    }
                },
                plugins: {
                    legend: { position: 'top', labels: { color: '#1E293B' } },
                    tooltip: {
                         callbacks: {
                            title: tooltipTitleCallback
                        }
                    }
                }
            }
        });
    </script>
</body>
</html>
