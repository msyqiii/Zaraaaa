<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zaraaa's Love Dashboard 🌸</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            min-height: 100vh;
            background: linear-gradient(135deg, #ffeef8 0%, #ffd3eb 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
            position: relative;
        }

        /* Elemen Ornamen Latar Belakang untuk Efek Glassmorphism Hidup */
        body::before, body::after {
            content: '';
            position: absolute;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff9ebb, #ff6b81);
            z-index: 1;
            opacity: 0.6;
            filter: blur(10px);
        }
        body::before {
            width: 150px;
            height: 150px;
            top: 15%;
            left: 10%;
            animation: floatBall 6s ease-in-out infinite alternate;
        }
        body::after {
            width: 250px;
            height: 250px;
            bottom: 10%;
            right: 5%;
            animation: floatBall 8s ease-in-out infinite alternate-reverse;
        }

        @keyframes floatBall {
            0% { transform: translateY(0px) rotate(0deg); }
            100% { transform: translateY(20px) rotate(15deg); }
        }

        /* Dashboard Container dengan Efek Glassmorphism Premium */
        .dashboard {
            width: 100%;
            max-width: 450px;
            background: rgba(255, 255, 255, 0.45);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.6);
            border-radius: 30px;
            padding: 25px;
            box-shadow: 0 20px 40px rgba(255, 107, 129, 0.15);
            z-index: 10;
            position: relative;
        }

        header {
            text-align: center;
            margin-bottom: 25px;
        }

        header h1 {
            color: #ff4757;
            font-size: 1.8rem;
            margin-bottom: 5px;
        }

        header p {
            color: #7f8c8d;
            font-size: 0.9rem;
        }

        /* --- FITUR 1: LEVEL BUCIN PROGRESS BAR --- */
        .bucin-container {
            background: rgba(255, 255, 255, 0.6);
            padding: 15px;
            border-radius: 20px;
            margin-bottom: 20px;
            border: 1px solid rgba(255, 255, 255, 0.4);
        }

        .bucin-label {
            display: flex;
            justify-content: space-between;
            font-size: 0.85rem;
            font-weight: 600;
            color: #ff4757;
            margin-bottom: 8px;
        }

        .progress-bar-bg {
            width: 100%;
            height: 14px;
            background: rgba(255, 182, 193, 0.4);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
            margin-bottom: 12px;
        }

        .progress-bar-fill {
            width: 50%;
            height: 100%;
            background: linear-gradient(90deg, #ff7675, #ff4757);
            border-radius: 10px;
            transition: width 0.3s ease;
        }

        .bucin-slider {
            width: 100%;
            -webkit-appearance: none;
            appearance: none;
            background: transparent;
            cursor: pointer;
        }

        .bucin-slider::-webkit-slider-runnable-track {
            background: rgba(255, 255, 255, 0.8);
            height: 6px;
            border-radius: 3px;
        }

        .bucin-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            height: 18px;
            width: 18px;
            border-radius: 50%;
            background: #ff4757;
            margin-top: -6px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        /* Card Menu Umum */
        .card {
            background: rgba(255, 255, 255, 0.6);
            border-radius: 20px;
            padding: 20px;
            margin-bottom: 15px;
            border: 1px solid rgba(255, 255, 255, 0.4);
            text-align: center;
        }

        .card h3 {
            color: #2c3e50;
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        /* Efek Transisi Halus pada Teks Alasan */
        #teks-alasan {
            font-size: 0.95rem;
            color: #57606f;
            min-height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: opacity 0.2s ease;
            line-height: 1.4;
            padding: 0 10px;
        }

        .btn {
            background: linear-gradient(135deg, #ff6b81 0%, #ff4757 100%);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 15px;
            font-weight: 600;
            font-size: 0.9rem;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            box-shadow: 0 5px 15px rgba(255, 107, 129, 0.2);
            margin-top: 10px;
        }

        .btn:active {
            transform: scale(0.95);
        }

        .btn-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
        }

        .btn-danger {
            background: linear-gradient(135deg, #ee5253 0%, #ff4757 100%);
        }

        /* --- FITUR 2: EFEK HUJAN HATI --- */
        .floating-heart {
            position: fixed;
            font-size: 24px;
            animation: flyUp 2s linear forwards;
            pointer-events: none;
            z-index: 9999;
        }

        @keyframes flyUp {
            0% {
                transform: translateY(100vh) translateX(0) scale(0.5);
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) translateX(var(--random-x)) scale(1.3);
                opacity: 0;
            }
        }

        /* --- FITUR 4: CUSTOM TOAST NOTIFICATION --- */
        .custom-toast {
            position: fixed;
            bottom: -100px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255, 71, 87, 0.95);
            backdrop-filter: blur(5px);
            color: white;
            padding: 14px 28px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 600;
            box-shadow: 0 10px 25px rgba(255, 71, 87, 0.3);
            transition: bottom 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 10000;
            text-align: center;
            white-space: nowrap;
            border: 1px solid rgba(255,255,255,0.2);
        }
        
        .custom-toast.show {
            bottom: 40px;
        }
    </style>
