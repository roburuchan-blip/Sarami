<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SARAMI | Profile</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Rajdhani:wght@500;700&display=swap');

  :root {
    --bg: #050505;
    --card-bg: #0f0f0f;
    --neon-red: #ff2a2a;
    --neon-blue: #2a2aff;
    --text-main: #ffffff;
    --text-sub: #888888;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background-color: var(--bg);
    color: var(--text-main);
    font-family: 'Rajdhani', sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    overflow: hidden;
  }

  /* 背景のグリッド装飾 */
  .bg-grid {
    position: absolute;
    width: 200%;
    height: 200%;
    background-image: 
      linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    transform: perspective(500px) rotateX(60deg) translateY(-100px) translateZ(-200px);
    animation: gridMove 20s linear infinite;
    z-index: -1;
  }

  @keyframes gridMove {
    0% { transform: perspective(500px) rotateX(60deg) translateY(0) translateZ(-200px); }
    100% { transform: perspective(500px) rotateX(60deg) translateY(40px) translateZ(-200px); }
  }

  .profile-card {
    width: 360px;
    background: rgba(15, 15, 15, 0.8);
    backdrop-filter: blur(10px);
    border: 1px solid #333;
    border-radius: 20px;
    padding: 40px 30px;
    text-align: center;
    box-shadow: 0 0 40px rgba(0,0,0,0.8);
    position: relative;
    transition: transform 0.3s ease;
  }

  .profile-card:hover {
    transform: translateY(-5px);
    border-color: #555;
  }

  .avatar-container {
    position: relative;
    width: 100px;
    height: 100px;
    margin: 0 auto 20px;
  }

  .avatar {
    width: 100%;
    height: 100%;
    background: #1a1a1a;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2.5rem;
    font-family: 'Orbitron', sans-serif;
    color: var(--neon-red);
    border: 2px solid var(--neon-red);
    box-shadow: 0 0 20px rgba(255, 42, 42, 0.3);
    position: relative;
    z-index: 2;
  }

  .status-dot {
    position: absolute;
    bottom: 5px;
    right: 10px;
    width: 15px;
    height: 15px;
    background: #00ff00;
    border-radius: 50%;
    border: 2px solid #000;
    z-index: 3;
    box-shadow: 0 0 10px #00ff00;
  }

  h1 {
    font-family: 'Orbitron', sans-serif;
    font-size: 2rem;
    letter-spacing: 4px;
    margin-bottom: 5px;
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
  }

  .meta {
    font-size: 0.9rem;
    color: var(--text-sub);
    margin-bottom: 25px;
    letter-spacing: 1px;
  }

  .bio {
    font-size: 1rem;
    line-height: 1.6;
    color: #ccc;
    margin-bottom: 35px;
    padding: 0 10px;
  }

  .links {
    display: flex;
    flex-direction: column;
    gap: 15px;
  }

  .link-btn {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 20px;
    background: #1a1a1a;
    border: 1px solid #333;
    border-radius: 12px;
    text-decoration: none;
    color: #fff;
    font-weight: 700;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }

  .link-btn span {
    z-index: 2;
  }

  .link-btn svg {
    width: 24px;
    height: 24px;
    fill: currentColor;
    z-index: 2;
  }

  /* ホバー時の光るエフェクト */
  .link-btn::before {
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
    transition: 0.5s;
  }

  .link-btn:hover::before {
    left: 100%;
  }

  .link-btn:hover {
    transform: scale(1.02);
    border-color: var(--neon-red);
    box-shadow: 0 0 20px rgba(255, 42, 42, 0.2);
  }

  /* プラットフォームごとのアクセント */
  .music:hover { border-color: #1db954; box-shadow: 0 0 20px rgba(29, 185, 84, 0.3); }
  .tiktok:hover { border-color: #fe2c55; box-shadow: 0 0 20px rgba(254, 44, 85, 0.3); }
  .discord:hover { border-color: #5865f2; box-shadow: 0 0 20px rgba(88, 101, 242, 0.3); }

</style>
</head>
<body>

<div class="bg-grid"></div>

<div class="profile-card">
  <div class="avatar-container">
    <div class="avatar">S</div>
    <div class="status-dot"></div>
  </div>
  
  <h1>SARAMI</h1>
  <div class="meta">13 YEARS OLD / JAPAN 🇯🇵</div>
  
  <p class="bio">
    マウンテンバイクで山を駆け回り、<br>
    夜はスクリプトをハックする。
  </p>

  <div class="links">
    <!-- 音楽ストリーミング -->
    <a href="#" class="link-btn music">
      <span>Listen to Music</span>
      <svg viewBox="0 0 24 24"><path d="M12 0C5.4 0 0 5.4 0 12s5.4 12 12 12 12-5.4 12-12S18.66 0 12 0zm5.521 17.34c-.24.359-.66.48-1.021.24-2.82-1.74-6.36-2.101-10.561-1.141-.418.122-.779-.179-.899-.539-.12-.421.18-.78.54-.9 4.56-1.021 8.52-.6 11.64 1.32.42.18.479.659.301 1.02zm1.44-3.3c-.301.42-.841.6-1.262.3-3.239-1.98-8.159-2.58-11.939-1.38-.479.12-.9-.18-1.02-.659-.12-.48.18-.9.659-1.021 4.2-1.32 9.6-0.6 13.2 1.621.36.24.48.78.36 1.14zm.12-3.36C15.241 8.4 8.821 8.16 5.161 9.301c-.6.179-1.2-.181-1.38-.721-.18-.601.18-1.2.72-1.381 4.26-1.26 11.4-1.02 15.721 1.56.54.3.72 1.02.42 1.56-.3.54-1.02.72-1.56.42z"/></svg>
    </a>

    <!-- TikTok -->
    <a href="#" class="link-btn tiktok">
      <span>TikTok</span>
      <svg viewBox="0 0 24 24"><path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93v6.16c0 2.52-1.12 4.84-2.9 6.24-1.72 1.36-4.04 1.94-6.18 1.63-2.14-.31-4.1-1.5-5.33-3.22-1.23-1.72-1.58-3.94-.97-5.96.61-2.02 2.14-3.7 4.13-4.53 1.99-.83 4.26-.66 6.12.46v4.03c-1.26-.76-2.86-.83-4.18-.19-1.32.64-2.22 1.93-2.36 3.37-.14 1.44.54 2.86 1.72 3.71 1.18.85 2.76.93 4.02.21 1.26-.72 2.04-2.06 2.04-3.51V.02h-2.18z"/></svg>
    </a>

    <!-- Discord -->
    <a href="#" class="link-btn discord">
      <span>Discord Server</span>
      <svg viewBox="0 0 24 24"><path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028 14.09 14.09 0 0 0 1.226-1.994.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/></svg>
    </a>
  </div>
</div>

</body>
</html>
