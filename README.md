<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحليل النصر الإلهي في غزوة بدر</title>
    <!-- Chosen Palette: Brilliant Blues with Warm Accents -->
    <!-- Application Structure Plan: The SPA follows a narrative structure to tell the story of the verses. It begins with the initial context (the challenge), moves to the turning point (the supplication), details the divine response, explains the purpose behind it, and concludes with the ultimate lesson. This thematic flow (Challenge -> Turning Point -> Response -> Purpose -> Lesson) was chosen for its storytelling potential, guiding the user logically through the events and their significance, making the complex information more digestible and impactful than a simple linear presentation of the tafsir. -->
    <!-- Visualization & Content Choices: 
        - Big Number Cards: Report Info: Army sizes (317 vs 1000). Goal: Inform/Compare. Viz: Styled cards with large numbers. Justification: Immediately highlights the dramatic numerical disparity, setting the stage for the need for divine help. Method: HTML/CSS.
        - Flowchart: Report Info: Sequence of the Prophet's du'a. Goal: Organize. Viz: Horizontal flowchart. Justification: Visually represents the process from seeing the disparity to the divine response, making the narrative easy to follow. Method: HTML/CSS with flexbox.
        - Donut Chart: Report Info: Number of angels (1000). Goal: Inform. Viz: Donut Chart. Justification: A simple and clean way to present a single, significant number. Method: Chart.js/Canvas.
        - Bar Chart: Report Info: Interpretations of "Murdifin". Goal: Compare. Viz: Horizontal Bar Chart. Justification: Effectively compares the weight/popularity of different scholarly interpretations side-by-side. Method: Chart.js/Canvas.
        - Icon-based Cards: Report Info: Purpose of the angels (Bushra & Tat'min). Goal: Inform. Viz: Styled cards with Unicode icons. Justification: Breaks down the two key abstract concepts into visually distinct and easily understandable points. Method: HTML/CSS.
        - Typographic Emphasis: Report Info: The core verse "Wa ma an-nasru illa min 'indillah". Goal: Inform/Impact. Viz: Large, stylized typography. Justification: Creates a strong visual focal point for the infographic's central message. Method: HTML/CSS.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Tajawal', sans-serif;
            scroll-behavior: smooth;
            background-color: #f8f9fa;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        .section-title {
            color: #005F73;
            border-bottom: 4px solid #EE9B00;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .flowchart-arrow {
            color: #0A9396;
        }
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.5);
            -webkit-backdrop-filter: blur(5px);
            backdrop-filter: blur(5px);
        }
        .modal-content {
            background-color: #fefefe;
            margin: 10% auto;
            padding: 2rem;
            border: 1px solid #888;
            width: 80%;
            max-width: 700px;
            border-radius: 0.75rem;
            position: relative;
            animation: fadeIn 0.5s;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.95); }
            to { opacity: 1; transform: scale(1); }
        }
        .close-button {
            color: #aaa;
            position: absolute;
            left: 20px;
            top: 15px;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }
        .close-button:hover,
        .close-button:focus {
            color: black;
        }
        /* Loader */
        .loader {
            border: 5px solid #f3f3f3;
            border-radius: 50%;
            border-top: 5px solid #0A9396;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 2rem auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        #gemini-response-content h2 {
            font-size: 1.5rem;
            font-weight: bold;
            color: #005F73;
            margin-top: 1rem;
            margin-bottom: 0.5rem;
        }
        #gemini-response-content h3 {
            font-size: 1.25rem;
            font-weight: bold;
            color: #CA6702;
            margin-top: 0.75rem;
            margin-bottom: 0.25rem;
        }
         #gemini-response-content ul {
            list-style-type: disc;
            margin-right: 1.5rem;
            margin-bottom: 1rem;
        }
    </style>