</head>
<body>

    <div class="dashboard">
        <header>
            <h1>Zara's Room 🌸</h1>
            <p>Halo sayang, selamat datang di dashboard banyy!</p>
        </header>

        <div class="bucin-container">
            <div class="bucin-label">
                <span>Level Kangen Uqii Hari Ini:</span>
                <span id="bucin-val">50%</span>
            </div>
            <div class="progress-bar-bg">
                <div id="progress-fill" class="progress-bar-fill"></div>
            </div>
            <input type="range" id="bucin-slider" class="bucin-slider" min="0" max="100" value="50">
        </div>

        <div class="card">
            <h3>Kenapa aku sayang kamu? 🤔</h3>
            <div id="teks-alasan">Klik tombol di bawah untuk cari tahu alesannya!</div>
            <button class="btn" onclick="gantiAlasan()">Cari Tahu 💖</button>
        </div>

        <div class="card">
            <h3>Pusat Bantuan Uqii 🚨</h3>
            <div class="btn-grid">
                <button class="btn" onclick="pencetBuzzer()">Love Buzzer 🛎️</button>
                <button class="btn btn-danger" onclick="panggilDarurat()">Peluk Darurat 🫂</button>
            </div>
        </div>
    </div>

    <div id="toast-notif" class="custom-toast">Notifikasi Sukses! ✨</div>

    <script>
        // Link Webhook Discord milikmu sudah otomatis aktif di sini
        const DISCORD_WEBHOOK_URL = "https://discordapp.com/api/webhooks/1524831289415434354/EiC3hkhyhbO4yKvPVcvUT3YbOJRMBgsr-LbD5SgqHah9O8Wz9bgoQWFdHKdlqnYPqwCs";

        const daftarAlasan = [
            "Karena kamu selalu bisa bikin aku ketawa bahkan di hari paling berat sekalipun.",
            "Sifat perhatian dan pengertian kamu itu berharga banget buat aku.",
            "Aku suka cara kamu melihat dunia, selalu positif dan penuh semangat.",
            "Kamu selalu dengerin cerita random aku tanpa pernah kelihatan bosen.",
            "Bersama kamu, aku merasa bisa jadi diri aku sendiri seutuhnya.",
            "Senyuman kamu itu obat paling ampuh buat ngilangin stres aku."
        ];

        let levelKangenSaatIni = "50%";

        // 1. Logika Pengatur Level Bucin & Trigger Shower Hati otomatis + Kirim Ke Discord
        const slider = document.getElementById("bucin-slider");
        const fill = document.getElementById("progress-fill");
        const valText = document.getElementById("bucin-val");

        slider.addEventListener("change", (e) => {
            const value = e.target.value;
            levelKangenSaatIni = value + "%";
            fill.style.width = value + "%";
            valText.innerText = value + "%";

            // Kirim data level kangen baru ke Discord begitu slider dilepas
            kirimKeDiscord("📊 UPDATE LEVEL KANGEN ZARA", `Zara baru saja menggeser level kangennya hari ini menjadi:\n## **${levelKangenSaatIni}**`, 3447003);

            if (value === "100") {
                valText.innerText = "100% (MAKSIMAL! 🥰)";
                tampilkanToast("Level kangen kamu maksimal! Membuka shower hati... ✨");
                efekHujanHati(25); 
            } else {
                tampilkanToast(`Level kangen diupdate: ${levelKangenSaatIni} 👌`);
            }
        });

        // Jalankan transisi fill visual saja saat digeser seret
        slider.addEventListener("input", (e) => {
            fill.style.width = e.target.value + "%";
            valText.innerText = e.target.value + "%";
        });

        // 2. Fungsi Toast Notification (Gantiin alert browser yang kaku)
        function tampilkanToast(pesan) {
            const toast = document.getElementById("toast-notif");
            toast.innerText = pesan;
            toast.classList.add("show");
            
            setTimeout(() => {
                toast.classList.remove("show");
            }, 2500);
        }

        // 3. Efek Hujan Hati (Heart Pop/Shower)
        function efekHujanHati(jumlah = 15) {
            const emojis = ["❤️", "🌸", "💕", "✨", "💖"];
            for (let i = 0; i < jumlah; i++) {
                setTimeout(() => {
                    const heart = document.createElement("div");
                    heart.classList.add("floating-heart");
                    heart.innerText = emojis[Math.floor(Math.random() * emojis.length)];
                    heart.style.left = Math.random() * 100 + "vw";
                    heart.style.setProperty('--random-x', (Math.random() * 300 - 150) + "px");
                    heart.style.animationDuration = (Math.random() * 1.2 + 1) + "s";
                    document.body.appendChild(heart);
                    
                    setTimeout(() => heart.remove(), 2200);
                }, i * 80);
            }
        }

        // 4. Optimasi Fungsi Alasan Sayang (Dengan Animasi Memudar Lembut)
        let indexTerakhir = -1;
        function gantiAlasan() {
            const elemenTeks = document.getElementById("teks-alasan");
            
            let indexBaru;
            do {
                indexBaru = Math.floor(Math.random() * daftarAlasan.length);
            } while (indexBaru === indexTerakhir);
            indexTerakhir = indexBaru;

            elemenTeks.style.opacity = 0;
            
            setTimeout(() => {
                elemenTeks.innerText = daftarAlasan[indexBaru];
                elemenTeks.style.opacity = 1;
                efekHujanHati(5);
            }, 200);
        }

        // 5. Integrasi Tombol Alerts dengan Notifikasi Webhook Discord
        function pencetBuzzer() {
            efekHujanHati(15);
            tampilkanToast("🛎️ Telolet! Uqii dapet sinyal kangen dari Zara!");
            
            kirimKeDiscord("❤️ ZARA PENCET LOVE BUZZER!", `Zara lagi kangen banget sama kamu sekarang! \n\n**Level Kangen Hari Ini:** ${levelKangenSaatIni}\n**Status:** Tombol Kangen Diaktifkan!`, 16739201);
        }

        function panggilDarurat() {
            efekHujanHati(20);
            tampilkanToast("🚨 SOS! Pengiriman pelukan online meluncur ke Zara! 🫂");
            
            kirimKeDiscord("🚨 PANGGILAN DARURAT: EMERGENCY HUG!", `Zara mengirim sinyal darurat! Dia lagi butuh support/pelukan virtual kamu sekarang juga. Hubungi dia segera! \n\n**Level Kangen Hari Ini:** ${levelKangenSaatIni}`, 16711715);
        }

        // FUNGSI UTAMA PENGIRIMAN DATA KE DISCORD WEBHOOK
        function kirimKeDiscord(judul, deskripsi, kodeWarna) {
            const payload = {
                content: "📢 @everyone — *Ada kabar baru dari Zara!*", 
                embeds: [{
                    title: judul,
                    description: deskripsi,
                    color: kodeWarna,
                    timestamp: new Date()
                }]
            };

            fetch(DISCORD_WEBHOOK_URL, {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify(payload)
            })
            .then(res => console.log("Notifikasi terkirim ke Discord Uqii!"))
            .catch(err => console.error("Gagal mengirim sinyal Discord:", err));
        }
    </script>
</body>
</html>
