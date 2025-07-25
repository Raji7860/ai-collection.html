<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Voice AI - دستیار هوشمند صوتی</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Naskh+Arabic:wght@400;500;600;700&display=swap');
        
        :root {
            --primary: #6D0586;
            --secondary: #FFD700;
            --accent: #0EE2E2;
            --text: #2D3748;
            --light-bg: #F9F5FF;
        }
        
        body {
            font-family: 'Noto Naskh Arabic', 'B Nazanin', Arial, sans-serif;
            background: linear-gradient(135deg, #f9f9f9 0%, #e6e6ff 100%);
            color: var(--text);
            line-height: 1.8;
            margin: 0;
            padding: 0;
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 40px auto;
            padding: 40px;
            background-color: white;
            border-radius: 20px;
            box-shadow: 0 15px 40px rgba(109, 5, 134, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 8px;
            background: linear-gradient(90deg, var(--primary) 0%, var(--accent) 100%);
        }
        
        h1 {
            color: var(--primary);
            text-align: center;
            font-size: 32px;
            margin: 0 0 30px 0;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--light-bg);
            font-weight: 700;
            position: relative;
        }
        
        h1::after {
            content: "";
            position: absolute;
            bottom: -2px;
            right: 0;
            width: 150px;
            height: 3px;
            background: var(--secondary);
        }
        
        .logo {
            text-align: center;
            font-size: 42px;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 30px;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.1);
            position: relative;
            display: inline-block;
            width: 100%;
        }
        
        .logo::after {
            content: "دستیار هوشمند تبدیل متن به گفتار";
            display: block;
            font-size: 18px;
            color: var(--text);
            font-weight: normal;
            margin-top: 10px;
        }
        
        p {
            font-size: 18px;
            margin-bottom: 25px;
            text-align: justify;
            line-height: 2;
        }
        
        .highlight {
            background-color: var(--light-bg);
            padding: 25px;
            border-radius: 15px;
            margin: 30px 0;
            border-right: 4px solid var(--primary);
            font-size: 18px;
            position: relative;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .highlight::before {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 60px;
            height: 60px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%236D0586" opacity="0.1"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>') no-repeat;
            background-size: contain;
        }
        
        .features {
            margin: 35px 0;
            position: relative;
        }
        
        .features::before {
            content: "قابلیت‌های کلیدی";
            display: block;
            font-size: 24px;
            color: var(--primary);
            margin-bottom: 20px;
            font-weight: 600;
            padding-right: 15px;
        }
        
        .features ul {
            padding-right: 20px;
        }
        
        .features li {
            margin-bottom: 15px;
            padding-right: 35px;
            position: relative;
            font-size: 18px;
            list-style-type: none;
            line-height: 1.8;
        }
        
        .features li::before {
            content: "";
            position: absolute;
            right: 0;
            top: 10px;
            width: 20px;
            height: 20px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%236D0586"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41L9 16.17z"/></svg>') no-repeat;
            background-size: contain;
        }
        
        .contact {
            background: linear-gradient(135deg, var(--primary) 0%, #4a148c 100%);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin-top: 40px;
            text-align: center;
            font-size: 18px;
            box-shadow: 0 10px 30px rgba(109, 5, 134, 0.2);
            position: relative;
            overflow: hidden;
        }
        
        .contact::before {
            content: "";
            position: absolute;
            top: -20px;
            right: -20px;
            width: 100px;
            height: 100px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="white" opacity="0.05"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>') no-repeat;
            background-size: contain;
        }
        
        .contact h2 {
            color: white;
            margin-top: 0;
            font-size: 24px;
            margin-bottom: 20px;
            position: relative;
        }
        
        .contact a {
            color: var(--secondary);
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            margin: 0 15px;
            transition: all 0.3s;
            display: inline-block;
            padding: 8px 15px;
            border-radius: 8px;
            background-color: rgba(255, 215, 0, 0.1);
        }
        
        .contact a:hover {
            color: white;
            background-color: rgba(255, 215, 0, 0.3);
            transform: translateY(-3px);
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            font-size: 16px;
            color: var(--primary);
            font-weight: 600;
            position: relative;
            padding-top: 20px;
        }
        
        .footer::before {
            content: "";
            position: absolute;
            top: 0;
            right: calc(50% - 50px);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary) 0%, var(--accent) 50%, var(--primary) 100%);
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 30px 20px;
                margin: 20px 15px;
            }
            
            h1 {
                font-size: 28px;
            }
            
            .logo {
                font-size: 36px;
            }
            
            .contact a {
                display: block;
                margin: 10px 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="logo">VOICE AI</div>
        <h1>درباره ما</h1>
        
        <div class="highlight">
            <p>پروژه‌ی «Voice AI» یک دستیار هوشمند صوتی است که با هدف تبدیل متن به گفتار طبیعی طراحی شده است. این برنامه می‌تواند متن‌های فارسی و انگلیسی را با صدای واضح و روان بخواند و دارای رابط کاربری جذاب و کاملاً فارسی‌سازی‌شده است که تجربه‌ای ساده و لذت‌بخش را برای کاربران فراهم می‌کند.</p>
        </div>
        
        <p>این نرم‌افزار برای طیف گسترده‌ای از کاربران، به‌ویژه دانش‌آموزان، معلمان، زبان‌آموزان و افراد کم‌توان طراحی شده و در زمینه‌هایی مانند تمرین املا، یادگیری واژگان، تقویت تلفظ و تولید فایل صوتی آموزشی کاربرد دارد.</p>
        
        <p>Voice AI فقط یک ابزار تبدیل متن به صدا نیست؛ بلکه یک دستیار آموزشی و هوشمند است با هزاران کاربرد دیگر که متناسب با نیاز کاربران در موقعیت‌های مختلف قابل استفاده است.</p>
        
        <div class="features">
            <ul>
                <li>تبدیل متن به گفتار با صدای طبیعی (مرد یا زن) با استفاده از فناوری TTS پیشرفته</li>
                <li>شناسایی متن از تصویر با بهره‌گیری از فناوری OCR دقیق</li>
                <li>پشتیبانی کامل از زبان‌های فارسی و انگلیسی با تلفظ طبیعی</li>
                <li>ذخیره‌سازی خروجی صوتی به‌صورت فایل MP3 با کیفیت بالا</li>
                <li>رابط کاربری زیبا، ساده و کاملاً فارسی‌سازی‌شده</li>
            </ul>
        </div>
        
        <div class="contact">
            <h2>راه‌های ارتباط با ما</h2>
            <p>
                <a href="mailto:raji.tech.ai.101@gmail.com">ایمیل: raji.tech.ai.101@gmail.com</a>
                <a href="tel:+989183094275">تلفن: 09183094275</a>
            </p>
        </div>
        
        <div class="footer">
            طراح و توسعه‌دهنده: محمدرضا راجی
        </div>
    </div>
</body>
</html>
