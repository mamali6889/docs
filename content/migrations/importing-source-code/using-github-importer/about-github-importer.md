<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بزرگان ایران</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f3f3f3;
            color: #333;
            margin: 0;
            padding: 0;
            transition: background-color 0.3s, color 0.3s;
        }
        body.dark-mode {
            background-color: #333;
            color: #f3f3f3;
        }
        header {
            background-color: #0066cc;
            color: white;
            padding: 20px 0;
        }
        nav {
            margin-top: 20px;
        }
        nav a {
            color: #0066cc;
            text-decoration: none;
            margin: 0 10px;
            font-size: 1.1em;
            font-weight: bold;
        }
        nav a:hover {
            text-decoration: underline;
            color: #004080;
        }
        nav a.dark-mode {
            color: #80c1ff;
        }
        .search-container {
            margin: 20px 0;
            text-align: center;
        }
        #searchInput {
            padding: 10px;
            font-size: 1em;
            border: 1px solid #ccc;
            border-radius: 5px;
            width: 80%;
            max-width: 400px;
        }
        .container {
            margin-top: 30px;
        }
        .container h1 {
            font-size: 2em;
        }
        .quote-box {
            margin: 20px auto;
            font-style: italic;
            font-size: 1.2em;
            color: #007acc;
            max-width: 600px;
        }
        footer {
            background-color: #e6e6e6;
            padding: 10px 0;
            margin-top: 20px;
            font-size: 0.9em;
            color: #666;
        }
        footer.dark-mode {
            background-color: #444;
            color: #ccc;
        }
        .toggle-button {
            margin: 10px;
            padding: 10px 20px;
            background-color: #0066cc;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1em;
            cursor: pointer;
        }
        .toggle-button:hover {
            background-color: #004080;
        }
    </style>
    <script>
        function updateDateTime() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById("date").innerHTML = now.toLocaleDateString('fa-IR', options);
            document.getElementById("time").innerHTML = now.toLocaleTimeString('fa-IR');
        }
        setInterval(updateDateTime, 1000);

        function searchFunction() {
            const input = document.getElementById('searchInput').value.toLowerCase();
            const links = document.querySelectorAll('nav a');

            links.forEach(link => {
                const text = link.textContent.toLowerCase();
                if (text.includes(input)) {
                    link.style.display = 'inline';
                } else {
                    link.style.display = 'none';
                }
            });
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            document.querySelectorAll('nav a').forEach(link => link.classList.toggle('dark-mode'));
            document.querySelector('footer').classList.toggle('dark-mode');
        }

        function showRandomQuote() {
            const quotes = [
                "بزرگی روح انسان در کلام او نمایان می‌شود.",
                "از بزرگان درس زندگی بگیریم.",
                "حافظ: هر که خود را نکشد یاری رفیق حق نشد.",
                "ابن سینا: علم بدون اخلاق همانند شمشیر در دست دیوانه است.",
                "سعدی: به راه نیک توان رفت، اگر اراده‌ایی باشد."
            ];
            const randomIndex = Math.floor(Math.random() * quotes.length);
            document.getElementById("quote").textContent = quotes[randomIndex];
        }
        setInterval(showRandomQuote, 5000); // تغییر نقل‌قول هر ۵ ثانیه
    </script>
</head>
<body>
    <header>
        <h1>بزرگان ایران</h1>
    </header>
    <nav>
        <a href="attar.html">عطار</a>
        <a href="avicenna.html">ابن سینا</a>
        <a href="ferdowsi.html">فردوسی</a>
        <a href="hafez.html">حافظ</a>
        <a href="khayyam.html">خیام</a>
        <a href="nezami.html">نظامی</a>
        <a href="razi.html">رازی</a>
        <a href="saadi.html">سعدی</a>
        <a href="soleimani.html">سردار سلیمانی</a>
    </nav>
    <div class="search-container">
        <input type="text" id="searchInput" placeholder="نام بزرگی را جستجو کنید..." onkeyup="searchFunction()" />
    </div>
    <button class="toggle-button" onclick="toggleDarkMode()">تغییر حالت روز/شب</button>
    <div class="container">
        <h1>صفحه اول وب‌سایت</h1>
        <p>برای اطلاعات بیشتر روی نام‌ها کلیک کنید.</p>
        <div class="quote-box" id="quote">از بزرگان درس زندگی بگیریم.</div>
        <div class="date-time">
            <p>تاریخ: <span id="date"></span></p>
            <p>ساعت: <span id="time"></span></p>
        </div>
    </div>
    <footer>
        <p>این وب‌سایت با هدف حفظ و بزرگداشت بزرگان ایران ساخته شده است.</p>
    </footer>
</body>
</html>
