# Ruang-Sastra-Nusantara
Web ini berisi perjalanan sastra di Indonesia, mencakup penjelasan singkat, tokoh, karya, dan cirinya.
DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ruang Sastra</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #d4a574 0%, #8b6f47 100%);
            min-height: 100vh;
        }

        .navbar {
            background: rgba(255, 255, 255, 0.95);
            padding: 1rem 2rem;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #8b6f47;
            /* Letakkan logo BAO kamu di sini */
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #8b6f47;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .section {
            display: none;
            background: white;
            border-radius: 20px;
            padding: 2rem;
            margin-top: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            animation: fadeIn 0.5s;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            color: #8b6f47;
            margin-bottom: 1rem;
            font-size: 2.5rem;
        }

        h2 {
            color: #a0826d;
            margin: 1.5rem 0 1rem;
        }

        .map-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .era-card {
            background: linear-gradient(135deg, #f5deb3 0%, #daa06d 100%);
            padding: 1.5rem;
            border-radius: 15px;
            cursor: pointer;
            transition: transform 0.3s, box-shadow 0.3s;
            text-align: center;
        }

        .era-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        .era-card h3 {
            color: #333;
            margin-bottom: 0.5rem;
        }

        .era-card p {
            color: #666;
            font-size: 0.9rem;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 20px;
            max-width: 600px;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
        }

        .close-btn {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: #8b6f47;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1rem;
        }

        .quiz-container {
            margin-top: 2rem;
        }

        .question {
            background: #f0f0f0;
            padding: 1.5rem;
            border-radius: 10px;
            margin-bottom: 1rem;
        }

        .options {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .option {
            background: white;
            padding: 1rem;
            border-radius: 10px;
            cursor: pointer;
            transition: background 0.3s;
            border: 2px solid transparent;
        }

        .option:hover {
            background: #e0e0e0;
        }

        .option.correct {
            background: #90EE90;
            border-color: #28a745;
        }

        .option.wrong {
            background: #FFB6C6;
            border-color: #dc3545;
        }

        .score {
            text-align: center;
            font-size: 1.5rem;
            color: #8b6f47;
            margin-top: 1rem;
        }

        .btn {
            background: #8b6f47;
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1rem;
            margin-top: 1rem;
            transition: background 0.3s;
        }

        .btn:hover {
            background: #6d563a;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .contact-btn {
            display: inline-block;
            background: #8b6f47;
            color: white;
            padding: 1rem 2rem;
            border-radius: 10px;
            text-decoration: none;
            transition: background 0.3s;
        }

        .contact-btn:hover {
            background: #6d563a;
        }

        .logo img {
  width: 120px;
  height: auto;
}
  
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-content">
            <div class="logo">
                <img src="logo.png">
            </div>
            <ul class="nav-links">
                <li><a href="#" onclick="showSection('beranda')">Beranda</a></li>
                <li><a href="#" onclick="showSection('about')">About Me</a></li>
                <li><a href="#" onclick="showSection('contact')">Contact</a></li>
            </ul>
        </div>
    </nav>

    <div class="container">
        <!-- Beranda Section -->
        <div id="beranda" class="section active">
            <h1>🗺️ Ruang Sastra</h1>
            <p style="font-size: 1.1rem; color: #666; margin-bottom: 2rem;">
                Mari jelajahi perjalanan sastra Indonesia dari masa ke masa dengan klik setiap angkatan untuk mengetahui sejarah, tokoh, dan karya-karya terkenalnya.
            </p>

            <div class="map-container">
                <div class="era-card" onclick="showEraDetail('pujangga')">
                    <h3>Pujangga Lama</h3>
                    <p>Sebelum 1900-an</p>
                </div>
                <div class="era-card" onclick="showEraDetail('balai')">
                    <h3>Balai Pustaka</h3>
                    <p>1920-1942</p>
                </div>
                <div class="era-card" onclick="showEraDetail('pujangga-baru')">
                    <h3>Pujangga Baru</h3>
                    <p>1933-1942</p>
                </div>
                <div class="era-card" onclick="showEraDetail('45')">
                    <h3>Angkatan 45</h3>
                    <p>1945-1950-an</p>
                </div>
                <div class="era-card" onclick="showEraDetail('66')">
                    <h3> Angkatan 66</h3>
                    <p>1966-1970-an</p>
                </div>
                <div class="era-card" onclick="showEraDetail('reformasi')">
                    <h3> Era Reformasi</h3>
                    <p>1998-Sekarang</p>
                </div>
            </div>

            <button class="btn" onclick="showSection('quiz')">🎮 Main Kuis Sastra!</button>
        </div>

        <!-- About Me Section -->
        <div id="about" class="section">
            <h1>About Me</h1>
            <p style="font-size: 1.1rem; color: #666; line-height: 1.8;">
                Halo! Saya Naya N.T seorang pelajar yang sedang tertarik dengan sastra Indonesia,
                website ini saya buat untuk memudahkan teman-teman belajar mengetahui tentang bagaimana perkembangan 
                sastra Indonesia dengan cara yang lebih seru.
            </p>
            <p style="font-size: 1.1rem; color: #666; line-height: 1.8; margin-top: 1rem;">
                Semoga website ini dapat membantu kalian memahami sastra Indonesia dengan lebih mudah 
                dan menyenangkan!
            </p>
        </div>

        <!-- Contact Section -->
        <div id="contact" class="section">
            <h1>Contact</h1>
            <p style="font-size: 1.1rem; color: #666; margin-bottom: 2rem;">
                Ada pertanyaan atau saran? Hubungi aku di:
            </p>
            <div class="contact-links">
                <a href="mailto:naya.nthaniah@gmail.com" class="contact-btn">Email</a>
                <a href="https://instagram.com/nythneea" target="_blank" class="contact-btn">Instagram</a>
            </div>
        </div>

        <!-- Quiz Section -->
        <div id="quiz" class="section">
            <h1>🎮 Kuis Sastra Indonesia</h1>
            <p style="color: #666; margin-bottom: 2rem;">Tes pengetahuanmu tentang sastra Indonesia!</p>
            <div class="quiz-container" id="quizContainer"></div>
            <div class="score" id="scoreDisplay"></div>
            <button class="btn" onclick="resetQuiz()">🔄 Main Lagi</button>
            <button class="btn" onclick="showSection('beranda')">🏠 Kembali</button>
        </div>
    </div>

    <!-- Modal -->
    <div id="modal" class="modal">
        <div class="modal-content">
            <button class="close-btn" onclick="closeModal()">✖ Tutup</button>
            <div id="modalContent"></div>
        </div>
    </div>

    <script>
        const eraData = {
            'pujangga': {
                title: 'Sastra Pujangga Lama',
                period: 'Sebelum 1900-an',
                description: 'Sastra Pujangga Lama adalah sastra tradisional Indonesia yang berkembang sebelum masuknya pengaruh Barat. Sastra ini umumnya berbentuk lisan dan diwariskan turun-temurun.',
                tokoh: ['Raja Ali Haji', 'Hamzah Fansuri', 'Ronggowarsito'],
                karya: [
                    'Gurindam Dua Belas - Raja Ali Haji',
                    'Syair Perahu - Hamzah Fansuri',
                    'Serat Kalatidha - Ronggowarsito'
                ],
                ciri: 'Menggunakan bahasa Melayu klasik, disebarkan secara lisan, dan berbentuk seperti pantun, syair, serta hikayat.'
            },
            'balai': {
                title: 'Angkatan Balai Pustaka',
                period: '1920-1942',
                description: 'Balai Pustaka adalah lembaga penerbit yang didirikan pemerintah kolonial Belanda. Karya-karyanya menceritakan kehidupan masyarakat dengan tema adat istiadat dan kritik sosial.',
                tokoh: ['Marah Rusli', 'Sitti Nurbaya', 'Merari Siregar', 'Abdul Muis'],
                karya: [
                    'Sitti Nurbaya (1922) - Marah Rusli',
                    'Azab dan Sengsara (1920) - Merari Siregar',
                    'Salah Asuhan (1928) - Abdul Muis'
                ],
                ciri: 'Tema konflik adat, bahasa Melayu-Indonesia baku, alur sederhana, latar lokal Nusantara, dan diterbitkan oleh Balai Pustaka'
            },
            'pujangga-baru': {
                title: 'Pujangga Baru',
                period: '1933-1942',
                description: 'Angkatan Pujangga Baru muncul sebagai reaksi terhadap Balai Pustaka. Mereka lebih bebas dalam berkarya dan mengangkat tema nasionalisme serta cinta tanah air.',
                tokoh: ['Sutan Takdir Alisjahbana', 'Armijn Pane', 'Amir Hamzah', 'Sanusi Pane'],
                karya: [
                    'Layar Terkembang - Roman, Sutan Takdir Alisjahbana',
                    'Nyanyi Sunyi - Amir Hamzah',
                    'Belenggu - Armijn Pane, Roman'
                ],
                ciri: 'Semangat nasionalisme, bahasa lebih bebas dan puitis, tema cinta tanah air dan modernisasi'
            },
            '45': {
                title: 'Angkatan 45',
                period: '1945-1950-an',
                description: 'Angkatan 45 lahir setelah kemerdekaan Indonesia. Karya-karyanya dipenuhi semangat perjuangan, revolusi, dan idealisme kebangsaan.',
                tokoh: ['Chairil Anwar', 'Idrus', 'Pramoedya Ananta Toer', 'Asrul Sani'],
                karya: [
                    'Aku - Chairil Anwar (puisi)',
                    'Krandji dan Bekasi Djatoeh - Pramoedya Ananta Toer',
                    'Surabaya - Idrus'
                ],
                ciri: 'Semangat revolusi, bahasa lugas dan dinamis, tema perjuangan dan humanisme universal'
            },
            '66': {
                title: 'Angkatan 66',
                period: '1966-1970-an',
                description: 'Angkatan 66 muncul setelah peristiwa G30S/PKI. Sastrawan angkatan ini lebih mengutamakan keindahan bahasa dan kebebasan berekspresi.',
                tokoh: ['W.S. Rendra', 'Taufiq Ismail', 'Sapardi Djoko Damono', 'Goenawan Mohamad'],
                karya: [
                    'Blues untuk Bonnie - W.S. Rendra',
                    'Tirani - Taufiq Ismail',
                    'Aku Ingin - Sapardi Djoko Damono'
                ],
                ciri: 'Tema sosial-politik, eksperimen bentuk dan bahasa, kritis terhadap kekuasaan'
            },
            'reformasi': {
                title: 'Sastra Era Reformasi',
                period: '1998-Sekarang',
                description: 'Sastra era reformasi berkembang dengan sangat beragam. Muncul banyak penulis muda dengan genre dan gaya penulisan yang lebih variatif dan bebas.',
                tokoh: ['Andrea Hirata', 'Dee Lestari', 'Tere Liye', 'Raditya Dika'],
                karya: [
                    'Laskar Pelangi - Andrea Hirata',
                    'Perahu Kertas - Dee Lestari',
                    'Hafalan Shalat Delisa - Tere Liye',
                    'Kambing Jantan - Raditya Dika'
                ],
                ciri: 'Sangat beragam, tema populer dan relatable, pengaruh media sosial, genre chicklit dan teenlit'
            }
        };

        const quizQuestions = [
            {
                question: 'Siapa penulis novel "Sitti Nurbaya"?',
                options: ['Marah Rusli', 'Abdul Muis', 'Chairil Anwar', 'Pramoedya Ananta Toer'],
                correct: 0
            },
            {
                question: 'Puisi "Aku" yang terkenal ditulis oleh siapa?',
                options: ['W.S. Rendra', 'Chairil Anwar', 'Taufiq Ismail', 'Sapardi Djoko Damono'],
                correct: 1
            },
            {
                question: 'Novel "Laskar Pelangi" bercerita tentang kehidupan di daerah mana?',
                options: ['Jakarta', 'Surabaya', 'Belitung', 'Padang'],
                correct: 2
            },
            {
                question: 'Angkatan sastra yang muncul setelah kemerdekaan Indonesia adalah?',
                options: ['Angkatan 45', 'Pujangga Baru', 'Balai Pustaka', 'Angkatan 66'],
                correct: 0
            },
            {
                question: 'Siapa penulis "Nyanyi Sunyi"?',
                options: ['Armijn Pane', 'Amir Hamzah', 'Sanusi Pane', 'Sutan Takdir Alisjahbana'],
                correct: 1
            }
        ];

        let currentScore = 0;
        let answeredQuestions = [];

        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
            document.getElementById(sectionId).classList.add('active');
            
            if (sectionId === 'quiz') {
                loadQuiz();
            }
        }

        function showEraDetail(era) {
            const data = eraData[era];
            const content = `
                <h2>${data.title}</h2>
                <p><strong>Periode:</strong> ${data.period}</p>
                <p style="margin: 1rem 0; line-height: 1.6;">${data.description}</p>
                
                <h3 style="color: #8b6f47; margin-top: 1.5rem;">📖 Tokoh Terkenal:</h3>
                <ul style="margin: 0.5rem 0; padding-left: 1.5rem;">
                    ${data.tokoh.map(t => `<li style="margin: 0.3rem 0;">${t}</li>`).join('')}
                </ul>
                
                <h3 style="color: #8b6f47; margin-top: 1.5rem;">✨ Karya Terkenal:</h3>
                <ul style="margin: 0.5rem 0; padding-left: 1.5rem;">
                    ${data.karya.map(k => `<li style="margin: 0.3rem 0;">${k}</li>`).join('')}
                </ul>
                
                <h3 style="color: #8b6f47; margin-top: 1.5rem;">🎯 Ciri Khas:</h3>
                <p style="margin: 0.5rem 0; line-height: 1.6;">${data.ciri}</p>
            `;
            
            document.getElementById('modalContent').innerHTML = content;
            document.getElementById('modal').classList.add('active');
        }

        function closeModal() {
            document.getElementById('modal').classList.remove('active');
        }

        function loadQuiz() {
            currentScore = 0;
            answeredQuestions = [];
            document.getElementById('scoreDisplay').textContent = '';
            
            const container = document.getElementById('quizContainer');
            container.innerHTML = quizQuestions.map((q, idx) => `
                <div class="question">
                    <h3>Pertanyaan ${idx + 1}</h3>
                    <p style="margin: 0.5rem 0;">${q.question}</p>
                    <div class="options">
                        ${q.options.map((opt, optIdx) => `
                            <div class="option" onclick="checkAnswer(${idx}, ${optIdx})">
                                ${String.fromCharCode(65 + optIdx)}. ${opt}
                            </div>
                        `).join('')}
                    </div>
                </div>
            `).join('');
        }

        function checkAnswer(questionIdx, selectedIdx) {
            if (answeredQuestions.includes(questionIdx)) return;
            
            const question = quizQuestions[questionIdx];
            const options = document.querySelectorAll(`.question:nth-child(${questionIdx + 1}) .option`);
            
            if (selectedIdx === question.correct) {
                options[selectedIdx].classList.add('correct');
                currentScore++;
            } else {
                options[selectedIdx].classList.add('wrong');
                options[question.correct].classList.add('correct');
            }
            
            answeredQuestions.push(questionIdx);
            
            if (answeredQuestions.length === quizQuestions.length) {
                setTimeout(() => {
                    document.getElementById('scoreDisplay').textContent = 
                        `🎉 Skor kamu: ${currentScore}/${quizQuestions.length}`;
                }, 500);
            }
        }

        function resetQuiz() {
            loadQuiz();
        }
    </script>
</body>
</html>