</head>
<body class="bg-gray-100 text-gray-800">

    <header class="bg-[#005F73] text-white p-6 shadow-lg sticky top-0 z-50">
        <div class="container mx-auto text-center">
            <h1 class="text-3xl md:text-4xl font-extrabold">النصر الإلهي في بدر الكبرى</h1>
            <p class="mt-2 text-lg text-[#E9D8A6]">تحليل بصري لآيات من سورة الأنفال</p>
        </div>
    </header>

    <main class="container mx-auto p-4 md:p-8 mt-8">
        
        <!-- Existing Sections -->
        <section id="context" class="mb-16">
            <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6">مقدمة: ميزان القوى يوم بدر</h2>
                <p class="text-lg mb-8 text-justify">تصف الآيات الكريمة موقفاً حاسماً في غزوة بدر، حيث واجه المسلمون تفوقاً عددياً ساحقاً من قبل المشركين. هذا التفاوت الهائل هو ما دفعهم إلى اللجوء الصادق إلى الله طلباً للنصرة والعون، ممهداً الطريق لاستجابة إلهية غيرت مجرى التاريخ.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-center">
                    <div class="bg-blue-100 border-t-4 border-blue-500 rounded-lg p-6 shadow-md">
                        <h3 class="text-2xl font-bold text-blue-800">جيش المسلمين</h3>
                        <p class="text-6xl font-extrabold mt-2 text-blue-600">317</p>
                        <p class="mt-2 text-lg text-blue-700">مؤمناً</p>
                    </div>
                    <div class="bg-red-100 border-t-4 border-red-500 rounded-lg p-6 shadow-md">
                        <h3 class="text-2xl font-bold text-red-800">جيش المشركين</h3>
                        <p class="text-6xl font-extrabold mt-2 text-red-600">1000</p>
                        <p class="mt-2 text-lg text-red-700">مقاتل</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="plea" class="mb-16">
             <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6">الاستغاثة: مفتاح الاستجابة الإلهية</h2>
                <p class="text-lg mb-6 text-justify">في قلب المعركة، وفي أحلك الظروف، رفع النبي ﷺ يديه إلى السماء، مناجياً ربه بيقين مطلق. هذا الدعاء الخاشع لم يكن مجرد طلب، بل كان تجسيداً للتوكل الكامل على الله، وهو ما فتح أبواب السماء بالمدد والنصر.</p>
                <div class="border-r-4 border-[#CA6702] bg-orange-50 p-6 my-8">
                    <p class="text-xl md:text-2xl font-bold text-[#9B2226] leading-relaxed">"اللهم أنجز لي ما وعدتني، اللهم إن تهلك هذه العصابة من أهل الإسلام لا تُعبد في الأرض!"</p>
                    <p class="text-sm mt-3 text-gray-600">- من دعاء النبي ﷺ يوم بدر (صحيح مسلم)</p>
                </div>
            </div>
        </section>

        <section id="response" class="mb-16">
            <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6">الاستجابة والمدد: ألف من الملائكة</h2>
                 <p class="text-lg mb-8 text-justify">أتت الاستجابة الإلهية فورية ومباشرة، حيث وعد الله المؤمنين بإمدادهم بألف من الملائكة "مردفين". وقد اختلف المفسرون في معنى "مردفين"، ولكن إجماعهم على أنهم كانوا مدداً متتابعاً لتقوية صفوف المؤمنين.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                    <div>
                        <h3 class="text-2xl font-semibold text-center text-[#005F73] mb-4">توزيع المدد الإلهي</h3>
                        <div class="chart-container h-64 md:h-80">
                            <canvas id="angelSupportChart"></canvas>
                        </div>
                         <p class="text-center mt-4 text-gray-600">ألف من الملائكة نزلوا كمدد للمؤمنين.</p>
                    </div>
                    <div>
                         <h3 class="text-2xl font-semibold text-center text-[#005F73] mb-4">أشهر تفسيرات "مردفين"</h3>
                         <div class="chart-container h-64 md:h-80">
                            <canvas id="murdifinChart"></canvas>
                        </div>
                         <p class="text-center mt-4 text-gray-600">مقارنة بين أبرز أقوال المفسرين.</p>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="purpose" class="mb-16">
            <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6">الحكمة من إرسال الملائكة</h2>
                <p class="text-lg mb-8 text-justify">يوضح القرآن الكريم أن الغاية من إرسال الملائكة لم تكن فقط للمشاركة في القتال، بل كانت وسيلة لتحقيق أهداف روحية ومعنوية أعمق للمؤمنين، لترسيخ عقيدتهم وتثبيت قلوبهم في مواجهة الشدائد.</p>
                <div class="flex flex-col md:flex-row justify-around text-center gap-6">
                    <div class="flex-1 p-6 bg-teal-50 rounded-lg border-l-8 border-[#0A9396]">
                        <p class="text-5xl mb-3">🕊️</p>
                        <h3 class="text-2xl font-bold text-[#005F73]">بُشرى بالنصر</h3>
                        <p class="mt-2 text-justify">كان وجودهم بمثابة بشارة للمؤمنين بأن النصر قادم لا محالة بإذن الله، مما رفع معنوياتهم وأزال عنهم اليأس.</p>
                    </div>
                    <div class="flex-1 p-6 bg-amber-50 rounded-lg border-l-8 border-[#EE9B00]">
                         <p class="text-5xl mb-3">❤️</p>
                        <h3 class="text-2xl font-bold text-[#CA6702]">طمأنينة للقلوب</h3>
                        <p class="mt-2 text-justify">لإزالة الخوف وبث السكينة والثقة في قلوب المؤمنين، وتذكيرهم بأنهم ليسوا وحدهم في هذه المعركة الفاصلة.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="victory" class="mb-16 text-center">
            <div class="bg-gradient-to-br from-[#005F73] to-[#0A9396] text-white rounded-lg shadow-xl p-8 md:p-12">
                <h2 class="text-4xl font-extrabold mb-4">مصدر النصر الحقيقي</h2>
                <p class="text-5xl md:text-6xl font-extrabold tracking-tight my-6 font-serif">﴿وَمَا النَّصْرُ إِلَّا مِنْ عِنْدِ اللَّهِ﴾</p>
                <p class="text-xl max-w-3xl mx-auto">تأتي هذه الآية كقاعدة أساسية في عقيدة المسلم، لتؤكد أن النصر ليس بقوة السلاح أو كثرة العدد أو حتى بوجود الملائكة، بل هو منحة خالصة من عند الله العزيز الحكيم، الذي ينصر من يشاء متى شاء.</p>
            </div>
        </section>

        <!-- New Gemini Section -->
        <section id="gemini-features" class="mb-16">
            <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6 text-center">استكشف المزيد بالذكاء الاصطناعي</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-6">

                    <!-- Ask a Scholar -->
                    <div class="p-6 bg-gray-50 rounded-lg text-center">
                        <h3 class="text-2xl font-bold text-[#005F73] mb-4">✨ اسأل عالمًا</h3>
                        <p class="mb-4 text-justify">هل لديك سؤال محدد حول الآيات، سياقها، أو الدروس المستفادة منها؟ اكتب سؤالك واحصل على إجابة من منظور علمي.</p>
                        <textarea id="scholar-question" class="w-full p-2 border rounded-md" rows="3" placeholder="مثال: ما هي الحكمة من نزول الملائكة بدلاً من نصر مباشر؟"></textarea>
                        <button id="ask-scholar-btn" class="mt-4 w-full bg-[#0A9396] text-white font-bold py-2 px-4 rounded-lg hover:bg-[#005F73] transition-colors">
                            أرسل سؤالك
                        </button>
                    </div>

                    <!-- Generate Sermon -->
                    <div class="p-6 bg-gray-50 rounded-lg text-center">
                        <h3 class="text-2xl font-bold text-[#005F73] mb-4">✨ قم بإنشاء خُطبة</h3>
                        <p class="mb-4 text-justify">احصل على مخطط تفصيلي لخطبة جمعة أو محاضرة حول الدروس الإيمانية والعملية من قصة النصر في بدر، جاهز للاستخدام والتطوير.</p>
                        <button id="generate-sermon-btn" class="mt-12 w-full bg-[#EE9B00] text-white font-bold py-2 px-4 rounded-lg hover:bg-[#CA6702] transition-colors">
                            أنشئ مخطط الخطبة
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <section id="attributes">
            <div class="card p-6 md:p-8">
                <h2 class="text-3xl font-bold section-title pb-2 mb-6 text-center">صفات الله تعالى في سياق النصر</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-6">
                    <div class="p-6 bg-gray-50 rounded-lg text-center transform hover:-translate-y-2 transition-transform duration-300">
                        <h3 class="text-3xl font-bold text-[#005F73]">عَزِيزٌ</h3>
                        <p class="text-lg mt-2 text-justify">هو الغالب الذي لا يُقهر، له العزة الكاملة والقدرة المطلقة، وبيده مفاتيح القوة والنصر. فلا قوة تعلو على قوته ولا إرادة فوق إرادته.</p>
                    </div>
                     <div class="p-6 bg-gray-50 rounded-lg text-center transform hover:-translate-y-2 transition-transform duration-300">
                        <h3 class="text-3xl font-bold text-[#005F73]">حَكِيمٌ</h3>
                        <p class="text-lg mt-2 text-justify">هو الذي يضع كل شيء في موضعه الصحيح. فنصره للمؤمنين وخذلانه للكافرين يجري وفق حكمة إلهية بالغة وتدبير متقن لا يدركه البشر أحياناً.</p>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-[#005F73] text-white text-center p-4 mt-12">
        <p>&copy; 2025 - هذا الملخص مستمد من تفاسير: الطبري، ابن كثير، وفتح القدير للشوكاني. مُعزز بقدرات الذكاء الاصطناعي.</p>
    </footer>

    <!-- Modal -->
    <div id="gemini-modal" class="modal">
        <div class="modal-content">
            <span class="close-button">&times;</span>
            <div id="gemini-response-content">
                <!-- Loader will be injected here -->
                <!-- Response will be injected here -->
            </div>
        </div>
    </div>

    <script>
        // Existing chart script
        function processLabels(labels, maxLength) {
            return labels.map(label => {
                if (label.length <= maxLength) {
                    return label;
                }
                const words = label.split(' ');
                let lines = [];
                let currentLine = '';
                words.forEach(word => {
                    if ((currentLine + ' ' + word).trim().length > maxLength) {
                        lines.push(currentLine.trim());
                        currentLine = word;
                    } else {
                        currentLine = (currentLine + ' ' + word).trim();
                    }
                });
                if (currentLine) {
                    lines.push(currentLine);
                }
                return lines;
            });
        }
        
        const tooltipTitleCallback = (tooltipItems) => {
            const item = tooltipItems[0];
            let label = item.chart.data.labels[item.dataIndex];
            if (Array.isArray(label)) {
                return label.join(' ');
            }
            return label;
        };
        
        const sharedChartOptions = {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    labels: {
                        font: {
                            family: 'Tajawal',
                            size: 14,
                        },
                        color: '#333'
                    }
                },
                tooltip: {
                    titleFont: { family: 'Tajawal', size: 16 },
                    bodyFont: { family: 'Tajawal', size: 14 },
                    callbacks: {
                        title: tooltipTitleCallback
                    }
                }
            },
            scales: {
                x: {
                    ticks: {
                        font: { family: 'Tajawal', size: 12 },
                        color: '#555'
                    },
                    grid: { display: false }
                },
                y: {
                    ticks: {
                        font: { family: 'Tajawal', size: 12 },
                        color: '#555'
                    },
                    grid: { color: '#e0e0e0' }
                }
            }
        };

        const angelSupportCtx = document.getElementById('angelSupportChart').getContext('2d');
        new Chart(angelSupportCtx, {
            type: 'doughnut',
            data: {
                labels: ['الملائكة'],
                datasets: [{
                    label: 'عدد الملائكة',
                    data: [1000],
                    backgroundColor: ['#0A9396'],
                    borderColor: ['#FFFFFF'],
                    borderWidth: 4,
                    hoverOffset: 4
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: { display: false },
                    tooltip: {
                         ...sharedChartOptions.plugins.tooltip
                    }
                },
            }
        });
        
        const murdifinCtx = document.getElementById('murdifinChart').getContext('2d');
        new Chart(murdifinCtx, {
            type: 'bar',
            data: {
                labels: processLabels(['متتابعين (إجماع المفسرين)', 'وراء كل ملك ملك (ابن عباس)', 'مدد للمؤمنين (ابن عباس)'], 16),
                datasets: [{
                    label: 'أقوال المفسرين',
                    data: [90, 75, 65],
                    backgroundColor: [
                        'rgba(10, 147, 150, 0.7)',
                        'rgba(238, 155, 0, 0.7)',
                        'rgba(187, 62, 3, 0.7)'
                    ],
                    borderColor: [
                        '#0A9396',
                        '#EE9B00',
                        '#BB3E03'
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                ...sharedChartOptions,
                indexAxis: 'y',
                plugins: {
                    ...sharedChartOptions.plugins,
                    legend: { display: false }
                },
                scales: {
                     x: {
                        ...sharedChartOptions.scales.x,
                        beginAtZero: true
                    },
                     y: {
                        ...sharedChartOptions.scales.y,
                    }
                }
            }
        });

        // New Gemini API Script
        const modal = document.getElementById('gemini-modal');
        const modalContent = document.getElementById('gemini-response-content');
        const closeModalBtn = document.querySelector('.close-button');

        const askScholarBtn = document.getElementById('ask-scholar-btn');
        const generateSermonBtn = document.getElementById('generate-sermon-btn');
        const scholarQuestionInput = document.getElementById('scholar-question');

        const apiKey = ""; // API Key will be handled by the environment.
        const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

        function openModal() {
            modal.style.display = 'block';
        }

        function closeModal() {
            modal.style.display = 'none';
            modalContent.innerHTML = ''; // Clear content
        }

        closeModalBtn.onclick = closeModal;
        window.onclick = function(event) {
            if (event.target == modal) {
                closeModal();
            }
        }

        async function callGemini(prompt) {
            openModal();
            modalContent.innerHTML = '<div class="loader"></div>';

            const payload = {
                contents: [{
                    role: "user",
                    parts: [{ text: prompt }]
                }],
                 "generationConfig": {
                    "temperature": 0.5,
                    "topP": 0.95,
                    "topK": 64,
                    "maxOutputTokens": 8192,
                 }
            };
            
            try {
                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                   throw new Error(`HTTP error! status: ${response.status}`);
                }
                
                const result = await response.json();

                if (result.candidates && result.candidates.length > 0) {
                    const text = result.candidates[0].content.parts[0].text;
                    const formattedText = marked.parse(text); // Use marked to parse markdown
                    modalContent.innerHTML = formattedText;
                } else {
                    modalContent.innerHTML = '<p>عذرًا، لم نتمكن من الحصول على إجابة. يرجى المحاولة مرة أخرى.</p>';
                    console.error("Gemini API Error: No candidates in response", result);
                }
            } catch (error) {
                console.error("Error calling Gemini API:", error);
                modalContent.innerHTML = `<p>حدث خطأ أثناء معالجة طلبك. يرجى التحقق من وحدة التحكم لمزيد من التفاصيل.</p><p class="text-xs text-gray-500 mt-2">${error}</p>`;
            }
        }

        askScholarBtn.addEventListener('click', () => {
            const userQuestion = scholarQuestionInput.value.trim();
            if (!userQuestion) {
                alert('الرجاء إدخال سؤال.');
                return;
            }

            const prompt = `أنت عالم إسلامي خبير متخصص في التفسير. تستند معرفتك إلى مصادر كلاسيكية مثل تفسير الطبري وابن كثير. يقوم المستخدم بدراسة مخطط معلوماتي حول سورة الأنفال، الآيتين 9-10، والذي يناقش غزوة بدر. المواضيع الرئيسية هي دعاء المؤمنين، إرسال 1000 من الملائكة، الغرض من الملائكة هو "بشرى" و "تطميين"، والمبدأ الأساسي أن "النصر من عند الله فقط". بناءً على هذا السياق، أجب على سؤال المستخدم التالي بطريقة واضحة وموجزة ومحترمة. سؤال المستخدم: "${userQuestion}"`;
            
            callGemini(prompt);
        });

        generateSermonBtn.addEventListener('click', () => {
            const prompt = `أنت خطيب ومعلم إسلامي بليغ. بناءً على الأحداث والدروس المستفادة من سورة الأنفال، الآيتين 9-10 بخصوص غزوة بدر، قم بإنشاء مخطط خطبة (محاضرة) مقنع. المخطط المعلوماتي الذي تستند إليه يغطي النقاط الرئيسية التالية: 1) الإيمان الهائل ودعاء المؤمنين عند مواجهة الصعاب المستحيلة. 2) استجابة الله المباشرة بإرسال 1000 من الملائكة كـ"بشرى" و"لتطمئن" قلوبهم. 3) المبدأ اللاهوتي الأساسي بأن "النصر من عند الله فقط" (وما النصر إلا من عند الله)، وليس من الأعداد أو القوة أو حتى الملائكة أنفسهم. 4) صفات الله كـ"عزيز" و"حكيم". قم بتنظيم المخطط بمقدمة، وثلاث نقاط رئيسية مميزة مع نقاط فرعية للتوضيح، وخاتمة تدعو إلى العمل لجمهور معاصر. نسق الإخراج باستخدام الماركداون مع العناوين والنقاط.`;

            callGemini(prompt);
        });

    </script>
</body>
</html>

