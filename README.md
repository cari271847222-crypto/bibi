<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover, user-scalable=yes">
    <title>MORE大家庭｜夥伴紀錄</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        /* 大地色系基底 */
        body {
            background-color: #F9F0E3;
            font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            padding: 20px 16px 40px;
            color: #5E3A1F;
        }

        .app-container {
            max-width: 600px;
            margin: 0 auto;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            flex-wrap: wrap;
            gap: 10px;
            border-bottom: 2px solid #EADBC6;
            padding-bottom: 12px;
        }
        .logo-area {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        #teamLogo {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background-color: #5E3A1F;
            border-radius: 50%;
            color: white;
            font-size: 1.3rem;
            font-weight: 600;
            font-family: inherit;
            cursor: default;
            box-shadow: 0 1px 3px rgba(0,0,0,0.1);
        }
        h1 {
            font-size: 1.6rem;
            font-weight: 600;
            color: #8B5A2B;
            margin: 0;
        }
        .tab-bar {
            display: flex;
            gap: 12px;
            margin-bottom: 24px;
            background: #F3E9DE;
            padding: 6px;
            border-radius: 60px;
        }
        .tab-btn {
            flex: 1;
            text-align: center;
            padding: 10px 0;
            border-radius: 40px;
            font-weight: 500;
            font-size: 0.85rem;
            background: transparent;
            border: none;
            color: #8B5A2B;
            cursor: pointer;
        }
        .tab-btn.active {
            background: #FFF7EF;
            color: #B87C4A;
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
            border: 1px solid #EADBC6;
        }
        .tab-pane {
            display: none;
            animation: fade 0.2s ease;
        }
        .tab-pane.active-pane {
            display: block;
        }
        @keyframes fade {
            from { opacity: 0; transform: translateY(5px);}
            to { opacity: 1; transform: translateY(0);}
        }

        /* 卡片風格 */
        .card {
            background: #FFFBF5;
            border-radius: 24px;
            padding: 16px 20px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.04);
            border: 1px solid #EDE0D2;
            margin-bottom: 16px;
            cursor: pointer;
            transition: 0.1s;
        }
        .card:active {
            background: #FEF6EC;
        }
        .flex-between {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        /* 級別標籤 - 純文字 */
        .level-badge {
            display: inline-block;
            font-size: 0.75rem;
            font-weight: 600;
            letter-spacing: 0.3px;
        }
        .level-royal {
            color: #B87C4A;
        }
        .level-1 {
            color: #9B6A42;
        }
        .level-2 {
            color: #A15E3A;
        }
        .level-3, .level-3-mentor {
            color: #6B4E3A;
        }
        .level-intern {
            color: #7C5E3A;
        }

        .status-badge {
            background: #F3E9DE;
            border-radius: 6px;
            padding: 2px 8px;
            font-size: 0.65rem;
            margin-left: 6px;
            color: #7C5E3A;
            border: 1px solid #E2D0BD;
        }
        .qualify-badge {
            background: #F4EADF;
            color: #9B6A42;
            border: 1px solid #E2D0BD;
            padding: 2px 8px;
            border-radius: 6px;
            font-size: 0.65rem;
            margin-left: 6px;
            display: inline-flex;
            align-items: center;
            gap: 4px;
        }
        .info-row {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 12px;
            font-size: 0.7rem;
            color: #7C5E3A;
        }
        .progress-bar-bg {
            background: #F0E2D4;
            border-radius: 10px;
            height: 6px;
            overflow: hidden;
            margin: 8px 0;
        }
        .progress-fill {
            background: #D9B48B;
            width: 0%;
            height: 100%;
            border-radius: 10px;
        }
        .small-text {
            font-size: 0.7rem;
            color: #7C5E3A;
        }
        .btn-sm {
            background: #E9D9CB;
            padding: 4px 12px;
            border-radius: 6px;
            font-size: 0.7rem;
            border: none;
            cursor: pointer;
            color: #5E3A1F;
            transition: 0.1s;
        }
        .btn-sm:active {
            background: #DECEBE;
        }
        .claim-btn {
            background: #E0EED7;
            color: #4A6A2F;
        }

        /* 重新設計金MORE獎頂部獎金門檻區塊 */
        .reward-table {
            background: #FDF9F2;
            border-radius: 32px;
            padding: 20px 12px;
            margin-bottom: 24px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            border: 1px solid #E8D9C8;
        }
        .reward-header {
            text-align: center;
            margin-bottom: 16px;
            position: relative;
        }
        .reward-header h3 {
            font-size: 1.1rem;
            font-weight: 600;
            color: #8B5A2B;
            background: #FDF9F2;
            display: inline-block;
            padding: 0 12px;
            letter-spacing: 1px;
        }
        .reward-header::before {
            content: "";
            position: absolute;
            top: 50%;
            left: 0;
            right: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, #D4BFA5, #D4BFA5, transparent);
            z-index: 0;
        }
        .reward-header h3 span {
            position: relative;
            background: #FDF9F2;
            padding: 0 8px;
            z-index: 1;
        }
        .reward-items {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 16px;
            margin-top: 8px;
        }
        .reward-item {
            background: white;
            border-radius: 28px;
            padding: 12px 16px;
            min-width: 100px;
            text-align: center;
            box-shadow: 0 2px 6px rgba(0,0,0,0.04);
            border: 1px solid #EDE0D2;
            transition: transform 0.1s ease;
        }
        .reward-item:hover {
            transform: translateY(-2px);
        }
        .reward-level {
            font-size: 0.8rem;
            font-weight: 600;
            color: #9B6A42;
            letter-spacing: 1px;
            margin-bottom: 6px;
        }
        .reward-amount {
            font-size: 1.2rem;
            font-weight: 700;
            color: #BC6F42;
            margin: 4px 0;
        }
        .reward-threshold {
            font-size: 0.65rem;
            color: #A58E73;
            background: #FEF8F0;
            display: inline-block;
            padding: 2px 10px;
            border-radius: 20px;
        }
        .reward-icon {
            font-size: 1.3rem;
            margin-bottom: 4px;
        }

        .empty-state {
            text-align: center;
            padding: 48px 20px;
            background: #FFFBF5;
            border-radius: 24px;
            color: #C2A07E;
            border: 1px solid #F0E4D4;
        }

        /* 模態框大地色 */
        .modal-mask {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(75, 55, 35, 0.4);
            backdrop-filter: blur(2px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            visibility: hidden;
            opacity: 0;
            transition: 0.2s;
        }
        .modal-mask.active {
            visibility: visible;
            opacity: 1;
        }
        .modal-container {
            background: #FFFCF8;
            width: 90%;
            max-width: 520px;
            max-height: 85vh;
            overflow-y: auto;
            padding: 24px;
            border-radius: 28px;
            border: 1px solid #EAD5C0;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            position: relative;
            color: #5E3A1F;
        }
        .modal-container h2 {
            font-size: 1.4rem;
            color: #B87C4A;
            margin-bottom: 16px;
            text-align: center;
        }
        .modal-container h3 {
            font-size: 1rem;
            color: #A57142;
            margin: 16px 0 8px;
            border-left: 3px solid #EAD0B6;
            padding-left: 10px;
        }
        .form-group {
            margin-bottom: 16px;
        }
        label {
            font-size: 0.75rem;
            font-weight: 500;
            color: #9B6A42;
            display: block;
            margin-bottom: 5px;
        }
        input, select {
            width: 100%;
            padding: 8px 12px;
            border-radius: 10px;
            border: 1px solid #F0DFCE;
            background: white;
            font-size: 0.85rem;
            color: #4A3525;
        }
        button {
            background: #F4E8DD;
            border: none;
            padding: 8px 16px;
            border-radius: 10px;
            font-weight: 500;
            cursor: pointer;
            font-size: 0.8rem;
            color: #5E3A1F;
        }
        .btn-group {
            display: flex;
            gap: 12px;
            margin: 16px 0;
            justify-content: center;
        }
        .add-section {
            display: flex;
            gap: 8px;
            margin: 12px 0;
            flex-wrap: wrap;
        }
        .history-item, .course-item {
            background: #FEFAF5;
            border-radius: 12px;
            padding: 8px 12px;
            margin-bottom: 8px;
            border: 1px solid #F5E5D6;
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            color: #5E3A1F;
        }
        hr {
            margin: 16px 0;
            border: none;
            border-top: 1px solid #EDE0D2;
        }
        footer {
            text-align: center;
            font-size: 0.7rem;
            color: #B88A5A;
            margin-top: 20px;
            font-weight: 500;
        }
        .search-box {
            background: #FFFBF5;
            border-radius: 40px;
            padding: 4px 16px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 8px;
            border: 1px solid #F2E5D6;
        }
        .search-box input {
            border: none;
            background: transparent;
            padding: 10px 0;
            font-size: 0.85rem;
            outline: none;
            color: #5E3A1F;
        }
        .bottom-buttons {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 12px;
        }
        .modal-close {
            position: absolute;
            top: 16px;
            right: 20px;
            font-size: 24px;
            cursor: pointer;
            color: #C8AE92;
            background: none;
            padding: 0;
            line-height: 1;
        }
        /* 備份頁面獨立樣式 */
        .backup-container {
            background: #FFFBF5;
            border-radius: 24px;
            padding: 24px 20px;
            text-align: center;
            border: 1px solid #F2E5D6;
        }
        .backup-title {
            font-size: 1.2rem;
            font-weight: 600;
            color: #8B5A2B;
            margin-bottom: 16px;
        }
        .backup-desc {
            font-size: 0.75rem;
            color: #7C5E3A;
            margin-bottom: 20px;
            line-height: 1.4;
        }
        .backup-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 8px;
        }
        .backup-action-btn {
            background: #F4E8DD;
            padding: 10px 24px;
            border-radius: 10px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #7C5E3A;
            cursor: pointer;
            border: 1px solid #E2D0BD;
            transition: 0.1s;
        }
        .backup-action-btn:active {
            transform: scale(0.97);
        }
        #fileInput {
            display: none;
        }

        /* 家庭照顧 - 按鈕在左上角 */
        .care-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 12px;
        }
        .care-care-btn {
            background: #E9D9CB;
            border: none;
            border-radius: 30px;
            width: 32px;
            height: 32px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1rem;
            transition: 0.1s;
        }
        .care-care-btn:active {
            transform: scale(0.95);
        }
        .care-care-btn.disabled {
            opacity: 0.5;
            pointer-events: none;
        }
        .care-info-block {
            flex: 1;
        }
        .streak-badge {
            display: inline-block;
            background: #F4EADF;
            border-radius: 6px;
            padding: 2px 8px;
            font-size: 0.65rem;
            margin-left: 6px;
            color: #9B6A42;
            border: 1px solid #E2D0BD;
        }
        .intimacy-line {
            display: flex;
            align-items: baseline;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 4px;
            font-size: 0.8rem;
        }
        .care-quote {
            font-size: 0.7rem;
            color: #B87C4A;
            background: #FEFAF0;
            padding: 2px 8px;
            border-radius: 20px;
            display: inline-block;
            border-left: 2px solid #EAD0B6;
        }
        .reminder-badge {
            display: inline-flex;
            align-items: center;
            gap: 4px;
            background: #FCE9D8;
            border-radius: 20px;
            padding: 2px 8px;
            font-size: 0.65rem;
            color: #C55A2C;
            margin-left: 8px;
        }
        @keyframes celebrate {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.02); background: #FFE0B5; }
            100% { transform: scale(1); opacity: 1; }
        }
        .celebrate-animation {
            animation: celebrate 0.4s ease-in-out;
        }
        .confetti {
            position: fixed;
            pointer-events: none;
            z-index: 2000;
            font-size: 1rem;
            animation: floatUp 1s ease-out forwards;
        }
        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-60px) rotate(15deg); opacity: 0; }
        }

        /* 夥伴名字加強大地色 */
        .card strong {
            color: #8B5A2B;
            font-weight: 600;
        }
        /* 金MORE獎金額強調 */
        .reward-amount {
            color: #BC6F42;
        }
    </style>
