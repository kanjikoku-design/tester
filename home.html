<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mode Hafalan Setoran (Muhaddits AI)</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f7f6;
            color: #333;
            max-width: 900px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
        }
        h1 { color: #2c3e50; }
        .card {
            background: white;
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            margin-top: 20px;
        }
        select {
            padding: 12px;
            font-size: 16px;
            width: 100%;
            max-width: 500px;
            border-radius: 8px;
            border: 1px solid #ccc;
            margin-bottom: 20px;
        }
        button {
            padding: 12px 25px;
            font-size: 16px;
            background-color: #27ae60;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s;
            margin: 5px;
        }
        button:hover { background-color: #2ecc71; }
        
        #status {
            margin-top: 15px;
            font-weight: bold;
            color: #e74c3c;
            padding: 10px;
            border-radius: 5px;
        }
        
        .arabic-container {
            margin-top: 40px;
            font-size: 40px;
            direction: rtl;
            line-height: 2.2;
            font-family: 'Amiri', 'Traditional Arabic', 'Scheherazade New', serif;
            padding: 20px;
            background: #fafafa;
            border-radius: 10px;
            min-height: 150px;
        }
        
        .word {
            display: inline-block;
            margin: 0 6px;
            color: transparent; 
            border-bottom: 3px dashed #bdc3c7; 
            min-width: 40px;
            text-align: center;
            transition: all 0.4s ease;
        }
        
        .word.matched {
            color: #27ae60; 
            border-bottom: 3px solid transparent; 
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }

        .word.active {
            border-bottom: 3px solid #3498db; 
        }

        #transcript-box {
            margin-top: 30px;
            text-align: left;
        }
        #transcript {
            padding: 15px;
            background: #ecf0f1;
            border-radius: 8px;
            font-style: italic;
            color: #555;
            min-height: 60px;
            font-size: 18px;
            direction: rtl;
        }
        .instructions {
            font-size: 15px;
            color: #34495e;
            margin-bottom: 20px;
            text-align: left;
            background: #e8f8f5;
            padding: 15px;
            border-radius: 8px;
            border-left: 5px solid #1abc9c;
        }
    </style>
