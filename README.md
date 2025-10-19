
[index.html](https://github.com/user-attachments/files/22988900/index.html)
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Chúc mừng 20/10</title>
    <link
        href="https://fonts.googleapis.com/css2?family=Mali:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;1,200;1,300;1,400;1,500;1,600;1,700&display=swap"
        rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #fffafa);
            overflow: hidden;
            font-family: "Mali", cursive;
            height: 100vh;
            position: relative;
        }

        .center-message {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.95), rgba(255, 240, 245, 0.9));
            padding: 40px 50px;
            border-radius: 30px;
            font-size: 1.6rem;
            font-weight: 400;
            color: #c2185b;
            text-align: center;
            box-shadow: 0 20px 60px rgba(216, 27, 96, 0.3),
                0 0 0 1px rgba(255, 255, 255, 0.5) inset;
            z-index: 1;
            max-width: 90%;
            animation: pulse 3s ease-in-out infinite;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        @keyframes pulse {

            0%,
            100% {
                transform: translate(-50%, -50%) scale(1);
            }

            50% {
                transform: translate(-50%, -50%) scale(1.05);
            }
        }

        .center-message strong {
            display: block;
            font-size: 2rem;
            margin-bottom: 15px;
            font-weight: 700;
            background: linear-gradient(45deg, #d81b60, #f06292, #d81b60);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 3s ease infinite;
        }

        @keyframes gradient {

            0%,
            100% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
            z-index: 99;
            display: none;
            animation: fadeInOverlay 0.3s ease;
        }

        @keyframes fadeInOverlay {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }

        .overlay.active {
            display: block;
        }

        .popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0.8);
            background: linear-gradient(135deg, #ffffff 0%, #fff5f8 100%);
            border-radius: 25px;
            box-shadow: 0 25px 80px rgba(216, 27, 96, 0.4);
            padding: 30px;
            text-align: center;
            z-index: 100;
            width: 90%;
            max-width: 400px;
            display: none;
            animation: popupShow 0.5s cubic-bezier(0.68, -0.55, 0.265, 1.55) forwards;
            border: 3px solid rgba(255, 255, 255, 0.8);
        }

        @keyframes popupShow {
            from {
                opacity: 0;
                transform: translate(-50%, -50%) scale(0.5) rotate(-5deg);
            }

            to {
                opacity: 1;
                transform: translate(-50%, -50%) scale(1) rotate(0deg);
            }
        }

        /* .popup::before {
            content: '🌸';
            position: absolute;
            top: -30px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3rem;
            animation: bounce 1s ease-in-out infinite;
        } */

        @keyframes bounce {

            0%,
            100% {
                transform: translateX(-50%) translateY(0);
            }

            50% {
                transform: translateX(-50%) translateY(-10px);
            }
        }

        .popup-content {
            margin-top: 20px;
        }

        .popup img {
            max-width: 100%;
            border-radius: 15px;
            margin-bottom: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            border: 3px solid white;
        }

        .popup p {
            font-size: 1.1rem;
            color: #d81b60;
            line-height: 1.6;
            margin-bottom: 20px;
            font-weight: 500;
        }

        .popup button {
            margin-top: 10px;
            background: linear-gradient(135deg, #d81b60 0%, #f06292 100%);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            box-shadow: 0 5px 20px rgba(216, 27, 96, 0.4);
            transition: all 0.3s ease;
        }

        .popup button:hover {
            background: linear-gradient(135deg, #ad1457 0%, #e91e63 100%);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(216, 27, 96, 0.5);
        }

        .popup button:active {
            transform: translateY(0);
        }

        .falling-letter {
            position: absolute;
            top: -100px;
            width: 50px;
            height: auto;
            animation: fall linear;
            cursor: pointer;
            user-select: none;
            z-index: 2;
            animation-duration: 8s;
            filter: drop-shadow(0 5px 10px rgba(0, 0, 0, 0.2));
            transition: transform 0.3s ease;
        }

        .falling-letter:hover {
            transform: scale(1.2) rotate(10deg);
            filter: drop-shadow(0 10px 20px rgba(216, 27, 96, 0.4));
        }

        @keyframes fall {
            0% {
                transform: translateY(0) translateX(0) rotate(0deg);
                opacity: 1;
            }

            20% {
                transform: translateY(20vh) translateX(-20px) rotate(-10deg);
            }

            40% {
                transform: translateY(40vh) translateX(15px) rotate(8deg);
            }

            60% {
                transform: translateY(60vh) translateX(-15px) rotate(-6deg);
            }

            80% {
                transform: translateY(80vh) translateX(10px) rotate(4deg);
            }

            100% {
                transform: translateY(100vh) translateX(0) rotate(0deg);
                opacity: 0.3;
            }
        }

        @keyframes letterClick {
            0% {
                transform: scale(1) rotate(0deg);
            }

            50% {
                transform: scale(1.3) rotate(360deg);
            }

            100% {
                transform: scale(0) rotate(720deg);
            }
        }

        .letter-clicked {
            animation: letterClick 0.6s ease-out forwards !important;
        }

        .heart {
            position: absolute;
            transform: translate(-50%, -50%);
            animation: explode 2s ease-out forwards;
            pointer-events: none;
            user-select: none;
        }

        @keyframes explode {
            0% {
                transform: translate(-50%, -50%) translate(0, 0);
                opacity: 1;
            }

            100% {
                transform: translate(-50%, -50%) translate(var(--dx), var(--dy)) scale(1.5);
                opacity: 0;
            }
        }

        .center-gif {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            max-width: 40vw;
            z-index: 10;
            pointer-events: none;
        }

        /* ------------------------------
        Responsive cho màn hình nhỏ
        ---------------------------------- */
        @media (max-width: 768px) {
            .center-message {
                width: calc(100% - 20px);
                max-width: none;
                padding: 20px 15px;
                font-size: 1.1rem;
                border-radius: 20px;
                left: 50%;
                transform: translate(-50%, -50%);
            }

            .center-message strong {
                font-size: 1.3rem;
                margin-bottom: 10px;
            }

            .popup {
                width: 90%;
                padding: 20px;
                border-radius: 20px;
            }

            .popup img {
                border-radius: 10px;
                margin-bottom: 15px;
            }

            .popup p {
                font-size: 1rem;
                line-height: 1.5;
            }

            .popup button {
                padding: 10px 25px;
                font-size: 0.95rem;
            }

            .falling-letter {
                width: 40px;
                animation-duration: 9s;
            }

            .heart {
                font-size: 18px !important;
            }

            .falling-letter::before {
                content: '';
                position: absolute;
                top: -10px;
                left: -10px;
                right: -10px;
                bottom: -10px;
            }
        }
    </style>
</head>

<body>
    <!-- Thông điệp chúc mừng-->
    <div class="center-message">
        <strong>Chúc mừng 20-10</strong> <!--Sửa tiêu đề chúc mừng ở đây-->
        <span id="centerText">
            Ngày Phụ nữ Việt Nam<br> <!-- Sử lời nhắn hiển thị đầu ở đây-->
            Mở quà rồi hảa .Trước hết thì chúc em luôn xinh xắn như 1 bông hoa he ((((= .Anh cx kh gỏi ăn nói đâu, có j thì bỏ qua nhá? Anh tặng em quà, chắc cx em cx đoán đc j r nhỉ?Không lòng vòng nữa, anh nói thật thì anh thih em mất rồi ((((=. Cho anh cơ hội tìm hiểu nhá? FB anh đây: Duy Bình Đào có thằng ngồi buồn buồn hút thuốc ý . Đồng ý thì kết hem, kh muốn thì thoai k sao cả. À quên quà anh còn món quà nho nhỏ nx mà nó về kh có kịp V:, hay đồng ý đi để anh tặng nốt ((((=. Thôi đùa đấy, lựa chọn là của em, anh đợi. Hết òi, còn j nữa đâu, đợi em trl đó, 2 ngày he
        </span>
    </div>

    <!-- Ảnh động trang trí -->
    <img src="./assets/mewmew.gif" alt="GIF" class="center-gif" /> <!-- Thay ảnh động bên dưới -->

    <!-- Hiển thị lời chúc -->
    <div class="popup" id="popup">
        <div class="popup-content">
            <img id="popupImage" src="" alt="Lời chúc">
            <p id="popupMessage">Lời chúc ở đây</p>
        </div>
    </div>
    <div class="overlay" id="overlay"></div>

    <!-- Nhạc nền  -->
    <audio id="player" src="./assets/a.mp3"></audio> <!-- Sửa bài hát ở đây -->

    <script>
        //Sửa ảnh và lời nhắn ở đây
        const messages = [
            {
                img: "./assets/a1.jpg", //Thay ảnh
                text: "Chúc bạn luôn vui vẻ, xinh đẹp và ngập tràn yêu thương!" //Thay lời nhắn
            },
            {
                img: "./assets/a2.jpg",
                text: "Mỗi ngày của bạn đều là một đoá hoa nở rộ."
            },
            {
                img: "./assets/a3.jpg",
                text: "Cảm ơn bạn vì đã luôn mạnh mẽ và tuyệt vời như thế!"
            },
            {
                img: "./assets/a4.jpg",
                text: "Chúc bạn một ngày 20/10 thật hạnh phúc và trọn vẹn! "
            },
            {
                img: "./assets/a5.jpg",
                text: "Bạn là món quà tuyệt vời nhất mà cuộc sống mang lại! "
            }
        ];

        let currentMessageIndex = 0;
        let hasFirstLetterFallen = false;

        const popup = document.getElementById("popup");
        const overlay = document.getElementById("overlay");
        const popupImage = document.getElementById("popupImage");
        const popupMessage = document.getElementById("popupMessage");
        const centerText = document.getElementById("centerText");
        //Thay những ảnh rơi từ trên xuống ở đây
        const letterImages = [
            "<!doctype html>
<html lang="vi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Hiển thị ảnh - q3.png</title>
<style>
:root{--bg:#fff8fb;--card:#fff;--accent:#f6c0d6;--border:#5b4156}
html,body{height:100%;margin:0;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial}
body{display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg,var(--bg),#fff);padding:32px}
.card{background:var(--card);border-radius:16px;padding:28px;box-shadow:0 10px 30px rgba(91,65,86,0.08);border:2px solid rgba(91,65,86,0.06);text-align:center;max-width:520px;width:100%}
h1{margin:0 0 10px;font-size:20px;color:var(--border)}
p{margin:0 0 18px;color:#6b5866}
.img-wrap{display:inline-block;padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(246,192,214,0.35), rgba(246,192,214,0.08));}
img{display:block;max-width:420px;width:100%;height:auto;border-radius:10px;box-shadow:0 6px 18px rgba(91,65,86,0.12)}
.controls{margin-top:18px;display:flex;gap:12px;justify-content:center}
.btn{padding:10px 14px;border-radius:10px;border:0;font-weight:600;cursor:pointer}
.btn--download{background:var(--accent);color:#5b2f4a}
.btn--full{background:#5b2f4a;color:#fff}
.note{margin-top:12px;color:#7a666f;font-size:13px}
@media (max-width:420px){.card{padding:18px}img{max-width:320px}}
</style>
</head>
<body>
<div class="card">
<h1>Ảnh: q3.png</h1>
<p>Ví dụ code HTML để hiển thị và tải ảnh này (đặt file ảnh cùng thư mục với file HTML).</p>


<div class="img-wrap">
<!-- Đổi src nếu bạn lưu ảnh với tên khác hoặc ở thư mục khác -->
<img id="myImage" src="q3.png" alt="Gift image" />
</div>


<div class="controls">
<!-- link download: attribute `download` gợi trình duyệt tải về thay vì mở -->
<a class="btn btn--download" href="q3.png" download="gift-q3.png">Tải ảnh (.png)</a>
<!-- mở ảnh trong tab mới -->
<button class="btn btn--full" id="openBtn">Mở ảnh trong tab mới</button>
</div>


<div class="note">Lưu ý: đặt <code>q3.png</code> vào cùng thư mục với file HTML rồi mở file bằng trình duyệt (double-click).</div>
</div>


<script>
document.getElementById('openBtn').addEventListener('click', ()=>{
const img = document.getElementById('myImage').src;
window.open(img, '_blank');",
            "./assets/q3.png",
            "./assets/h1.png",
            "./assets/h3.png",
            "./assets/t2.png",
            "./assets/t5.png",
        ];

        function createHeartExplosion(x, y) {
            //Thay icon khi ấn thư, hoa, quà
            const hearts = ['💗'];
            const numHearts = 12;

            for (let i = 0; i < numHearts; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.textContent = hearts[Math.floor(Math.random() * hearts.length)];

                const angle = (Math.PI * 2 / numHearts) * i;
                const distance = Math.random() * 80 + 40;

                heart.style.left = x + 'px';
                heart.style.top = y + 'px';
                heart.style.setProperty('--dx', Math.cos(angle) * distance + 'px');
                heart.style.setProperty('--dy', Math.sin(angle) * distance + 'px');
                heart.style.fontSize = (Math.random() * 10 + 20) + 'px';

                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 2000);
            }
        }

        function createFallingLetter() {
            const letter = document.createElement("img");
            const randomImage = letterImages[Math.floor(Math.random() * letterImages.length)];
            letter.src = randomImage;
            letter.classList.add("falling-letter");
            letter.style.left = Math.random() * (window.innerWidth - 50) + "px";
            letter.addEventListener("click", (e) => {
                createHeartExplosion(e.clientX, e.clientY);
                letter.classList.add('letter-clicked');
                setTimeout(() => {
                    showPopup();
                }, 300);
            });

            document.body.appendChild(letter);

            setTimeout(() => {
                letter.remove();
            }, 8000);
        }

        function showPopup() {
            const message = messages[currentMessageIndex];
            popupImage.src = message.img;
            popupMessage.textContent = message.text;
            popup.style.display = "block";
            overlay.classList.add("active");

            popup.dataset.currentMessage = message.text;

            currentMessageIndex = (currentMessageIndex + 1) % messages.length;
        }

        function closePopup() {
            popup.style.display = "none";
            overlay.classList.remove("active");

            if (popup.dataset.currentMessage) {
                centerText.innerHTML = popup.dataset.currentMessage;
            }
        }

        document.body.addEventListener("click", function () {
            const player = document.getElementById("player");
            if (player.paused) {
                player.play();
            }
        });

        overlay.addEventListener("click", closePopup);
        setInterval(() => {
            createFallingLetter();
        }, 1000);
    </script>

</body>

</html>
