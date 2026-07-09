<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Zara's Love Dashboard ✨</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: linear-gradient(135deg, #ffeef8 0%, #fff5f5 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 15px;
            color: #4a4a4a;
        }

        .dashboard {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            width: 100%;
            max-width: 450px;
            border-radius: 30px;
            padding: 25px 20px;
            box-shadow: 0 15px 35px rgba(255, 182, 193, 0.2);
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.6);
        }

        .header h1 {
            font-size: 1.5rem;
            color: #ff6b81;
            margin-bottom: 5px;
        }

        .header p {
            font-size: 0.85rem;
            color: #777;
            margin-bottom: 25px;
        }

        /* 1. MOOD PICKER STYLE */
        .section-title {
            font-size: 0.9rem;
            font-weight: 600;
            color: #ff6b81;
            margin-bottom: 12px;
            text-align: left;
            padding-left: 5px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .mood-container {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
            margin-bottom: 25px;
        }

        .mood-box {
            background: white;
            border: 2px solid #fff0f2;
            border-radius: 16px;
            padding: 12px 5px;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 4px 10px rgba(0,0,0,0.02);
        }

        .mood-box span {
            display: block;
            font-size: 1.8rem;
            margin-bottom: 4px;
        }

        .mood-box p {
            font-size: 0.7rem;
            font-weight: 600;
            color: #888;
        }

        .mood-box.active {
            border-color: #ff6b81;
            background: #fff5f6;
            transform: scale(1.05);
        }

        .mood-box.active p {
            color: #ff6b81;
        }

        /* 2. LOVE BUZZER STYLE */
        .buzzer-wrapper {
            background: white;
            border-radius: 24px;
            padding: 20px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.02);
            margin-bottom: 25px;
            border: 1px solid rgba(255, 107, 129, 0.1);
        }

        .btn-buzzer {
            background: radial-gradient(circle, #ff4757, #ff6b81);
            color: white;
            border: none;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            font-size: 2.5rem;
            cursor: pointer;
            box-shadow: 0 10px 25px rgba(255, 71, 87, 0.4);
            display: block;
            margin: 15px auto;
            transition: transform 0.1s;
        }

        .btn-buzzer:active {
            transform: scale(0.9);
        }

        #buzzer-text {
            font-size: 0.85rem;
            font-weight: 600;
            color: #ff4757;
            min-height: 20px;
            margin-top: 10px;
        }

        /* 3. EMERGENCY & NOTE STYLE */
        .action-container {
            display: flex;
            gap: 12px;
            margin-bottom: 20px;
        }

        .btn-emergency {
            flex: 1;
            background: #fff;
            border: 2px dashed #ff4757;
            color: #ff4757;
            padding: 12px;
            border-radius: 16px;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            transition: all 0.2s;
        }

        .btn-emergency:active {
            background: #fff5f5;
            transform: scale(0.98);
        }

        .note-section {
            background: white;
            border-radius: 20px;
            padding: 15px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.02);
            text-align: left;
        }

        .note-input {
            width: 100%;
            border: 1px solid #eee;
            border-radius: 12px;
            padding: 10px 12px;
            font-size: 0.85rem;
            resize: none;
            outline: none;
            font-family: inherit;
            margin-bottom: 10px;
            transition: border-color 0.2s;
        }

        .note-input:focus {
            border-color: #ff6b81;
        }

        .btn-send-note {
            background: #ff6b81;
            color: white;
            border: none;
            width: 100%;
            padding: 10px;
            border-radius: 12px;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: background 0.2s;
        }

        .btn-send-note:offset-parent { background: #ff4757; }
    </style>
</head>
<body>

    <div class="dashboard">
        <div class="header">
            <h1>Zara's Love Dashboard ✨</h1>
            <p>Ruang interaksi rahasia Zara & Uqii</p>
        </div>

        <!-- FITUR 1: DAILY MOOD PICKER -->
        <div class="section-title">📊 Update Mood Kamu Hari Ini</div>
        <div class="mood-container">
            <div class="mood-box" onclick="pilihMood(this, '😊 Senang')">
                <span>😊</span>
                <p>Senang</p>
            </div>
            <div class="mood-box" onclick="pilihMood(this, '😴 Capek')">
                <span>😴</span>
                <p>Capek</p>
            </div>
            <div class="mood-box" onclick="pilihMood(this, '😡 Badmood')">
                <span>😡</span>
                <p>Badmood</p>
            </div>
            <div class="mood-box" onclick="pilihMood(this, '🤒 Sakit')">
                <span>🤒</span>
                <p>Gak Enak Badan</p>
            </div>
        </div>

        <!-- FITUR 2: LOVE BUZZER -->
        <div class="section-title">❤️ Love Buzzer</div>
        <div class="buzzer-wrapper">
            <p style="font-size: 0.8rem; color: #888;">Pencet tombol hati di bawah kalau lagi kangen Uqii!</p>
            <button class="btn-buzzer" onclick="pencetBuzzer()">❤️</button>
            <p id="buzzer-text"></p>
        </div>

        <!-- FITUR 3: EMERGENCY HUG -->
        <div class="section-title">🚨 Tombol Darurat</div>
        <div class="action-container">
            <button class="btn-emergency" onclick="panggilDarurat()">
                <span>🚨</span> Emergency Hug
            </button>
        </div>

        <!-- FITUR 4: STICKY NOTES -->
        <div class="section-title">📌 Titip Catatan Kecil</div>
        <div class="note-section">
            <textarea class="note-input" id="note-text" rows="2" placeholder="Tulis pesan random atau titipan buat Uqii di sini..."></textarea>
            <button class="btn-send-note" onclick="kirimCatatan()">Tempel Catatan 🕊️</button>
        </div>
    </div>

    <script>
        // URL WEBHOOK DISCORD KAMU
        const DISCORD_WEBHOOK_URL = "https://discordapp.com/api/webhooks/1524831289415434354/EiC3hkhyhbO4yKvPVcvUT3YbOJRMBgsr-LbD5SgqHah9O8Wz9bgoQWFdHKdlqnYPqwCs";

        let moodSekarang = "Belum diupdate";
        const teksBuzzer = [
            "Uqii juga kangen bangeeet sama Zaraaa! ❤️",
            "Ayo keluar lagii zaraaaa, kitaa ketemuann lagii! 🫶🏻",
            "Hehehe kangen yaaa? Sini hugs! 🤗",
            "Kangennya dikirim ke WA dong, jangan cuma dipencet! 😜",
        ];

        // Jalur Audio Synthesizer internal biar HP bunyi pop imut saat klik tombol
        let audioCtx = null;
        function initAudio() {
            if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            if (audioCtx.state === 'suspended') audioCtx.resume();
        }

        function playSound(freq, duration, type = 'sine') {
            initAudio();
            let osc = audioCtx.createOscillator();
            let gain = audioCtx.createGain();
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            osc.type = type;
            osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
            if(type === 'sine') osc.frequency.exponentialRampToValueAtTime(10, audioCtx.currentTime + duration);
            gain.gain.setValueAtTime(0.3, audioCtx.currentTime);
            gain.gain.linearRampToValueAtTime(0.01, audioCtx.currentTime + duration);
            osc.start();
            osc.stop(audioCtx.currentTime + duration);
        }

        // LOGIKA FITUR 1: MOOD PICKER
        function pilihMood(elemen, namaMood) {
            playSound(300, 0.1, 'triangle');
            document.querySelectorAll('.mood-box').forEach(box => box.classList.remove('active'));
            elemen.classList.add('active');
            moodSekarang = namaMood;

            // Kirim notifikasi update mood ke Discord
            kirimKeDiscord("📊 UPDATE MOOD ZARA", `Zara baru saja memperbarui status mood-nya harian menjadi:\n## **${namaMood}**`, 5026544);
            alert(`Mood kamu berhasil diupdate ke Uqii: ${namaMood} ✨`);
        }

        // LOGIKA FITUR 2: LOVE BUZZER
        function pencetBuzzer() {
            playSound(250, 0.15, 'triangle');
            const indexAcak = Math.floor(Math.random() * teksBuzzer.length);
            const pesanDipilih = teksBuzzer[indexAcak];
            document.getElementById("buzzer-text").innerText = pesanDipilih;

            // Kirim notifikasi Love Buzzer ke Discord
            kirimKeDiscord("❤️ ZARA PENCET LOVE BUZZER!", `Zara lagi kangen banget sama kamu sekarang! \n\n**Status Mood Saat Ini:** ${moodSekarang}\n**Respons Web:** _"${pesanDipilih}"_`, 16739201);
        }

        // LOGIKA FITUR 3: EMERGENCY HUG
        function panggilDarurat() {
            playSound(600, 0.3, 'sawtooth');
            
            // Kirim notifikasi darurat ke Discord
            kirimKeDiscord("🚨 PANGGILAN DARURAT: EMERGENCY HUG!", `Zara mengirim sinyal darurat! Dia lagi butuh support/pelukan virtual kamu sekarang juga. Hubungi dia segera! \n\n**Status Mood Saat Ini:** ${moodSekarang}`, 16711715);
            alert("Sinyal darurat berhasil dikirim! Uqii bakal langsung notice di HP-nya! 🚨❤️");
        }

        // LOGIKA FITUR 4: STICKY NOTES
        function kirimCatatan() {
            playSound(400, 0.08);
            const inputCatatan = document.getElementById("note-text");
            const isiCatatan = inputCatatan.value.trim();

            if (isiCatatan === "") {
                alert("Kotak catatannya diisi dulu yaa zaraaa~");
                return;
            }

            // Kirim notifikasi catatan ke Discord
            kirimKeDiscord("📌 ZARA MENEMPEL CATATAN BARU", `Zara ninggalin pesan/catatan kecil buat kamu:\n\n> "${isiCatatan}"\n\n**Status Mood Saat Ini:** ${moodSekarang}`, 16761035);
            
            alert("Catatan kecilmu berhasil ditempel! 🕊️");
            inputCatatan.value = ""; // Reset form
        }

        // FUNGSI UTAMA PENGIRIMAN DATA KE DISCORD WEBHOOK
        function kirimKeDiscord(judul, deskripsi, kodeWarna) {
            if (DISCORD_WEBHOOK_URL === "TEMPEL_URL_WEBHOOK_DISCORD_KAMU_DISINI") {
                console.log("Notifikasi gagal terkirim: URL Webhook belum diisi.");
                return;
            }

            const payload = {
                content: "📢 @everyone — *Ada kabar baru dari Zara!*", // Tag ini bikin HP kamu bergetar/bunyi kencang
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
            .then(res => console.log("Sinyal terkirim ke HP Uqii!"))
            .catch(err => console.error("Gagal mengirim sinyal:", err));
        }
    </script>
</body>
</html>
