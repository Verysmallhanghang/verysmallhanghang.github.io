<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>赛博朋克个人介绍 | 科技未来</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Orbitron', sans-serif;
        }

        :root {
            --primary-color: #00f3ff;
            --secondary-color: #ff00ff;
            --accent-color: #00ff9d;
            --dark-bg: #0a0a16;
            --darker-bg: #050510;
            --text-color: #e0e0ff;
            --neon-glow: 0 0 10px var(--primary-color),
                         0 0 20px var(--primary-color),
                         0 0 30px var(--primary-color);
        }

        body {
            background-color: var(--darker-bg);
            color: var(--text-color);
            overflow-x: hidden;
            min-height: 100vh;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(0, 243, 255, 0.05) 0%, transparent 20%),
                radial-gradient(circle at 80% 80%, rgba(255, 0, 255, 0.05) 0%, transparent 20%);
        }

        /* 流星效果 */
        .shooting-stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            box-shadow: 0 0 6px white;
        }

        .shooting-star {
            position: absolute;
            height: 2px;
            background: linear-gradient(90deg, transparent, var(--primary-color));
            border-radius: 50%;
            filter: drop-shadow(0 0 6px var(--primary-color));
            animation: shoot linear forwards;
        }

        @keyframes shoot {
            0% {
                transform: translateX(0) translateY(0) rotate(45deg);
                opacity: 0;
                width: 0;
            }
            10% {
                opacity: 1;
            }
            70% {
                opacity: 1;
            }
            100% {
                transform: translateX(100vw) translateY(100vh) rotate(45deg);
                opacity: 0;
                width: 100px;
            }
        }

        /* 容器布局 */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 2;
        }

        /* 头部区域 */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            border-bottom: 1px solid rgba(0, 243, 255, 0.3);
            margin-bottom: 40px;
        }

        .logo {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.2rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 10px rgba(0, 243, 255, 0.5);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: var(--text-color);
            text-decoration: none;
            font-size: 1.1rem;
            padding: 8px 16px;
            border-radius: 4px;
            transition: all 0.3s ease;
            position: relative;
        }

        nav a:hover {
            color: var(--primary-color);
            text-shadow: var(--neon-glow);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }

        nav a:hover::after {
            width: 80%;
        }

        /* 主内容区域 */
        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 60px;
        }

        @media (max-width: 992px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }

        /* 个人信息区域 */
        .profile-section {
            padding: 30px;
            background: rgba(10, 10, 30, 0.7);
            border-radius: 10px;
            border: 1px solid rgba(0, 243, 255, 0.2);
            box-shadow: 0 0 20px rgba(0, 243, 255, 0.1);
            backdrop-filter: blur(5px);
        }

        .profile-header {
            display: flex;
            align-items: center;
            margin-bottom: 30px;
        }

        .profile-img-container {
            position: relative;
            width: 150px;
            height: 150px;
            margin-right: 25px;
        }

        /* 脉络呼吸效果 */
        .pulse-circle {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 2px solid var(--primary-color);
            animation: pulse 3s infinite ease-in-out;
            box-shadow: 0 0 15px var(--primary-color);
        }

        .pulse-circle:nth-child(2) {
            animation-delay: 1s;
        }

        .pulse-circle:nth-child(3) {
            animation-delay: 2s;
        }

        @keyframes pulse {
            0% {
                transform: scale(0.8);
                opacity: 0.8;
            }
            50% {
                transform: scale(1.1);
                opacity: 0.3;
            }
            100% {
                transform: scale(0.8);
                opacity: 0.8;
            }
        }

        .profile-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            position: relative;
            z-index: 2;
            border: 3px solid transparent;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color)) border-box;
            mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
            mask-composite: exclude;
        }

        .profile-title h1 {
            font-size: 2.5rem;
            margin-bottom: 5px;
            background: linear-gradient(to right, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .profile-title p {
            color: var(--secondary-color);
            font-size: 1.2rem;
            letter-spacing: 2px;
        }

        /* 个人介绍内容 */
        .intro-text {
            line-height: 1.8;
            font-size: 1.1rem;
            margin-bottom: 30px;
        }

        .highlight {
            color: var(--primary-color);
            font-weight: bold;
        }

        .skills-section h3 {
            color: var(--accent-color);
            margin-bottom: 15px;
            font-size: 1.5rem;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .skill-tag {
            background: rgba(0, 243, 255, 0.1);
            padding: 8px 16px;
            border-radius: 20px;
            border: 1px solid var(--primary-color);
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: rgba(0, 243, 255, 0.3);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 243, 255, 0.2);
        }

        /* 科技信息区域 */
        .tech-section {
            padding: 30px;
            background: rgba(10, 10, 30, 0.7);
            border-radius: 10px;
            border: 1px solid rgba(255, 0, 255, 0.2);
            box-shadow: 0 0 20px rgba(255, 0, 255, 0.1);
            backdrop-filter: blur(5px);
        }

        .section-title {
            font-size: 1.8rem;
            margin-bottom: 25px;
            color: var(--secondary-color);
            text-align: center;
            text-shadow: 0 0 10px rgba(255, 0, 255, 0.5);
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .tech-card {
            background: rgba(20, 20, 40, 0.8);
            padding: 20px;
            border-radius: 8px;
            border-left: 4px solid var(--accent-color);
            transition: all 0.3s ease;
        }

        .tech-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 255, 157, 0.2);
        }

        .tech-card i {
            font-size: 2rem;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .tech-card h4 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary-color);
        }

        /* 联系区域 */
        .contact-section {
            padding: 40px;
            text-align: center;
            margin-top: 40px;
            background: rgba(10, 10, 30, 0.7);
            border-radius: 10px;
            border: 1px solid rgba(0, 243, 255, 0.2);
            box-shadow: 0 0 20px rgba(0, 243, 255, 0.1);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 30px;
            margin-top: 30px;
        }

        .contact-link {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-decoration: none;
            color: var(--text-color);
            padding: 15px 25px;
            border-radius: 8px;
            background: rgba(0, 243, 255, 0.05);
            border: 1px solid rgba(0, 243, 255, 0.2);
            transition: all 0.3s ease;
            min-width: 120px;
        }

        .contact-link:hover {
            background: rgba(0, 243, 255, 0.2);
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 243, 255, 0.3);
        }

        .contact-link i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--primary-color);
        }

        /* 页脚 */
        footer {
            text-align: center;
            padding: 30px 0;
            margin-top: 60px;
            border-top: 1px solid rgba(0, 243, 255, 0.3);
            font-size: 0.9rem;
            color: rgba(224, 224, 255, 0.7);
        }

        .cyber-text {
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: gradient-shift 5s infinite alternate;
        }

        @keyframes gradient-shift {
            0% {
                filter: hue-rotate(0deg);
            }
            100% {
                filter: hue-rotate(360deg);
            }
        }

        /* 响应式调整 */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .profile-header {
                flex-direction: column;
                text-align: center;
            }
            
            .profile-img-container {
                margin-right: 0;
                margin-bottom: 20px;
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- 流星效果容器 -->
    <div class="shooting-stars" id="shootingStars"></div>

    <div class="container">
        <!-- 头部 -->
        <header>
            <div class="logo">CYBER_ PROFILE</div>
            <nav>
                <ul>
                    <li><a href="#profile">个人资料</a></li>
                    <li><a href="#tech">技术领域</a></li>
                    <li><a href="#projects">项目经验</a></li>
                    <li><a href="#contact">联系方式</a></li>
                </ul>
            </nav>
        </header>

        <!-- 主内容区域 -->
        <main>
            <div class="main-content">
                <!-- 个人信息区域 -->
                <section class="profile-section" id="profile">
                    <div class="profile-header">
                        <div class="profile-img-container">
                            <div class="pulse-circle"></div>
                            <div class="pulse-circle"></div>
                            <div class="pulse-circle"></div>
                            <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" alt="个人形象" class="profile-img">
                        </div>
                        <div class="profile-title">
                            <h1>张逸风</h1>
                            <p>全栈开发工程师 | 科技未来探索者</p>
                        </div>
                    </div>
                    
                    <div class="intro-text">
                        <p>你好，我是<span class="highlight">张逸风</span>，一名专注于<span class="highlight">前沿科技</span>与<span class="highlight">创新解决方案</span>的全栈开发工程师。</p>
                        <br>
                        <p>在<span class="highlight">赛博空间</span>中，我致力于构建连接现实与数字世界的桥梁。拥有<span class="highlight">8年</span>的行业经验，参与过多个大型企业级应用和<span class="highlight">未来科技</span>项目开发。</p>
                        <br>
                        <p>我相信科技的力量可以<span class="highlight">改变未来</span>，而代码是我们塑造这个未来的工具。我的工作涵盖从<span class="highlight">量子计算模拟</span>到<span class="highlight">神经界面设计</span>的前沿领域。</p>
                    </div>
                    
                    <div class="skills-section">
                        <h3>核心技术</h3>
                        <div class="skills">
                            <span class="skill-tag">量子算法</span>
                            <span class="skill-tag">神经界面</span>
                            <span class="skill-tag">全息投影</span>
                            <span class="skill-tag">区块链技术</span>
                            <span class="skill-tag">AI集成</span>
                            <span class="skill-tag">增强现实</span>
                            <span class="skill-tag">物联网架构</span>
                            <span class="skill-tag">数据可视化</span>
                        </div>
                    </div>
                </section>
                
                <!-- 科技信息区域 -->
                <section class="tech-section" id="tech">
                    <h2 class="section-title">技术领域</h2>
                    <div class="tech-grid">
                        <div class="tech-card">
                            <i class="fas fa-brain"></i>
                            <h4>神经界面设计</h4>
                            <p>开发人机直接交互的神经接口，实现思维与数字世界的无缝连接。</p>
                        </div>
                        <div class="tech-card">
                            <i class="fas fa-atom"></i>
                            <h4>量子计算</h4>
                            <p>构建量子算法和模拟环境，解决传统计算无法处理的复杂问题。</p>
                        </div>
                        <div class="tech-card">
                            <i class="fas fa-hologram"></i>
                            <h4>全息投影技术</h4>
                            <p>创建逼真的三维全息影像，改变信息呈现和交互方式。</p>
                        </div>
                        <div class="tech-card">
                            <i class="fas fa-robot"></i>
                            <h4>人工智能集成</h4>
                            <p>将高级AI模型整合到日常应用中，实现智能决策和自动化。</p>
                        </div>
                    </div>
                </section>
            </div>
            
            <!-- 联系区域 -->
            <section class="contact-section" id="contact">
                <h2 class="section-title">连接未来</h2>
                <p>如果您对科技未来有共同的热情，或者有创新的项目需要合作，欢迎与我联系。</p>
                
                <div class="contact-links">
                    <a href="mailto:contact@cyberprofile.net" class="contact-link">
                        <i class="fas fa-envelope"></i>
                        <span>邮件联系</span>
                    </a>
                    <a href="#" class="contact-link">
                        <i class="fab fa-github"></i>
                        <span>GitHub</span>
                    </a>
                    <a href="#" class="contact-link">
                        <i class="fab fa-linkedin"></i>
                        <span>LinkedIn</span>
                    </a>
                    <a href="#" class="contact-link">
                        <i class="fas fa-terminal"></i>
                        <span>暗网端口</span>
                    </a>
                </div>
            </section>
        </main>
        
        <!-- 页脚 -->
        <footer>
            <p>&copy; 2023 赛博朋克个人档案 | 设计融合科技与未来元素</p>
            <p class="cyber-text">接入端口：CYBER_PROFILE::2077::FUTURE_READY</p>
        </footer>
    </div>

    <script>
        // 创建流星效果
        function createShootingStars() {
            const container = document.getElementById('shootingStars');
            
            // 创建背景星星
            for (let i = 0; i < 100; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // 随机位置和大小
                const size = Math.random() * 3;
                const posX = Math.random() * 100;
                const posY = Math.random() * 100;
                
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                star.style.left = `${posX}vw`;
                star.style.top = `${posY}vh`;
                
                // 随机亮度
                star.style.opacity = Math.random() * 0.8 + 0.2;
                
                container.appendChild(star);
            }
            
            // 创建流星
            function createShootingStar() {
                const shootingStar = document.createElement('div');
                shootingStar.classList.add('shooting-star');
                
                // 随机起始位置
                const startX = Math.random() * 20;
                const startY = Math.random() * 20;
                
                shootingStar.style.left = `${startX}vw`;
                shootingStar.style.top = `${startY}vh`;
                
                // 随机颜色
                const colors = ['#00f3ff', '#ff00ff', '#00ff9d'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                shootingStar.style.background = `linear-gradient(90deg, transparent, ${color})`;
                shootingStar.style.filter = `drop-shadow(0 0 6px ${color})`;
                
                // 随机动画持续时间
                const duration = Math.random() * 3 + 2;
                shootingStar.style.animationDuration = `${duration}s`;
                
                container.appendChild(shootingStar);
                
                // 动画结束后移除元素
                setTimeout(() => {
                    shootingStar.remove();
                }, duration * 1000);
            }
            
            // 定时创建流星
            setInterval(createShootingStar, 1000);
            
            // 初始创建一些流星
            for (let i = 0; i < 5; i++) {
                setTimeout(() => createShootingStar(), i * 500);
            }
        }
        
        // 脉络呼吸效果增强
        function enhancePulseEffect() {
            const pulseCircles = document.querySelectorAll('.pulse-circle');
            
            pulseCircles.forEach((circle, index) => {
                // 为每个脉冲圈添加随机颜色偏移
                const hue = Math.floor(Math.random() * 60) + 180; // 蓝绿色调范围
                circle.style.borderColor = `hsl(${hue}, 100%, 50%)`;
                circle.style.boxShadow = `0 0 15px hsl(${hue}, 100%, 50%)`;
                
                // 随机动画延迟
                circle.style.animationDelay = `${index * 0.5}s`;
            });
        }
        
        // 导航高亮效果
        function setupNavigation() {
            const navLinks = document.querySelectorAll('nav a');
            
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        // 平滑滚动到目标位置
                        window.scrollTo({
                            top: targetElement.offsetTop - 100,
                            behavior: 'smooth'
                        });
                        
                        // 添加点击效果
                        this.style.color = 'var(--primary-color)';
                        this.style.textShadow = 'var(--neon-glow)';
                        
                        setTimeout(() => {
                            this.style.color = '';
                            this.style.textShadow = '';
                        }, 300);
                    }
                });
            });
        }
        
        // 卡片悬停效果增强
        function enhanceCardHover() {
            const cards = document.querySelectorAll('.tech-card, .contact-link');
            
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    const randomHue = Math.floor(Math.random() * 360);
                    this.style.borderColor = `hsl(${randomHue}, 100%, 50%)`;
                    this.style.boxShadow = `0 10px 20px hsla(${randomHue}, 100%, 50%, 0.3)`;
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.borderColor = '';
                    this.style.boxShadow = '';
                });
            });
        }
        
        // 页面加载完成后初始化效果
        document.addEventListener('DOMContentLoaded', function() {
            createShootingStars();
            enhancePulseEffect();
            setupNavigation();
            enhanceCardHover();
            
            // 添加控制台欢迎信息
            console.log('%c 欢迎来到赛博空间! 🔮', 'color: #00f3ff; font-size: 18px; font-weight: bold; text-shadow: 0 0 10px #00f3ff;');
            console.log('%c 系统状态: ONLINE | 安全协议: ACTIVE', 'color: #00ff9d; font-size: 14px;');
        });
    </script>
</body>
</html>