</head>
<body>
<div class="app-container">
    <div class="header">
        <div class="logo-area">
            <div id="teamLogo">M</div>
            <h1>MORE 大家庭</h1>
        </div>
        <button id="globalAddBtn" style="background:#FFF2E6; border:1px solid #E2D0BD; color:#B87C4A;">+ 新增夥伴</button>
    </div>

    <div class="tab-bar">
        <button class="tab-btn active" data-tab="partners">我的夥伴們</button>
        <button class="tab-btn" data-tab="gold">金MORE獎</button>
        <button class="tab-btn" data-tab="family">家庭照顧</button>
        <button class="tab-btn" data-tab="backup">備份</button>
    </div>

    <div id="partnersPane" class="tab-pane active-pane">
        <div class="search-box">
            <span>🔍</span>
            <input type="text" id="searchPartnerInput" placeholder="搜尋夥伴姓名">
            <button id="clearSearchBtn" style="background:none; font-size:1rem; color:#C8AE92;">✕</button>
        </div>
        <div id="partnerListContainer"></div>
    </div>

    <div id="goldPane" class="tab-pane">
        <div class="reward-table">
            <div class="reward-header">
                <h3><span>🏆 年度業績達標獎金 🏆</span></h3>
            </div>
            <div class="reward-items">
                <div class="reward-item">
                    <div class="reward-icon">🌿</div>
                    <div class="reward-level">三級 / 三級輔導</div>
                    <div class="reward-amount">$666</div>
                    <div class="reward-threshold">門檻 10萬</div>
                </div>
                <div class="reward-item">
                    <div class="reward-icon">🍂</div>
                    <div class="reward-level">二級</div>
                    <div class="reward-amount">$3,000</div>
                    <div class="reward-threshold">門檻 30萬</div>
                </div>
                <div class="reward-item">
                    <div class="reward-icon">🌟</div>
                    <div class="reward-level">一級</div>
                    <div class="reward-amount">$5,000</div>
                    <div class="reward-threshold">門檻 90萬</div>
                </div>
            </div>
            <div class="small-text" style="text-align:center; margin-top:12px;">年度內升級分段累計，達標即可領獎</div>
        </div>
        <div id="goldRewardContainer"></div>
    </div>

    <div id="familyPane" class="tab-pane">
        <div id="careGameContainer"></div>
    </div>

    <div id="backupPane" class="tab-pane">
        <div class="backup-container">
            <div class="backup-title">📦 資料備份與還原</div>
            <div class="backup-desc">
                更換手機或清除瀏覽器資料前，請先「匯出備份」保存檔案。<br>
                換到新手機後，點擊「匯入備份」選擇之前儲存的檔案即可還原所有夥伴資料。
            </div>
            <div class="backup-buttons">
                <div class="backup-action-btn" id="exportBtn">📤 匯出備份</div>
                <div class="backup-action-btn" id="importBtn">📥 匯入備份</div>
            </div>
            <input type="file" id="fileInput" accept=".json">
        </div>
    </div>

    <footer>培訓做得好 事業沒煩惱</footer>
