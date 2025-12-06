<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>照片歸檔神器 v6.0 (全能整合版)</title>
    <style>
        :root { --primary: #0d6efd; --purple: #6610f2; --success: #198754; --warning: #ffc107; --danger: #dc3545; --bg: #f8f9fa; --overlay-bg: rgba(0,0,0,0.85); }
        body { font-family: "Microsoft JhengHei", "Segoe UI", sans-serif; margin: 0; padding: 20px; background: var(--bg); color: #333; height: 100vh; box-sizing: border-box; display: flex; flex-direction: column; overflow: hidden; }
        
        /* 導航列 */
        .navbar { display: flex; justify-content: space-between; align-items: center; margin-bottom: 15px; background: white; padding: 10px 20px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.05); z-index: 5; }
        .nav-title { margin: 0; font-size: 1.2rem; font-weight: bold; }

        .main-layout { display: grid; grid-template-columns: 1fr 420px; gap: 20px; flex: 1; min-height: 0; position: relative; }
        
        /* 圖片區 */
        .image-panel { background: #222; border-radius: 8px; display: flex; flex-direction: column; align-items: center; justify-content: center; position: relative; overflow: hidden; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        .image-panel img { max-width: 100%; max-height: 100%; object-fit: contain; transition: transform 0.3s ease; }
        .status-overlay { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); display: none; justify-content: center; align-items: center; color: #ff6b6b; font-size: 4rem; font-weight: bold; z-index: 10; flex-direction: column; pointer-events: none; }
        
        /* 側邊欄 */
        .sidebar { background: white; border-radius: 8px; padding: 20px; display: flex; flex-direction: column; gap: 15px; overflow-y: auto; box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
        .section-header { border-bottom: 2px solid #eee; padding-bottom: 5px; margin-bottom: 8px; font-weight: bold; color: #555; font-size: 0.95rem; display: flex; justify-content: space-between; align-items: center; }
        
        /* 工具列 */
        .toolbar { display: flex; gap: 8px; margin-bottom: 5px; }
        .tool-btn { flex: 1; padding: 8px; border: 1px solid #ccc; background: white; border-radius: 6px; cursor: pointer; font-size: 13px; display: flex; align-items: center; justify-content: center; gap: 5px; transition: 0.2s; }
        .tool-btn:hover { background: #f0f0f0; }
        .tool-btn.active { background: #e7f5ff; border-color: var(--primary); color: var(--primary); font-weight: bold; }

        /* 分類按鈕 */
        .btn-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(90px, 1fr)); gap: 8px; }
        .cat-btn, .tag-btn { 
            background: white; border: 1px solid #ccc; padding: 10px 5px; border-radius: 6px; 
            cursor: pointer; font-size: 14px; text-align: center; transition: 0.2s; position: relative;
            display: flex; flex-direction: column; align-items: center; justify-content: center; min-height: 45px; user-select: none;
        }
        .cat-btn:hover, .tag-btn:hover { background: #f8f9fa; border-color: #999; }
        .cat-btn.active { background: var(--primary); color: white; border-color: var(--primary); font-weight: bold; transform: scale(0.98); }
        .tag-btn.active { background: var(--purple); color: white; border-color: var(--purple); font-weight: bold; transform: scale(0.98); }
        .key-badge { position: absolute; top: 2px; right: 2px; background: #333; color: white; font-size: 10px; padding: 2px 5px; border-radius: 4px; opacity: 0.8; font-family: monospace; }
        .cat-btn.active .key-badge, .tag-btn.active .key-badge { background: white; color: #333; }

        /* 命名控制區 (恢復功能) */
        .naming-control { border: 1px solid #eee; padding: 12px; border-radius: 8px; background: #fafafa; }
        .toggle-row { display: flex; align-items: center; justify-content: space-between; margin-bottom: 8px; cursor: pointer; user-select: none; }
        .switch { position: relative; display: inline-block; width: 36px; height: 20px; }
        .switch input { opacity: 0; width: 0; height: 0; }
        .slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: #ccc; transition: .4s; border-radius: 34px; }
        .slider:before { position: absolute; content: ""; height: 14px; width: 14px; left: 3px; bottom: 3px; background-color: white; transition: .4s; border-radius: 50%; }
        input:checked + .slider { background-color: var(--primary); }
        input:checked + .slider:before { transform: translateX(16px); }
        
        .input-wrapper { position: relative; }
        .custom-input { width: 100%; padding: 8px; border: 2px solid #ddd; border-radius: 6px; font-size: 14px; box-sizing: border-box; background: #fff; transition:0.3s; }
        .custom-input:disabled { background: #e9ecef; color: #aaa; cursor: not-allowed; }
        .custom-input:focus { border-color: var(--primary); outline: none; }

        /* 預覽與下載 */
        .preview-box { background: #e9ecef; padding: 12px; border-radius: 6px; text-align: right; font-family: monospace; font-size: 0.95rem; color: #555; margin-top: auto; border: 1px solid #dee2e6; }
        .btn-download { background: #fd7e14; color: white; width: 100%; padding: 15px; font-size: 16px; margin-top: 10px; border: none; border-radius: 6px; cursor: not-allowed; font-weight: bold; opacity: 0.5; transition:0.3s; }
        .btn-download.active { cursor: pointer; opacity: 1; }
        .btn-download.active:hover { background: #e96b02; }

        /* 教學相關 */
        .btn-help { background: var(--purple); color: white; border: none; padding: 8px 15px; border-radius: 6px; cursor: pointer; font-weight: bold; font-size: 14px; }
        .btn-upload { background: var(--success); color: white; border: none; padding: 10px 20px; border-radius: 6px; cursor: pointer; font-weight: bold; font-size: 15px; opacity: 0.5; pointer-events: none; }
        .btn-upload.active { opacity: 1; pointer-events: auto; }

        /* 歡迎與導覽 */
        .tour-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: var(--overlay-bg); z-index: 9999; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; color: white; }
        .welcome-box { background: white; color: #333; padding: 40px; border-radius: 12px; max-width: 500px; box-shadow: 0 20px 50px rgba(0,0,0,0.5); }
        .start-btn { padding: 12px 30px; font-size: 1.1rem; background: var(--primary); color: white; border: none; border-radius: 50px; cursor: pointer; font-weight: bold; margin: 10px; }
        .skip-btn { background: transparent; color: #666; border: 1px solid #ccc; padding: 10px 20px; border-radius: 50px; cursor: pointer; margin: 10px; }
        
        .spotlight { position: relative; z-index: 10000; box-shadow: 0 0 0 9999px var(--overlay-bg); background: white; pointer-events: none; border-radius: 6px; }
        .allow-click { pointer-events: auto !important; cursor: pointer; }
        .tour-tooltip { position: fixed; background: white; color: #333; padding: 20px; border-radius: 10px; width: 300px; z-index: 10003; box-shadow: 0 10px 30px rgba(0,0,0,0.5); display: none; }
        .tour-actions { display: flex; justify-content: flex-end; margin-top: 10px; padding-top: 10px; border-top: 1px solid #eee; }
        .tour-skip-step { font-size: 12px; color: #999; background: none; border: none; cursor: pointer; text-decoration: underline; }

        /* Modal */
        .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); z-index: 2000; justify-content: center; align-items: center; }
        .modal-content { background: white; width: 90%; max-width: 850px; height: 85vh; border-radius: 12px; display: flex; flex-direction: column; overflow: hidden; box-shadow: 0 10px 30px rgba(0,0,0,0.3); }
        .modal-tabs { display: flex; background: #f8f9fa; border-bottom: 1px solid #ddd; }
        .tab-btn { flex: 1; padding: 15px; cursor: pointer; font-weight: bold; color: #666; text-align: center; border-bottom: 3px solid transparent; }
        .tab-btn.active { color: var(--primary); border-bottom-color: var(--primary); background: white; }
        .modal-body { padding: 30px; overflow-y: auto; flex: 1; display: none; }
        .modal-body.active { display: block; }

        /* 設定表格 */
        .settings-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        .settings-col h3 { margin-top: 0; border-bottom: 1px solid #eee; padding-bottom: 10px; color: #555; }
        .settings-table { width: 100%; border-collapse: collapse; }
        .settings-table td { padding: 5px 0; border-bottom: 1px solid #f0f0f0; }
        .settings-input { width: 100%; padding: 6px; border: 1px solid #ddd; border-radius: 4px; box-sizing: border-box; }
        .key-input { width: 40px; text-align: center; text-transform: uppercase; font-weight: bold; }
        .add-btn { width: 100%; padding: 8px; margin-top: 10px; background: #f8f9fa; border: 1px dashed #ccc; cursor: pointer; }
        .save-btn { background: var(--primary); color: white; padding: 10px; border: none; border-radius: 6px; width: 100%; margin-top: 15px; font-weight: bold; cursor: pointer; }

        /* 原理圖解與警告 */
        .bat-diagram { display: flex; gap: 10px; background: #f8f9fa; padding: 15px; border-radius: 8px; border: 1px dashed #ccc; text-align: center; font-size: 13px; }
        .bat-step { flex: 1; } .bat-icon { font-size: 1.8rem; display: block; }
        .win-alert { border: 1px solid #d9d9d9; background: white; margin: 15px 0; box-shadow: 0 2px 5px rgba(0,0,0,0.1); font-family: "Segoe UI", sans-serif; }
        .win-bar { background: #ffcc00; padding: 10px; display: flex; align-items: center; gap: 10px; }
        .win-body { padding: 15px; font-size: 13px; color: #333; }
    </style>
</head>
<body>

<div class="navbar">
    <div class="nav-title">📷 照片歸檔神器 <span style="font-size:0.8em; font-weight:normal;">v6.0 全能版</span></div>
    <div style="display:flex; gap:10px; align-items:center;">
        <button class="btn-help" onclick="openHelpModal('tab1')">❓ 教學與原理</button>
        <label for="folderInput" id="uploadBtn" class="btn-upload"><span>📂 選擇資料夾</span></label>
        <input type="file" id="folderInput" webkitdirectory directory multiple style="display:none;">
    </div>
</div>

<div class="main-layout">
    <div class="image-panel" id="imgPanel">
        <img id="currentImage" src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI4MDAiIGhlaWdodD0iNjAwIiB2aWV3Qm94PSIwIDAgODAwIDYwMCI+CiAgPHJlY3Qgd2lkdGg9IjgwMCIgaGVpZ2h0PSI2MDAiIGZpbGw9IiMzMzMiIC8+CiAgPHRleHQgeD0iNTA1IiB5PSI1MCUiIGRvbWluYW50LWJhc2VsaW5lPSJtaWRkbGUiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGZpbGw9IiM4ODgiIGZvbnQtZmFtaWx5PSJzYW5zLXNlcmlmIiBmb250LXNpemU9IjI0Ij7lronlhajltoPpoIzjgIjmsqHmnInmhuHmoYjvvIk8L3RleHQ+Cjwvc3ZnPg==" alt="Demo">
        <div class="status-overlay" id="trashOverlay"><div>🗑️</div><div style="font-size:1.5rem; color:white;">已丟入回收桶</div></div>
    </div>

    <div class="sidebar" id="sidebar">
        <div class="toolbar">
            <button class="tool-btn" onclick="openSettings()">⚙️ 設定</button>
            <button class="tool-btn" id="lockBtn" onclick="toggleLock()">🔓 鎖定分類</button>
            <button class="tool-btn" onclick="rotateImage()">⟳ 轉向 (R)</button>
        </div>

        <div id="catSection">
            <div class="section-header">📂 主分類 (資料夾)</div>
            <div id="catContainer" class="btn-grid"></div>
        </div>

        <div id="tagSection">
            <div class="section-header">🏷️ 子標籤 (後綴)</div>
            <div id="tagContainer" class="btn-grid"></div>
        </div>

        <div class="naming-control" id="namingSection">
            <div class="section-header" style="border:none; margin-bottom:5px;">✏️ 命名規則</div>
            <label class="toggle-row">
                <span style="font-size:14px; font-weight:bold; color:#555;">自動流水號 (_001)</span>
                <label class="switch">
                    <input type="checkbox" id="autoSeqCheck" checked onchange="updatePreview()">
                    <span class="slider"></span>
                </label>
            </label>
            <div class="input-wrapper">
                <input type="text" id="customInput" class="custom-input" placeholder="輸入自訂名稱..." disabled oninput="validateInput(this)">
            </div>
        </div>

        <div style="margin-top:auto;">
            <div class="preview-box" id="finalPreview">等待操作...</div>
            <button id="downloadBtn" class="btn-download" onclick="exportBat()">⚡ 下載整理執行檔 (.bat)</button>
        </div>
    </div>
</div>

<div id="welcomeOverlay" class="tour-overlay">
    <div class="welcome-box">
        <h1>👋 歡迎使用</h1>
        <p style="color:#666; margin-bottom:30px;">第一次使用嗎？建議花 30 秒完成新手引導，確保操作無誤。</p>
        <div style="display:flex; justify-content:center; gap:10px;">
            <button class="skip-btn" onclick="skipTour()">跳過教學</button>
            <button class="start-btn" onclick="startTour()">🚀 開始新手導引</button>
        </div>
    </div>
</div>

<div id="tourTooltip" class="tour-tooltip">
    <span style="background:#0d6efd; color:white; padding:2px 8px; border-radius:10px; font-size:12px;">Step <span id="tourStepBadge">1</span></span>
    <div id="tourText" style="margin-top:5px; font-weight:bold;">標題</div>
    <div id="tourSubText" style="font-size:13px; color:#666; margin-top:5px;">說明</div>
    <div class="tour-actions"><button class="tour-skip-step" onclick="forceNextStep()">跳過這一步 ➔</button></div>
</div>

<div id="dimmer" style="position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.5); z-index:10001; display:none;"></div>

<div id="helpModal" class="modal-overlay" onclick="closeHelpModal()">
    <div class="modal-content" onclick="event.stopPropagation()">
        <div class="modal-tabs">
            <div class="tab-btn active" onclick="switchTab('tab1')" id="btn-tab1">📖 操作流程</div>
            <div class="tab-btn" onclick="switchTab('tab2')" id="btn-tab2">🧪 原理與安全性</div>
            <button style="margin-left:auto; border:none; background:none; font-size:24px; cursor:pointer; padding:0 20px;" onclick="closeHelpModal()">×</button>
        </div>
        <div id="tab1" class="modal-body active">
            <div class="help-section">
                <div class="help-title">基本操作</div>
                <ul style="line-height:2;">
                    <li><b>步驟 1：</b>點擊右上角綠色按鈕 <b>「📂 選擇資料夾」</b>。</li>
                    <li><b>步驟 2：</b>左手按鍵盤 (1~4, A~D) 分類，右手按 Enter 下一張。</li>
                    <li><b>步驟 3：</b>遇到廢片直接按 <b>Delete</b> 丟棄。</li>
                    <li><b>步驟 4：</b>完成後下載 .bat 檔執行。</li>
                </ul>
            </div>
            <div class="help-section">
                <div class="help-title">進階功能</div>
                <p><b>⚙️ 設定：</b> 可以自己修改分類名稱與快捷鍵。</p>
                <p><b>🔓 鎖定分類：</b> 適合連拍場景，不用每一張都重選主分類。</p>
                <p><b>✏️ 自訂命名：</b> 關閉「自動流水號」開關，即可輸入特殊檔名。</p>
            </div>
        </div>
        <div id="tab2" class="modal-body">
            <div class="help-section">
                <div class="help-title">.bat 檔是什麼？</div>
                <p>它是純文字的「工作清單」，幫您自動建立資料夾、移動檔案。<b>完全不需連網，照片不上傳。</b></p>
                <div class="bat-diagram"><div class="bat-step"><span class="bat-icon">🏗️</span>建資料夾</div><div class="bat-step"><span class="bat-icon">🚚</span>移動改名</div><div class="bat-step"><span class="bat-icon">🗑️</span>廢片回收</div></div>
            </div>
            <div class="help-section">
                <div class="help-title">遇到 Windows 警告？</div>
                <div class="win-alert"><div class="win-bar"><strong>!</strong> 無法開啟這些檔案</div><div class="win-body">C:\Users\...\開始整理.bat</div></div>
                <p>請對檔案按 <b>右鍵</b> ➔ <b>內容</b> ➔ 勾選 <b>「解除鎖定」</b> ➔ 確定。</p>
            </div>
        </div>
    </div>
</div>

<div id="settingsModal" class="modal-overlay" onclick="closeSettings()">
    <div class="modal-content" onclick="event.stopPropagation()">
        <button style="align-self:flex-end; border:none; background:none; font-size:24px; cursor:pointer;" onclick="closeSettings()">×</button>
        <h2 style="margin-top:0;">🛠️ 設定分類與標籤</h2>
        <div class="settings-grid">
            <div class="settings-col">
                <h3>📂 主分類</h3>
                <table class="settings-table"><tbody id="catSettingsBody"></tbody></table>
                <button class="add-btn" onclick="addCatRow()">+ 新增</button>
            </div>
            <div class="settings-col">
                <h3>🏷️ 子標籤</h3>
                <table class="settings-table"><tbody id="tagSettingsBody"></tbody></table>
                <button class="add-btn" onclick="addTagRow()">+ 新增</button>
            </div>
        </div>
        <button class="save-btn" onclick="saveSettings()">💾 儲存設定</button>
    </div>
</div>

<script>
    // --- 核心資料 ---
    let categories = [ { name: "活動", key: "1" }, { name: "會議", key: "2" }, { name: "場勘", key: "3" }, { name: "其他", key: "4" } ];
    let tags = [ { name: "長官", key: "A" }, { name: "大合照", key: "S" }, { name: "特寫", key: "D" } ];
    
    let isDemoMode = true; 
    let isTourActive = false;
    let tourStep = 0;
    
    let demoData = { category: null, tags: new Set(), isDeleted: false, customName: "", isAuto: true };
    let files = [], fileData = [], currentIndex = 0;
    let keyMap = {}; 
    let rotationDeg = 0;
    let isLocked = false;

    // --- DOM ---
    const UI = {
        img: document.getElementById('currentImage'),
        catContainer: document.getElementById('catContainer'),
        tagContainer: document.getElementById('tagContainer'),
        preview: document.getElementById('finalPreview'),
        uploadBtn: document.getElementById('uploadBtn'),
        downloadBtn: document.getElementById('downloadBtn'),
        trashOverlay: document.getElementById('trashOverlay'),
        welcomeOverlay: document.getElementById('welcomeOverlay'),
        dimmer: document.getElementById('dimmer'),
        tourTooltip: document.getElementById('tourTooltip'),
        helpModal: document.getElementById('helpModal'),
        settingsModal: document.getElementById('settingsModal'),
        autoSeqCheck: document.getElementById('autoSeqCheck'),
        customInput: document.getElementById('customInput'),
        lockBtn: document.getElementById('lockBtn')
    };

    // --- 初始化 ---
    initUI();

    function initUI() {
        UI.catContainer.innerHTML = '';
        keyMap = {};
        categories.forEach(c => {
            const btn = document.createElement('div');
            btn.className = 'cat-btn';
            btn.id = `cat_${c.key}`; // For tour
            btn.dataset.val = c.name;
            btn.innerHTML = `${c.name} ${c.key?`<span class="key-badge">${c.key}</span>`:''}`;
            btn.onclick = () => selectCategory(c.name);
            UI.catContainer.appendChild(btn);
            if(c.key) keyMap[c.key.toLowerCase()] = { type: 'cat', val: c.name };
        });

        UI.tagContainer.innerHTML = '';
        tags.forEach(t => {
            const btn = document.createElement('div');
            btn.className = 'tag-btn';
            btn.id = `tag_${t.key}`;
            btn.dataset.val = t.name;
            btn.innerHTML = `${t.name} ${t.key?`<span class="key-badge">${t.key}</span>`:''}`;
            btn.onclick = () => toggleTag(t.name);
            UI.tagContainer.appendChild(btn);
            if(t.key) keyMap[t.key.toLowerCase()] = { type: 'tag', val: t.name };
        });
    }

    // --- 核心邏輯 ---
    function getData() { return isDemoMode ? demoData : fileData[currentIndex]; }

    function selectCategory(name) {
        if (isTourActive && tourStep === 1 && name !== '活動') return; // Tour guard
        let data = getData();
        if(data.isDeleted) { data.isDeleted = false; }
        data.category = name;
        updateUI();
        if(isTourActive && tourStep === 1 && name === '活動') nextTourStep();
    }

    function toggleTag(name) {
        if (isTourActive && tourStep === 2 && name !== '長官') return;
        let data = getData();
        if (data.tags.has(name)) data.tags.delete(name); else data.tags.add(name);
        updateUI();
        if(isTourActive && tourStep === 2 && data.tags.has('長官')) nextTourStep();
    }

    function markDeleted() {
        if (isTourActive && tourStep !== 3) return;
        let data = getData();
        data.isDeleted = !data.isDeleted;
        updateUI();
        if(isTourActive && tourStep === 3 && data.isDeleted) nextTourStep();
    }

    function toggleLock() {
        isLocked = !isLocked;
        UI.lockBtn.classList.toggle('active', isLocked);
        UI.lockBtn.innerHTML = isLocked ? "🔒 已鎖定" : "🔓 鎖定分類";
    }

    function rotateImage() {
        rotationDeg = (rotationDeg + 90) % 360;
        UI.img.style.transform = `rotate(${rotationDeg}deg)`;
    }

    function validateInput(input) {
        let val = input.value.replace(/[\\/:*?"<>|]/g, ''); // 移除 Windows 非法字元
        input.value = val;
        let data = getData();
        data.customName = val;
        updateUI();
    }

    function updateUI() {
        let data = getData();
        
        // 刪除遮罩
        UI.trashOverlay.style.display = data.isDeleted ? 'flex' : 'none';
        
        // 按鈕狀態
        document.querySelectorAll('.cat-btn').forEach(b => b.classList.toggle('active', !data.isDeleted && b.dataset.val === data.category));
        document.querySelectorAll('.tag-btn').forEach(b => b.classList.toggle('active', data.tags.has(b.dataset.val)));

        // 命名控制項狀態回填
        // 注意：如果是 Demo 模式，只用簡單邏輯；如果是真實模式，要讀取 data.isAuto
        if (!isDemoMode) {
            UI.autoSeqCheck.checked = (data.isAuto !== false); // 預設 true
            UI.customInput.value = data.customName || "";
        }
        // 控制輸入框啟用/禁用
        UI.customInput.disabled = UI.autoSeqCheck.checked;
        if (!UI.autoSeqCheck.checked) { 
            // 存回 data
            data.isAuto = false;
            data.customName = UI.customInput.value;
        } else {
            data.isAuto = true;
        }

        // 預覽文字
        if (data.isDeleted) {
            UI.preview.textContent = "🗑️ 將移至回收桶";
            UI.preview.style.color = "#dc3545";
        } else if (!data.category) {
            UI.preview.textContent = "請選擇主分類...";
            UI.preview.style.color = "#666";
        } else {
            let parts = [data.category];
            tags.forEach(t => { if(data.tags.has(t.name)) parts.push(t.name); });
            
            // 檔名邏輯
            let fileName = "";
            if (data.isAuto !== false) { // Auto Seq
                fileName = `${parts.join('_')}_001.jpg`;
            } else { // Custom
                let customPart = data.customName || "名稱";
                fileName = `${parts.join('_')}_${customPart}.jpg`;
            }
            UI.preview.textContent = `存檔為: ${data.category}\\${fileName}`;
            UI.preview.style.color = "#333";
        }
    }
    
    // UI觸發的 updatePreview (給 checkbox 用)
    function updatePreview() { updateUI(); }

    // --- 鍵盤監聽 ---
    document.addEventListener('keydown', (e) => {
        if (UI.welcomeOverlay.style.display !== 'none') return;
        if (UI.helpModal.style.display === 'flex' || UI.settingsModal.style.display === 'flex') return;
        if (document.activeElement === UI.customInput) { 
            if(e.key === "Enter") nextImage(); 
            return; 
        }

        const key = e.key.toLowerCase();
        if (key === 'delete') markDeleted();
        else if (key === 'r') rotateImage();
        else if (key === 'enter' && !isDemoMode && !isTourActive) nextImage();
        else if (key === 'arrowleft' && !isDemoMode && !isTourActive) prevImage();
        else if (key === 'arrowright' && !isDemoMode && !isTourActive) nextImage();
        else if (keyMap[key]) {
            const act = keyMap[key];
            if (act.type === 'cat') selectCategory(act.val);
            if (act.type === 'tag') toggleTag(act.val);
            // Visual feedback
            const btn = document.getElementById(`${act.type}_${key.toUpperCase()}`);
            if(btn) { btn.style.transform = "scale(0.95)"; setTimeout(()=>btn.style.transform="scale(1)", 100); }
        }
    });

    // --- 導覽流程 ---
    function skipTour() { UI.welcomeOverlay.style.display = 'none'; endDemoMode(); }
    function startTour() {
        UI.welcomeOverlay.style.display = 'none';
        isTourActive = true;
        document.body.classList.add('tour-active');
        UI.dimmer.style.display = 'block';
        tourStep = 1; showTourStep(1);
    }
    function showTourStep(step) {
        document.querySelectorAll('.spotlight').forEach(el => { el.classList.remove('spotlight'); el.classList.remove('allow-click'); });
        const tooltip = UI.tourTooltip;
        tooltip.style.display = 'block';
        
        let targetId = '';
        if(step===1) { setupTip(1, "選擇主分類", "請按鍵盤 '1' 選擇活動", 'cat_1', 'right'); }
        else if(step===2) { setupTip(2, "加上子標籤", "請按鍵盤 'A' 加上長官", 'tag_A', 'right'); }
        else if(step===3) { setupTip(3, "刪除廢片", "按 'Delete' 鍵丟棄照片", 'imgPanel', 'center'); }
        else if(step===4) {
            UI.dimmer.style.display = 'none'; tooltip.style.display = 'none';
            document.body.classList.remove('tour-active'); isTourActive = false;
            alert("🎉 練習結束！功能全解鎖。"); endDemoMode();
        }
    }
    function setupTip(num, title, desc, targetId, pos) {
        document.getElementById('tourStepBadge').innerText = num;
        document.getElementById('tourText').innerText = title;
        document.getElementById('tourSubText').innerText = desc;
        let el = document.getElementById(targetId);
        if(el) {
            el.classList.add('spotlight'); el.classList.add('allow-click');
            let rect = el.getBoundingClientRect();
            if(pos==='right') { UI.tourTooltip.style.top = rect.top+"px"; UI.tourTooltip.style.left = (rect.left - 320)+"px"; }
            else { UI.tourTooltip.style.top = "50%"; UI.tourTooltip.style.left = "50%"; UI.tourTooltip.style.transform = "translate(-50%, -50%)"; }
        }
    }
    function nextTourStep() { setTimeout(() => { tourStep++; showTourStep(tourStep); }, 500); }
    function forceNextStep() { nextTourStep(); }
    function endDemoMode() {
        isDemoMode = false;
        demoData = { category: null, tags: new Set(), isDeleted: false };
        updateUI();
        UI.uploadBtn.classList.add('active'); 
        UI.downloadBtn.classList.add('active'); 
        document.getElementById('currentImage').src = "";
    }

    // --- 真實檔案 ---
    document.getElementById('folderInput').addEventListener('change', function(e) {
        if(isDemoMode) return;
        files = Array.from(e.target.files).filter(f => f.type.startsWith('image/'));
        if (!files.length) { alert("沒有圖片！"); return; }
        // Init real data
        fileData = files.map(f => ({ originalName: f.name, category: null, tags: new Set(), isDeleted: false, isAuto: true, customName: "" }));
        const collator = new Intl.Collator(undefined, {numeric: true, sensitivity: 'base'});
        files.sort((a, b) => collator.compare(a.name, b.name));
        fileData.sort((a, b) => collator.compare(a.originalName, b.originalName));
        currentIndex = 0; loadRealImage();
    });
    function loadRealImage() {
        if (!files.length) return;
        const img = document.getElementById('currentImage');
        if (img.src) URL.revokeObjectURL(img.src);
        img.src = URL.createObjectURL(files[currentIndex]);
        img.style.transform = "rotate(0deg)"; rotationDeg = 0;
        updateUI();
    }
    function nextImage() {
        // 鎖定邏輯
        if(currentIndex < files.length - 1) {
            let prevCat = fileData[currentIndex].category;
            currentIndex++;
            if(isLocked && prevCat && !fileData[currentIndex].category) {
                fileData[currentIndex].category = prevCat; // Apply Lock
            }
            loadRealImage();
        } else alert("🎉 全部完成！");
    }
    function prevImage() { if(currentIndex > 0) { currentIndex--; loadRealImage(); } }

    // --- Modal 與 設定 ---
    function openHelpModal(tab) { UI.helpModal.style.display = 'flex'; switchTab(tab); }
    function closeHelpModal() { UI.helpModal.style.display = 'none'; }
    function switchTab(t) {
        document.querySelectorAll('.modal-body').forEach(e=>e.classList.remove('active'));
        document.querySelectorAll('.tab-btn').forEach(e=>e.classList.remove('active'));
        document.getElementById(t).classList.add('active'); document.getElementById('btn-'+t).classList.add('active');
    }
    function openSettings() {
        // Render settings table
        const cBody = document.getElementById('catSettingsBody'); cBody.innerHTML = '';
        categories.forEach((c,i) => cBody.innerHTML += `<tr><td><input class="settings-input" value="${c.name}" onchange="categories[${i}].name=this.value"></td><td><input class="settings-input key-input" value="${c.key}" onchange="categories[${i}].key=this.value" maxlength="1"></td><td onclick="categories.splice(${i},1);openSettings()" style="color:red;cursor:pointer">✖</td></tr>`);
        const tBody = document.getElementById('tagSettingsBody'); tBody.innerHTML = '';
        tags.forEach((t,i) => tBody.innerHTML += `<tr><td><input class="settings-input" value="${t.name}" onchange="tags[${i}].name=this.value"></td><td><input class="settings-input key-input" value="${t.key}" onchange="tags[${i}].key=this.value" maxlength="1"></td><td onclick="tags.splice(${i},1);openSettings()" style="color:red;cursor:pointer">✖</td></tr>`);
        UI.settingsModal.style.display = 'flex';
    }
    function closeSettings() { UI.settingsModal.style.display = 'none'; }
    function saveSettings() {
        initUI(); // Re-render buttons
        closeSettings();
        updateUI(); // Refresh view
    }
    function addCatRow() { categories.push({name:"", key:""}); openSettings(); }
    function addTagRow() { tags.push({name:"", key:""}); openSettings(); }

    // --- Export BAT ---
    function exportBat() {
        if(isDemoMode) { alert("請先載入真實照片！"); return; }
        if(!files.length) return;
        let bat = "@echo off\r\nchcp 65001 >nul\r\necho 正在整理照片...\r\n\r\n";
        
        let folders = new Set(); folders.add("_TRASH");
        fileData.forEach(d => { if(d.category && !d.isDeleted) folders.add(d.category); });
        folders.forEach(f => bat += `if not exist "${f}" md "${f}"\r\n`);
        bat += "\r\n";

        let counts = {};
        fileData.forEach(d => {
            if(d.isDeleted) { bat += `move "${d.originalName}" "_TRASH\\${d.originalName}"\r\n`; return; }
            if(!d.category) return;
            
            // 流水號計算：同分類共用
            if(!counts[d.category]) counts[d.category]=0;
            counts[d.category]++;
            let seq = String(counts[d.category]).padStart(3,'0');
            
            let parts = [d.category];
            tags.forEach(t => { if(d.tags.has(t.name)) parts.push(t.name); });
            
            let ext = d.originalName.split('.').pop();
            let finalName = "";
            
            if(d.isAuto !== false) { // Auto
                finalName = `${parts.join('_')}_${seq}.${ext}`;
            } else { // Custom
                let cust = d.customName || "名稱";
                finalName = `${parts.join('_')}_${cust}.${ext}`;
            }
            bat += `move "${d.originalName}" "${d.category}\\${finalName}"\r\n`;
        });
        bat += "\r\necho 整理完成！\r\npause";
        
        const blob = new Blob([bat], {type: 'text/plain;charset=utf-8'});
        const link = document.createElement("a");
        link.href = URL.createObjectURL(blob);
        link.download = "開始整理.bat";
        link.click();
    }
</script>
</body>
</html>
