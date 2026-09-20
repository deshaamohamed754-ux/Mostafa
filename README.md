<!DOCTYPE html>
<html lang="ar" dir="rtl">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>يا هري ❤️</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #000;
            color: #00ff66;
            font-family: "Courier New", monospace;
            height: 100vh;
            overflow: hidden;
        }

        /* كود الهكر في الخلفية */

        .matrix {
            position: fixed;
            inset: 0;
            overflow: hidden;
            opacity: .35;
            z-index: 1;
        }

        .code {
            position: absolute;
            top: -200px;
            color: #00ff66;
            font-size: 18px;
            line-height: 1.5;
            white-space: pre;
            animation: fall linear infinite;
            text-shadow: 0 0 8px #00ff66;
        }

        @keyframes fall {
            from {
                transform: translateY(-300px);
            }

            to {
                transform: translateY(110vh);
            }
        }

        /* الكلام الأساسي */

        .content {
            position: relative;
            z-index: 5;
            height: 100vh;

            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            text-align: center;
        }

        h1 {
            font-size: 70px;
            color: #00ff66;
            text-shadow:
                0 0 10px #00ff66,
                0 0 30px #00ff66;

            animation: pulse 1.5s infinite;
        }

        p {
            margin-top: 20px;
            color: #00ff66;
            font-size: 20px;
            text-shadow: 0 0 10px #00ff66;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.08);
            }
        }

        /* القلوب */

        .heart {
            position: fixed;
            bottom: -50px;
            z-index: 6;
            font-size: 25px;
            animation: heartUp linear forwards;
            filter: drop-shadow(0 0 8px red);
        }

        @keyframes heartUp {
            0% {
                transform: translateY(0) scale(.5);
                opacity: 0;
            }

            15% {
                opacity: 1;
            }

            100% {
                transform: translateY(-110vh) scale(1.4);
                opacity: 0;
            }
        }

        @media (max-width: 600px) {

            h1 {
                font-size: 55px;
            }

            p {
                font-size: 17px;
            }

            .code {
                font-size: 14px;
            }
        }
    </style>
</head>

<body>

    <!-- الخلفية -->

    <div class="matrix" id="matrix"></div>


    <!-- الرسالة -->

    <div class="content">

        <h1>يا هري ❤️</h1>

        <p>
            دي ليك يا صاحبي 😂
        </p>

    </div>


    <script>

        /* إنشاء كود الهكر في الخلفية */

        const matrix = document.getElementById("matrix");

        const hackerText = [
            "01010101",
            "SYSTEM ONLINE",
            "ACCESS GRANTED",
            "01001000",
            "WELCOME",
            "CODE 404",
            "HELLO WORLD",
            "01010110",
            "LOADING...",
            "USER FRIEND",
            "SYSTEM READY",
            "01001111",
            "01010101",
            "LOVE.exe",
            "FRIENDSHIP.exe"
        ];


        for (let i = 0; i < 25; i++) {

            const code = document.createElement("div");

            code.className = "code";

            code.innerText =
                Array(8)
                .fill(0)
                .map(() =>
                    hackerText[
                        Math.floor(
                            Math.random() * hackerText.length
                        )
                    ]
                )
                .join("\n");

            code.style.left =
                Math.random() * 100 + "vw";

            code.style.animationDuration =
                (5 + Math.random() * 8) + "s";

            code.style.animationDelay =
                Math.random() * 5 + "s";

            matrix.appendChild(code);
        }


        /* إنشاء القلوب */

        function createHeart() {

            const heart =
                document.createElement("div");

            heart.className = "heart";

            heart.innerHTML = "❤️";

            heart.style.left =
                Math.random() * 100 + "vw";

            heart.style.animationDuration =
                (4 + Math.random() * 4) + "s";

            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 8000);
        }


        setInterval(createHeart, 500);

    </script>

</body>

</html>
