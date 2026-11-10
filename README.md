<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bảng Tuần Hoàn Các Nguyên Tố Hóa Học - Index2</title>
  <style>
    :root {
      --bg-color: #0a1f2e;
      --card-bg: rgba(255, 255, 255, 0.05);
      --text-main: #e2e8f0;
      --text-muted: #94a3b8;
      
      /* Colors */
      --block-s: #f43f5e;
      --block-p: #eab308;
      --block-d: #3b82f6;
      --block-f: #22c55e;
      --block-placeholder: #64748b;

      /* Chemical Properties Colors */
      --cat-alkali: #ff4d4d;
      --cat-alkaline-earth: #ffa64d;
      --cat-transition: #4da6ff;
      --cat-post-transition: #4dffff;
      --cat-metalloid: #70db70;
      --cat-nonmetal: #ffff4d;
      --cat-halogen: #ff99e6;
      --cat-noble: #b366ff;
      --cat-lanthanide: #ff66b3;
      --cat-actinide: #00e699;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-main);
      font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
      min-height: 100vh;
      padding: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    header {
      text-align: center;
      margin-bottom: 20px;
    }

    h1 {
      font-size: 2rem;
      text-transform: uppercase;
      letter-spacing: 2px;
      color: #38bdf8;
      text-shadow: 0 0 10px rgba(56, 189, 248, 0.4);
      margin-bottom: 6px;
    }

    .subtitle {
      color: var(--text-muted);
      font-size: 0.95rem;
    }

    /* Controls Panel */
    .controls-panel {
      width: 100%;
      max-width: 1400px;
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: 12px;
      padding: 16px;
      margin-bottom: 20px;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .top-controls {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      justify-content: space-between;
      align-items: center;
    }

    .search-box input {
      background: rgba(15, 23, 42, 0.8);
      border: 1px solid #334155;
      color: #fff;
      padding: 8px 16px;
      border-radius: 8px;
      outline: none;
      font-size: 0.9rem;
      width: 260px;
      transition: all 0.3s;
    }

    .search-box input:focus {
      border-color: #38bdf8;
      box-shadow: 0 0 8px rgba(56, 189, 248, 0.3);
    }

    /* Tabs */
    .mode-tabs {
      display: flex;
      gap: 8px;
      background: rgba(0, 0, 0, 0.2);
      padding: 4px;
      border-radius: 8px;
    }

    .tab-btn {
      background: none;
      border: none;
      color: var(--text-muted);
      padding: 6px 14px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 0.85rem;
      font-weight: 600;
      transition: all 0.2s;
    }

    .tab-btn.active {
      background: #38bdf8;
      color: #0f172a;
    }

    /* Filters Bar */
    .filter-bar {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      align-items: center;
      padding-top: 8px;
      border-top: 1px dashed rgba(255, 255, 255, 0.1);
    }

    .filter-btn {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.15);
      color: var(--text-main);
      padding: 6px 12px;
      border-radius: 6px;
      font-size: 0.8rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.2s;
    }

    .filter-btn:hover, .filter-btn.active {
      background: rgba(56, 189, 248, 0.2);
      border-color: #38bdf8;
      color: #fff;
    }

    .btn-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
    }

    .sub-filter-bar {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      align-items: center;
      padding: 8px 12px;
      background: rgba(0, 0, 0, 0.25);
      border-radius: 8px;
      margin-top: 4px;
      width: 100%;
    }

    .sub-title {
      font-size: 0.75rem;
      color: var(--text-muted);
      margin-right: 4px;
    }

    /* Periodic Table Grid */
    .table-container {
      width: 100%;
      max-width: 1400px;
      overflow-x: auto;
      padding-bottom: 10px;
    }

    .table-layout {
      min-width: 1150px;
      display: grid;
      grid-template-columns: 50px minmax(1100px, 1fr);
      gap: 6px;
    }

    .axis-corner {
      grid-column: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-muted);
      font-size: 0.7rem;
      font-weight: 700;
    }

    .group-axis {
      grid-column: 2;
      display: grid;
      grid-template-columns: repeat(18, minmax(60px, 1fr));
      gap: 6px;
      margin-bottom: 2px;
    }

    .axis-label {
      display: flex;
      align-items: center;
      justify-content: center;
      color: #38bdf8;
      background: rgba(56, 189, 248, 0.10);
      border: 1px solid rgba(56, 189, 248, 0.25);
      border-radius: 6px;
      font-size: 0.8rem;
      font-weight: 700;
      min-height: 30px;
      text-align: center;
    }

    .group-axis .axis-label {
      min-height: 34px;
      padding: 2px;
      font-size: 0.78rem;
    }

    .table-row-layout {
      grid-column: 1 / 3;
      display: grid;
      grid-template-columns: 50px minmax(1100px, 1fr);
      gap: 6px;
      align-items: stretch;
    }

    .period-axis-wrap {
      display: grid;
      grid-template-columns: 18px 26px;
      gap: 4px;
    }

    .period-axis-title {
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-muted);
      font-size: 0.65rem;
      font-weight: 700;
      writing-mode: vertical-rl;
      transform: rotate(180deg);
    }

    .period-axis {
      display: grid;
      grid-template-rows: repeat(7, 60px) 20px 60px 60px;
      gap: 6px;
    }

    .period-axis .axis-label {
      min-height: 0;
    }

    .periodic-table {
      display: grid;
      grid-template-columns: repeat(18, minmax(60px, 1fr));
      grid-template-rows: repeat(7, 60px) 20px 60px 60px;
      gap: 6px;
      min-width: 1100px;
    }

    .element-card {
      background: var(--card-bg);
      border-radius: 6px;
      padding: 4px;
      aspect-ratio: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      cursor: pointer;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.2s ease;
      user-select: none;
    }

    .element-card:hover {
      transform: scale(1.15);
      z-index: 10;
      box-shadow: 0 0 15px currentColor;
    }

    .element-card.dimmed {
      opacity: 0.12;
      filter: grayscale(90%);
    }

    /* Color styles according to Electron Block */
    .mode-electron .block-s { border-color: var(--block-s); color: var(--block-s); }
    .mode-electron .block-p { border-color: var(--block-p); color: var(--block-p); }
    .mode-electron .block-d { border-color: var(--block-d); color: var(--block-d); }
    .mode-electron .block-f { border-color: var(--block-f); color: var(--block-f); }

    /* Color styles according to Chemical Property */
    .mode-property .cat-alkali { border-color: var(--cat-alkali); color: var(--cat-alkali); }
    .mode-property .cat-alkaline-earth { border-color: var(--cat-alkaline-earth); color: var(--cat-alkaline-earth); }
    .mode-property .cat-transition { border-color: var(--cat-transition); color: var(--cat-transition); }
    .mode-property .cat-post-transition { border-color: var(--cat-post-transition); color: var(--cat-post-transition); }
    .mode-property .cat-metalloid { border-color: var(--cat-metalloid); color: var(--cat-metalloid); }
    .mode-property .cat-nonmetal { border-color: var(--cat-nonmetal); color: var(--cat-nonmetal); }
    .mode-property .cat-halogen { border-color: var(--cat-halogen); color: var(--cat-halogen); }
    .mode-property .cat-noble { border-color: var(--cat-noble); color: var(--cat-noble); }
    .mode-property .cat-lanthanide { border-color: var(--cat-lanthanide); color: var(--cat-lanthanide); }
    .mode-property .cat-actinide { border-color: var(--cat-actinide); color: var(--cat-actinide); }

    /* Color styles according to Group A/B */
    .mode-group .group-A { border-color: #38bdf8; color: #38bdf8; }
    .mode-group .group-B { border-color: #f43f5e; color: #f43f5e; }

    .element-card .symbol { color: #fff; font-size: 1.1rem; font-weight: 700; text-align: center; }
    .element-card .number { font-size: 0.65rem; font-weight: 600; }
    .element-card .name { font-size: 0.55rem; text-align: center; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; color: var(--text-muted); }

    .placeholder-card {
      border: 1px dashed var(--block-placeholder);
      color: var(--block-placeholder);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 1.1rem;
    }

    .spacer {
      grid-column: span 18;
      height: 20px;
    }

    /* Modal Layout */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      backdrop-filter: blur(6px);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 100;
    }

    .modal-overlay.active {
      display: flex;
    }

    .modal-content {
      background: #0f172a;
      border: 2px solid #38bdf8;
      border-radius: 16px;
      padding: 24px;
      max-width: 820px;
      width: 92%;
      box-shadow: 0 0 35px rgba(56, 189, 248, 0.3);
      position: relative;
    }

    .close-btn {
      position: absolute;
      top: 12px;
      right: 16px;
      background: none;
      border: none;
      color: var(--text-muted);
      font-size: 1.6rem;
      cursor: pointer;
    }

    .modal-grid {
      display: grid;
      grid-template-columns: 1.1fr 1fr;
      gap: 20px;
      margin-top: 10px;
    }

    @media (max-width: 768px) {
      .modal-grid {
        grid-template-columns: 1fr;
      }
    }

    .modal-left {
      display: flex;
      flex-direction: column;
      gap: 12px;
      border-right: 1px solid rgba(255, 255, 255, 0.1);
      padding-right: 20px;
    }

    .config-box {
      background: rgba(255, 255, 255, 0.03);
      padding: 12px;
      border-radius: 8px;
      border-left: 3px solid #38bdf8;
    }

    .config-box span {
      font-size: 0.75rem;
      color: var(--text-muted);
      display: block;
      margin-bottom: 4px;
    }

    .config-box strong {
      font-size: 0.95rem;
      color: #38bdf8;
      word-break: break-all;
    }

    /* Fixed Responsive Atom Container */
    .atom-container {
      background: rgba(0, 0, 0, 0.3);
      border-radius: 12px;
      padding: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 1px solid rgba(255, 255, 255, 0.05);
      position: relative;
      min-height: 220px;
    }

    .atom-title {
      font-size: 0.75rem;
      color: var(--text-muted);
      margin-bottom: 6px;
    }

    .atom-stage {
      width: 200px;
      height: 200px;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .nucleus {
      width: 26px;
      height: 26px;
      border-radius: 50%;
      background: radial-gradient(circle, #f43f5e 0%, #9f1239 100%);
      box-shadow: 0 0 10px #f43f5e;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.65rem;
      font-weight: bold;
      color: #fff;
      z-index: 10;
      position: absolute;
    }

    .orbit {
      position: absolute;
      top: 50%;
      left: 50%;
      border: 1px dashed rgba(56, 189, 248, 0.35);
      border-radius: 50%;
      transform: translate(-50%, -50%);
      animation: spin 10s linear infinite;
    }

    .electron {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 7px;
      height: 7px;
      background: #38bdf8;
      border-radius: 50%;
      box-shadow: 0 0 6px #38bdf8;
    }

    @keyframes spin {
      from { transform: translate(-50%, -50%) rotate(0deg); }
      to { transform: translate(-50%, -50%) rotate(360deg); }
    }

    /* Right Stats */
    .modal-right {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .element-header {
      display: flex;
      align-items: center;
      gap: 15px;
      margin-bottom: 5px;
    }

    .element-badge {
      width: 60px;
      height: 60px;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 2px solid currentColor;
      background: rgba(255, 255, 255, 0.02);
    }

    .element-badge .b-symbol { font-size: 1.5rem; font-weight: bold; color: #fff; }
    .element-badge .b-number { font-size: 0.7rem; }

    .header-text h2 { font-size: 1.3rem; color: #fff; }
    .header-text p { font-size: 0.85rem; color: var(--text-muted); }

    .info-list {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .info-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(255, 255, 255, 0.03);
      padding: 8px 12px;
      border-radius: 6px;
      font-size: 0.85rem;
    }

    .info-item .label { color: var(--text-muted); }
    .info-item .val { font-weight: 600; color: #e2e8f0; }


    .formula-section {
      margin-top: 10px;
      padding: 12px;
      border: 1px solid rgba(56, 189, 248, 0.25);
      border-radius: 10px;
      background: rgba(56, 189, 248, 0.06);
    }
    .formula-title {
      color: #38bdf8;
      font-size: 0.8rem;
      font-weight: 700;
      margin-bottom: 9px;
      letter-spacing: .4px;
    }
    .formula-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 7px;
    }
    .formula-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      padding: 8px 10px;
      background: rgba(255,255,255,.035);
      border-radius: 6px;
      font-size: .82rem;
    }
    .formula-item .label { color: var(--text-muted); }
    .formula-item .val { color: #7dd3fc; font-weight: 700; text-align: right; }
    @media (max-width: 768px) {
      .modal-content { max-height: 92vh; overflow-y: auto; padding: 18px; }
      .modal-left { border-right: none; border-bottom: 1px solid rgba(255,255,255,.1); padding: 0 0 15px; }
    }

    .property-tag {
      padding: 2px 8px;
      border-radius: 4px;
      font-size: 0.8rem;
      font-weight: 600;
    }
  </style>
</head>
<body class="mode-property">

  <header>
    <h1>Bảng Tuần Hoàn Các Nguyên Tố Hóa Học</h1>
    <p class="subtitle">Phân loại linh hoạt theo Tính chất hóa học, Cấu hình Electron và Nhóm A/B</p>
  </header>

  <div class="controls-panel">
    <div class="top-controls">
      <div class="search-box">
        <input type="text" id="searchInput" placeholder="Tìm theo tên, ký hiệu, số hiệu Z...">
      </div>

      <div class="mode-tabs">
        <button class="tab-btn active" onclick="switchMode('property')">Theo Tính chất Hóa học</button>
        <button class="tab-btn" onclick="switchMode('electron')">Theo Cấu hình Electron</button>
        <button class="tab-btn" onclick="switchMode('group')">Theo Nhóm A & B</button>
      </div>
    </div>

    <!-- Filters Bar Dynamic -->
    <div class="filter-bar" id="primaryFilterBar"></div>
    <div id="subFilterContainer"></div>
  </div>

  <div class="table-container">
    <div class="table-layout">
      <div class="axis-corner">NHÓM</div>
      <div class="group-axis" id="groupAxis"></div>
      <div class="table-row-layout">
        <div class="period-axis-wrap">
          <div class="period-axis-title">CHU KỲ</div>
          <div class="period-axis" id="periodAxis"></div>
        </div>
        <div class="periodic-table" id="periodicTable"></div>
      </div>
    </div>
  </div>

  <!-- Modal Chi Tiết -->
  <div class="modal-overlay" id="modalOverlay">
    <div class="modal-content">
      <button class="close-btn" onclick="closeModal()">&times;</button>
      
      <div class="modal-grid">
        <!-- BÊN TRÁI -->
        <div class="modal-left">
          <div class="config-box">
            <span>CẤU HÌNH ELECTRON</span>
            <strong id="mConfig">1s² 2s² 2p⁶ 3s¹</strong>
          </div>

          <div class="atom-container">
            <div class="atom-title">MÔ HÌNH CẤU TẠO NGUYÊN TỬ</div>
            <div class="atom-stage" id="atomStage"></div>
          </div>
        </div>

        <!-- BÊN PHẢI -->
        <div class="modal-right">
          <div class="element-header">
            <div class="element-badge" id="mBadge">
              <span class="b-number" id="mNumber">11</span>
              <span class="b-symbol" id="mSymbol">Na</span>
            </div>
            <div class="header-text">
              <h2 id="mName">Natri</h2>
              <p id="mSubText">Khối s | Chu kỳ 3 - Nhóm IA</p>
            </div>
          </div>

          <div class="info-list">
            <div class="info-item">
              <span class="label">Số khối (Nguyên tử khối):</span>
              <span class="val" id="mMass">22.990 amu</span>
            </div>
            <div class="info-item">
              <span class="label">Hóa trị phổ biến:</span>
              <span class="val" id="mValence">I</span>
            </div>
            <div class="info-item">
              <span class="label">Độ âm điện:</span>
              <span class="val" id="mElectroneg">0.93</span>
            </div>
            <div class="info-item">
              <span class="label">Bán kính nguyên tử:</span>
              <span class="val" id="mRadius">186 pm</span>
            </div>
            <div class="info-item">
              <span class="label">Tính chất hóa học:</span>
              <span class="val" id="mProperty">Kim loại kiềm</span>
            </div>
          </div>

          <div class="formula-section">
            <div class="formula-title">CÔNG THỨC HÓA HỌC ĐẶC TRƯNG</div>
            <div class="formula-grid">
              <div class="formula-item">
                <span class="label">Oxide cao nhất:</span>
                <span class="val" id="mOxide">—</span>
              </div>
              <div class="formula-item">
                <span class="label">Hydroxide tương ứng:</span>
                <span class="val" id="mHydroxide">—</span>
              </div>
              <div class="formula-item">
                <span class="label">Hợp chất với hydrogen:</span>
                <span class="val" id="mHydrogen">—</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Dữ liệu chuẩn 118 Nguyên Tố Hóa Học
    const rawElements = [
  { z: 1, symbol: 'H', name: 'Hydrogen', mass: '1.008', block: 's', row: 1, col: 1, config: '1s¹', shells: [1], valence: 'I', electroneg: '2.20', radius: '37 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 2, symbol: 'He', name: 'Helium', mass: '4.0026', block: 's', row: 1, col: 18, config: '1s²', shells: [2], valence: '0', electroneg: '-', radius: '31 pm', propType: 'khikiem', propText: 'Noble Gas' },
  
  { z: 3, symbol: 'Li', name: 'Lithium', mass: '6.94', block: 's', row: 2, col: 1, config: '1s² 2s¹', shells: [2, 1], valence: 'I', electroneg: '0.98', radius: '152 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 4, symbol: 'Be', name: 'Beryllium', mass: '9.0122', block: 's', row: 2, col: 2, config: '1s² 2s²', shells: [2, 2], valence: 'II', electroneg: '1.57', radius: '112 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },
  { z: 5, symbol: 'B', name: 'Boron', mass: '10.81', block: 'p', row: 2, col: 13, config: '1s² 2s² 2p¹', shells: [2, 3], valence: 'III', electroneg: '2.04', radius: '85 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 6, symbol: 'C', name: 'Carbon', mass: '12.011', block: 'p', row: 2, col: 14, config: '1s² 2s² 2p²', shells: [2, 4], valence: 'IV, II', electroneg: '2.55', radius: '77 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 7, symbol: 'N', name: 'Nitrogen', mass: '14.007', block: 'p', row: 2, col: 15, config: '1s² 2s² 2p³', shells: [2, 5], valence: 'III, V, II, IV', electroneg: '3.04', radius: '75 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 8, symbol: 'O', name: 'Oxygen', mass: '15.999', block: 'p', row: 2, col: 16, config: '1s² 2s² 2p⁴', shells: [2, 6], valence: 'II', electroneg: '3.44', radius: '73 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 9, symbol: 'F', name: 'Fluorine', mass: '18.998', block: 'p', row: 2, col: 17, config: '1s² 2s² 2p⁵', shells: [2, 7], valence: 'I', electroneg: '3.98', radius: '71 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 10, symbol: 'Ne', name: 'Neon', mass: '20.180', block: 'p', row: 2, col: 18, config: '1s² 2s² 2p⁶', shells: [2, 8], valence: '0', electroneg: '-', radius: '69 pm', propType: 'khikiem', propText: 'Noble Gas' },

  { z: 11, symbol: 'Na', name: 'Sodium', mass: '22.990', block: 's', row: 3, col: 1, config: '[Ne] 3s¹', shells: [2, 8, 1], valence: 'I', electroneg: '0.93', radius: '186 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 12, symbol: 'Mg', name: 'Magnesium', mass: '24.305', block: 's', row: 3, col: 2, config: '[Ne] 3s²', shells: [2, 8, 2], valence: 'II', electroneg: '1.31', radius: '160 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },
  { z: 13, symbol: 'Al', name: 'Aluminium', mass: '26.982', block: 'p', row: 3, col: 13, config: '[Ne] 3s² 3p¹', shells: [2, 8, 3], valence: 'III', electroneg: '1.61', radius: '143 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 14, symbol: 'Si', name: 'Silicon', mass: '28.085', block: 'p', row: 3, col: 14, config: '[Ne] 3s² 3p²', shells: [2, 8, 4], valence: 'IV', electroneg: '1.90', radius: '118 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 15, symbol: 'P', name: 'Phosphorus', mass: '30.974', block: 'p', row: 3, col: 15, config: '[Ne] 3s² 3p³', shells: [2, 8, 5], valence: 'III, V', electroneg: '2.19', radius: '110 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 16, symbol: 'S', name: 'Sulfur', mass: '32.06', block: 'p', row: 3, col: 16, config: '[Ne] 3s² 3p⁴', shells: [2, 8, 6], valence: 'II, IV, VI', electroneg: '2.58', radius: '103 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 17, symbol: 'Cl', name: 'Chlorine', mass: '35.45', block: 'p', row: 3, col: 17, config: '[Ne] 3s² 3p⁵', shells: [2, 8, 7], valence: 'I, III, V, VII', electroneg: '3.16', radius: '99 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 18, symbol: 'Ar', name: 'Argon', mass: '39.948', block: 'p', row: 3, col: 18, config: '[Ne] 3s² 3p⁶', shells: [2, 8, 8], valence: '0', electroneg: '-', radius: '97 pm', propType: 'khikiem', propText: 'Noble Gas' },

  { z: 19, symbol: 'K', name: 'Potassium', mass: '39.098', block: 's', row: 4, col: 1, config: '[Ar] 4s¹', shells: [2, 8, 8, 1], valence: 'I', electroneg: '0.82', radius: '227 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 20, symbol: 'Ca', name: 'Calcium', mass: '40.078', block: 's', row: 4, col: 2, config: '[Ar] 4s²', shells: [2, 8, 8, 2], valence: 'II', electroneg: '1.00', radius: '197 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },
  { z: 21, symbol: 'Sc', name: 'Scandium', mass: '44.956', block: 'd', row: 4, col: 3, config: '[Ar] 3d¹ 4s²', shells: [2, 8, 9, 2], valence: 'III', electroneg: '1.36', radius: '162 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 22, symbol: 'Ti', name: 'Titanium', mass: '47.867', block: 'd', row: 4, col: 4, config: '[Ar] 3d² 4s²', shells: [2, 8, 10, 2], valence: 'IV, III', electroneg: '1.54', radius: '147 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 23, symbol: 'V', name: 'Vanadium', mass: '50.942', block: 'd', row: 4, col: 5, config: '[Ar] 3d³ 4s²', shells: [2, 8, 11, 2], valence: 'V, IV, III, II', electroneg: '1.63', radius: '134 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 24, symbol: 'Cr', name: 'Chromium', mass: '51.996', block: 'd', row: 4, col: 6, config: '[Ar] 3d⁵ 4s¹', shells: [2, 8, 13, 1], valence: 'III, II, VI', electroneg: '1.66', radius: '128 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 25, symbol: 'Mn', name: 'Manganese', mass: '54.938', block: 'd', row: 4, col: 7, config: '[Ar] 3d⁵ 4s²', shells: [2, 8, 13, 2], valence: 'II, IV, VII', electroneg: '1.55', radius: '127 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 26, symbol: 'Fe', name: 'Iron', mass: '55.845', block: 'd', row: 4, col: 8, config: '[Ar] 3d⁶ 4s²', shells: [2, 8, 14, 2], valence: 'II, III', electroneg: '1.83', radius: '126 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 27, symbol: 'Co', name: 'Cobalt', mass: '58.933', block: 'd', row: 4, col: 9, config: '[Ar] 3d⁷ 4s²', shells: [2, 8, 15, 2], valence: 'II, III', electroneg: '1.88', radius: '125 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 28, symbol: 'Ni', name: 'Nickel', mass: '58.693', block: 'd', row: 4, col: 10, config: '[Ar] 3d⁸ 4s²', shells: [2, 8, 16, 2], valence: 'II, III', electroneg: '1.91', radius: '124 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 29, symbol: 'Cu', name: 'Copper', mass: '63.546', block: 'd', row: 4, col: 11, config: '[Ar] 3d¹⁰ 4s¹', shells: [2, 8, 18, 1], valence: 'II, I', electroneg: '1.90', radius: '128 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 30, symbol: 'Zn', name: 'Zinc', mass: '65.38', block: 'd', row: 4, col: 12, config: '[Ar] 3d¹⁰ 4s²', shells: [2, 8, 18, 2], valence: 'II', electroneg: '1.65', radius: '134 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 31, symbol: 'Ga', name: 'Gallium', mass: '69.723', block: 'p', row: 4, col: 13, config: '[Ar] 3d¹⁰ 4s² 4p¹', shells: [2, 8, 18, 3], valence: 'III', electroneg: '1.81', radius: '135 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 32, symbol: 'Ge', name: 'Germanium', mass: '72.630', block: 'p', row: 4, col: 14, config: '[Ar] 3d¹⁰ 4s² 4p²', shells: [2, 8, 18, 4], valence: 'IV', electroneg: '2.01', radius: '122 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 33, symbol: 'As', name: 'Arsenic', mass: '74.922', block: 'p', row: 4, col: 15, config: '[Ar] 3d¹⁰ 4s² 4p³', shells: [2, 8, 18, 5], valence: 'III, V', electroneg: '2.18', radius: '120 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 34, symbol: 'Se', name: 'Selenium', mass: '78.971', block: 'p', row: 4, col: 16, config: '[Ar] 3d¹⁰ 4s² 4p⁴', shells: [2, 8, 18, 6], valence: 'II, IV, VI', electroneg: '2.55', radius: '119 pm', propType: 'phikim', propText: 'Reactive Nonmetal' },
  { z: 35, symbol: 'Br', name: 'Bromine', mass: '79.904', block: 'p', row: 4, col: 17, config: '[Ar] 3d¹⁰ 4s² 4p⁵', shells: [2, 8, 18, 7], valence: 'I, III, V', electroneg: '2.96', radius: '120 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 36, symbol: 'Kr', name: 'Krypton', mass: '83.798', block: 'p', row: 4, col: 18, config: '[Ar] 3d¹⁰ 4s² 4p⁶', shells: [2, 8, 18, 8], valence: '0', electroneg: '3.00', radius: '116 pm', propType: 'khikiem', propText: 'Noble Gas' },

  { z: 37, symbol: 'Rb', name: 'Rubidium', mass: '85.468', block: 's', row: 5, col: 1, config: '[Kr] 5s¹', shells: [2, 8, 18, 8, 1], valence: 'I', electroneg: '0.82', radius: '248 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 38, symbol: 'Sr', name: 'Strontium', mass: '87.62', block: 's', row: 5, col: 2, config: '[Kr] 5s²', shells: [2, 8, 18, 8, 2], valence: 'II', electroneg: '0.95', radius: '215 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },
  { z: 39, symbol: 'Y', name: 'Yttrium', mass: '88.906', block: 'd', row: 5, col: 3, config: '[Kr] 4d¹ 5s²', shells: [2, 8, 18, 9, 2], valence: 'III', electroneg: '1.22', radius: '180 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 40, symbol: 'Zr', name: 'Zirconium', mass: '91.224', block: 'd', row: 5, col: 4, config: '[Kr] 4d² 5s²', shells: [2, 8, 18, 10, 2], valence: 'IV', electroneg: '1.33', radius: '160 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 41, symbol: 'Nb', name: 'Niobium', mass: '92.906', block: 'd', row: 5, col: 5, config: '[Kr] 4d⁴ 5s¹', shells: [2, 8, 18, 12, 1], valence: 'V, III', electroneg: '1.6', radius: '146 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 42, symbol: 'Mo', name: 'Molybdenum', mass: '95.95', block: 'd', row: 5, col: 6, config: '[Kr] 4d⁵ 5s¹', shells: [2, 8, 18, 13, 1], valence: 'VI, IV', electroneg: '2.16', radius: '139 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 43, symbol: 'Tc', name: 'Technetium', mass: '98', block: 'd', row: 5, col: 7, config: '[Kr] 4d⁵ 5s²', shells: [2, 8, 18, 13, 2], valence: 'VII, IV', electroneg: '1.9', radius: '136 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 44, symbol: 'Ru', name: 'Ruthenium', mass: '101.07', block: 'd', row: 5, col: 8, config: '[Kr] 4d⁷ 5s¹', shells: [2, 8, 18, 15, 1], valence: 'III, IV, VIII', electroneg: '2.2', radius: '134 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 45, symbol: 'Rh', name: 'Rhodium', mass: '102.91', block: 'd', row: 5, col: 9, config: '[Kr] 4d⁸ 5s¹', shells: [2, 8, 18, 16, 1], valence: 'III', electroneg: '2.28', radius: '134 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 46, symbol: 'Pd', name: 'Palladium', mass: '106.42', block: 'd', row: 5, col: 10, config: '[Kr] 4d¹⁰', shells: [2, 8, 18, 18], valence: 'II, IV', electroneg: '2.20', radius: '137 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 47, symbol: 'Ag', name: 'Silver', mass: '107.87', block: 'd', row: 5, col: 11, config: '[Kr] 4d¹⁰ 5s¹', shells: [2, 8, 18, 18, 1], valence: 'I', electroneg: '1.93', radius: '144 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 48, symbol: 'Cd', name: 'Cadmium', mass: '112.41', block: 'd', row: 5, col: 12, config: '[Kr] 4d¹⁰ 5s²', shells: [2, 8, 18, 18, 2], valence: 'II', electroneg: '1.69', radius: '151 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 49, symbol: 'In', name: 'Indium', mass: '114.82', block: 'p', row: 5, col: 13, config: '[Kr] 4d¹⁰ 5s² 5p¹', shells: [2, 8, 18, 18, 3], valence: 'III', electroneg: '1.78', radius: '167 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 50, symbol: 'Sn', name: 'Tin', mass: '118.71', block: 'p', row: 5, col: 14, config: '[Kr] 4d¹⁰ 5s² 5p²', shells: [2, 8, 18, 18, 4], valence: 'IV, II', electroneg: '1.96', radius: '140 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 51, symbol: 'Sb', name: 'Antimony', mass: '121.76', block: 'p', row: 5, col: 15, config: '[Kr] 4d¹⁰ 5s² 5p³', shells: [2, 8, 18, 18, 5], valence: 'III, V', electroneg: '2.05', radius: '140 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 52, symbol: 'Te', name: 'Tellurium', mass: '127.60', block: 'p', row: 5, col: 16, config: '[Kr] 4d¹⁰ 5s² 5p⁴', shells: [2, 8, 18, 18, 6], valence: 'II, IV, VI', electroneg: '2.1', radius: '142 pm', propType: 'phikim', propText: 'Metalloid' },
  { z: 53, symbol: 'I', name: 'Iodine', mass: '126.90', block: 'p', row: 5, col: 17, config: '[Kr] 4d¹⁰ 5s² 5p⁵', shells: [2, 8, 18, 18, 7], valence: 'I, III, V, VII', electroneg: '2.66', radius: '133 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 54, symbol: 'Xe', name: 'Xenon', mass: '131.29', block: 'p', row: 5, col: 18, config: '[Kr] 4d¹⁰ 5s² 5p⁶', shells: [2, 8, 18, 18, 8], valence: '0', electroneg: '2.6', radius: '131 pm', propType: 'khikiem', propText: 'Noble Gas' },

  { z: 55, symbol: 'Cs', name: 'Caesium', mass: '132.91', block: 's', row: 6, col: 1, config: '[Xe] 6s¹', shells: [2, 8, 18, 18, 8, 1], valence: 'I', electroneg: '0.79', radius: '267 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 56, symbol: 'Ba', name: 'Barium', mass: '137.33', block: 's', row: 6, col: 2, config: '[Xe] 6s²', shells: [2, 8, 18, 18, 8, 2], valence: 'II', electroneg: '0.89', radius: '222 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },

  /* Lanthanides (57-70) - f-block row 9 */
  { z: 57, symbol: 'La', name: 'Lanthanum', mass: '138.91', block: 'f', row: 9, col: 4, config: '[Xe] 5d¹ 6s²', shells: [2, 8, 18, 18, 9, 2], valence: 'III', electroneg: '1.10', radius: '187 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 58, symbol: 'Ce', name: 'Cerium', mass: '140.12', block: 'f', row: 9, col: 5, config: '[Xe] 4f¹ 5d¹ 6s²', shells: [2, 8, 18, 19, 9, 2], valence: 'III, IV', electroneg: '1.12', radius: '181 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 59, symbol: 'Pr', name: 'Praseodymium', mass: '140.91', block: 'f', row: 9, col: 6, config: '[Xe] 4f³ 6s²', shells: [2, 8, 18, 21, 8, 2], valence: 'III', electroneg: '1.13', radius: '182 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 60, symbol: 'Nd', name: 'Neodymium', mass: '144.24', block: 'f', row: 9, col: 7, config: '[Xe] 4f⁴ 6s²', shells: [2, 8, 18, 22, 8, 2], valence: 'III', electroneg: '1.14', radius: '181 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 61, symbol: 'Pm', name: 'Promethium', mass: '145', block: 'f', row: 9, col: 8, config: '[Xe] 4f⁵ 6s²', shells: [2, 8, 18, 23, 8, 2], valence: 'III', electroneg: '1.13', radius: '183 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 62, symbol: 'Sm', name: 'Samarium', mass: '150.36', block: 'f', row: 9, col: 9, config: '[Xe] 4f⁶ 6s²', shells: [2, 8, 18, 24, 8, 2], valence: 'III, II', electroneg: '1.17', radius: '180 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 63, symbol: 'Eu', name: 'Europium', mass: '151.96', block: 'f', row: 9, col: 10, config: '[Xe] 4f⁷ 6s²', shells: [2, 8, 18, 25, 8, 2], valence: 'III, II', electroneg: '1.20', radius: '180 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 64, symbol: 'Gd', name: 'Gadolinium', mass: '157.25', block: 'f', row: 9, col: 11, config: '[Xe] 4f⁷ 5d¹ 6s²', shells: [2, 8, 18, 25, 9, 2], valence: 'III', electroneg: '1.20', radius: '180 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 65, symbol: 'Tb', name: 'Terbium', mass: '158.93', block: 'f', row: 9, col: 12, config: '[Xe] 4f⁹ 6s²', shells: [2, 8, 18, 27, 8, 2], valence: 'III, IV', electroneg: '1.20', radius: '178 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 66, symbol: 'Dy', name: 'Dysprosium', mass: '162.50', block: 'f', row: 9, col: 13, config: '[Xe] 4f¹⁰ 6s²', shells: [2, 8, 18, 28, 8, 2], valence: 'III', electroneg: '1.22', radius: '177 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 67, symbol: 'Ho', name: 'Holmium', mass: '164.93', block: 'f', row: 9, col: 14, config: '[Xe] 4f¹¹ 6s²', shells: [2, 8, 18, 29, 8, 2], valence: 'III', electroneg: '1.23', radius: '176 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 68, symbol: 'Er', name: 'Erbium', mass: '167.26', block: 'f', row: 9, col: 15, config: '[Xe] 4f¹² 6s²', shells: [2, 8, 18, 30, 8, 2], valence: 'III', electroneg: '1.24', radius: '175 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 69, symbol: 'Tm', name: 'Thulium', mass: '168.93', block: 'f', row: 9, col: 16, config: '[Xe] 4f¹³ 6s²', shells: [2, 8, 18, 31, 8, 2], valence: 'III, II', electroneg: '1.25', radius: '174 pm', propType: 'kimloai', propText: 'Lanthanide' },
  { z: 70, symbol: 'Yb', name: 'Ytterbium', mass: '173.05', block: 'f', row: 9, col: 17, config: '[Xe] 4f¹⁴ 6s²', shells: [2, 8, 18, 32, 8, 2], valence: 'III, II', electroneg: '1.10', radius: '173 pm', propType: 'kimloai', propText: 'Lanthanide' },

  /* Period 6 main row (71-86) */
  { z: 71, symbol: 'Lu', name: 'Lutetium', mass: '174.97', block: 'd', row: 6, col: 3, config: '[Xe] 4f¹⁴ 5d¹ 6s²', shells: [2, 8, 18, 32, 9, 2], valence: 'III', electroneg: '1.27', radius: '172 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 72, symbol: 'Hf', name: 'Hafnium', mass: '178.49', block: 'd', row: 6, col: 4, config: '[Xe] 4f¹⁴ 5d² 6s²', shells: [2, 8, 18, 32, 10, 2], valence: 'IV', electroneg: '1.3', radius: '159 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 73, symbol: 'Ta', name: 'Tantalum', mass: '180.95', block: 'd', row: 6, col: 5, config: '[Xe] 4f¹⁴ 5d³ 6s²', shells: [2, 8, 18, 32, 11, 2], valence: 'V', electroneg: '1.5', radius: '146 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 74, symbol: 'W', name: 'Tungsten', mass: '183.84', block: 'd', row: 6, col: 6, config: '[Xe] 4f¹⁴ 5d⁴ 6s²', shells: [2, 8, 18, 32, 12, 2], valence: 'VI', electroneg: '2.36', radius: '139 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 75, symbol: 'Re', name: 'Rhenium', mass: '186.21', block: 'd', row: 6, col: 7, config: '[Xe] 4f¹⁴ 5d⁵ 6s²', shells: [2, 8, 18, 32, 13, 2], valence: 'VII, IV', electroneg: '1.9', radius: '137 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 76, symbol: 'Os', name: 'Osmium', mass: '190.23', block: 'd', row: 6, col: 8, config: '[Xe] 4f¹⁴ 5d⁶ 6s²', shells: [2, 8, 18, 32, 14, 2], valence: 'IV, VIII', electroneg: '2.2', radius: '135 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 77, symbol: 'Ir', name: 'Iridium', mass: '192.22', block: 'd', row: 6, col: 9, config: '[Xe] 4f¹⁴ 5d⁷ 6s²', shells: [2, 8, 18, 32, 15, 2], valence: 'IV, III', electroneg: '2.20', radius: '136 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 78, symbol: 'Pt', name: 'Platinum', mass: '195.08', block: 'd', row: 6, col: 10, config: '[Xe] 4f¹⁴ 5d⁹ 6s¹', shells: [2, 8, 18, 32, 17, 1], valence: 'IV, II', electroneg: '2.28', radius: '139 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 79, symbol: 'Au', name: 'Gold', mass: '196.97', block: 'd', row: 6, col: 11, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s¹', shells: [2, 8, 18, 32, 18, 1], valence: 'III, I', electroneg: '2.54', radius: '144 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 80, symbol: 'Hg', name: 'Mercury', mass: '200.59', block: 'd', row: 6, col: 12, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s²', shells: [2, 8, 18, 32, 18, 2], valence: 'I, II', electroneg: '2.00', radius: '151 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 81, symbol: 'Tl', name: 'Thallium', mass: '204.38', block: 'p', row: 6, col: 13, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p¹', shells: [2, 8, 18, 32, 18, 3], valence: 'I, III', electroneg: '1.62', radius: '170 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 82, symbol: 'Pb', name: 'Lead', mass: '207.2', block: 'p', row: 6, col: 14, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p²', shells: [2, 8, 18, 32, 18, 4], valence: 'II, IV', electroneg: '1.87', radius: '175 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 83, symbol: 'Bi', name: 'Bismuth', mass: '208.98', block: 'p', row: 6, col: 15, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p³', shells: [2, 8, 18, 32, 18, 5], valence: 'III, V', electroneg: '2.02', radius: '155 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 84, symbol: 'Po', name: 'Polonium', mass: '209', block: 'p', row: 6, col: 16, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p⁴', shells: [2, 8, 18, 32, 18, 6], valence: 'II, IV', electroneg: '2.0', radius: '167 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 85, symbol: 'At', name: 'Astatine', mass: '210', block: 'p', row: 6, col: 17, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p⁵', shells: [2, 8, 18, 32, 18, 7], valence: 'I, III, V', electroneg: '2.2', radius: '140 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 86, symbol: 'Rn', name: 'Radon', mass: '222', block: 'p', row: 6, col: 18, config: '[Xe] 4f¹⁴ 5d¹⁰ 6s² 6p⁶', shells: [2, 8, 18, 32, 18, 8], valence: '0', electroneg: '-', radius: '140 pm', propType: 'khikiem', propText: 'Noble Gas' },

  { z: 87, symbol: 'Fr', name: 'Francium', mass: '223', block: 's', row: 7, col: 1, config: '[Rn] 7s¹', shells: [2, 8, 18, 32, 18, 8, 1], valence: 'I', electroneg: '0.7', radius: '270 pm', propType: 'kimloai', propText: 'Alkali Metal' },
  { z: 88, symbol: 'Ra', name: 'Radium', mass: '226', block: 's', row: 7, col: 2, config: '[Rn] 7s²', shells: [2, 8, 18, 32, 18, 8, 2], valence: 'II', electroneg: '0.9', radius: '223 pm', propType: 'kimloai', propText: 'Alkaline Earth Metal' },

  /* Actinides (89-102) - f-block row 10 */
  { z: 89, symbol: 'Ac', name: 'Actinium', mass: '227', block: 'f', row: 10, col: 4, config: '[Rn] 6d¹ 7s²', shells: [2, 8, 18, 32, 18, 9, 2], valence: 'III', electroneg: '1.1', radius: '188 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 90, symbol: 'Th', name: 'Thorium', mass: '232.04', block: 'f', row: 10, col: 5, config: '[Rn] 6d² 7s²', shells: [2, 8, 18, 32, 18, 10, 2], valence: 'IV', electroneg: '1.3', radius: '179 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 91, symbol: 'Pa', name: 'Protactinium', mass: '231.04', block: 'f', row: 10, col: 6, config: '[Rn] 5f² 6d¹ 7s²', shells: [2, 8, 18, 32, 20, 9, 2], valence: 'V, IV', electroneg: '1.5', radius: '161 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 92, symbol: 'U', name: 'Uranium', mass: '238.03', block: 'f', row: 10, col: 7, config: '[Rn] 5f³ 6d¹ 7s²', shells: [2, 8, 18, 32, 21, 9, 2], valence: 'VI, IV, III', electroneg: '1.38', radius: '156 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 93, symbol: 'Np', name: 'Neptunium', mass: '237', block: 'f', row: 10, col: 8, config: '[Rn] 5f⁴ 6d¹ 7s²', shells: [2, 8, 18, 32, 22, 9, 2], valence: 'V, IV, III, VI', electroneg: '1.36', radius: '155 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 94, symbol: 'Pu', name: 'Plutonium', mass: '244', block: 'f', row: 10, col: 9, config: '[Rn] 5f⁶ 7s²', shells: [2, 8, 18, 32, 24, 8, 2], valence: 'IV, VI, III', electroneg: '1.28', radius: '159 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 95, symbol: 'Am', name: 'Americium', mass: '243', block: 'f', row: 10, col: 10, config: '[Rn] 5f⁷ 7s²', shells: [2, 8, 18, 32, 25, 8, 2], valence: 'III, IV', electroneg: '1.3', radius: '173 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 96, symbol: 'Cm', name: 'Curium', mass: '247', block: 'f', row: 10, col: 11, config: '[Rn] 5f⁷ 6d¹ 7s²', shells: [2, 8, 18, 32, 25, 9, 2], valence: 'III, IV', electroneg: '1.3', radius: '174 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 97, symbol: 'Bk', name: 'Berkelium', mass: '247', block: 'f', row: 10, col: 12, config: '[Rn] 5f⁹ 7s²', shells: [2, 8, 18, 32, 27, 8, 2], valence: 'III, IV', electroneg: '1.3', radius: '170 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 98, symbol: 'Cf', name: 'Californium', mass: '251', block: 'f', row: 10, col: 13, config: '[Rn] 5f¹⁰ 7s²', shells: [2, 8, 18, 32, 28, 8, 2], valence: 'III', electroneg: '1.3', radius: '186 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 99, symbol: 'Es', name: 'Einsteinium', mass: '252', block: 'f', row: 10, col: 14, config: '[Rn] 5f¹¹ 7s²', shells: [2, 8, 18, 32, 29, 8, 2], valence: 'III', electroneg: '1.3', radius: '186 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 100, symbol: 'Fm', name: 'Fermium', mass: '257', block: 'f', row: 10, col: 15, config: '[Rn] 5f¹² 7s²', shells: [2, 8, 18, 32, 30, 8, 2], valence: 'III', electroneg: '1.3', radius: '180 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 101, symbol: 'Md', name: 'Mendelevium', mass: '258', block: 'f', row: 10, col: 16, config: '[Rn] 5f¹³ 7s²', shells: [2, 8, 18, 32, 31, 8, 2], valence: 'III, II', electroneg: '1.3', radius: '180 pm', propType: 'kimloai', propText: 'Actinide' },
  { z: 102, symbol: 'No', name: 'Nobelium', mass: '259', block: 'f', row: 10, col: 17, config: '[Rn] 5f¹⁴ 7s²', shells: [2, 8, 18, 32, 32, 8, 2], valence: 'II, III', electroneg: '1.3', radius: '180 pm', propType: 'kimloai', propText: 'Actinide' },

  /* Period 7 main row (103-118) */
  { z: 103, symbol: 'Lr', name: 'Lawrencium', mass: '266', block: 'd', row: 7, col: 3, config: '[Rn] 5f¹⁴ 7s² 7p¹', shells: [2, 8, 18, 32, 32, 8, 3], valence: 'III', electroneg: '1.3', radius: '180 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 104, symbol: 'Rf', name: 'Rutherfordium', mass: '267', block: 'd', row: 7, col: 4, config: '[Rn] 5f¹⁴ 6d² 7s²', shells: [2, 8, 18, 32, 32, 10, 2], valence: 'IV', electroneg: '-', radius: '150 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 105, symbol: 'Db', name: 'Dubnium', mass: '268', block: 'd', row: 7, col: 5, config: '[Rn] 5f¹⁴ 6d³ 7s²', shells: [2, 8, 18, 32, 32, 11, 2], valence: 'V', electroneg: '-', radius: '139 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 106, symbol: 'Sg', name: 'Seaborgium', mass: '269', block: 'd', row: 7, col: 6, config: '[Rn] 5f¹⁴ 6d⁴ 7s²', shells: [2, 8, 18, 32, 32, 12, 2], valence: 'VI', electroneg: '-', radius: '132 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 107, symbol: 'Bh', name: 'Bohrium', mass: '270', block: 'd', row: 7, col: 7, config: '[Rn] 5f¹⁴ 6d⁵ 7s²', shells: [2, 8, 18, 32, 32, 13, 2], valence: 'VII', electroneg: '-', radius: '128 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 108, symbol: 'Hs', name: 'Hassium', mass: '277', block: 'd', row: 7, col: 8, config: '[Rn] 5f¹⁴ 6d⁶ 7s²', shells: [2, 8, 18, 32, 32, 14, 2], valence: 'VIII', electroneg: '-', radius: '134 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 109, symbol: 'Mt', name: 'Meitnerium', mass: '278', block: 'd', row: 7, col: 9, config: '[Rn] 5f¹⁴ 6d⁷ 7s²', shells: [2, 8, 18, 32, 32, 15, 2], valence: 'III, IV', electroneg: '-', radius: '141 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 110, symbol: 'Ds', name: 'Darmstadtium', mass: '281', block: 'd', row: 7, col: 10, config: '[Rn] 5f¹⁴ 6d⁸ 7s²', shells: [2, 8, 18, 32, 32, 16, 2], valence: 'VI, IV', electroneg: '-', radius: '132 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 111, symbol: 'Rg', name: 'Roentgenium', mass: '282', block: 'd', row: 7, col: 11, config: '[Rn] 5f¹⁴ 6d⁹ 7s²', shells: [2, 8, 18, 32, 32, 17, 2], valence: 'III, V', electroneg: '-', radius: '138 pm', propType: 'kimloai', propText: 'Transition Metal' },
  { z: 112, symbol: 'Cn', name: 'Copernicium', mass: '285', block: 'd', row: 7, col: 12, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s²', shells: [2, 8, 18, 32, 32, 18, 2], valence: 'II, IV', electroneg: '-', radius: '147 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 113, symbol: 'Nh', name: 'Nihonium', mass: '286', block: 'p', row: 7, col: 13, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p¹', shells: [2, 8, 18, 32, 32, 18, 3], valence: 'I, III', electroneg: '-', radius: '170 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 114, symbol: 'Fl', name: 'Flerovium', mass: '289', block: 'p', row: 7, col: 14, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p²', shells: [2, 8, 18, 32, 32, 18, 4], valence: 'II, IV', electroneg: '-', radius: '180 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 115, symbol: 'Mc', name: 'Moscovium', mass: '290', block: 'p', row: 7, col: 15, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p³', shells: [2, 8, 18, 32, 32, 18, 5], valence: 'I, III', electroneg: '-', radius: '187 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 116, symbol: 'Lv', name: 'Livermorium', mass: '293', block: 'p', row: 7, col: 16, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p⁴', shells: [2, 8, 18, 32, 32, 18, 6], valence: 'II, IV', electroneg: '-', radius: '183 pm', propType: 'kimloai', propText: 'Post-Transition Metal' },
  { z: 117, symbol: 'Ts', name: 'Tennessine', mass: '294', block: 'p', row: 7, col: 17, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p⁵', shells: [2, 8, 18, 32, 32, 18, 7], valence: 'I, III', electroneg: '-', radius: '138 pm', propType: 'phikim', propText: 'Halogen' },
  { z: 118, symbol: 'Og', name: 'Oganesson', mass: '294', block: 'p', row: 7, col: 18, config: '[Rn] 5f¹⁴ 6d¹⁰ 7s² 7p⁶', shells: [2, 8, 18, 32, 32, 18, 8], valence: '0', electroneg: '-', radius: '152 pm', propType: 'khikiem', propText: 'Noble Gas' }
    ];

    // Auto fill elements
    const elements = [];
    for (let i = 1; i <= 118; i++) {
      const found = rawElements.find(e => e.z === i);
      if (found) {
        const z = found.z;
        let cat = 'nonmetal';
        let catName = found.propText || 'Phi kim';

        const alkali = [3, 11, 19, 37, 55, 87];
        const alkalineEarth = [4, 12, 20, 38, 56, 88];
        const halogens = [9, 17, 35, 53, 85, 117];
        const nobleGases = [2, 10, 18, 36, 54, 86, 118];
        const metalloids = [5, 14, 32, 33, 51, 52, 84];

        if (z >= 57 && z <= 70) {
          cat = 'lanthanide';
          catName = 'Họ Lantan';
        } else if (z >= 89 && z <= 102) {
          cat = 'actinide';
          catName = 'Họ Actini';
        } else if (alkali.includes(z)) {
          cat = 'alkali';
          catName = 'Kim loại kiềm';
        } else if (alkalineEarth.includes(z)) {
          cat = 'alkaline-earth';
          catName = 'Kim loại kiềm thổ';
        } else if (nobleGases.includes(z)) {
          cat = 'noble';
          catName = 'Khí hiếm';
        } else if (halogens.includes(z)) {
          cat = 'halogen';
          catName = 'Halogen';
        } else if (metalloids.includes(z) || (found.propText || '').includes('Á kim')) {
          cat = 'metalloid';
          catName = 'Á kim';
        } else if (found.block === 'd' || (found.propText || '').includes('chuyển tiếp')) {
          cat = 'transition';
          catName = 'Kim loại chuyển tiếp';
        } else if (found.propType === 'kimloai') {
          cat = 'post-transition';
          catName = 'Kim loại sau chuyển tiếp';
        } else {
          cat = 'nonmetal';
          catName = 'Phi kim';
        }

        const groupType = (found.block === 'd' || found.block === 'f') ? 'B' : 'A';
        elements.push({ ...found, cat, catName, groupType });
      } else {
        let block = 'p';
        let groupType = 'A';
        let row = 4;
        let col = 14;

        if ((i >= 21 && i <= 30) || (i >= 39 && i <= 48) || (i >= 71 && i <= 80) || (i >= 103 && i <= 112)) {
          block = 'd';
          groupType = 'B';
        } else if (i >= 57 && i <= 70) {
          block = 'f';
          groupType = 'B';
          row = 9;
          col = i - 54;
        } else if (i >= 89 && i <= 102) {
          block = 'f';
          groupType = 'B';
          row = 10;
          col = i - 86;
        }

        let cat = 'transition';
        let catName = 'Kim loại chuyển tiếp';
        if (block === 'f') {
          if (i <= 70) { cat = 'lanthanide'; catName = 'Lantan'; }
          else { cat = 'actinide'; catName = 'Actini'; }
        } else if (i > 80 && i < 87) {
          cat = 'post-transition'; catName = 'Kim loại sau chuyển tiếp';
        }

        elements.push({
          z: i,
          symbol: `E${i}`,
          name: `Nguyên tố ${i}`,
          mass: `${(i * 2.25).toFixed(1)}`,
          block: block,
          row: row,
          col: col,
          groupType: groupType,
          cat: cat,
          catName: catName,
          config: `[Core] ${block}${i % 10}`,
          shells: [2, 8, 18, 8],
          valence: 'Phổ biến',
          electroneg: '1.5',
          radius: '135 pm'
        });
      }
    }

    let currentMode = 'property'; // 'property' | 'electron' | 'group'
    let currentCriteria = 'all';
    let currentSearch = '';

    function applyFilters() {
      const cards = document.querySelectorAll('.element-card:not(.placeholder-card)');
      cards.forEach(card => {
        const q = currentSearch;
        const matchesSearch = !q ||
          card.dataset.z.includes(q) ||
          card.dataset.symbol.includes(q) ||
          card.dataset.name.includes(q);

        let matchesFilter = false;
        const criteria = currentCriteria;

        if (criteria === 'all') {
          matchesFilter = true;
        } else if (criteria.startsWith('block-')) {
          matchesFilter = card.dataset.block === criteria.slice(6);
        } else if (criteria.startsWith('cat-')) {
          matchesFilter = card.dataset.cat === criteria.slice(4);
        } else if (criteria.startsWith('group-')) {
          matchesFilter = card.dataset.group === criteria.slice(6);
        } else if (criteria === 'metal-all') {
          matchesFilter = ['alkali', 'alkaline-earth', 'transition', 'post-transition', 'lanthanide', 'actinide'].includes(card.dataset.cat);
        } else if (criteria === 'nonmetal-all') {
          matchesFilter = ['nonmetal', 'halogen'].includes(card.dataset.cat);
        }

        card.classList.toggle('dimmed', !(matchesSearch && matchesFilter));
      });
    }

    function switchMode(mode) {
      currentMode = mode;
      document.body.className = `mode-${mode}`;
      
      document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.classList.toggle('active', btn.getAttribute('onclick').includes(mode));
      });

      currentCriteria = 'all';
      renderFilterBar();
      applyFilters();
    }

    function renderFilterBar() {
      const primaryBar = document.getElementById('primaryFilterBar');
      const subContainer = document.getElementById('subFilterContainer');
      primaryBar.innerHTML = '';
      subContainer.innerHTML = '';

      if (currentMode === 'electron') {
        primaryBar.innerHTML = `
          <button class="filter-btn active" onclick="filterElements('all')">Hiển thị tất cả</button>
          <button class="filter-btn" onclick="filterElements('block-s')"><span class="btn-dot" style="background:var(--block-s)"></span>Khối s</button>
          <button class="filter-btn" onclick="filterElements('block-p')"><span class="btn-dot" style="background:var(--block-p)"></span>Khối p</button>
          <button class="filter-btn" onclick="filterElements('block-d')"><span class="btn-dot" style="background:var(--block-d)"></span>Khối d</button>
          <button class="filter-btn" onclick="filterElements('block-f')"><span class="btn-dot" style="background:var(--block-f)"></span>Khối f</button>
        `;
      } else if (currentMode === 'property') {
        primaryBar.innerHTML = `
          <button class="filter-btn active" onclick="filterPropertyMain('all')">Hiển thị tất cả</button>
          <button class="filter-btn" onclick="filterPropertyMain('metal')">Kim loại</button>
          <button class="filter-btn" onclick="filterPropertyMain('nonmetal-group')">Phi kim</button>
          <button class="filter-btn" onclick="filterElements('cat-metalloid')"><span class="btn-dot" style="background:var(--cat-metalloid)"></span>Á kim</button>
          <button class="filter-btn" onclick="filterElements('cat-noble')"><span class="btn-dot" style="background:var(--cat-noble)"></span>Khí hiếm</button>
          <button class="filter-btn" onclick="filterElements('cat-lanthanide')"><span class="btn-dot" style="background:var(--cat-lanthanide)"></span>Họ Lantan</button>
          <button class="filter-btn" onclick="filterElements('cat-actinide')"><span class="btn-dot" style="background:var(--cat-actinide)"></span>Họ Actini</button>
        `;
      } else if (currentMode === 'group') {
        primaryBar.innerHTML = `
          <button class="filter-btn active" onclick="filterElements('all')">Hiển thị tất cả</button>
          <button class="filter-btn" onclick="filterElements('group-A')">Nhóm A (Nguyên tố s, p)</button>
          <button class="filter-btn" onclick="filterElements('group-B')">Nhóm B (Nguyên tố d, f)</button>
        `;
      }

      // Add active toggle effect
      document.querySelectorAll('.filter-btn').forEach(btn => {
        btn.addEventListener('click', function() {
          this.parentElement.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
          this.classList.add('active');
        });
      });
    }

    function filterPropertyMain(type) {
      const subContainer = document.getElementById('subFilterContainer');
      subContainer.innerHTML = '';

      if (type === 'metal') {
        subContainer.innerHTML = `
          <div class="sub-filter-bar">
            <span class="sub-title">Danh mục Kim loại:</span>
            <button class="filter-btn active" onclick="filterElements('metal-all')">Tất cả Kim loại</button>
            <button class="filter-btn" onclick="filterElements('cat-alkali')"><span class="btn-dot" style="background:var(--cat-alkali)"></span>Kim loại kiềm</button>
            <button class="filter-btn" onclick="filterElements('cat-alkaline-earth')"><span class="btn-dot" style="background:var(--cat-alkaline-earth)"></span>Kiềm thổ</button>
            <button class="filter-btn" onclick="filterElements('cat-transition')"><span class="btn-dot" style="background:var(--cat-transition)"></span>Chuyển tiếp</button>
            <button class="filter-btn" onclick="filterElements('cat-post-transition')"><span class="btn-dot" style="background:var(--cat-post-transition)"></span>Sau chuyển tiếp</button>
          </div>
        `;
        filterElements('metal-all');
      } else if (type === 'nonmetal-group') {
        subContainer.innerHTML = `
          <div class="sub-filter-bar">
            <span class="sub-title">Danh mục Phi kim:</span>
            <button class="filter-btn active" onclick="filterElements('nonmetal-all')">Tất cả Phi kim</button>
            <button class="filter-btn" onclick="filterElements('cat-nonmetal')"><span class="btn-dot" style="background:var(--cat-nonmetal)"></span>Phi kim thường</button>
            <button class="filter-btn" onclick="filterElements('cat-halogen')"><span class="btn-dot" style="background:var(--cat-halogen)"></span>Halogen</button>
          </div>
        `;
        filterElements('nonmetal-all');
      } else {
        filterElements('all');
      }

      // Bind active effect for sub-bar buttons
      subContainer.querySelectorAll('.filter-btn').forEach(btn => {
        btn.addEventListener('click', function() {
          this.parentElement.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
          this.classList.add('active');
        });
      });
    }

    function filterElements(criteria) {
      currentCriteria = criteria;
      applyFilters();
    }

    // Tao truc hien thi nhom va chu ky theo cach ghi A/B
    function renderAxes() {
      const groupAxis = document.getElementById('groupAxis');
      const periodAxis = document.getElementById('periodAxis');
      groupAxis.innerHTML = '';
      periodAxis.innerHTML = '';

      const groups = [
        ['IA', 1, 1], ['IIA', 2, 1],
        ['IIIB', 3, 1], ['IVB', 4, 1], ['VB', 5, 1],
        ['VIB', 6, 1], ['VIIB', 7, 1], ['VIIIB', 8, 3],
        ['IB', 11, 1], ['IIB', 12, 1],
        ['IIIA', 13, 1], ['IVA', 14, 1], ['VA', 15, 1],
        ['VIA', 16, 1], ['VIIA', 17, 1], ['VIIIA', 18, 1]
      ];

      groups.forEach(([name, column, span]) => {
        const label = document.createElement('div');
        label.className = 'axis-label';
        label.textContent = name;
        label.style.gridColumn = `${column} / span ${span}`;
        groupAxis.appendChild(label);
      });

      for (let i = 1; i <= 7; i++) {
        const label = document.createElement('div');
        label.className = 'axis-label';
        label.textContent = i;
        periodAxis.appendChild(label);
      }

      periodAxis.appendChild(document.createElement('div'));

      for (const labelText of ['Lantan', 'Actini']) {
        const label = document.createElement('div');
        label.className = 'axis-label';
        label.textContent = labelText;
        label.style.fontSize = '0.58rem';
        label.style.writingMode = 'vertical-rl';
        label.style.transform = 'rotate(180deg)';
        periodAxis.appendChild(label);
      }
    }

    // Render Table Grid
    function renderTable() {
      const table = document.getElementById('periodicTable');
      table.innerHTML = '';

      const gridMap = {};
      elements.forEach(el => {
        if (el.row && el.col) gridMap[`${el.row}-${el.col}`] = el;
      });

      for (let r = 1; r <= 10; r++) {
        if (r === 8) {
          const spacer = document.createElement('div');
          spacer.className = 'spacer';
          table.appendChild(spacer);
          continue;
        }

        for (let c = 1; c <= 18; c++) {
          const el = gridMap[`${r}-${c}`];
          if (el) {
            const card = document.createElement('div');
            card.className = `element-card block-${el.block} cat-${el.cat} group-${el.groupType}`;
            card.dataset.z = el.z;
            card.dataset.block = el.block;
            card.dataset.cat = el.cat;
            card.dataset.group = el.groupType;
            card.dataset.symbol = el.symbol.toLowerCase();
            card.dataset.name = el.name.toLowerCase();
            card.onclick = () => showModal(el);

            card.innerHTML = `
              <div class="number">${el.z}</div>
              <div class="symbol">${el.symbol}</div>
              <div class="name">${el.name}</div>
            `;
            table.appendChild(card);
          } else if (r === 6 && c === 3) {
            const ph = document.createElement('div');
            ph.className = 'element-card placeholder-card';
            ph.innerText = '*';
            table.appendChild(ph);
          } else if (r === 7 && c === 3) {
            const ph = document.createElement('div');
            ph.className = 'element-card placeholder-card';
            ph.innerText = '**';
            table.appendChild(ph);
          } else {
            table.appendChild(document.createElement('div'));
          }
        }
      }
    }


    // Công thức oxide cao nhất, hydroxide (hoặc acid tương ứng) và hợp chất với hydrogen.
    // Với nguyên tố không có hợp chất đặc trưng hoặc chưa đủ dữ liệu, hiển thị dấu —.
    const formulaData = {
      H:  { oxide: 'H₂O', hydroxide: '—', hydrogen: '—' },
      Li: { oxide: 'Li₂O', hydroxide: 'LiOH', hydrogen: 'LiH' },
      Be: { oxide: 'BeO', hydroxide: 'Be(OH)₂', hydrogen: 'BeH₂' },
      B:  { oxide: 'B₂O₃', hydroxide: 'H₃BO₃', hydrogen: 'BH₃' },
      C:  { oxide: 'CO₂', hydroxide: 'H₂CO₃', hydrogen: 'CH₄' },
      N:  { oxide: 'N₂O₅', hydroxide: 'HNO₃', hydrogen: 'NH₃' },
      O:  { oxide: '—', hydroxide: '—', hydrogen: 'H₂O' },
      F:  { oxide: '—', hydroxide: '—', hydrogen: 'HF' },
      Na: { oxide: 'Na₂O', hydroxide: 'NaOH', hydrogen: 'NaH' },
      Mg: { oxide: 'MgO', hydroxide: 'Mg(OH)₂', hydrogen: 'MgH₂' },
      Al: { oxide: 'Al₂O₃', hydroxide: 'Al(OH)₃', hydrogen: 'AlH₃' },
      Si: { oxide: 'SiO₂', hydroxide: 'H₂SiO₃', hydrogen: 'SiH₄' },
      P:  { oxide: 'P₂O₅', hydroxide: 'H₃PO₄', hydrogen: 'PH₃' },
      S:  { oxide: 'SO₃', hydroxide: 'H₂SO₄', hydrogen: 'H₂S' },
      Cl: { oxide: 'Cl₂O₇', hydroxide: 'HClO₄', hydrogen: 'HCl' },
      K:  { oxide: 'K₂O', hydroxide: 'KOH', hydrogen: 'KH' },
      Ca: { oxide: 'CaO', hydroxide: 'Ca(OH)₂', hydrogen: 'CaH₂' },
      Ga: { oxide: 'Ga₂O₃', hydroxide: 'Ga(OH)₃', hydrogen: 'GaH₃' },
      Ge: { oxide: 'GeO₂', hydroxide: 'H₂GeO₃', hydrogen: 'GeH₄' },
      As: { oxide: 'As₂O₅', hydroxide: 'H₃AsO₄', hydrogen: 'AsH₃' },
      Se: { oxide: 'SeO₃', hydroxide: 'H₂SeO₄', hydrogen: 'H₂Se' },
      Br: { oxide: 'Br₂O₇', hydroxide: 'HBrO₄', hydrogen: 'HBr' },
      Rb: { oxide: 'Rb₂O', hydroxide: 'RbOH', hydrogen: 'RbH' },
      Sr: { oxide: 'SrO', hydroxide: 'Sr(OH)₂', hydrogen: 'SrH₂' },
      In: { oxide: 'In₂O₃', hydroxide: 'In(OH)₃', hydrogen: 'InH₃' },
      Sn: { oxide: 'SnO₂', hydroxide: 'Sn(OH)₄', hydrogen: 'SnH₄' },
      Sb: { oxide: 'Sb₂O₅', hydroxide: 'H₃SbO₄', hydrogen: 'SbH₃' },
      Te: { oxide: 'TeO₃', hydroxide: 'H₂TeO₄', hydrogen: 'H₂Te' },
      I:  { oxide: 'I₂O₇', hydroxide: 'HIO₄', hydrogen: 'HI' },
      Cs: { oxide: 'Cs₂O', hydroxide: 'CsOH', hydrogen: 'CsH' },
      Ba: { oxide: 'BaO', hydroxide: 'Ba(OH)₂', hydrogen: 'BaH₂' },
      Tl: { oxide: 'Tl₂O₃', hydroxide: 'Tl(OH)₃', hydrogen: 'TlH₃' },
      Pb: { oxide: 'PbO₂', hydroxide: 'Pb(OH)₄', hydrogen: 'PbH₄' },
      Bi: { oxide: 'Bi₂O₅', hydroxide: 'Bi(OH)₅', hydrogen: 'BiH₃' },
      Po: { oxide: 'PoO₃', hydroxide: 'H₂PoO₄', hydrogen: 'H₂Po' },
      At: { oxide: 'At₂O₇', hydroxide: 'HAtO₄', hydrogen: 'HAt' },
      Fr: { oxide: 'Fr₂O', hydroxide: 'FrOH', hydrogen: 'FrH' },
      Ra: { oxide: 'RaO', hydroxide: 'Ra(OH)₂', hydrogen: 'RaH₂' }
    };

    function getFormulaData(el) {
      if (formulaData[el.symbol]) return formulaData[el.symbol];

      // Công thức oxide cao nhất theo nhóm, trình bày theo bảng tham khảo.
      // el.col là vị trí cột của nguyên tố trong bảng tuần hoàn.
      const oxideByGroup = {
        1:  `${el.symbol}₂O`,
        2:  `${el.symbol}O`,
        3:  `${el.symbol}₂O₃`,
        4:  `${el.symbol}O₂`,
        5:  `${el.symbol}₂O₅`,
        6:  `${el.symbol}O₃`,
        7:  `${el.symbol}₂O₇`,
        8:  `${el.symbol}O₄`,
        9:  `${el.symbol}O₄`,
        10: `${el.symbol}O₄`,
        11: `${el.symbol}₂O`,
        12: `${el.symbol}O`,
        13: `${el.symbol}₂O₃`,
        14: `${el.symbol}O₂`,
        15: `${el.symbol}₂O₅`,
        16: `${el.symbol}O₃`,
        17: `${el.symbol}₂O₇`
      };

      return {
        oxide: oxideByGroup[el.col] || 'Không có oxide cao nhất đặc trưng',
        hydroxide: 'Chưa có dữ liệu phổ thông',
        hydrogen: 'Chưa có dữ liệu phổ thông'
      };
    }

    // Modal
    function showModal(el) {
      document.getElementById('mConfig').innerText = el.config;
      document.getElementById('mNumber').innerText = el.z;
      document.getElementById('mSymbol').innerText = el.symbol;
      document.getElementById('mName').innerText = el.name;
      document.getElementById('mSubText').innerText = `Khối ${el.block.toUpperCase()} | Chu kỳ ${el.row > 7 ? (el.row === 9 ? '6 (Lantan)' : '7 (Actini)') : el.row} - Nhóm ${el.groupType}`;
      document.getElementById('mMass').innerText = `${el.mass} amu`;
      document.getElementById('mValence').innerText = el.valence || 'I';
      document.getElementById('mElectroneg').innerText = el.electroneg;
      document.getElementById('mRadius').innerText = el.radius;
      document.getElementById('mProperty').innerText = el.catName;

      const formulas = getFormulaData(el);
      document.getElementById('mOxide').innerText = formulas.oxide;
      document.getElementById('mHydroxide').innerText = formulas.hydroxide;
      document.getElementById('mHydrogen').innerText = formulas.hydrogen;

      const badge = document.getElementById('mBadge');
      badge.className = `element-badge block-${el.block} cat-${el.cat}`;

      renderAtomStage(el);
      document.getElementById('modalOverlay').classList.add('active');
    }

    function renderAtomStage(el) {
      const stage = document.getElementById('atomStage');
      stage.innerHTML = '';

      const nucleus = document.createElement('div');
      nucleus.className = 'nucleus';
      nucleus.innerText = `${el.z}+`;
      stage.appendChild(nucleus);

      const shells = el.shells || [2, 8, 1];
      const maxRadius = 85;
      const step = maxRadius / Math.max(shells.length, 1);

      shells.forEach((count, index) => {
        const radius = (index + 1) * step + 12;
        const orbit = document.createElement('div');
        orbit.className = 'orbit';
        orbit.style.width = `${radius * 2}px`;
        orbit.style.height = `${radius * 2}px`;
        orbit.style.animationDuration = `${7 + index * 2.5}s`;

        for (let i = 0; i < count; i++) {
          const angle = (i / count) * 360;
          const electron = document.createElement('div');
          electron.className = 'electron';
          electron.style.transform =
            `translate(-50%, -50%) rotate(${angle}deg) translateY(-${radius}px)`;
          orbit.appendChild(electron);
        }
        stage.appendChild(orbit);
      });
    }

    function closeModal() {
      document.getElementById('modalOverlay').classList.remove('active');
    }

    // Search: kết hợp với bộ lọc đang chọn
    document.getElementById('searchInput').addEventListener('input', (e) => {
      currentSearch = e.target.value.toLowerCase().trim();
      applyFilters();
    });

    // Đóng modal khi nhấn ra ngoài hoặc nhấn Escape
    document.getElementById('modalOverlay').addEventListener('click', (e) => {
      if (e.target.id === 'modalOverlay') closeModal();
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeModal();
    });

    // Init
    renderAxes();
    renderTable();
    switchMode('property');
  </script>
</body>
</html>
