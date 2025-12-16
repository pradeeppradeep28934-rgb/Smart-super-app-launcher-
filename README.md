
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>launchX</title>

    <style>
        body {
            font-family: sans-serif;
            text-align: center;
            background: #f4f6f8;
            padding: 30px;
            transition: background 0.3s, color 0.3s;
            border-left: 6px solid cadetblue;
            border-right: 6px solid cadetblue;
            border-top: 6px solid cadetblue;
            border-bottom: 6px cadetblue;
            box-sizing: border-box;
        }

        h1 {
            color: cadetblue;
            margin-bottom: 20px;
        }

        #search {
            padding: 10px;
            width: 250px;
            font-size: 16px;
            margin-bottom: 20px;
        }

        button {
            padding: 10px 15px;
            margin-left: 10px;
            cursor: pointer;
        }

        .app-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            max-width: 800px;
            margin: auto;
        }

        .app-box {
            background: rgb(55, 215, 135);
            padding: 20px;
            border-radius: 10px;
            text-decoration: none;
            color: #333;
            font-size: 18px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.2s ease, background-color 0.2s ease;
        }

        .app-box:hover {
            transform: scale(1.05);
            background-color: rgb(53, 96, 188);
            color: white;
        }

        /* Dark mode */
        .dark {
            background: #111;
            color: white;
        }

        .dark .app-box {
            background: #222;
            color: white;
        }
    </style>
</head>

<body>

    <h1>smart super app launcher</h1>

    <!-- Search & Dark Mode -->
    <input type="text" id="search" placeholder="Search app..." onkeyup="searchApp()">
    <button onclick="toggleDark()">Dark Mode</button>

    <p id="count">Apps Opened: 0</p>

    <div class="app-grid">
        <a href="https://www.swiggy.com" target="_blank" class="app-box">Swiggy</a>
        <a href="https://www.zomato.com" target="_blank" class="app-box">Zomato</a>
        <a href="https://www.amazon.in" target="_blank" class="app-box">Amazon</a>
        <a href="https://www.flipkart.com" target="_blank" class="app-box">Flipkart</a>
        <a href="https://www.blinkit.com" target="_blank" class="app-box">Blinkit</a>
        <a href="https://www.makemytrip.com" target="_blank" class="app-box">Travel</a>
        <a href="https://www.bookmyshow.com" target="_blank" class="app-box">BookMyShow</a>
        <a href="https://www.pharmeasy.com" target="_blank" class="app-box">PharmEasy</a>
        <a href="https://www.youtube.com" target="_blank" class="app-box">youtube</a>
        <a href="https://www.instagram.com" target="_blank" class="app-box">instagram</a>
        <a href="https://www.google.com" target="_blank" class="app-box">google</a>
        <a href="https://www.rapido.com" target="_blank" class="app-box">rapido</a>
        <a href="https://www.poki.com" target="_blank" class="app-box">free online gams</a>
        </div>

    <!-- JavaScript -->
    <script>
        // Search Filter
        function searchApp() {
            let input = document.getElementById("search").value.toLowerCase();
            let apps = document.getElementsByClassName("app-box");

            for (let i = 0; i < apps.length; i++) {
                let name = apps[i].innerText.toLowerCase();
                apps[i].style.display = name.includes(input) ? "block" : "none";
            }
        }

        // Dark Mode
        function toggleDark() {
            document.body.classList.toggle("dark");
        }

        // Click Counter
        let count = 0;
        let display = document.getElementById("count");

        document.querySelectorAll(".app-box").forEach(app => {
            app.addEventListener("click", () => {
                count++;
                display.innerText = "Apps Opened: " + count;
            });
        });
    </script>

</body>
</html>


