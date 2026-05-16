# 💜
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>2026 東京夢幻之旅 ✨</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @font-face {
            font-family: 'Chenyuluoyan';
            src: url('https://cdn.jsdelivr.net/gh/chenyu-shuo/Chenyuluoyan-Thin@main/Chenyuluoyan-Thin.ttf') format('truetype');
            font-display: swap;
        }
        :root {
            --primary: #9D84B7;
            --secondary: #6B4E8D;
            --bg: #EAE5F3;
            --card-bg: #FFFFFF;
            --tape-color-1: rgba(245, 235, 204, 0.9);
            --tape-color-2: rgba(230, 215, 255, 0.9);
            --accent-pink: #FFD1DC;
        }
        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        body {
            margin: 0;
            font-family: 'Chenyuluoyan', "PingFang TC", sans-serif;
            background-color: var(--bg);
            color: #4A4A4A;
            padding-bottom: calc(90px + env(safe-area-inset-bottom));
            letter-spacing: 0.05em;
            background-image: radial-gradient(rgba(107, 78, 141, 0.15) 1.5px, transparent 1.5px);
            background-size: 20px 20px;
        }

        /* 頂部標題 */
        .header {
            padding: calc(30px + env(safe-area-inset-top)) 20px 10px;
            text-align: center;
        }
        .header h1 { margin: 0; font-size: 1.8rem; color: #333; display: flex; justify-content: center; gap: 8px; }
        .header h1 span { color: #F2C94C; }

        /* 日期選擇器 */
        .day-scroller { display: flex; overflow-x: auto; gap: 10px; padding: 15px 20px; scrollbar-width: none; }
        .day-scroller::-webkit-scrollbar { display: none; }
        .day-btn { flex: 0 0 65px; height: 65px; background: white; border-radius: 12px; display: flex; flex-direction: column; align-items: center; justify-content: center; border: 1.5px solid #555; font-size: 0.75rem; color: #555; transition: 0.3s; }
        .day-btn b { font-size: 0.9rem; margin-bottom: 2px; }
        .day-btn.active { background: #555; color: white; border-color: #555; transform: scale(1.05); box-shadow: 2px 4px 10px rgba(0,0,0,0.15); }

        /* 次標籤 */
        .sub-tabs { display: flex; justify-content: space-around; border-bottom: 2px solid rgba(0,0,0,0.1); margin: 0 20px 15px; padding-bottom: 10px; }
        .sub-tab { font-size: 1.1rem; color: #888; font-weight: bold; cursor: pointer; padding: 5px 10px; transition: 0.2s; }
        .sub-tab.active { color: #333; position: relative; }
        .sub-tab.active::after { content: ''; position: absolute; bottom: -12px; left: 0; width: 100%; height: 3px; background: #555; }

        .container { padding: 0 20px; max-width: 500px; margin: 0 auto; position: relative; }

        /* 行程卡片與時間軸 */
        .timeline-item { display: flex; margin-bottom: 25px; }
        .time-col { width: 50px; font-size: 1rem; font-weight: bold; color: #333; padding-top: 15px; }
        .line-col { width: 25px; position: relative; }
        .line-col::before { content: ''; position: absolute; left: 11px; top: 0; bottom: -30px; width: 2px; background: #555; }
        .dot { width: 16px; height: 16px; background: white; border: 2.5px solid #555; border-radius: 50%; position: absolute; left: 4px; top: 15px; z-index: 2; }
        .card-col { flex: 1; position: relative; }
        
        .card { background: var(--card-bg); border-radius: 12px; padding: 18px; border: 1.5px solid #555; box-shadow: 4px 4px 0px rgba(0,0,0,0.05); position: relative; overflow: hidden; }
        .card-clickable { cursor: pointer; transition: 0.2s; }
        .card-clickable:active { transform: scale(0.98); }
        
        .tape-tr { position: absolute; top: 5px; right: -15px; width: 70px; height: 20px; background: var(--tape-color-1); transform: rotate(45deg); z-index: 2; box-shadow: 1px 1px 3px rgba(0,0,0,0.05); }
        .tape-bl { position: absolute; bottom: 5px; left: -15px; width: 70px; height: 20px; background: var(--tape-color-2); transform: rotate(45deg); z-index: 2; box-shadow: 1px 1px 3px rgba(0,0,0,0.05); }

        .card-title { font-size: 1.25rem; font-weight: bold; color: #333; margin-bottom: 12px; display: flex; align-items: center; gap: 8px; }
        .card-img-row { display: flex; gap: 8px; margin-bottom: 12px; }
        .card-img { width: 100%; height: 110px; object-fit: cover; border-radius: 8px; border: 1px solid #EEE; flex: 1; }
        
        .nav-btn { display: block; width: 100%; text-align: center; background: #F0E6FF; color: var(--secondary); padding: 12px; border-radius: 8px; font-weight: bold; text-decoration: none; border: 1.5px solid var(--secondary); margin-top: 10px; cursor: pointer; font-size: 1.05rem; }

        /* 記帳頁面 */
        .budget-header { display: flex; background: white; border: 1.5px solid #555; border-radius: 12px; text-align: center; margin-bottom: 20px; overflow: hidden; box-shadow: 2px 2px 0px rgba(0,0,0,0.05); }
        .budget-header > div { flex: 1; padding: 15px; }
        .budget-header > div:first-child { border-right: 1.5px solid #555; }
        .budget-header span { display: block; font-weight: bold; font-size: 1rem; color: #333; margin-bottom: 5px; }
        .budget-header b { font-size: 1.4rem; color: var(--secondary); }
        .budget-subtitle { text-align: center; font-size: 0.85rem; color: #888; margin-top: -15px; margin-bottom: 20px; }

        .table-card { background: white; border: 1.5px solid #555; border-radius: 12px; padding: 15px; margin-bottom: 20px; position: relative; box-shadow: 2px 2px 0px rgba(0,0,0,0.05); }
        .table-card::before { content: ""; position: absolute; top: -8px; left: -10px; width: 60px; height: 18px; background: var(--tape-color-2); transform: rotate(-10deg); z-index: 1; }
        
        table { width: 100%; border-collapse: collapse; font-size: 0.95rem; }
        th { text-align: left; padding: 8px; border-bottom: 1.5px solid #555; color: #333; font-size: 1rem; }
        td { padding: 10px 8px; border-bottom: 1px dashed #CCC; color: #555; }
        
        .form-label { font-size: 0.95rem; color: #333; margin-bottom: 5px; display: block; font-weight: bold; margin-top: 10px; }
        .form-input { width: 100%; padding: 10px; border-radius: 8px; border: 1.5px solid #CCC; font-family: 'Chenyuluoyan'; outline: none; font-size: 1rem; }
        
        .payer-row { display: flex; gap: 8px; margin-top: 5px; }
        .payer-btn { flex: 1; padding: 10px; border-radius: 8px; border: 1.5px solid #CCC; background: white; font-family: 'Chenyuluoyan'; font-size: 1rem; font-weight: bold; color: #555; cursor: pointer; }
        .payer-btn.active { background: var(--secondary); color: white; border-color: var(--secondary); }

        .split-row { display: flex; gap: 5px; margin-top: 5px; margin-bottom: 10px; }
        .split-btn { flex: 1; padding: 8px; border-radius: 8px; border: 1px solid #CCC; background: white; font-family: 'Chenyuluoyan'; font-size: 0.9rem; cursor: pointer; }
        .split-btn.active { background: var(--primary); color: white; border-color: var(--primary); }
        .split-input-wrap { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; padding-top: 5px; }
        .split-input-wrap input { width: 80px; padding: 5px; border-radius: 5px; border: 1px solid #CCC; text-align: right; font-family: 'Chenyuluoyan'; }

        /* 導覽列 */
        .bottom-nav { position: fixed; bottom: 0; width: 100%; background: #F8F6FF; border-top: 1.5px solid #555; display: flex; justify-content: space-around; padding: 12px 0 calc(12px + env(safe-area-inset-bottom)); z-index: 1000; }
        .nav-item { display: flex; flex-direction: column; align-items: center; color: #888; font-size: 0.85rem; flex: 1; border: none; background: none; font-family: 'Chenyuluoyan'; font-weight: bold; cursor: pointer; }
        .nav-item.active { color: var(--secondary); }
        .nav-item i { font-size: 1.4rem; margin-bottom: 4px; }

        /* 三麗鷗插畫 */
        .sanrio-doodle { position: fixed; bottom: 85px; right: 10px; width: 140px; z-index: 10; pointer-events: none; }

        .tab-content { display: none; animation: fadeIn 0.4s ease; }
        .tab-content.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* 彈窗設計 */
        .modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.6); backdrop-filter: blur(5px); display: none; justify-content: center; align-items: flex-end; z-index: 2000; }
        .modal-overlay.active { display: flex; }
        .modal-content { background: white; width: 100%; max-width: 500px; border-radius: 25px 25px 0 0; padding: 30px 25px calc(30px + env(safe-area-inset-bottom)); transform: translateY(100%); transition: 0.3s cubic-bezier(0.165, 0.84, 0.44, 1); max-height: 85vh; overflow-y: auto; position: relative; }
        .modal-overlay.active .modal-content { transform: translateY(0); }
        .btn-close { position: absolute; top: 15px; right: 15px; font-size: 1.8rem; color: #CCC; cursor: pointer; line-height: 1; }
    </style>
</head>
<body>

    <header class="header">
        <h1><span>✨</span> 2026 東京夢幻之旅 <span>✨</span></h1>
    </header>

    <div class="day-scroller" id="day-selector"></div>

    <div class="sub-tabs" id="sub-tabs">
        <div class="sub-tab active" onclick="switchSubTab('itinerary')">地圖 / 行程</div>
        <div class="sub-tab" onclick="switchSubTab('info')">詳細資訊</div>
    </div>

    <main class="container">
        <div id="section-itinerary" class="tab-content active">
            <div id="itinerary-list"></div>
        </div>

        <div id="section-info" class="tab-content">
            <div class="table-card">
                <div class="tape-tr"></div>
                <h3 style="margin-top:0; color:#333;"><i class="fas fa-hotel"></i> D・レガーロ (南行德)</h3>
                <div class="card-img-row">
                    <img src="thumbnail.jpg" class="card-img" onerror="this.src='https://images.unsplash.com/photo-1598214813160-580a91e57a3d?q=80&w=400'">
                </div>
                <p style="font-size:0.95rem; color:#555; line-height: 1.6;">
                    Address：〒272-0138 千葉県市川市南行德２丁目２１
                </p>
                <a href="https://maps.app.goo.gl/1nyp2nPgscnQ9BL5A" target="_blank" class="nav-btn" style="background:var(--primary); color:white; border:none;">查看地圖導航 📍</a>
            </div>

            <div class="table-card">
                <div class="tape-bl"></div>
                <h3 style="margin-top:0; color:#333;"><i class="fas fa-cloud-sun"></i> 天氣與穿著建議</h3>
                <p style="font-size:0.95rem; line-height:1.8; color:#555;">
                    <b>預測氣溫：</b> 13°C ~ 21°C<br>
                    <b>穿著建議：</b> 建議洋蔥式穿法。白天著薄長袖，晚間備妥防風外套。前往迪士尼因靠海風大，強烈建議攜帶輕羽絨或保暖圍巾。
                </p>
                <button onclick="window.open('https://www.accuweather.com/zh/jp/tokyo/31032/daily-weather-forecast/31032?page=0', '_blank')" class="nav-btn" style="background:#FFF5F7; color:#D14D72; border-color:#FFD1DC;">查看當週氣象預報 🌤️</button>
            </div>
            
            <div class="table-card">
                <h3 style="margin-top:0; color:#333;"><i class="fas fa-shopping-bag"></i> 必買大眾清單</h3>
                <ul style="padding-left:20px; font-size:0.95rem; line-height:2; color:#555;">
                    <li><b>NY Perfect Cheese：</b> 機場必搶超人氣起司捲。</li>
                    <li><b>Press Butter Sand：</b> 濃郁現烤焦糖奶油夾心。</li>
                    <li><b>茅乃舍高湯包：</b> 送禮自用兩相宜，主婦最愛。</li>
                    <li><b>壽壽喜園抹茶粉：</b> 在家也能泡出極濃抹茶。</li>
                    <li><b>LOFT 限定：</b> 各種精美手帳貼紙與生活小物。</li>
                </ul>
            </div>
        </div>

        <div id="section-budget" class="tab-content">
            <div class="budget-header">
                <div><span>總計日幣 (¥)</span><b id="total-jpy">0</b></div>
                <div><span>總計台幣 (NT$)</span><b id="total-twd">0</b></div>
            </div>
            <div class="budget-subtitle">(依據實時匯率換算 / 匯率：<span id="current-rate-display">讀取中</span>)</div>

            <div class="table-card">
                <div class="tape-tr"></div>
                <table>
                    <thead><tr><th>消費項目</th><th>付款人</th><th>日期</th></tr></thead>
                    <tbody id="expense-list-body"></tbody>
                </table>
            </div>

            <div class="table-card">
                <table>
                    <thead>
                        <tr><th colspan="2" style="font-size:1.1rem; border-bottom:none;">結算：誰該給誰多少錢 (¥)</th></tr>
                        <tr><th style="color:#888; padding-top:0;">付款人   ➜   收款人</th><th style="text-align:right; color:#888; padding-top:0;">金額 (¥)</th></tr>
                    </thead>
                    <tbody id="settlement-results"></tbody>
                </table>
            </div>

            <div class="table-card" style="padding-bottom: 30px;">
                <div class="tape-bl"></div>
                <h3 style="margin-top:0; color:#333;">新增一筆消費</h3>
                
                <label class="form-label">項目名稱</label>
                <input type="text" id="exp-title" class="form-input" placeholder="例如：敘敘苑午餐">
                
                <label class="form-label">日幣總金額 (¥)</label>
                <input type="number" id="exp-amount" class="form-input" placeholder="0">
                
                <label class="form-label">先付款的人</label>
                <div class="payer-row">
                    <button class="payer-btn active" onclick="setPayer('蒂', this)">蒂</button>
                    <button class="payer-btn" onclick="setPayer('丞', this)">丞</button>
                    <button class="payer-btn" onclick="setPayer('頻', this)">頻</button>
                </div>

                <label class="form-label">分帳分配方式</label>
                <div class="split-row">
                    <button class="split-btn active" onclick="setSplitMethod('equal', this)">平均分攤</button>
                    <button class="split-btn" onclick="setSplitMethod('percent', this)">按百分比 (%)</button>
                    <button class="split-btn" onclick="setSplitMethod('exact', this)">自訂金額 (¥)</button>
                </div>
                <div id="split-inputs-container">
                    </div>

                <button class="nav-btn" style="background:var(--secondary); color:white; border:none; padding:15px; font-size:1.1rem; margin-top: 15px;" onclick="addExpense()">新增消費記錄</button>
            </div>
        </div>

    </main>

    <img src="https://i.pinimg.com/originals/2c/64/73/2c64736f86326162383842c16cb60eeb.png" class="sanrio-doodle" alt="sanrio" id="sanrio-img" style="display:none;" onerror="this.style.display='none'">

    <nav class="bottom-nav">
        <button class="nav-item active" onclick="switchMainTab('itinerary', this)">
            <i class="fas fa-map-marked-alt"></i><span>地圖/行程</span>
        </button>
        <button class="nav-item" onclick="switchMainTab('info', this)">
            <i class="fas fa-info-circle"></i><span>詳細資訊</span>
        </button>
        <button class="nav-item" onclick="switchMainTab('budget', this)">
            <i class="fas fa-wallet"></i><span>記帳結算</span>
        </button>
    </nav>

    <div id="detail-modal" class="modal-overlay" onclick="closeModal(event)">
        <div class="modal-content" onclick="event.stopPropagation()">
            <span class="btn-close" onclick="closeModal()">×</span>
            <div id="modal-body"></div>
        </div>
    </div>

<script>
    let exchangeRate = 0.215; 
    let currentPayer = '蒂';
    let currentSplitMethod = 'equal';
    const users = ['蒂', '丞', '頻'];

    // 🎀 絕對完整！一字不漏的 6 天行程數據 (採用穩定圖庫網址與專屬照片) 🎀
    const tripData = [
        { date: "10/26", spots: [
            { time: "13:00", title: "抵達成田機場", img: "src_64931908.jpg", desc: "抵達機場後領取行李、辦理入境，購買或儲值 Suica。旅程正式開始！", buy: "Suica 卡 (綁定 Apple Pay)", transport: "成田機場 (Skyliner) ➔ 船橋 ➔ 南行德", must: "IT280去程" },
            { time: "16:00", title: "星巴克臻選®東京烘焙工坊", img: "atl_m_180014793_346.jpg", desc: "全球僅六間烘焙工坊。建築由隈研吾設計，櫻花柱與紅銅噴泉必拍。", buy: "限定咖啡豆、限定隨行杯", transport: "地鐵中目黑站步行", must: "必拍櫻花柱" },
            { time: "17:30", title: "自由之丘 La vita", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/Jiyugaoka_la_vita_04.jpg/640px-Jiyugaoka_la_vita_04.jpg", desc: "有「小威尼斯」之稱的歐風角落，非常適合漫步與拍照。", buy: "質感生活雜貨", transport: "自由之丘站步行", must: "拍照聖地" },
            { time: "19:30", title: "上野阿美橫町", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Ameya_Yokocho_Entrance.jpg/640px-Ameya_Yokocho_Entrance.jpg", desc: "藥妝與零食的天堂，體驗東京熱鬧的下町活力。", buy: "二木菓子、OS Drug 藥妝", transport: "上野站即達", must: "採買藥妝" }
        ]},
        { date: "10/27", spots: [
            { time: "10:00", title: "淺草和服雅 (和服體驗)", img: "https://images.unsplash.com/photo-1493976040374-85c8e12f0c0e?q=80&w=600", desc: "預約代號 JK2026，換上精緻和服慢步淺草巷弄。", buy: "和服寫真回憶", transport: "南行德 ➔ 地鐵淺草站", must: "JK2026" },
            { time: "11:00", title: "淺草寺 / 雷門", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Kaminarimon_at_night.jpg/640px-Kaminarimon_at_night.jpg", desc: "穿越巨大雷門大紅燈籠拍照，在仲見世通享用傳統小吃。", buy: "雷門御守、炸饅頭", transport: "淺草站步行即達", must: "求個御守" },
            { time: "14:00", title: "Suzukien 抹茶甜點", img: "https://images.unsplash.com/photo-1515823064-d6e0c04616a7?q=80&w=600", desc: "壽壽喜園。挑戰世界最濃 No.7 抹茶冰淇淋！", buy: "抹茶系列點心", transport: "淺草寺後方步行", must: "挑戰 No.7" },
            { time: "16:00", title: "今戶神社 & 晴空塔", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Tokyo_Skytree_at_night.jpg/640px-Tokyo_Skytree_at_night.jpg", desc: "招財貓發源地祈求良緣，隨後前往晴空塔欣賞高空美景。", buy: "貓咪御守、限定 Banana", transport: "淺草 ➔ 地鐵押上站", must: "夕陽夜景" },
            { time: "19:00", title: "燒肉黑田 (澀谷店)", img: "https://images.unsplash.com/photo-1514355315815-2b64b0216b14?q=80&w=600", desc: "高級 A5 燒肉饗宴，隱身澀谷巷弄的精緻美味。", buy: "特選厚切牛舌", transport: "押上 ➔ 澀谷站", must: "必吃厚牛舌" }
        ]},
        { date: "10/28", spots: [{ time: "全天", title: "東京迪士尼海洋 (Sea)", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d4/Tokyo_DisneySea_Entrance.jpg/640px-Tokyo_DisneySea_Entrance.jpg", desc: "暢玩全新「夢幻泉鄉」區，走進冰雪奇緣與彼得潘的世界。", buy: "達菲周邊、園區限定商品", transport: "南行德 ➔ 舞濱站轉迪士尼單軌", must: "搶 DPA 卡" }]},
        { date: "10/29", spots: [{ time: "全天", title: "東京迪士尼樂園 (Land)", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Cinderella_Castle_Tokyo_Disneyland_2019.jpg/640px-Cinderella_Castle_Tokyo_Disneyland_2019.jpg", desc: "經典公主夢幻日，美女與野獸城堡巡禮。", buy: "造型爆米花桶、米奇髮箍", transport: "舞濱站步行", must: "公主風格" }]},
        { date: "10/30", spots: [
            { time: "10:00", title: "東京都廳展望台", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Tokyo_Metropolitan_Government_Building_2012.jpg/640px-Tokyo_Metropolitan_Government_Building_2012.jpg", desc: "免費俯瞰新宿與東京壯觀的天際線。", buy: "都廳限定紀念品", transport: "新宿站步行", must: "免費觀景" },
            { time: "11:30", title: "明治神宮", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c0/Meiji_Jingu_Shrine_Torii.jpg/640px-Meiji_Jingu_Shrine_Torii.jpg", desc: "在東京都心的森林大鳥居下漫步，洗滌心靈。", buy: "開運御守", transport: "JR 原宿站", must: "心靈洗滌" },
            { time: "13:00", title: "敘敘苑 (歌劇城 53F)", img: "https://images.unsplash.com/photo-1544365558-35aa4afcf11f?q=80&w=600", desc: "邊吃燒肉邊從 53 樓高處眺望東京都景色。", buy: "敘敘苑燒肉醬", transport: "初台站直結", must: "窗邊位置" },
            { time: "15:00", title: "原宿竹下通 & 伊勢丹", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Takeshita_Street_Harajuku.jpg/640px-Takeshita_Street_Harajuku.jpg", desc: "潮流發源與高級精品百貨一次滿足。", buy: "可麗餅、潮流小物", transport: "原宿/新宿", must: "購物瘋" },
            { time: "19:00", title: "澀谷 SKY 夜景", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/e/ef/Shibuya_Crossing_from_Shibuya_Sky.jpg/640px-Shibuya_Crossing_from_Shibuya_Sky.jpg", desc: "360度露天展望台，飽覽東京十字路口最美夜景。", buy: "限定周邊照", transport: "地鐵澀谷站", must: "提早預約" },
            { time: "21:00", title: "歌舞伎町散策", img: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/Kabukicho_Ichibangai_Gate.jpg/640px-Kabukicho_Ichibangai_Gate.jpg", desc: "看巨大的哥吉拉大樓，體驗東京繁華的不夜城。", buy: "唐吉訶德採購", transport: "新宿站東口", must: "拍哥吉拉" }
        ]},
        { date: "10/31", spots: [{ time: "08:15", title: "前往成田機場", img: "src_64931908.jpg", desc: "成田機場返程報到 (IT281)。結束夢幻的東京之旅。", buy: "免稅店最後衝刺", transport: "南行德 ➔ 機場", must: "IT281返台" }] }
    ];

    let expenses = JSON.parse(localStorage.getItem('tokyo_expenses_final_v5')) || [];

    function init() {
        renderDaySelector();
        renderItinerary(0);
        renderSplitInputs();
        updateBudgetUI();
        fetchRate();
    }

    // 渲染上方日期選擇器
    function renderDaySelector() {
        const container = document.getElementById('day-selector');
        container.innerHTML = tripData.map((d, i) => `
            <div class="day-btn ${i === 0 ? 'active' : ''}" onclick="switchDay(${i}, this)">
                <b>Day ${i+1}</b><span>(${d.date})</span>
            </div>
        `).join('');
    }

    function switchDay(index, btn) {
        document.querySelectorAll('.day-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        renderItinerary(index);
    }

    // ✨ 完美修復的行程渲染邏輯，點擊卡片絕對會彈出詳情 ✨
    function renderItinerary(dayIndex) {
        const container = document.getElementById('itinerary-list');
        const spots = tripData[dayIndex].spots;
        
        container.innerHTML = spots.map((s, spotIdx) => `
            <div class="timeline-item">
                <div class="time-col">${s.time}</div>
                <div class="line-col"><div class="dot"></div></div>
                <div class="card-col">
                    <div class="card card-clickable" onclick="showModal(${dayIndex}, ${spotIdx})">
                        <div class="tape-tr"></div><div class="tape-bl"></div>
                        <div class="card-title">✨ ${s.title}</div>
                        <div style="font-size:0.9rem; color:#888; margin-bottom:12px;"># ${s.must}</div>
                        <div style="font-size:0.95rem; color:var(--primary); font-weight:bold; text-align:right; border-top:1px dashed #EEE; padding-top:10px;">
                            點擊查看詳細介紹與導航 👆
                        </div>
                    </div>
                </div>
            </div>
        `).join('');
    }

    // ✨ 修復的彈出視窗功能 ✨
    function showModal(dayIndex, spotIdx) {
        const s = tripData[dayIndex].spots[spotIdx];
        document.getElementById('modal-body').innerHTML = `
            <div style="font-size:1.4rem; color:var(--secondary); font-weight:bold; margin-bottom:12px; border-bottom:2px dashed var(--accent-pink); padding-bottom:8px;">🌸 ${s.title}</div>
            
            <img src="${s.img}" style="width:100%; border-radius:12px; margin-bottom:15px; max-height:220px; object-fit:cover; border:1px solid #EEE;" onerror="this.src='https://images.unsplash.com/photo-1542931237-323a19592736?q=80&w=400'">
            
            <div style="font-weight:bold; color:var(--primary); font-size:1.1rem; margin-top:10px;">📖 景點介紹</div>
            <div style="font-size:1rem; line-height:1.6; margin-bottom:15px; color:#555;">${s.desc}</div>
            
            <div style="font-weight:bold; color:var(--primary); font-size:1.1rem;">🛍️ 推薦購買</div>
            <div style="font-size:0.95rem; margin-bottom:15px; color:#555;">${s.buy}</div>
            
            <div style="font-weight:bold; color:var(--primary); font-size:1.1rem;">🚆 交通方式</div>
            <div style="font-size:0.95rem; background:#F8F6FF; padding:12px; border-radius:12px; color:#5D4E7A; line-height:1.5; border:1.5px solid #EEDDFF;">${s.transport}</div>
            
            <a href="https://www.google.com/maps/search/?api=1&query=$$${encodeURIComponent(s.title)}" target="_blank" class="nav-btn" style="background:var(--primary); color:white; border:none; margin-top:25px; padding:15px; font-size:1.1rem;">
                <i class="fas fa-location-arrow"></i> 開啟地圖導航
            </a>
        `;
        document.getElementById('detail-modal').classList.add('active');
    }

    function closeModal(event) { 
        if(!event || event.target.id === 'detail-modal' || event.target.classList.contains('btn-close')) {
            document.getElementById('detail-modal').classList.remove('active'); 
        }
    }

    function switchSubTab(type) {
        document.querySelectorAll('.sub-tab').forEach(t => t.classList.remove('active'));
        event.target.classList.add('active');
        if(type === 'info') {
            document.getElementById('section-itinerary').style.display = 'none';
            document.getElementById('section-info').style.display = 'block';
        } else {
            document.getElementById('section-info').style.display = 'none';
            document.getElementById('section-itinerary').style.display = 'block';
        }
    }

    function switchMainTab(id, btn) {
        document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
        document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
        
        document.getElementById('section-' + id).classList.add('active');
        btn.classList.add('active');
        
        // 顯示/隱藏特定 UI 元件
        if(id === 'budget') {
            document.getElementById('sub-tabs').style.display = 'none';
            document.getElementById('day-selector').style.display = 'none';
            document.getElementById('sanrio-img').style.display = 'block';
        } else {
            document.getElementById('sub-tabs').style.display = 'flex';
            document.getElementById('day-selector').style.display = 'flex';
            document.getElementById('sanrio-img').style.display = 'none';
            if(id === 'itinerary') switchSubTab('itinerary');
            else switchSubTab('info');
        }
        window.scrollTo(0,0);
    }

    // --- 記帳分帳邏輯 (包含三種分配方式) ---
    async function fetchRate() {
        try {
            const res = await fetch('https://api.exchangerate-api.com/v4/latest/JPY');
            const data = await res.json(); exchangeRate = data.rates.TWD;
            document.getElementById('current-rate-display').innerText = `${exchangeRate.toFixed(4)}`;
            updateBudgetUI();
        } catch (e) { document.getElementById('current-rate-display').innerText = "0.215"; }
    }

    function setPayer(name, btn) {
        currentPayer = name;
        document.querySelectorAll('.payer-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
    }

    function setSplitMethod(method, btn) {
        currentSplitMethod = method;
        document.querySelectorAll('.split-btn').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        renderSplitInputs();
    }

    function renderSplitInputs() {
        const container = document.getElementById('split-inputs-container');
        if (currentSplitMethod === 'equal') {
            container.innerHTML = `<p style="text-align:center; font-size:0.9rem; color:#888; padding: 10px 0;">✨ 將由三人平均分攤此筆費用</p>`;
        } else {
            const unit = currentSplitMethod === 'percent' ? '%' : '¥';
            container.innerHTML = users.map(u => `
                <div class="split-input-wrap">
                    <span style="font-size:0.9rem; color:#555;">${u} 應負擔</span>
                    <div><input type="number" class="split-val" data-user="${u}"> <span style="color:#555;">${unit}</span></div>
                </div>
            `).join('');
        }
    }

    function addExpense() {
        const title = document.getElementById('exp-title').value;
        const amount = parseFloat(document.getElementById('exp-amount').value);
        if(!title || isNaN(amount)) return alert("請確認已填寫項目名稱與總金額喔！");

        let splits = {};
        
        if (currentSplitMethod === 'equal') {
            users.forEach(u => splits[u] = amount / 3);
        } else if (currentSplitMethod === 'percent') {
            let sumP = 0;
            document.querySelectorAll('.split-val').forEach(el => {
                let p = parseFloat(el.value) || 0;
                splits[el.dataset.user] = (amount * p) / 100;
                sumP += p;
            });
            if (sumP !== 100) return alert("分配錯誤：百分比總和必須為 100% 喔！");
        } else if (currentSplitMethod === 'exact') {
            let sumE = 0;
            document.querySelectorAll('.split-val').forEach(el => {
                let v = parseFloat(el.value) || 0;
                splits[el.dataset.user] = v;
                sumE += v;
            });
            if (Math.abs(sumE - amount) > 1) return alert(`分配錯誤：自訂金額加總必須等於總金額 ¥${amount}！`);
        }

        const dateStr = new Date().toLocaleDateString('zh-TW', { month: '2-digit', day: '2-digit' });
        
        expenses.push({ id: Date.now(), title, amount, payer: currentPayer, splits, date: dateStr });
        localStorage.setItem('tokyo_expenses_final_v5', JSON.stringify(expenses));
        
        document.getElementById('exp-title').value = '';
        document.getElementById('exp-amount').value = '';
        if(currentSplitMethod !== 'equal') {
            document.querySelectorAll('.split-val').forEach(el => el.value = '');
        }
        updateBudgetUI();
    }

    function deleteExpense(id) {
        if(confirm("確定要刪除這筆紀錄嗎？")) {
            expenses = expenses.filter(e => e.id !== id);
            localStorage.setItem('tokyo_expenses_final_v5', JSON.stringify(expenses));
            updateBudgetUI();
        }
    }

    function updateBudgetUI() {
        const body = document.getElementById('expense-list-body');
        const netBalances = { '蒂': 0, '丞': 0, '頻': 0 };
        
        body.innerHTML = expenses.map(e => {
            netBalances[e.payer] += e.amount;
            users.forEach(u => netBalances[u] -= e.splits[u]);
            return `<tr>
                        <td>🖍️ ${e.title}<br><small style="color:#888;">¥ ${e.amount.toLocaleString()}</small></td>
                        <td>${e.payer}</td>
                        <td style="display:flex; justify-content:space-between; align-items:center;">
                            ${e.date}
                            <button onclick="deleteExpense(${e.id})" style="background:none; border:none; color:#FFB7B2; padding:0; cursor:pointer;"><i class="fas fa-times"></i></button>
                        </td>
                    </tr>`;
        }).reverse().join('');

        const totalJPY = expenses.reduce((s, e) => s + e.amount, 0);
        document.getElementById('total-jpy').innerText = totalJPY.toLocaleString();
        document.getElementById('total-twd').innerText = Math.round(totalJPY * exchangeRate).toLocaleString();

        let inst = [];
        let debtors = users.map(u => ({ name: u, bal: netBalances[u] })).filter(u => u.bal < -1).sort((a,b) => a.bal - b.bal);
        let creditors = users.map(u => ({ name: u, bal: netBalances[u] })).filter(u => u.bal > 1).sort((a,b) => b.bal - a.bal);
        let d = 0, c = 0;
        
        while (d < debtors.length && c < creditors.length) {
            let amt = Math.min(Math.abs(debtors[d].bal), creditors[c].bal);
            inst.push(`<tr><td>🧧 ${debtors[d].name} ➜ ${creditors[c].name}</td><td style="text-align:right; font-weight:bold; color:#6B4E8D;">¥ ${Math.round(amt).toLocaleString()}</td></tr>`);
            debtors[d].bal += amt; creditors[c].bal -= amt;
            if (Math.abs(debtors[d].bal) < 1) d++; if (Math.abs(creditors[c].bal) < 1) c++;
        }
        
        document.getElementById('settlement-results').innerHTML = inst.length ? inst.join('') : '<tr><td colspan="2" style="text-align:center; color:#888;">帳目完美平衡 ✨</td></tr>';
    }

    init();
</script>
</body>
</html>