</div>

<div id="dynamicModal" class="modal-mask">
    <div class="modal-container">
        <span class="modal-close">&times;</span>
        <div id="modalContent"></div>
    </div>
</div>

<script>
    // ---------- 配置 ----------
    const LEVEL_ORDER = ['皇家', '一級', '二級', '三級輔導', '三級', '實習'];
    const ALL_LEVELS = [...LEVEL_ORDER];
    const PARTNER_TYPES = ['自用', '經營', '保留', '退出'];
    const PRESET_COURSES = ['絕對成交', '執行力', '領導力', '引爆生命力', '彩妝課'];
    const REWARD_CONFIG = {
        '三級輔導': { threshold: 100000, amount: 666 },
        '三級': { threshold: 100000, amount: 666 },
        '二級': { threshold: 300000, amount: 3000 },
        '一級': { threshold: 900000, amount: 5000 }
    };
    const CURRENT_YEAR = 2026;

    // 暖心語錄庫（簡化文字）
    const QUOTES = [
        "有你陪伴，今天特別有動力",
        "每天一點點，成長看得見",
        "辛苦了，休息一下再出發",
        "你是我最棒的戰友",
        "今天也要一起加油",
        "朝著目標前進，我們都在",
        "你的努力，夥伴都看在眼裡",
        "謝謝你記得照顧我",
        "有你真好，團隊越來越溫暖"
    ];

    let partners = [];
    let activeTab = 'partners';
    let searchKeyword = '';

    function save() { localStorage.setItem('partners_app_data', JSON.stringify(partners)); }

    function typeWeight(t) { return t === '自用' || t === '經營' ? 0 : (t === '保留' ? 1 : 2); }
    function levelWeight(l) { return LEVEL_ORDER.indexOf(l); }
    function sortPartners(list) {
        return [...list].sort((a,b) => {
            if (typeWeight(a.type) !== typeWeight(b.type)) return typeWeight(a.type) - typeWeight(b.type);
            if (levelWeight(a.level) !== levelWeight(b.level)) return levelWeight(a.level) - levelWeight(b.level);
            return (a.joinDate || '').localeCompare(b.joinDate || '') * -1;
        });
    }

    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, m => ({ '&':'&amp;','<':'&lt;','>':'&gt;' }[m])); }
    function isBirthdayToday(bd) { if(!bd) return false; const t=new Date(), b=new Date(bd); return t.getMonth()===b.getMonth() && t.getDate()===b.getDate(); }

    function effectiveMonths(p) {
        const date = p.effectiveJoinDate || p.joinDate;
        if(!date) return 0;
        const start = new Date(date), now = new Date();
        let months = (now.getFullYear()-start.getFullYear())*12 + (now.getMonth()-start.getMonth());
        if(now.getDate() < start.getDate()) months--;
        return Math.max(0, months);
    }
    function getQualifyBadge(p) {
        if(p.type !== '自用' && p.type !== '經營') return null;
        const m = effectiveMonths(p);
        if(m >= 12) return '滿一年';
        if(m >= 6) return '滿半年｜半額金MORE';
        return null;
    }

    function updateEffectiveDate(p, oldType, newType) {
        const wasActive = (oldType === '自用' || oldType === '經營');
        const isActive = (newType === '自用' || newType === '經營');
        if(!wasActive && isActive) p.effectiveJoinDate = new Date().toISOString().slice(0,10);
        if(!p.effectiveJoinDate) p.effectiveJoinDate = p.joinDate;
    }

    // ----- 升降級與業績計算（與之前相同）-----
    function getSegments(p, year) {
        const histories = (p.levelHistory || []).filter(h => LEVEL_ORDER.includes(h.level));
        const filtered = histories.filter(h => h.date && h.date.startsWith(year)).sort((a,b)=>a.date.localeCompare(b.date));
        let startLevel = p.level;
        const before = histories.filter(h => h.date < `${year}-01-01`).sort((a,b)=>b.date.localeCompare(a.date));
        if(before.length) startLevel = before[0].level;
        let segs = [], cur = startLevel, last = `${year}-01-01`;
        for(let r of filtered) {
            if(r.date > last) segs.push({ level: cur, start: last, end: r.date });
            cur = r.level;
            last = r.date;
        }
        segs.push({ level: cur, start: last, end: `${year}-12-31` });
        return segs;
    }
    function calcLevelSales(p, year) {
        const monthly = p.annualData?.[year]?.monthlySales || new Array(12).fill(0);
        const segs = getSegments(p, year);
        let sales = { '三級輔導':0, '三級':0, '二級':0, '一級':0 };
        for(let s of segs) {
            if(!REWARD_CONFIG[s.level]) continue;
            let sm = new Date(s.start).getMonth(), em = new Date(s.end).getMonth();
            if(s.start.slice(0,4) < year) sm = 0;
            if(s.end.slice(0,4) > year) em = 11;
            for(let m=sm; m<=em; m++) sales[s.level] += monthly[m] || 0;
        }
        return sales;
    }
    function getRewardStatus(p, year) {
        const sales = calcLevelSales(p, year);
        const claimed = p.annualData?.[year]?.claimedRewards || {};
        return Object.entries(REWARD_CONFIG).map(([lvl,cfg]) => ({
            level: lvl, threshold: cfg.threshold, amount: cfg.amount,
            sales: sales[lvl] || 0, isQualified: (sales[lvl]||0) >= cfg.threshold,
            isClaimed: claimed[lvl] || false
        }));
    }
    function claimReward(pid, lvl) {
        const p = partners.find(p=>p.id===pid);
        if(!p) return;
        const status = getRewardStatus(p, CURRENT_YEAR).find(r=>r.level===lvl);
        if(status?.isQualified && !status.isClaimed) {
            if(!p.annualData) p.annualData = {};
            if(!p.annualData[CURRENT_YEAR]) p.annualData[CURRENT_YEAR] = { monthlySales: new Array(12).fill(0), claimedRewards: {} };
            p.annualData[CURRENT_YEAR].claimedRewards[lvl] = true;
            save();
            alert(`已領取 ${lvl} 獎金 $${status.amount.toLocaleString()} 元`);
            renderGoldPage();
        } else alert("尚未符合領獎資格或已領取過");
    }
    function editMonthly(pid) {
        const p = partners.find(p=>p.id===pid);
        if(!p) return;
        if(!p.annualData) p.annualData = {};
        if(!p.annualData[CURRENT_YEAR]) p.annualData[CURRENT_YEAR] = { monthlySales: new Array(12).fill(0), claimedRewards: {} };
        const monthly = p.annualData[CURRENT_YEAR].monthlySales;
        let html = `<h3>${p.name} - ${CURRENT_YEAR} 每月補貨 (元)</h3><div style="display:grid; grid-template-columns:repeat(3,1fr); gap:8px;">`;
        const months = ['1月','2月','3月','4月','5月','6月','7月','8月','9月','10月','11月','12月'];
        for(let i=0;i<12;i++) html += `<div><label>${months[i]}</label><input type="number" id="m${i}" value="${monthly[i]||0}" step="1000"></div>`;
        html += `</div><div class="btn-group"><button id="saveMonthBtn">儲存</button><button id="cancelMonthBtn">取消</button></div>`;
        const modal = document.getElementById('dynamicModal'), modalC = document.getElementById('modalContent');
        modalC.innerHTML = html;
        modal.classList.add('active');
        document.getElementById('saveMonthBtn').onclick = () => {
            for(let i=0;i<12;i++) monthly[i] = parseInt(document.getElementById(`m${i}`).value) || 0;
            save();
            modal.classList.remove('active');
            renderGoldPage();
            if(activeTab === 'partners') renderPartnerList();
        };
        document.getElementById('cancelMonthBtn').onclick = () => modal.classList.remove('active');
    }
    function renderGoldPage() {
        const container = document.getElementById('goldRewardContainer');
        if(!container) return;
        const valid = partners.filter(p => (p.type==='自用'||p.type==='經營') && p.level!=='皇家' && p.level!=='實習');
        if(!valid.length) { container.innerHTML = `<div class="empty-state">✨ 無符合獎金資格夥伴 ✨</div>`; return; }
        let html = '';
        for(let p of sortPartners(valid)) {
            const rewards = getRewardStatus(p, CURRENT_YEAR);
            const current = p.level;
            const cfg = REWARD_CONFIG[current];
            const sales = cfg ? (calcLevelSales(p, CURRENT_YEAR)[current]||0) : 0;
            const progress = cfg ? Math.min(100, (sales/cfg.threshold)*100) : 0;
            const remaining = cfg ? Math.max(0, cfg.threshold - sales) : 0;
            const hasClaimable = rewards.some(r=>r.isQualified && !r.isClaimed);
            const badge = getQualifyBadge(p);
            let levelClass = '';
            if(p.level === '皇家') levelClass = 'level-royal';
            else if(p.level === '一級') levelClass = 'level-1';
            else if(p.level === '二級') levelClass = 'level-2';
            else if(p.level === '三級輔導' || p.level === '三級') levelClass = 'level-3';
            else if(p.level === '實習') levelClass = 'level-intern';
            html += `<div class="card" data-id="${p.id}" style="cursor:pointer;">
                <div class="flex-between">
                    <div>
                        <span class="level-badge ${levelClass}">${p.level}</span>
                        <strong> ${escapeHtml(p.name)}</strong>
                        ${hasClaimable ? '<span style="margin-left:4px;">👑</span>' : ''}
                        ${badge ? `<span class="qualify-badge" style="margin-left:6px;">${badge}</span>` : ''}
                    </div>
                    <button class="btn-sm" onclick="event.stopPropagation(); editMonthly('${p.id}')">業績</button>
                </div>
                ${cfg ? `<div class="progress-bar-bg"><div class="progress-fill" style="width:${progress}%"></div></div>
                <div class="small-text flex-between"><span>${current} 門檻 ${cfg.threshold.toLocaleString()}</span><span>累積 ${sales.toLocaleString()} ${remaining>0 ? `(差 ${remaining.toLocaleString()})` : '達標'}</span></div>` : `<div class="small-text">⭐ ${current} 無年度獎金，可領取升級前獎勵</div>`}
                ${rewards.filter(r=>r.isQualified && !r.isClaimed).map(r=>`<div class="flex-between" style="margin-top:8px;"><span>${r.level} 獎金 $${r.amount.toLocaleString()}</span><button class="btn-sm claim-btn" onclick="event.stopPropagation(); claimReward('${p.id}','${r.level}')">領取</button></div>`).join('')}
            </div>`;
        }
        container.innerHTML = html;
        document.querySelectorAll('#goldRewardContainer .card').forEach(c => c.addEventListener('click', (e) => { if(e.target.tagName!=='BUTTON') editMonthly(c.dataset.id); }));
    }
    function renderPartnerList() {
        const container = document.getElementById('partnerListContainer');
        let filtered = partners.filter(p => p.name.toLowerCase().includes(searchKeyword.toLowerCase()));
        const sorted = sortPartners(filtered);
        if(!sorted.length) { container.innerHTML = `<div class="empty-state">✨ 沒有夥伴 ✨</div>`; return; }
        let html = '';
        for(let p of sorted) {
            const cake = isBirthdayToday(p.birthday) ? '🎂' : '';
            const badge = getQualifyBadge(p);
            let levelClass = '';
            if(p.level === '皇家') levelClass = 'level-royal';
            else if(p.level === '一級') levelClass = 'level-1';
            else if(p.level === '二級') levelClass = 'level-2';
            else if(p.level === '三級輔導' || p.level === '三級') levelClass = 'level-3';
            else if(p.level === '實習') levelClass = 'level-intern';
            html += `<div class="card" data-id="${p.id}">
                <div class="flex-between">
                    <div>
                        <span class="level-badge ${levelClass}">${p.level}</span>
                        <strong> ${escapeHtml(p.name)}</strong> ${cake}
                        <span class="status-badge">${p.type}</span>
                        ${badge ? `<span class="qualify-badge" style="margin-left:6px;">${badge}</span>` : ''}
                    </div>
                </div>
                <div class="info-row">
                    <span>加盟 ${p.joinDate?.slice(0,7) || '?'}</span>
                    <span>📍 ${escapeHtml(p.location) || '未填'}</span>
                    <span>🎂 ${p.birthday || '無'}</span>
                </div>
            </div>`;
        }
        container.innerHTML = html;
        document.querySelectorAll('#partnerListContainer .card').forEach(c => c.addEventListener('click', () => openDetailModal(c.dataset.id)));
    }

    // 家庭照顧頁面（鼓勵語放在親密度後面，並加入一個月未關心提醒）
    function renderFamily() {
        const container = document.getElementById('careGameContainer');
        if(!container) return;
        if(!partners.length) { container.innerHTML = '<div class="empty-state">還沒有家庭成員</div>'; return; }
        const today = new Date();
        const todayStr = today.toISOString().slice(0,10);
        let html = '';
        for(let p of partners) {
            const canCare = (p.lastCareDate !== todayStr);
            const intimacy = p.intimacy || 0;
            const streak = p.careStreak || 0;
            let streakText = '';
            if (streak >= 30) streakText = '忠誠戰友';
            else if (streak >= 14) streakText = '模範夥伴';
            else if (streak >= 7) streakText = '溫暖之星';
            else if (streak >= 3) streakText = '萌芽夥伴';
            
            // 計算距離上次照顧的天數
            let daysSinceLastCare = null;
            if (p.lastCareDate) {
                const last = new Date(p.lastCareDate);
                const diffTime = today - last;
                daysSinceLastCare = Math.floor(diffTime / (1000 * 60 * 60 * 24));
            } else {
                // 從未照顧過，視為超過30天
                daysSinceLastCare = 999;
            }
            const showReminder = daysSinceLastCare > 30;
            
            const randomQuote = QUOTES[Math.floor(Math.random() * QUOTES.length)];
            let levelClass = '';
            if(p.level === '皇家') levelClass = 'level-royal';
            else if(p.level === '一級') levelClass = 'level-1';
            else if(p.level === '二級') levelClass = 'level-2';
            else if(p.level === '三級輔導' || p.level === '三級') levelClass = 'level-3';
            else if(p.level === '實習') levelClass = 'level-intern';
            
            html += `<div class="card" data-id="${p.id}" id="care-card-${p.id}">
                <div class="care-header">
                    <button class="care-care-btn ${!canCare ? 'disabled' : ''}" data-id="${p.id}" ${!canCare ? 'disabled' : ''}>${canCare ? '🐻' : '✅'}</button>
                    <div class="care-info-block">
                        <strong>${escapeHtml(p.name)}</strong> 
                        <span class="level-badge ${levelClass}">${p.level}</span>
                        ${isBirthdayToday(p.birthday) ? '🎂' : ''}
                        <span class="status-badge">${p.type}</span>
                        ${streakText ? `<span class="streak-badge">${streakText}</span>` : ''}
                    </div>
                </div>
                <div class="intimacy-line">
                    <span>💖 親密度 ${intimacy}/100</span>
                    <span class="care-quote" id="quote-${p.id}">💬 ${randomQuote}</span>
                </div>
                <div class="progress-bar-bg"><div class="progress-fill" style="width:${intimacy}%"></div></div>
                <div class="small-text" style="display: flex; justify-content: space-between; align-items: center;">
                    <span>上次照顧：${p.lastCareDate || '尚未照顧'} ｜ 連續 ${streak} 天</span>
                    ${showReminder ? `<span class="reminder-badge">🔔 可以關心我～</span>` : ''}
                </div>
            </div>`;
        }
        container.innerHTML = html;
        document.querySelectorAll('.care-care-btn').forEach(btn => {
            if(!btn.disabled) {
                btn.onclick = (e) => {
                    e.stopPropagation();
                    const pid = btn.getAttribute('data-id');
                    if(pid) carePartner(pid);
                };
            }
        });
    }
    
    function carePartner(pid) {
        const p = partners.find(p => p.id === pid);
        if(!p) return;
        const today = new Date();
        const todayStr = today.toISOString().slice(0,10);
        if(p.lastCareDate === todayStr) { 
            alert('今天已經照顧過囉，明天再來吧');
            return;
        }
        let newStreak = 1;
        if(p.lastCareDate) {
            const lastDate = new Date(p.lastCareDate);
            const diffDays = (today - lastDate) / (1000 * 60 * 60 * 24);
            if (diffDays === 1) newStreak = (p.careStreak || 0) + 1;
            else if (diffDays > 1) newStreak = 1;
            else newStreak = (p.careStreak || 0) + 1;
        } else {
            newStreak = 1;
        }
        let newIntimacy = Math.min(100, (p.intimacy || 0) + 5);
        const wasFull = (p.intimacy === 100);
        const becomeFull = (newIntimacy === 100);
        
        p.intimacy = newIntimacy;
        p.lastCareDate = todayStr;
        p.careStreak = newStreak;
        save();
        
        const randomIndex = Math.floor(Math.random() * QUOTES.length);
        const quoteText = QUOTES[randomIndex];
        const quoteSpan = document.getElementById(`quote-${pid}`);
        if(quoteSpan) {
            quoteSpan.innerHTML = `💬 ${quoteText}`;
            setTimeout(() => {
                if(quoteSpan) quoteSpan.innerHTML = `💬 ${QUOTES[Math.floor(Math.random() * QUOTES.length)]}`;
            }, 4000);
        }
        
        if(becomeFull && !wasFull) {
            for(let i=0; i<12; i++) {
                const conf = document.createElement('div');
                conf.className = 'confetti';
                conf.innerText = ['🎉', '✨', '💖', '🎊'][Math.floor(Math.random()*4)];
                conf.style.left = Math.random() * 80 + 10 + '%';
                conf.style.top = '70%';
                conf.style.fontSize = (Math.random() * 0.8 + 0.8) + 'rem';
                document.body.appendChild(conf);
                setTimeout(() => conf.remove(), 1000);
            }
            const card = document.getElementById(`care-card-${pid}`);
            if(card) {
                card.classList.add('celebrate-animation');
                setTimeout(() => card.classList.remove('celebrate-animation'), 600);
            }
            alert(`🎉 太棒了！${p.name} 的親密度已達 100！你們是最佳戰友 🎉`);
        }
        
        if(newStreak === 3 || newStreak === 7 || newStreak === 14 || newStreak === 30) {
            let msg = '';
            if(newStreak === 3) msg = '連續照顧3天！獲得「萌芽夥伴」';
            else if(newStreak === 7) msg = '連續照顧7天！獲得「溫暖之星」';
            else if(newStreak === 14) msg = '連續照顧14天！獲得「模範夥伴」';
            else if(newStreak === 30) msg = '連續照顧30天！獲得「忠誠戰友」';
            alert(msg);
        }
        
        renderFamily();
        if(activeTab === 'partners') renderPartnerList();
    }
    
    // 以下為原有的 openDetailModal 等函數（保持完整）
    function openDetailModal(id) {
        const p = partners.find(p=>p.id===id);
        if(!p) return;
        const levelOpts = ALL_LEVELS.map(l => `<option ${p.level===l?'selected':''}>${l}</option>`).join('');
        const typeOpts = PARTNER_TYPES.map(t => `<option ${p.type===t?'selected':''}>${t}</option>`).join('');
        const historyHtml = (p.levelHistory||[]).slice().reverse().map(h => `<div class="history-item"><span><strong>${h.level}</strong> ${h.date}</span><span>${h.awardReceived ? '已領獎' : ''}</span></div>`).join('');
        const coursesHtml = (p.courses||[]).map(c => `<div class="course-item">📘 ${c.name} ${c.date}</div>`).join('');
        const levelSelectWithStatus = `<select id="newLevelSel">${ALL_LEVELS.map(l=>`<option>${l}</option>`).join('')}<option value="保留">保留</option><option value="退出">退出</option></select>`;
        const content = `
            <h2>✏️ ${escapeHtml(p.name)}</h2>
            <div class="form-group"><label>姓名</label><input id="editName" value="${escapeHtml(p.name)}"></div>
            <div class="form-group"><label>生日</label><input type="date" id="editBirth" value="${p.birthday||''}"></div>
            <div class="form-group"><label>級別</label><select id="editLevel">${levelOpts}</select></div>
            <div class="form-group"><label>類型</label><select id="editType">${typeOpts}</select></div>
            <div class="form-group"><label>加盟日</label><input type="date" id="editJoin" value="${p.joinDate||''}"></div>
            <div class="form-group"><label>居住地</label><input id="editLoc" value="${escapeHtml(p.location||'')}"></div>
            <hr>
            <h3>升降級紀錄</h3>
            <div id="historyArea">${historyHtml || '<div class="small-text">無</div>'}</div>
            <div class="add-section">${levelSelectWithStatus}<input type="date" id="newDate"><button id="addHistoryBtn" class="btn-sm">新增</button></div>
            <hr>
            <h3>課程紀錄</h3>
            <div id="courseArea">${coursesHtml || '<div class="small-text">無</div>'}</div>
            <div class="add-section"><select id="courseSel"><option value="">選擇課程</option>${PRESET_COURSES.map(c=>`<option>${c}</option>`).join('')}</select><input type="date" id="courseDate"><button id="addCourseBtn" class="btn-sm">新增</button></div>
            <div class="bottom-buttons">
                <button id="saveBtn">儲存</button>
                <button id="delBtn" style="background:#F3DFD4;">刪除</button>
            </div>
        `;
        const modal = document.getElementById('dynamicModal'), modalC = document.getElementById('modalContent');
        modalC.innerHTML = content;
        modal.classList.add('active');
        document.getElementById('saveBtn').onclick = () => {
            const oldType = p.type, newType = document.getElementById('editType').value;
            p.name = document.getElementById('editName').value;
            p.birthday = document.getElementById('editBirth').value;
            const newLv = document.getElementById('editLevel').value;
            if(p.level !== newLv) { p.levelHistory.push({level:newLv, date:new Date().toISOString().slice(0,10), awardReceived:false}); p.level = newLv; }
            p.type = newType;
            p.joinDate = document.getElementById('editJoin').value;
            p.location = document.getElementById('editLoc').value;
            updateEffectiveDate(p, oldType, newType);
            if(!p.effectiveJoinDate) p.effectiveJoinDate = p.joinDate;
            save();
            openDetailModal(p.id);
        };
        document.getElementById('delBtn').onclick = () => { if(confirm('刪除此夥伴？')){ partners=partners.filter(x=>x.id!==p.id); save(); closeModal(); refreshAll(); } };
        document.getElementById('addHistoryBtn').onclick = () => {
            const val = document.getElementById('newLevelSel').value;
            const dt = document.getElementById('newDate').value;
            if(!dt) { alert("請選日期"); return; }
            if(val === '保留' || val === '退出') {
                p.levelHistory.push({level:val, date:dt, awardReceived:false});
                const oldType = p.type, newType = val;
                if(oldType !== newType) { p.type = newType; updateEffectiveDate(p, oldType, newType); }
                save();
                openDetailModal(p.id);
            } else {
                p.levelHistory.push({level:val, date:dt, awardReceived:false});
                p.level = val;
                save();
                openDetailModal(p.id);
            }
        };
        document.getElementById('addCourseBtn').onclick = () => {
            const cn = document.getElementById('courseSel').value;
            const cd = document.getElementById('courseDate').value;
            if(cn && cd) { p.courses.push({name:cn, date:cd}); save(); openDetailModal(p.id); }
        };
    }
    
    function closeModal() { document.getElementById('dynamicModal').classList.remove('active'); }
    function refreshAll() {
        if(activeTab === 'partners') renderPartnerList();
        else if(activeTab === 'gold') renderGoldPage();
        else if(activeTab === 'family') renderFamily();
        // 備份頁面無需刷新內容
    }
    
    function openAddModal() {
        const content = `<h2>新增夥伴</h2>
            <div class="form-group"><label>姓名 *</label><input id="newName"></div>
            <div class="form-group"><label>生日</label><input type="date" id="newBirth"></div>
            <div class="form-group"><label>級別</label><select id="newLevel">${ALL_LEVELS.map(l=>`<option>${l}</option>`).join('')}</select></div>
            <div class="form-group"><label>類型</label><select id="newType">${PARTNER_TYPES.map(t=>`<option>${t}</option>`).join('')}</select></div>
            <div class="form-group"><label>加盟日</label><input type="date" id="newJoin"></div>
            <div class="form-group"><label>居住地</label><input id="newLoc"></div>
            <div class="btn-group"><button id="confirmAdd">建立</button><button id="cancelAdd">取消</button></div>`;
        const modal = document.getElementById('dynamicModal'), modalC = document.getElementById('modalContent');
        modalC.innerHTML = content;
        modal.classList.add('active');
        document.getElementById('confirmAdd').onclick = () => {
            const name = document.getElementById('newName').value.trim();
            if(!name) return;
            const join = document.getElementById('newJoin').value || new Date().toISOString().slice(0,10);
            const newType = document.getElementById('newType').value;
            const newP = {
                id: Date.now()+'-'+Math.random(),
                name, birthday: document.getElementById('newBirth').value,
                level: document.getElementById('newLevel').value,
                type: newType, joinDate: join,
                location: document.getElementById('newLoc').value,
                levelHistory: [], courses: [], intimacy: 0, lastCareDate: null, careStreak: 0, annualData: {}
            };
            newP.levelHistory.push({level:newP.level, date:join, awardReceived:false});
            if(newType === '自用' || newType === '經營') newP.effectiveJoinDate = join;
            else newP.effectiveJoinDate = null;
            partners.push(newP);
            save();
            closeModal();
            refreshAll();
        };
        document.getElementById('cancelAdd').onclick = closeModal;
    }
    
    function switchTab(tab) {
        activeTab = tab;
        document.querySelectorAll('.tab-pane').forEach(p => p.classList.remove('active-pane'));
        document.getElementById(`${tab}Pane`).classList.add('active-pane');
        document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.toggle('active', btn.dataset.tab === tab));
        if(tab === 'partners') renderPartnerList();
        else if(tab === 'gold') renderGoldPage();
        else if(tab === 'family') renderFamily();
        // 備份頁面無需額外渲染
    }
    
    // 備份功能
    function exportBackup() {
        const dataStr = JSON.stringify(partners, null, 2);
        const blob = new Blob([dataStr], {type: 'application/json'});
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = `more_backup_${new Date().toISOString().slice(0,19)}.json`;
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
        alert('備份已匯出！請妥善保存檔案');
    }
    
    function importBackup(file) {
        const reader = new FileReader();
        reader.onload = function(e) {
            try {
                const imported = JSON.parse(e.target.result);
                if (Array.isArray(imported)) {
                    partners = imported.map(p => {
                        if (!p.levelHistory) p.levelHistory = [];
                        if (!p.courses) p.courses = [];
                        if (p.intimacy === undefined) p.intimacy = 0;
                        if (p.lastCareDate === undefined) p.lastCareDate = null;
                        if (p.careStreak === undefined) p.careStreak = 0;
                        if (p.annualData === undefined) p.annualData = {};
                        if (p.effectiveJoinDate === undefined) {
                            p.effectiveJoinDate = (p.type === '自用' || p.type === '經營') ? p.joinDate : null;
                        }
                        p.levelHistory.forEach(h => { if (h.awardReceived === undefined) h.awardReceived = false; });
                        return p;
                    });
                    save();
                    refreshAll();
                    alert(`成功匯入 ${partners.length} 位夥伴資料！`);
                } else {
                    alert('檔案格式錯誤，請確認是正確的備份檔');
                }
            } catch(err) {
                alert('讀取失敗，檔案可能已損毀');
            }
        };
        reader.readAsText(file);
    }
    
    function loadData() {
        const stored = localStorage.getItem('partners_app_data');
        if(stored) {
            partners = JSON.parse(stored);
            partners.forEach(p => {
                if(!p.levelHistory) p.levelHistory = [];
                if(!p.courses) p.courses = [];
                p.levelHistory.forEach(h => { if(h.awardReceived===undefined) h.awardReceived=false; });
                if(!p.annualData) p.annualData = {};
                if(p.intimacy === undefined) p.intimacy = 0;
                if(p.lastCareDate === undefined) p.lastCareDate = null;
                if(p.careStreak === undefined) p.careStreak = 0;
                if(p.effectiveJoinDate === undefined) p.effectiveJoinDate = (p.type==='自用'||p.type==='經營'||p.type==='自用夥伴') ? p.joinDate : null;
                if(p.type === '自用夥伴') p.type = '自用';
            });
            save();
        } else {
            partners = [
                { id:'1', name:'林芳儀', birthday:'1995-03-21', level:'一級', type:'經營', joinDate:'2023-05-10', location:'台北市', intimacy:32, lastCareDate:'2026-04-14', careStreak:2, effectiveJoinDate:'2023-05-10', levelHistory:[{level:'實習',date:'2023-05-10',awardReceived:true},{level:'三級',date:'2023-09-15',awardReceived:false},{level:'一級',date:'2024-02-20',awardReceived:false}], courses:[{name:'領導力',date:'2023-11-12'}], annualData:{} },
                { id:'2', name:'陳冠宇', birthday:'1990-04-15', level:'皇家', type:'自用', joinDate:'2022-11-20', location:'台中市', intimacy:78, lastCareDate:'2026-04-15', careStreak:5, effectiveJoinDate:'2022-11-20', levelHistory:[{level:'實習',date:'2022-11-20',awardReceived:true},{level:'二級',date:'2023-06-01',awardReceived:true},{level:'皇家',date:'2024-01-10',awardReceived:false}], courses:[], annualData:{} },
                { id:'3', name:'張子晴', birthday:'2000-05-10', level:'三級輔導', type:'經營', joinDate:'2024-01-15', location:'高雄市', intimacy:15, lastCareDate:'2026-04-10', careStreak:1, effectiveJoinDate:'2024-01-15', levelHistory:[{level:'實習',date:'2024-01-15',awardReceived:true},{level:'三級輔導',date:'2024-08-01',awardReceived:false}], courses:[], annualData:{} }
            ];
            save();
        }
    }
    
    // 全域事件
    document.querySelector('.modal-close')?.addEventListener('click', closeModal);
    document.getElementById('dynamicModal')?.addEventListener('click', (e) => {
        if(e.target.classList.contains('modal-mask')) closeModal();
    });
    document.getElementById('exportBtn')?.addEventListener('click', exportBackup);
    document.getElementById('importBtn')?.addEventListener('click', () => {
        document.getElementById('fileInput').click();
    });
    document.getElementById('fileInput')?.addEventListener('change', (e) => {
        if(e.target.files.length) importBackup(e.target.files[0]);
        e.target.value = '';
    });
    
    const searchInput = document.querySelector('#searchPartnerInput');
    if(searchInput) searchInput.addEventListener('input', e => { searchKeyword = e.target.value; renderPartnerList(); });
    document.getElementById('clearSearchBtn')?.addEventListener('click', () => { if(searchInput) searchInput.value=''; searchKeyword=''; renderPartnerList(); });
    document.getElementById('globalAddBtn')?.addEventListener('click', openAddModal);
    document.querySelectorAll('.tab-btn').forEach(btn => btn.addEventListener('click', () => switchTab(btn.dataset.tab)));
    window.editMonthly = editMonthly;
    window.claimReward = claimReward;
    
    loadData();
    switchTab('partners');
</script>
</body>
</html>