</head>
<body>

    <h1>Muhaddits AI - Mode Hafalan Lengkap</h1>
    
    <div class="card">
        <div class="instructions">
            <strong>Cara Penggunaan (Mode Setoran Tarteel):</strong><br>
            1. Pilih hadits atau zikir dari daftar terlengkap.<br>
            2. Teks Arab akan <b>disembunyikan</b> (berupa garis putus-putus).<br>
            3. Klik <b>"Mulai Setoran"</b> dan bacalah dengan tartil.<br>
            4. Kata yang Anda baca <b>harus berurutan</b>. Teks hanya akan muncul satu per satu setiap kali sistem mendeteksi ucapan Anda benar.
        </div>

        <select id="haditsSelect">
            <option value="">-- Pilih Hadits / Zikir untuk Dihafal --</option>
        </select>

        <br>
        <button id="startBtn">🎤 Mulai Setoran</button>
        <button id="stopBtn" style="background-color:#e74c3c; display:none;">⏹ Hentikan</button>
        <button id="resetBtn" style="background-color:#f39c12;">🔄 Ulangi</button>
        
        <div id="status">Pilih hadits dari menu di atas.</div>
        
        <div id="haditsDisplay" class="arabic-container"></div>
        
        <div id="transcript-box">
            <h4>Teks yang ditangkap suara Anda:</h4>
            <div id="transcript">...</div>
        </div>
    </div>

    <script>
        // Database Ekstensif (diambil dari seluruh file PDF Al-Adzkar wal-Aadab)
        const database = [
            { id: 1, title: "1. Keutamaan Menuntut Ilmu 1", text: "مَنْ سَلَكَ طَرِيقاً يَلْتَمِسُ فِيهِ عِلْماً؛ سَهَّلَ اللَّهُ لَهُ بِهِ طَرِيقاً إِلَى الجَنَّةِ" },
            { id: 2, title: "2. Keutamaan Menuntut Ilmu 2", text: "مَنْ يُرِدِ اللَّهُ بِهِ خَيْراً؛ يُفَقِّهْهُ فِي الدِّينِ" },
            { id: 3, title: "3. Amal Jariyah (Ilmu)", text: "إِذَا مَاتَ الإِنْسَانُ انْقَطَعَ عَنْهُ عَمَلُهُ إِلَّا مِنْ ثَلَاثَةٍ: إِلَّا مِنْ صَدَقَةٍ جَارِيَةٍ، أَوْ عِلْمٍ يُنْتَفَعُ بِهِ، أَوْ وَلَدٍ صَالِحٍ يَدْعُو لَهُ" },
            { id: 4, title: "4. Keutamaan Belajar Al-Quran", text: "خَيْرُكُمْ مَنْ تَعَلَّمَ القُرْآنَ وَعَلَّمَهُ" },
            { id: 5, title: "5. Pahala Membaca Al-Quran", text: "مَثَلُ الَّذِي يَقْرَأُ القُرْآنَ وَهُوَ حَافِظٌ لَهُ مَعَ السَّفَرَةِ الكِرَامِ البَرَرَةِ، وَمَثَلُ الَّذِي يَقْرَأُ وَهُوَ يَتَعَاهَدُهُ وَهُوَ عَلَيْهِ شَدِيدٌ؛ فَلَهُ أَجْرَانِ" },
            { id: 6, title: "6. Syafaat Al-Quran", text: "اقْرَؤُوا القُرْآنَ؛ فَإِنَّهُ يَأْتِي يَوْمَ القِيَامَةِ شَفِيعاً لِأَصْحَابِهِ" },
            { id: 7, title: "7. Perumpamaan Orang Berdzikir", text: "مَثَلُ الَّذِي يَذْكُرُ رَبَّهُ وَالَّذِي لَا يَذْكُرُ رَبَّهُ، مَثَلُ الحَيِّ وَالمَيِّتِ" },
            { id: 8, title: "8. Kedekatan Allah bagi yang Berdzikir", text: "يَقُولُ اللَّهُ تَعَالَى: أَنَا عِنْدَ ظَنِّ عَبْدِي بِي، وَأَنَا مَعَهُ إِذَا ذَكَرَنِي، فَإِنْ ذَكَرَنِي فِي نَفْسِهِ ذَكَرْتُهُ فِي نَفْسِي، وَإِنْ ذَكَرَنِي فِي مَلَإٍ ذَكَرْتُهُ فِي مَلَإٍ خَيْرٍ مِنْهُمْ" },
            { id: 9, title: "9. Al-Mufarridun", text: "سَبَقَ المُفَرِّدُونَ، قَالُوا: وَمَا المُفَرِّدُونَ يَا رَسُولَ اللَّهِ؟ قَالَ: الذَّاكِرُونَ اللَّهَ كَثِيراً، وَالذَّاكِرَاتُ" },
            { id: 10, title: "10. Keutamaan Majelis Dzikir", text: "وَمَا اجْتَمَعَ قَوْمٌ فِي بَيْتٍ مِنْ بُيُوتِ اللَّهِ، يَتْلُونَ كِتَابَ اللَّهِ، وَيَتَدَارَسُونَهُ بَيْنَهُمْ، إِلَّا نَزَلَتْ عَلَيْهِمُ السَّكِينَةُ، وَغَشِيَتْهُمُ الرَّحْمَةُ، وَحَفَّتْهُمُ المَلَائِكَةُ، وَذَكَرَهُمُ اللَّهُ فِيمَنْ عِنْدَهُ" },
            { id: 11, title: "11. Doa Masuk Toilet", text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الخُبُثِ وَالخَبَائِثِ" },
            { id: 12, title: "12. Doa Keluar Toilet", text: "غُفْرَانَكَ" },
            { id: 13, title: "13. Doa Selesai Wudhu", text: "أَشْهَدُ أَلَّا إِلَهَ إِلَّا اللَّهُ، وَأَنَّ مُحَمَّداً عَبْدُ اللَّهِ وَرَسُولُهُ" },
            { id: 14, title: "14. Menjawab Adzan", text: "إِذَا سَمِعْتُمُ المُؤَذِّنَ؛ فَقُولُوا مِثْلَ مَا يَقُولُ، ثُمَّ صَلُّوا عَلَيَّ" },
            { id: 15, title: "15. Syahadat setelah Adzan", text: "أَشْهَدُ أَلَّا إِلَهَ إِلَّا اللَّهُ وَحْدَهُ لَا شَرِيكَ لَهُ، وَأَنَّ مُحَمَّداً عَبْدُهُ وَرَسُولُهُ، رَضِيتُ بِاللَّهِ رَبِّاً، وَبِمُحَمَّدٍ رَسُولاً، وَبِالإِسْلَامِ دِيناً" },
            { id: 16, title: "16. Menjawab Hayya 'alash-shalah/falah", text: "لَا حَوْلَ وَلَا قُوَّةَ إِلَّا بِاللَّهِ" },
            { id: 17, title: "17. Doa Selesai Adzan", text: "اللَّهُمَّ رَبَّ هَذِهِ الدَّعْوَةِ التَّامَّةِ، وَالصَّلَاةِ القَائِمَةِ، آتِ مُحَمَّداً الوَسِيلَةَ وَالفَضِيلَةَ، وَابْعَثْهُ مَقَاماً مَحْمُوداً الَّذِي وَعَدْتَهُ" },
            { id: 18, title: "18. Doa Masuk Masjid", text: "اللَّهُمَّ افْتَحْ لِي أَبْوَابَ رَحْمَتِكَ" },
            { id: 19, title: "19. Doa Keluar Masjid", text: "اللَّهُمَّ إِنِّي أَسْأَلُكَ مِنْ فَضْلِكَ" },
            { id: 20, title: "20. Doa Istiftah 1", text: "سُبْحَانَكَ اللَّهُمَّ وَبِحَمْدِكَ، وَتَبَارَكَ اسْمُكَ، وَتَعَالَى جَدُّكَ، وَلَا إِلَهَ غَيْرُكَ" },
            { id: 21, title: "21. Doa Istiftah 2", text: "اللَّهُمَّ بَاعِدْ بَيْنِي وَبَيْنَ خَطَايَايَ كَمَا بَاعَدْتَ بَيْنَ المَشْرِقِ وَالمَغْرِبِ. اللَّهُمَّ نَقِّنِي مِنْ خَطَايَايَ كَمَا يُنَقَّى الثَّوْبُ الأَبْيَضُ مِنَ الدَّنَسِ. اللَّهُمَّ اغْسِلْنِي مِنْ خَطَايَايَ بِالثَّلْجِ وَالمَاءِ وَالبَرَدِ" },
            { id: 22, title: "22. Gangguan Setan Saat Shalat", text: "أَعُوذُ بِاللَّهِ مِنْهُ" },
            { id: 23, title: "23. Doa Rukuk 1", text: "سُبْحَانَ رَبِّيَ العَظِيمِ" },
            { id: 24, title: "24. Doa Rukuk 2", text: "اللَّهُمَّ لَكَ رَكَعْتُ، وَبِكَ آمَنْتُ، وَلَكَ أَسْلَمْتُ، خَشَعَ لَكَ سَمْعِي، وَبَصَرِي، وَمُخِّي، وَعَظْمِي، وَعَصَبِي" },
            { id: 25, title: "25. Doa Rukuk & Sujud 1", text: "سُبْحَانَكَ اللَّهُمَّ رَبَّنَا وَبِحَمْدِكَ، اللَّهُمَّ اغْفِرْ لِي" },
            { id: 26, title: "26. Doa Rukuk & Sujud 2", text: "سُبُّوحٌ قُدُّوسٌ، رَبُّ المَلَائِكَةِ وَالرُّوحِ" },
            { id: 27, title: "27. Doa Rukuk & Sujud 3", text: "سُبْحَانَ ذِي الجَبَرُوتِ وَالمَلَكُوتِ وَالكِبْرِيَاءِ وَالعَظَمَةِ" },
            { id: 28, title: "28. Doa I'tidal 1", text: "رَبَّنَا وَلَكَ الحَمْدُ، حَمْداً كَثِيراً، طَيِّباً، مُبَارَكاً فِيهِ" },
            { id: 29, title: "29. Doa I'tidal 2", text: "رَبَّنَا لَكَ الحَمْدُ، مِلْءَ السَّمَوَاتِ وَالأَرْضِ، وَمِلْءَ مَا شِئْتَ مِنْ شَيْءٍ بَعْدُ، أَهْلَ الثَّنَاءِ وَالمَجْدِ، أَحَقُّ مَا قَالَ العَبْدُ، وَكُلُّنَا لَكَ عَبْدٌ. اللَّهُمَّ لَا مَانِعَ لِمَا أَعْطَيْتَ، وَلَا مُعْطِيَ لِمَا مَنَعْتَ، وَلَا يَنْفَعُ ذَا الجَدِّ مِنْكَ الجَدُّ" },
            { id: 30, title: "30. Doa Sujud 1", text: "سُبْحَانَ رَبِّيَ الْأَعْلَى" },
            { id: 31, title: "31. Doa Sujud 2", text: "اللَّهُمَّ اغْفِرْ لِي ذَنْبِي كُلَّهُ؛ دِقَّهُ وَجِلَّهُ، وَأَوَّلَهُ وَآخِرَهُ، وَعَلَانِيَتَهُ وَسِرَّهُ" },
            { id: 32, title: "32. Doa Sujud 3", text: "اللَّهُمَّ لَكَ سَجَدْتُ، وَبِكَ آمَنْتُ، وَلَكَ أَسْلَمْتُ، سَجَدَ وَجْهِي لِلَّذِي خَلَقَهُ وَصَوَّرَهُ، وَشَقَّ سَمْعَهُ وَبَصَرَهُ، تَبَارَكَ اللَّهُ أَحْسَنُ الخَالِقِينَ" },
            { id: 33, title: "33. Bacaan Tasyahud", text: "التَّحِيَّاتُ لِلَّهِ، وَالصَّلَوَاتُ، وَالطَّيِّبَاتُ، السَّلَامُ عَلَيْكَ أَيُّهَا النَّبِيُّ وَرَحْمَةُ اللَّهِ وَبَرَكَاتُهُ، السَّلَامُ عَلَيْنَا وَعَلَى عِبَادِ اللَّهِ الصَّالِحِينَ، أَشْهَدُ أَلَّا إِلَهَ إِلَّا اللَّهُ، وَأَشْهَدُ أَنَّ مُحَمَّداً عَبْدُهُ وَرَسُولُهُ" },
            { id: 34, title: "34. Bacaan Shalawat (Singkat)", text: "اللَّهُمَّ صَلِّ عَلَى مُحَمَّدٍ وَعَلَى آلِ مُحَمَّدٍ، كَمَا صَلَّيْتَ عَلَى إِبْرَاهِيمَ وَعَلَى آلِ إِبْرَاهِيمَ، إِنَّكَ حَمِيدٌ مَجِيدٌ. اللَّهُمَّ بَارِكْ عَلَى مُحَمَّدٍ وَعَلَى آلِ مُحَمَّدٍ، كَمَا بَارَكْتَ عَلَى إِبْرَاهِيمَ وَعَلَى آلِ إِبْرَاهِيمَ، إِنَّكَ حَمِيدٌ مَجِيدٌ" },
            { id: 35, title: "35. Doa Sebelum Salam 1 (Perlindungan 4 Hal)", text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنْ عَذَابِ جَهَنَّمَ، وَمِنْ عَذَابِ القَبْرِ، وَمِنْ فِتْنَةِ المَحْيَا وَالمَمَاتِ، وَمِنْ شَرِّ فِتْنَةِ المَسِيحِ الدَّجَّالِ" },
            { id: 36, title: "36. Doa Sebelum Salam 2", text: "اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنَ الجُبْنِ، وَأَعُوذُ بِكَ أَنْ أُرَدَّ إِلَى أَرْذَلِ العُمُرِ، وَأَعُوذُ بِكَ مِنْ فِتْنَةِ الدُّنْيَا، وَأَعُوذُ بِكَ مِنْ عَذَابِ القَبْرِ" },
            { id: 37, title: "37. Dzikir Selesai Shalat 1", text: "أَسْتَغْفِرُ اللَّهَ اللَّهُمَّ أَنْتَ السَّلَامُ، وَمِنْكَ السَّلَامُ، تَبَارَكْتَ يَا ذَا الجَلَالِ وَالإِكْرَامِ" },
            { id: 38, title: "38. Dzikir Selesai Shalat 2 (Tahlil Singkat)", text: "لَا إِلَهَ إِلَّا اللَّهُ وَحْدَهُ لَا شَرِيكَ لَهُ، لَهُ المُلْكُ، وَلَهُ الحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ. اللَّهُمَّ لَا مَانِعَ لِمَا أَعْطَيْتَ، وَلَا مُعْطِيَ لِمَا مَنَعْتَ، وَلَا يَنْفَعُ ذَا الجَدِّ مِنْكَ الجَدُّ" },
            { id: 39, title: "39. Doa Mu'adz Setelah Shalat", text: "اللَّهُمَّ أَعِنِّي عَلَى ذِكْرِكَ، وَشُكْرِكَ، وَحُسْنِ عِبَادَتِكَ" },
            { id: 40, title: "40. Doa Qunut Witir", text: "اللَّهُمَّ اهْدِنِي فِيمَنْ هَدَيْتَ، وَعَافِنِي فِيمَنْ عَافَيْتَ، وَتَوَلَّنِي فِيمَنْ تَوَلَّيْتَ، وَبَارِكْ لِي فِيمَا أَعْطَيْتَ، وَقِنِي شَرَّ مَا قَضَيْتَ، فَإِنَّكَ تَقْضِي وَلَا يُقْضَى عَلَيْكَ، إِنَّهُ لَا يَذِلُّ مَنْ وَالَيْتَ، تَبَارَكْتَ رَبَّنَا وَتَعَالَيْتَ" },
            { id: 41, title: "41. Dzikir Setelah Salam Witir", text: "سُبْحَانَ المَلِكِ القُدُّوسِ" },
            { id: 42, title: "42. Ruqyah Mandiri (Rasa Sakit di Tubuh)", text: "بِسْمِ اللَّهِ أَعُوذُ بِاللَّهِ وَقُدْرَتِهِ، مِنْ شَرِّ مَا أَجِدُ وَأُحَاذِرُ" },
            { id: 43, title: "43. Menjenguk Orang Sakit 1", text: "لَا بَأْسَ طَهُورٌ إِنْ شَاءَ اللَّهُ" },
            { id: 44, title: "44. Menjenguk Orang Sakit 2 (Ruqyah)", text: "اللَّهُمَّ رَبَّ النَّاسِ، أَذْهِبِ البَاسَ، اشْفِهِ وَأَنْتَ الشَّافِي، لَا شِفَاءَ إِلَّا شِفَاؤُكَ، شِفَاءً لَا يُغَادِرُ سَقَماً" },
            { id: 45, title: "45. Ruqyah Jibril", text: "بِسْمِ اللَّهِ أَرْقِيكَ، مِنْ كُلِّ شَيْءٍ يُؤْذِيكَ مِنْ شَرِّ كُلِّ نَفْسٍ أَوْ عَيْنِ حَاسِدٍ، اللَّهُ يَشْفِيكَ، بِسْمِ اللَّهِ أَرْقِيكَ" },
            { id: 46, title: "46. Doa untuk Orang Sakit", text: "أَسْأَلُ اللَّهَ العَظِيمَ رَبَّ العَرْشِ العَظِيمِ أَنْ يَشْفِيَكَ" },
            { id: 47, title: "47. Talqin Orang Sakaratul Maut", text: "لَا إِلَهَ إِلَّا اللَّهُ" },
            { id: 48, title: "48. Shalat Jenazah", text: "اللَّهُمَّ اغْفِرْ لَهُ، وَارْحَمْهُ، وَعَافِهِ، وَاعْفُ عَنْهُ. وَأَكْرِمْ نُزُلَهُ، وَوَسِّعْ مُدْخَلَهُ، وَاغْسِلْهُ بِالمَاءِ وَالثَّلْجِ وَالْبَرَدِ. وَنَقِّهِ مِنَ الخَطَايَا كَمَا نَقَّيْتَ الثَّوْبَ الأَبْيَضَ مِنَ الدَّنَسِ. وَأَبْدِلْهُ دَاراً خَيْراً مِنْ دَارِهِ، وَأَهْلاً خَيْراً مِنْ أَهْلِهِ، وَزَوْجاً خَيْراً مِنْ زَوْجِهِ. وَأَدْخِلْهُ الجَنَّةَ، وَأَعِذْهُ مِنْ عَذَابِ القَبْرِ، وَمِنْ عَذَابِ النَّارِ" },
            { id: 49, title: "49. Takziah", text: "إِنَّ لِلَّهِ مَا أَخَذَ وَلَهُ مَا أَعْطَى، وَكُلُّ شَيْءٍ عِنْدَهُ بِأَجَلٍ مُسَمًّى؛ فَمُرْهَا فَلْتَصْبِرْ وَلْتَحْتَسِبْ" },
            { id: 50, title: "50. Ziarah Kubur", text: "السَّلَامُ عَلَيْكُمْ أَهْلَ الدِّيَارِ مِنَ المُؤْمِنِينَ وَالمُسْلِمِينَ، وَإِنَّا إِنْ شَاءَ اللَّهُ لَلَاحِقُونَ، أَسْأَلُ اللَّهَ لَنَا وَلَكُمُ العَافِيَةَ" },
            { id: 51, title: "51. Kesusahan (Karb)", text: "لَا إِلَهَ إِلَّا اللَّهُ، العَظِيمُ الحَلِيمُ. لَا إِلَهَ إِلَّا اللَّهُ، رَبُّ العَرْشِ العَظِيمِ. لَا إِلَهَ إِلَّا اللَّهُ، رَبُّ السَّمَوَاتِ، وَرَبُّ الأَرْضِ، وَرَبُّ العَرْشِ الكَرِيمِ" },
            { id: 52, title: "52. Tertimpa Musibah 1", text: "قَدَّرَ اللَّهُ وَمَا شَاءَ فَعَلَ" },
            { id: 53, title: "53. Tertimpa Musibah 2", text: "إِنَّا لِلَّهِ وَإِنَّا إِلَيْهِ رَاجِعُونَ، اللَّهُمَّ اؤْجُرْنِي فِي مُصِيبَتِي، وَأَخْلِفْ لِي خَيْراً مِنْهَا" },
            { id: 54, title: "54. Takut Kepada Musuh", text: "اللَّهُمَّ إِنَّا نَجْعَلُكَ فِي نُحُورِهِمْ، وَنَعُوذُ بِكَ مِنْ شُرُورِهِمْ" },
            { id: 55, title: "55. Menghadapi Musuh", text: "اللَّهُمَّ مُنْزِلَ الكِتَابِ، سَرِيعَ الحِسَابِ، اهْزِمِ الأَحْزَابَ اللَّهُمَّ اهْزِمْهُمْ وَزَلْزِلْهُمْ" },
            { id: 56, title: "56. Melepas Musafir", text: "أَسْتَوْدِعُ اللَّهَ دِينَكَ، وَأَمَانَتَكَ، وَخَوَاتِيمَ عَمَلِكَ" },
            { id: 57, title: "57. Doa Safar / Naik Kendaraan", text: "سُبْحَانَ الَّذِي سَخَّرَ لَنَا هَذَا وَمَا كُنَّا لَهُ مُقْرِنِينَ وَإِنَّا إِلَى رَبَّنَا لَمُنقَلِبُونَ. اللَّهُمَّ إِنَّا نَسْأَلُكَ فِي سَفَرِنَا هَذَا البِرَّ وَالتَّقْوَى، وَمِنَ العَمَلِ مَا تَرْضَى. اللَّهُمَّ هَوِّنْ عَلَيْنَا سَفَرَنَا هَذَا، وَأَطْوِ عَنَّا بُعْدَهُ. اللَّهُمَّ أَنْتَ الصَّاحِبُ فِي السَّفَرِ، وَالخَلِيفَةُ فِي الأَهْلِ. اللَّهُمَّ إِنِّي أَعُوذُ بِكَ مِنْ وَعْثَاءِ السَّفَرِ، وَكَآبَةِ المَنْظَرِ، وَسُوءِ المُنْقَلَبِ فِي المَالِ وَالأَهْلِ" },
            { id: 58, title: "58. Kembali dari Safar", text: "آيِبُونَ تَائِبُونَ، عَابِدُونَ، لِرَبِّنَا حَامِدُونَ" },
            { id: 59, title: "59. Sahur di Perjalanan", text: "سَمِعَ سَامِعٌ بِحَمْدِ اللَّهِ، وَحُسْنِ بَلَائِهِ عَلَيْنَا، رَبَّنَا صَاحِبْنَا، وَأَفْضِلْ عَلَيْنَا، عَائِذاً بِاللَّهِ مِنَ النَّارِ" },
            { id: 60, title: "60. Talbiyah Haji/Umrah", text: "لَبَّيْكَ اللَّهُمَّ لَبَّيْكَ لَا شَرِيكَ لَكَ لَبَّيْكَ. إِنَّ الحَمْدَ وَالنِّعْمَةَ لَكَ وَالمُلْكَ، لَا شَرِيكَ لَكَ" },
            { id: 61, title: "61. Antara Rukun Yamani & Hajar Aswad", text: "رَبَّنَا آتِنَا فِي الدُّنْيَا حَسَنَةً وَفِي الآخِرَةِ حَسَنَةً وَقِنَا عَذَابَ النَّارِ" },
            { id: 62, title: "62. Di Atas Shafa dan Marwah", text: "لَا إِلَهَ إِلَّا اللَّهُ وَحْدَهُ لَا شَرِيكَ لَهُ، لَهُ المُلْكُ، وَلَهُ الحَمْدُ، وَهُوَ عَلَى كُلِّ شَيْءٍ قَدِيرٌ. لَا إِلَهَ إِلَّا اللَّهُ وَحْدَهُ، أَنْجَزَ وَعْدَهُ، وَنَصَرَ عَبْدَهُ، وَهَزَمَ الأَحْزَابَ وَحْدَهُ" },
            { id: 63, title: "63. Memakai Pakaian Baru", text: "اللَّهُمَّ لَكَ الحَمْدُ أَنْتَ كَسَوْتَنِيهِ، أَسْأَلُكَ خَيْرَهُ وَخَيْرَ مَا صُنِعَ لَهُ، وَأَعُوذُ بِكَ مِنْ شَرِّهِ وَشَرِّ مَا صُنِعَ لَهُ" },
            { id: 64, title: "64. Doa Melihat Buah Pertama", text: "اللَّهُمَّ بَارِكْ لَنَا فِي ثَمَرِنَا" },
            { id: 65, title: "65. Sebelum Makan", text: "بِسْمِ اللَّهِ" },
            { id: 66, title: "66. Jika Lupa Doa Sebelum Makan", text: "بِسْمِ اللَّهِ فِي أَوَّلِهِ وَآخِرِهِ" },
            { id: 67, title: "67. Setelah Makan", text: "الحَمْدُ لِلَّهِ كَثِيراً، طَيِّباً، مُبَارَكاً فِيهِ، غَيْرَ مَكْفِيٍّ، وَلَا مُوَدَّعٍ، وَلَا مُسْتَغْنًى عَنْهُ رَبَّنَا" },
            { id: 68, title: "68. Setelah Makan di Rumah Orang Lain", text: "اللَّهُمَّ بَارِكْ لَهُمْ فِيمَا رَزَقْتَهُمْ، وَاغْفِرْ لَهُمْ، وَارْحَمْهُمْ" }
        ];

        const selectEl = document.getElementById('haditsSelect');
        const displayEl = document.getElementById('haditsDisplay');
        const startBtn = document.getElementById('startBtn');
        const stopBtn = document.getElementById('stopBtn');
        const resetBtn = document.getElementById('resetBtn');
        const statusEl = document.getElementById('status');
        const transcriptEl = document.getElementById('transcript');

        let currentWords = [];
        let currentTargetIndex = 0; 
        let recognition = null;
        let finalTranscriptBuffer = ""; 

        // Populate dropdown
        database.forEach(item => {
            let opt = document.createElement('option');
            opt.value = item.id;
            opt.textContent = item.title;
            selectEl.appendChild(opt);
        });

        // Menghilangkan harakat DAN tanda baca untuk pencocokan murni huruf Arab
        function cleanArabicText(str) {
            // Hanya sisakan huruf Arab (Hamzah hingga Yaa)
            return str.replace(/[^ء-ي]/g, "");
        }

        function loadHadits() {
            const selectedId = parseInt(selectEl.value);
            displayEl.innerHTML = '';
            transcriptEl.innerHTML = '...';
            currentTargetIndex = 0;
            finalTranscriptBuffer = "";
            
            if(!selectedId) {
                statusEl.textContent = "Pilih hadits dari menu di atas.";
                return;
            }

            const hadits = database.find(h => h.id === selectedId);
            const words = hadits.text.split(' ');
            
            currentWords = words.map((w, index) => {
                const span = document.createElement('span');
                span.className = 'word';
                span.textContent = w;
                span.id = 'word-' + index;
                displayEl.appendChild(span);
                
                return {
                    id: index,
                    original: w,
                    clean: cleanArabicText(w),
                    matched: false
                };
            });
            
            if(currentWords.length > 0) {
                document.getElementById('word-0').classList.add('active');
            }
            
            statusEl.textContent = "Siap direkam. Teks disembunyikan, silakan hafal.";
            statusEl.style.color = "#f39c12";
        }

        selectEl.addEventListener('change', loadHadits);
        resetBtn.addEventListener('click', loadHadits);

        // Setup Speech Recognition
        if ('webkitSpeechRecognition' in window) {
            recognition = new webkitSpeechRecognition();
            recognition.continuous = true;
            recognition.interimResults = true;
            recognition.lang = 'ar-SA'; 

            recognition.onstart = function() {
                statusEl.textContent = "🔴 Mendengarkan... Silakan setorkan hafalan Anda.";
                statusEl.style.backgroundColor = "#ffeaa7";
                statusEl.style.color = "#d35400";
                startBtn.style.display = 'none';
                stopBtn.style.display = 'inline-block';
            };

            recognition.onresult = function(event) {
                let interim_transcript = '';

                for (let i = event.resultIndex; i < event.results.length; ++i) {
                    if (event.results[i].isFinal) {
                        finalTranscriptBuffer += event.results[i][0].transcript + " ";
                    } else {
                        interim_transcript += event.results[i][0].transcript;
                    }
                }
                
                const currentTranscript = finalTranscriptBuffer + interim_transcript;
                transcriptEl.innerHTML = currentTranscript;
                
                checkSequentialWords(currentTranscript);
            };

            recognition.onerror = function(event) {
                statusEl.textContent = "Terjadi kesalahan audio: " + event.error;
                statusEl.style.backgroundColor = "transparent";
                statusEl.style.color = "#e74c3c";
                stopRecording();
            };

            recognition.onend = function() {
                if (currentTargetIndex < currentWords.length) {
                    statusEl.textContent = "Perekaman berhenti (Hafalan belum selesai).";
                    statusEl.style.backgroundColor = "transparent";
                    statusEl.style.color = "#333";
                }
                stopRecording();
            };
        } else {
            statusEl.textContent = "Browser Anda tidak mendukung Pengenalan Suara. Gunakan Google Chrome Desktop/Android.";
        }

        function checkSequentialWords(transcript) {
            // Pecah transkrip dan bersihkan setiap kata
            const rawWords = transcript.trim().split(/\s+/);
            const cleanTranscript = rawWords.map(w => cleanArabicText(w)).filter(w => w.length > 0);
            
            // Cek berurutan
            while (currentTargetIndex < currentWords.length) {
                let expectedWord = currentWords[currentTargetIndex].clean;
                
                let found = cleanTranscript.includes(expectedWord);
                
                if (found) {
                    currentWords[currentTargetIndex].matched = true;
                    
                    let el = document.getElementById('word-' + currentTargetIndex);
                    el.classList.remove('active');
                    el.classList.add('matched'); 
                    
                    currentTargetIndex++;
                    
                    if (currentTargetIndex < currentWords.length) {
                        document.getElementById('word-' + currentTargetIndex).classList.add('active');
                    }
                } else {
                    break; 
                }
            }
            
            if(currentTargetIndex === currentWords.length && currentWords.length > 0) {
                statusEl.innerHTML = "🎉 <b>Sempurna!</b> Hafalan Anda selesai dan benar.";
                statusEl.style.backgroundColor = "#d4efdf";
                statusEl.style.color = "#27ae60";
                stopRecording();
            }
        }

        function stopRecording() {
            if(recognition) recognition.stop();
            startBtn.style.display = 'inline-block';
            stopBtn.style.display = 'none';
        }

        startBtn.addEventListener('click', () => {
            if(!selectEl.value) {
                alert("Pilih hadits terlebih dahulu!");
                return;
            }
            recognition.start();
        });

        stopBtn.addEventListener('click', stopRecording);

    </script>
</body>
</html>
