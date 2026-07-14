<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kho Tàng Của Koi</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;800&family=Playfair+Display:ital,wght@0,700;1,400&display=swap" rel="stylesheet">
    <style>
        /* Thiết lập biến màu sắc để dễ quản lý */
        :root {
            --color-bg: #0a0a0a;          /* Đen chủ đạo */
            --color-card-bg: #141414;     /* Đen nhạt cho thẻ */
            --color-primary: #e63946;     /* Đỏ nổi bật */
            --color-beige: #f1ebd9;       /* Màu be sáng sang trọng */
            --color-beige-dark: #d8cfb4;  /* Màu be trầm hơn cho text phụ */
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        /* Reset css cơ bản */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--color-bg);
            color: var(--color-beige);
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            overflow-x: hidden;
        }

        /* Hiệu ứng hạt bụi mờ ảo phía sau nền */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(230, 57, 70, 0.05) 0%, rgba(0,0,0,0) 70%);
            z-index: -1;
            pointer-events: none;
        }

        /* Header / Tiêu đề chính */
        header {
            text-align: center;
            padding: 60px 20px 40px 20px;
        }

        header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            font-weight: 700;
            color: var(--color-beige);
            letter-spacing: 2px;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        header h1 span {
            color: var(--color-primary);
            position: relative;
        }

        /* Đường gạch dưới chữ nghệ thuật */
        header h1 span::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--color-primary);
            box-shadow: 0 0 8px var(--color-primary);
        }

        header p {
            font-size: 1rem;
            color: var(--color-beige-dark);
            font-weight: 300;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-top: 15px;
        }

        /* Khu vực hiển thị danh sách các Website */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
            width: 100%;
        }

        .web-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }

        /* Định dạng từng ô liên kết (Card) */
        .web-card {
            background-color: var(--color-card-bg);
            border: 1px solid rgba(241, 235, 217, 0.1);
            border-radius: 12px;
            padding: 30px 24px;
            text-decoration: none;
            color: var(--color-beige);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        }

        /* Viền đỏ mỏng bên trái thẻ tạo điểm nhấn */
        .web-card::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 4px;
            background-color: var(--color-primary);
            transform: scaleY(0);
            transition: var(--transition);
            transform-origin: bottom;
        }

        /* Hiệu ứng Hover chuyển động mượt mà */
        .web-card:hover {
            transform: translateY(-5px);
            border-color: rgba(230, 57, 70, 0.4);
            box-shadow: 0 10px 25px rgba(230, 57, 70, 0.15);
        }

        .web-card:hover::before {
            transform: scaleY(1);
        }

        .card-icon {
            font-size: 2rem;
            color: var(--color-primary);
            margin-bottom: 15px;
        }

        .card-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--color-beige);
        }

        .card-desc {
            font-size: 0.9rem;
            color: var(--color-beige-dark);
            font-weight: 300;
            margin-bottom: 20px;
            flex-grow: 1;
        }

        .card-btn {
            align-self: flex-start;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            color: var(--color-primary);
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition);
        }

        .web-card:hover .card-btn {
            color: var(--color-beige);
            transform: translateX(5px);
        }

        /* Footer dưới cùng */
        footer {
            text-align: center;
            padding: 30px 20px;
            font-size: 0.8rem;
            color: var(--color-beige-dark);
            border-top: 1px solid rgba(241, 235, 217, 0.05);
            letter-spacing: 1px;
        }

        footer a {
            color: var(--color-primary);
            text-decoration: none;
        }

        /* Responsive cho thiết bị di động */
        @media (max-width: 600px) {
            header h1 {
                font-size: 2.2rem;
            }
            .web-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Kho Tàng Của <span>Koi</span></h1>
        <p>Thế giới nhỏ và những dự án cá nhân</p>
    </header>

    <div class="container">
        <div class="web-grid">
            
            <a href="https://2410phongnguyen-eng.github.io/-/" target="_blank" class="web-card">
                <div>
                    <div class="card-icon">✦</div>
                    <h3 class="card-title">Dự Án Chính</h3>
                    <p class="card-desc">Cổng thông tin chính thức và các nội dung cập nhật mới nhất từ tôi.</p>
                </div>
                <div class="card-btn">Khám phá ngay →</div>
            </a>

            <a href="https://2410phongnguyen-eng.github.io/----/" target="_blank" class="web-card">
                <div>
                    <div class="card-icon">✧</div>
                    <h3 class="card-title">Khu Lưu Trữ</h3>
                    <p class="card-desc">Nơi cất giữ những ý tưởng sáng tạo, bản nháp và tài liệu độc đáo.</p>
                </div>
                <div class="card-btn">Ghé thăm →</div>
            </a>

            </div>
    </div>

    <footer>
        <p>© 2026 Bản quyền thuộc về <a href="#">Koi</a>. Thiết kế với cả trái tim.</p>
    </footer>

</body>
</html>
