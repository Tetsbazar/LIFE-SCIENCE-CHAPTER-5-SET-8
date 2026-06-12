<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জীবন বিজ্ঞান কুইজ - অধ্যায় ৫ (সেট ৮ - ১০ মিনিট)</title>
    <style>
        :root {
            --primary-color: #27ae60;
            --primary-hover: #1e8449;
            --bg-color: #f4f9f4;
            --text-color: #2c3e50;
            --card-bg: #ffffff;
            --correct-color: #2ecc71;
            --wrong-color: #e74c3c;
            --timer-color: #d35400;
            --admin-color: #8e44ad;
            --next-set-color: #2980b9;
            --next-set-hover: #3498db;
        }

        body {
            font-family: 'Segoe UI', Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 800px;
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(39, 174, 96, 0.08);
            position: relative;
            height: fit-content;
        }

        h1 {
            text-align: center;
            color: var(--primary-hover);
            margin-bottom: 5px;
            font-size: 1.8em;
        }

        .subtitle {
            text-align: center;
            color: #7f8c8d;
            margin-bottom: 25px;
            font-size: 1em;
        }

        /* Login Section Styles */
        #login-section {
            display: block;
            max-width: 400px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #555;
        }

        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1.1em;
            box-sizing: border-box;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        .error-message {
            color: var(--wrong-color);
            text-align: center;
            font-weight: bold;
            margin-bottom: 15px;
            display: none;
        }

        /* Quiz & Admin Sections */
        #quiz-section, #admin-section {
            display: none;
        }

        .question-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            font-weight: bold;
            color: #7f8c8d;
        }

        .timer-box {
            background-color: #fdf2e9;
            color: var(--timer-color);
            padding: 6px 15px;
            border-radius: 20px;
            border: 1px solid #fadbd8;
            font-size: 1.1em;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .question-text {
            font-size: 1.25em;
            font-weight: 600;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .options-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .option-item {
            background-color: #f8f9fa;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            padding: 15px 20px;
            margin-bottom: 12px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .option-item:hover {
            border-color: var(--primary-color);
            background-color: #f4fbf6;
        }

        .option-item.selected {
            background-color: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        .btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn:hover {
            background-color: var(--primary-hover);
        }

        /* Next Set Link Button */
        .btn-next-set {
            background-color: var(--next-set-color);
            text-align: center;
            text-decoration: none;
            display: block;
            box-sizing: border-box;
            font-size: 1.1em;
            font-weight: bold;
            color: white;
            padding: 15px 30px;
            border-radius: 8px;
            margin-top: 10px;
            transition: background-color 0.3s ease;
        }

        .btn-next-set:hover {
            background-color: var(--next-set-hover);
        }

        /* Admin Dashboard Table */
        .admin-title {
            color: var(--admin-color) !important;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            font-size: 1.05em;
        }

        th, td {
            border: 1px solid #e2e8f0;
            padding: 12px 15px;
            text-align: left;
        }

        th {
            background-color: #f1f5f9;
            color: #334155;
            font-weight: bold;
        }

        tr:nth-child(even) {
            background-color: #f8fafc;
        }

        /* Results Display */
        #result-section {
            display: none;
        }

        .score-board {
            text-align: center;
            padding: 20px;
            background: linear-gradient(135deg, #eaf2e8, #d5ebd5);
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .score-board h2 {
            margin: 0;
            color: #2c3e50;
            font-size: 1.8em;
        }

        .review-item {
            background-color: #fdfdfd;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.02);
        }

        .review-q {
            font-size: 1.1em;
            font-weight: bold;
            margin-bottom: 15px;
        }

        .review-ans {
            margin-bottom: 8px;
            font-size: 1em;
        }

        .ans-correct { color: var(--correct-color); font-weight: bold; }
        .ans-wrong { color: var(--wrong-color); font-weight: bold; }

        .explanation {
            background-color: #fff9e6;
            border-left: 4px solid #f1c40f;
            padding: 12px 15px;
            margin-top: 15px;
            font-size: 0.95em;
            color: #555;
            border-radius: 0 4px 4px 0;
        }

        .welcome-text {
            color: var(--primary-hover);
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="container">

    <!-- Login Section -->
    <div id="login-section">
        <h1>স্টুডেন্ট ও অ্যাডমিন লগইন</h1>
        <p class="subtitle">জীবন বিজ্ঞান প্র্যাকটিস সেট শুরু করতে নিচে লগইন করুন</p>

        <div class="form-group">
            <label for="username">ইউজারনেম (Username)</label>
            <input type="text" id="username" placeholder="আপনার ইউজারনেম দিন" autocomplete="off">
        </div>

        <div class="form-group">
            <label for="password">পাসওয়ার্ড (Password)</label>
            <input type="password" id="password" placeholder="আপনার গোপন পাসওয়ার্ড দিন">
        </div>

        <div class="error-message" id="error-message">ইউজারনেম অথবা পাসওয়ার্ড ভুল হয়েছে!</div>

        <button class="btn" id="login-btn">লগইন করুন</button>
    </div>

    <!-- Admin Panel Section -->
    <div id="admin-section">
        <h1 class="admin-title">📊 শিক্ষক ড্যাশবোর্ড (Admin Panel)</h1>
        <p class="subtitle">পরীক্ষার্থীদের লাইভ পারফরম্যান্স ও মক টেস্টের ফুল রিপোর্ট</p>
        
        <table>
            <thead>
                <tr>
                    <th>ছাত্রের নাম (Username)</th>
                    <th>সর্বোচ্চ স্কোর (Best Score)</th>
                    <th>মোট কতবার দিয়েছে (Total Attempts)</th>
                </tr>
            </thead>
            <tbody id="admin-table-body">
                <!-- Data injected via JS -->
            </tbody>
        </table>
        
        <button class="btn" style="background-color: var(--admin-color); margin-top: 30px;" onclick="clearReports()">সমস্ত রেকর্ড রিসেট করুন</button>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

    <!-- Quiz Section -->
    <div id="quiz-section">
        <h1>জীবন বিজ্ঞান কুইজ: অধ্যায় ৫</h1>
        <div class="subtitle">
            <span class="welcome-text">পরীক্ষার্থী: <span id="student-name"></span></span> | সেট ৮: জীববৈচিত্র্য সংরক্ষণ (In-situ ও Ex-situ)
        </div>

        <div class="question-header">
            <span id="q-counter">প্রশ্ন: ১ / ১৫</span>
            <div class="timer-box">
                ⏱️ সময় বাকি: <span id="timer-display">10:00</span>
            </div>
        </div>

        <div class="question-text" id="question-text">এখানে প্রশ্ন আসবে</div>
        <ul class="options-list" id="options-list">
            <!-- Options via JS -->
        </ul>

        <button class="btn" id="next-btn">পরবর্তী প্রশ্ন</button>
    </div>

    <!-- Result Section -->
    <div id="result-section">
        <div class="score-board">
            <h2>পরীক্ষা সম্পন্ন হয়েছে, <span id="result-student-name"></span>!</h2>
            <h1 style="margin-top: 10px;" id="final-score">স্কোর: 0 / 15</h1>
        </div>

        <!-- Set 9 Link Redirect Button -->
        <a href="https://tetsbazar.github.io/LIFE-SCIENCE-CHAPTER-5-SET-9-/" target="_blank" class="btn-next-set">
            👉 পরবর্তী মক টেস্ট (সেট - ৯) দেওয়ার জন্য এখানে ক্লিক করুন
        </a>

        <h3 style="margin-top: 30px;">প্রশ্নের বিস্তারিত পর্যালোচনা:</h3>
        <div id="review-container">
            <!-- Review items via JS -->
        </div>
        <button class="btn" onclick="location.reload()">লগ আউট করুন</button>
    </div>

</div>

<script>
    // --- Login System Database ---
    const approvedStudents = {
        "anil7890": "12345677",
        "samir7890": "12345666",
        "rahul2024": "pass1234",
        "rohit999": "88889999",
        "suman007": "abcdef12",
        "Dhiren": "Dhiren1234",
        "Pradip": "Pradip1234",
        "Bijay": "Bijay1234",
        "admin": "admin1234" 
    };

    const loginSection = document.getElementById("login-section");
    const quizSection = document.getElementById("quiz-section");
    const adminSection = document.getElementById("admin-section");
    const adminTableBody = document.getElementById("admin-table-body");
    const usernameInput = document.getElementById("username");
    const passwordInput = document.getElementById("password");
    const loginBtn = document.getElementById("login-btn");
    const errorMessage = document.getElementById("error-message");
    const studentNameDisplay = document.getElementById("student-name");
    const resultStudentName = document.getElementById("result-student-name");

    let currentUsername = "";

    loginBtn.addEventListener("click", () => {
        const username = usernameInput.value.trim();
        const password = passwordInput.value.trim();

        if (approvedStudents[username] && approvedStudents[username] === password) {
            errorMessage.style.display = "none";
            loginSection.style.display = "none";
            currentUsername = username;

            if (username === "admin") {
                adminSection.style.display = "block";
                loadAdminData();
            } else {
                quizSection.style.display = "block";
                studentNameDisplay.innerText = username;
                resultStudentName.innerText = username;

                loadQuestion();
                startTimer(10 * 60); // 10 Minutes Timer
            }
        } else {
            errorMessage.style.display = "block";
        }
    });

    // --- Admin Dashboard Storage ---
    function loadAdminData() {
        adminTableBody.innerHTML = "";
        Object.keys(approvedStudents).forEach(user => {
            if (user !== "admin") {
                const userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s8_${user}`)) || { bestScore: "পরীক্ষা দেয়নি", attempts: 0 };
                
                const row = document.createElement("tr");
                row.innerHTML = `
                    <td><strong>${user}</strong></td>
                    <td style="color: ${typeof userReport.bestScore === 'number' ? 'var(--primary-color)' : '#7f8c8d'}; font-weight: bold;">
                        ${typeof userReport.bestScore === 'number' ? userReport.bestScore + ' / 15' : userReport.bestScore}
                    </td>
                    <td><span style="background: #e2e8f0; padding: 3px 10px; border-radius: 10px; font-weight: bold;">${userReport.attempts} বার</span></td>
                `;
                adminTableBody.appendChild(row);
            }
        });
    }

    function clearReports() {
        if (confirm("আপনি কি নিশ্চিতভাবে সমস্ত ছাত্র-ছাত্রীর পরীক্ষার রেকর্ড ও অ্যাটেম্পট হিস্ট্রি ডিলিট করতে চান?")) {
            Object.keys(approvedStudents).forEach(user => {
                if (user !== "admin") {
                    localStorage.removeItem(`quiz_report_ch5_s8_${user}`);
                }
            });
            loadAdminData();
            alert("সমস্ত ডাটা সফলভাবে রিসেট করা হয়েছে।");
        }
    }

    // --- Life Science Chapter 5 Set 8 Question Data Bank ---
    const quizData = [
        {
            question: "১. বন্যপ্রাণী বা উদ্ভিদকে তাদের নিজস্ব প্রাকৃতিক পরিবেশের মধ্যেই সংরক্ষণ করাকে কী বলে?",
            options: ["এক্স-সিটু সংরক্ষণ", "ইন-সিটু (In-situ) সংরক্ষণ", "চিড়িয়াখানা সংরক্ষণ", "ক্রায়োসংরক্ষণ"],
            answer: "ইন-সিটু (In-situ) সংরক্ষণ",
            explanation: "প্রাণী বা উদ্ভিদ যে প্রাকৃতিক অরণ্যে থাকে, সেই অরণ্যকেই সুরক্ষিত ঘোষণা করে তাকে সেখানে বাঁচিয়ে রাখার পদ্ধতিকে ইন-সিটু (স্বস্থানিক) সংরক্ষণ বলে।"
        },
        {
            question: "২. নিচের কোনটি ইন-সিটু সংরক্ষণের উদাহরণ নয়?",
            options: ["জাতীয় উদ্যান (National Park)", "অভয়ারণ্য (Sanctuary)", "বায়োস্ফিয়ার রিজার্ভ", "চিড়িয়াখানা (Zoo)"],
            answer: "চিড়িয়াখানা (Zoo)",
            explanation: "চিড়িয়াখানা হলো এক্স-সিটু সংরক্ষণ, কারণ এখানে প্রাণীকে তাদের প্রাকৃতিক পরিবেশ থেকে সরিয়ে এনে মানুষের তৈরি কৃত্রিম পরিবেশে খাঁচায় রাখা হয়।"
        },
        {
            question: "৩. বন্যপ্রাণী বা উদ্ভিদকে তাদের প্রাকৃতিক বাসস্থানের বাইরে কৃত্রিম পরিবেশে মানুষের পাহারায় সংরক্ষণ করাকে কী বলে?",
            options: ["ইন-সিটু সংরক্ষণ", "এক্স-সিটু (Ex-situ) সংরক্ষণ", "ইন-ভিট্রো", "ইন-ভিভো"],
            answer: "এক্স-সিটু (Ex-situ) সংরক্ষণ",
            explanation: "প্রাকৃতিক পরিবেশের বাইরে চিড়িয়াখানা, বোটানিক্যাল গার্ডেন এবং ক্রায়োসংরক্ষণ প্রযুক্তিতে সংরক্ষণ করাকে এক্স-সিটু (অস্থানিক) সংরক্ষণ বলে।"
        },
        {
            question: "৪. ভারতের প্রথম জাতীয় উদ্যান (National Park) কোনটি?",
            options: ["সুন্দরবন", "কাজিরাঙা", "জিম করবেট জাতীয় উদ্যান (Jim Corbett National Park)", "জলদাপাড়া"],
            answer: "জিম করবেট জাতীয় উদ্যান (Jim Corbett National Park)",
            explanation: "১৯৩৬ সালে উত্তরাখণ্ডে ভারতের প্রথম এই জাতীয় উদ্যানটি তৈরি হয়, যা বাঘ সংরক্ষণের জন্য বিখ্যাত।"
        },
        {
            question: "৫. জাতীয় উদ্যান বা ন্যাশনাল পার্কের একটি প্রধান বৈশিষ্ট্য কী?",
            options: ["এটি কেন্দ্রীয় সরকারের আইন দ্বারা নিয়ন্ত্রিত হয় এবং সাধারণ মানুষের অবাধ প্রবেশ নিষেধ", "এটি রাজ্য সরকারের অধীন", "এখানে সবাই পশু শিকার করতে পারে", "এখানে গাছ কাটা বৈধ"],
            answer: "এটি কেন্দ্রীয় সরকারের আইন দ্বারা নিয়ন্ত্রিত হয় এবং সাধারণ মানুষের অবাধ প্রবেশ নিষেধ",
            explanation: "জাতীয় উদ্যান হলো আইনত অত্যন্ত সুরক্ষিত বনাঞ্চল, যেখানে কোর বা প্রধান এলাকায় সাধারণ মানুষের প্রবেশ এবং কোনো প্রকার চাষবাস বা গাছ কাটা সম্পূর্ণ নিষিদ্ধ।"
        },
        {
            question: "৬. পশ্চিমবঙ্গের 'চাপড়ামারি' এবং কর্ণাটকের 'বন্দিপুর' কিসের উদাহরণ?",
            options: ["বোটানিক্যাল গার্ডেন", "চিড়িয়াখানা", "অভয়ারণ্য (Sanctuary)", "বায়োস্ফিয়ার রিজার্ভ"],
            answer: "অভয়ারণ্য (Sanctuary)",
            explanation: "অভয়ারণ্য বা স্যাঙ্কচুয়ারি হলো রাজ্য সরকারের নিয়ন্ত্রণাধীন বনাঞ্চল যেখানে নির্দিষ্ট বন্যপ্রাণী ও উদ্ভিদ প্রজাতি সুরক্ষিত থাকে।"
        },
        {
            question: "৭. ইউনেস্কোর (UNESCO) 'MAB' (Man and Biosphere) প্রকল্পের অধীনে কোনটি পড়ে?",
            options: ["জাতীয় উদ্যান", "অভয়ারণ্য", "বায়োস্ফিয়ার রিজার্ভ (Biosphere Reserve)", "চিড়িয়াখানা"],
            answer: "বায়োস্ফিয়ার রিজার্ভ (Biosphere Reserve)",
            explanation: "বায়োস্ফিয়ার রিজার্ভ হলো এমন একটি বিশাল এলাকা যেখানে বন্যপ্রাণীর পাশাপাশি পুরো বাস্তুতন্ত্র ও সেখানকার আদিবাসী বা স্থানীয় মানুষদের সংস্কৃতিও একসঙ্গে সংরক্ষণ করা হয়।"
        },
        {
            question: "৮. ভারতের প্রথম বায়োস্ফিয়ার রিজার্ভের নাম কী?",
            options: ["নীলগিরি", "সুন্দরবন", "মানস", "নন্দাদেবী"],
            answer: "নীলগিরি",
            explanation: "১৯৮৬ সালে ঘোষিত দক্ষিণ ভারতের নীলগিরি হলো ভারতবর্ষের প্রথম বায়োস্ফিয়ার রিজার্ভ।"
        },
        {
            question: "৯. ক্রায়োসংরক্ষণ (Cryopreservation) পদ্ধতিতে কত তাপমাত্রায় জীবজ উপাদান সংরক্ষণ করা হয়?",
            options: ["০°C", "মাইনাস ৫০°C (-50°C)", "মাইনাস ১৯৬°C (-196°C)", "১০০°C"],
            answer: "মাইনাস ১৯৬°C (-196°C)",
            explanation: "এই পদ্ধতিতে চরম শীতল অবস্থায় (মাইনাস ১৯৬ ডিগ্রি সেলসিয়াস) তরল নাইট্রোজেনের মধ্যে বিলুপ্তপ্রায় উদ্ভিদের শুক্রাণu, পরাগরেণু বা বীজ দীর্ঘদিন অক্ষত জমিয়ে রাখা হয়।"
        },
        {
            question: "১০. বিলুপ্ত বা বিপন্ন উদ্ভিদ ও প্রাণীর সমস্ত তথ্য সম্বলিত রেকর্ড বইটিকে কী বলা হয়?",
            options: ["গ্রিন ডাটা বুক", "ব্লু ডাটা বুক", "রেড ডাটা বুক (Red Data Book)", "হোয়াইট ডাটা বুক"],
            answer: "রেড ডাটা বুক (Red Data Book)",
            explanation: "১৯৬৩ সালে IUCN (ইন্টারন্যাশনাল ইউনিয়ন ফর কনজারভেশন অব নেচার) নামক বিশ্বসংস্থা বিলুপ্তপ্রায় জীবের তথ্য সম্বলিত এই রেড ডাটা বুক প্রথম প্রকাশ করে।"
        },
        {
            question: "১১. পৃথিবীর বিলুপ্তপ্রায় উদ্ভিদ প্রজাতি 'সোফোরা টোরোনিরো' (Sophora toroniro) বর্তমানে কোথায় সংরক্ষিত হয়ে বেঁচে আছে?",
            options: ["বোটানিক্যাল গার্ডেন-এ", "চিড়িয়াখানায়", "বনের গভীরে", "ন্যাশনাল পার্কে"],
            answer: "বোটানিক্যাল গার্ডেন-এ",
            explanation: "প্রাকৃতিক পরিবেশ থেকে সম্পূর্ণরূপে বিলুপ্ত হয়ে গেলেও এই এক্স-সিটু সংরক্ষণস্থল বোটানিক্যাল গার্ডেনগুলোতে গাছটিকে বৈজ্ঞানিক উপায়ে বাঁচিয়ে রাখা হয়েছে।"
        },
        {
            question: "১২. পশ্চিমবঙ্গের 'বক্সা' এবং গুজরাটের 'গির' অরণ্য কীসের উদাহরণ?",
            options: ["চিড়িয়াখানা", "সংরক্ষিত অরণ্য (Reserve Forest)", "ক্রায়োসংরক্ষণ", "বোটানিক্যাল গার্ডেন"],
            answer: "সংরক্ষিত অরণ্য (Reserve Forest)",
            explanation: "সংরক্ষিত অরণ্য বা রিজার্ভ ফরেস্ট হলো রাজ্য সরকার নিয়ন্ত্রিত বনাঞ্চল, যেখানে বন্যপ্রাণী সুরক্ষার্থে সাধারণের প্রবেশাধিকার আংশিক বা পূর্ণ নিয়ন্ত্রিত থাকে।"
        },
        {
            question: "১৩. তরল নাইট্রোজেনে শুক্রাণু বা বীজ সংরক্ষণ করা কোন সংরক্ষণের অংশ?",
            options: ["ইন-সিটু", "এক্স-সিটু (Ex-situ)", "অভয়ারণ্য", "কোনোটিই নয়"],
            answer: "এক্স-সিটু (Ex-situ)",
            explanation: "প্রাকৃতিক বা স্বাভাবিক পরিবেশের বাইরে সম্পূর্ণ ল্যাবরেটরির ভেতরে কৃত্রিমভাবে সংরক্ষণ করা হয় বলে এটি এক্স-সিটু সংরক্ষণের অন্তর্ভুক্ত।"
        },
        {
            question: "১৪. জীববৈচিত্র্য সংরক্ষণে 'WWF'-এর পুরো নাম কী?",
            options: ["ওয়ার্ল্ড ওয়াইড ফান্ড ফর নেচার (World Wide Fund for Nature)", "ওয়ার্ল্ড ওয়াইল্ডলাইফ ফরেস্ট", "ওয়ার্ল্ড ওয়েদার ফান্ড", "ওয়ার্ল্ড ওয়াটার ফোর্স"],
            answer: "ওয়ার্ল্ড ওয়াইড ফান্ড ফর নেচার (World Wide Fund for Nature)",
            explanation: "WWF হলো একটি আন্তর্জাতিক বেসরকারি সংস্থা যা বিশ্বজুড়ে পরিবেশের অবক্ষয় রোধ এবং বন্যপ্রাণী ও প্রকৃতি সংরক্ষণের জন্য কাজ করে।"
        },
        {
            question: "১৫. জলদাপাড়া ও গোরুমারা মূলত কী সংরক্ষণের জন্য বিখ্যাত?",
            options: ["বাঘ", "সিংহ", "একশৃঙ্গ গন্ডার", "রেড পান্ডা"],
            answer: "একশৃঙ্গ গন্ডার",
            explanation: "পশ্চিমবঙ্গের ডুয়ার্স অঞ্চলের অন্তর্গত জলদাপাড়া এবং গোরুমারা জাতীয় উদ্যানে বিলুপ্তপ্রায় ভারতীয় একশৃঙ্গ গন্ডারকে সফলভাবে ইন-সিটু সংরক্ষণ করা হচ্ছে।"
        }
    ];

    let currentQuestionIndex = 0;
    let score = 0;
    let selectedOption = "";
    let userAnswers = [];
    let timerInterval;

    const questionTextEl = document.getElementById("question-text");
    const optionsListEl = document.getElementById("options-list");
    const nextBtn = document.getElementById("next-btn");
    const qCounterEl = document.getElementById("q-counter");
    const timerDisplayEl = document.getElementById("timer-display");

    const resultSection = document.getElementById("result-section");
    const reviewContainer = document.getElementById("review-container");
    const finalScoreEl = document.getElementById("final-score");

    function startTimer(durationInSeconds) {
        let timeRemaining = durationInSeconds;
        
        timerInterval = setInterval(() => {
            let minutes = Math.floor(timeRemaining / 60);
            let seconds = timeRemaining % 60;

            minutes = minutes < 10 ? "0" + minutes : minutes;
            seconds = seconds < 10 ? "0" + seconds : seconds;

            timerDisplayEl.innerText = `${minutes}:${seconds}`;

            if (timeRemaining <= 0) {
                clearInterval(timerInterval);
                alert("আপনার কুইজের নির্ধারিত ১০ মিনিট সময় শেষ হয়ে গেছে! কুইজটি স্বয়ংক্রিয়ভাবে সাবমিট করা হচ্ছে।");
                showResults();
            }
            timeRemaining--;
        }, 1000);
    }

    function loadQuestion() {
        selectedOption = "";
        const currentData = quizData[currentQuestionIndex];

        qCounterEl.innerText = `প্রশ্ন: ${currentQuestionIndex + 1} / ${quizData.length}`;
        questionTextEl.innerText = currentData.question;
        optionsListEl.innerHTML = "";

        if(currentQuestionIndex === quizData.length - 1) {
            nextBtn.innerText = "কুইজ সম্পূর্ণ সাবমিট করুন";
            nextBtn.style.backgroundColor = "#27ae60";
        } else {
            nextBtn.innerText = "পরবর্তী প্রশ্ন";
            nextBtn.style.backgroundColor = "var(--primary-color)";
        }

        currentData.options.forEach(option => {
            const li = document.createElement("li");
            li.classList.add("option-item");
            li.innerText = option;
            li.onclick = () => selectOption(li, option);
            optionsListEl.appendChild(li);
        });
    }

    function selectOption(li, option) {
        const allOptions = document.querySelectorAll(".option-item");
        allOptions.forEach(opt => opt.classList.remove("selected"));
        li.classList.add("selected");
        selectedOption = option;
    }

    function saveStudentReport(finalScore) {
        let userReport = JSON.parse(localStorage.getItem(`quiz_report_ch5_s8_${currentUsername}`)) || { bestScore: 0, attempts: 0 };
        
        userReport.attempts += 1; 
        if (finalScore > userReport.bestScore) {
            userReport.bestScore = finalScore; 
        }

        localStorage.setItem(`quiz_report_ch5_s8_${currentUsername}`, JSON.stringify(userReport));
    }

    function showResults() {
        clearInterval(timerInterval);
        quizSection.style.display = "none";
        resultSection.style.display = "block";
        finalScoreEl.innerText = `স্কোর: ${score} / ${quizData.length}`;

        saveStudentReport(score);

        reviewContainer.innerHTML = ""; 
        quizData.forEach((item, index) => {
            const userAnswer = userAnswers[index];
            const isCorrect = userAnswer === item.answer;

            const reviewHtml = `
                <div class="review-item">
                    <div class="review-q">${item.question}</div>
                    <div class="review-ans">
                        আপনার উত্তর: <span class="${isCorrect ? 'ans-correct' : 'ans-wrong'}">
                            ${userAnswer ? userAnswer : 'উত্তর দেননি (Skipped/Time Out)'}
                        </span>
                    </div>
                    ${!isCorrect ? `<div class="review-ans">সঠিক উত্তর: <span class="ans-correct">${item.answer}</span></div>` : ''}
                    <div class="explanation">
                        <strong>ব্যাখ্যা:</strong> ${item.explanation}
                    </div>
                </div>
            `;
            reviewContainer.innerHTML += reviewHtml;
        });
    }

    nextBtn.addEventListener("click", () => {
        if (selectedOption === "") {
            const confirmSkip = confirm("আপনি কোনো অপশন সিলেক্ট করেননি। আপনি কি এই প্রশ্নটি স্কিপ (Skip) করতে চান?");
            if (!confirmSkip) {
                return; 
            }
            userAnswers[currentQuestionIndex] = null; 
        } else {
            userAnswers[currentQuestionIndex] = selectedOption;
            if (selectedOption === quizData[currentQuestionIndex].answer) {
                score++;
            }
        }

        currentQuestionIndex++;

        if (currentQuestionIndex < quizData.length) {
            loadQuestion();
        } else {
            showResults();
        }
    });
</script>

</body>
</html>
