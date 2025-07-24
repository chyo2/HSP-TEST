<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>HSP 자가진단 테스트</title>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #6a5acd;
      --secondary: #9370db;
      --accent: #ff69b4;
      --light: #f8f9fa;
      --dark: #343a40;
      --gradient: linear-gradient(135deg, #6a5acd, #9370db, #ff69b4);
      
      --sensory: #4caf50;
      --empathy: #2196f3;
      --analytical: #9c27b0;
      --recovery: #ff9800;
      
      --very-low: #4caf50;
      --low: #8bc34a;
      --medium: #ffeb3b;
      --high: #ff9800;
      --very-high: #f44336;
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    body {
      font-family: 'Noto Sans KR', sans-serif;
      max-width: 800px;
      margin: 0 auto;
      padding: 15px;
      color: var(--dark);
      background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab, #9b59b6, #3498db, #2ecc71, #f1c40f);
      background-size: 800% 800%;
      animation: gradientBG 20s ease infinite;
      line-height: 1.5;
      min-height: 100vh;
    }
    
    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      25% { background-position: 50% 100%; }
      50% { background-position: 100% 50%; }
      75% { background-position: 50% 0%; }
      100% { background-position: 0% 50%; }
    }
    
    .container {
      background-color: rgba(255, 255, 255, 0.85);
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
      padding: 20px;
      margin-bottom: 20px;
      backdrop-filter: blur(5px);
    }
    
    header {
      text-align: center;
      margin-bottom: 20px;
    }
    
    h1 {
      font-size: 28px;
      color: var(--primary);
      margin-bottom: 8px;
      font-weight: 700;
    }
    
    .progress-container {
      width: 100%;
      height: 6px;
      background-color: #e9ecef;
      border-radius: 4px;
      margin-bottom: 20px;
      margin-top: 20px;
      overflow: hidden;
    }
    
    .progress-bar {
      height: 100%;
      background: var(--gradient);
      width: 0%;
      transition: width 0.3s ease;
      border-radius: 4px;
    }
    
    .question {
      margin-bottom: 18px;
      padding: 15px;
      border-radius: 12px;
      background-color: rgba(255, 255, 255, 0.8);
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }
    
    .question:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.08);
    }
    
    .question-text {
      font-size: 16px;
      font-weight: 500;
      margin-bottom: 12px;
      color: var(--dark);
    }
    
    .slider-container {
      position: relative;
      width: 100%;
      padding: 8px 0 20px 0;
    }
    
    input[type=range] {
      width: 100%;
      background: transparent;
      -webkit-appearance: none;
      margin: 8px 0;
      position: relative;
      z-index: 1;
    }
    
    input[type=range]:focus {
      outline: none;
    }
    
    input[type=range]::-webkit-slider-runnable-track {
      height: 8px;
      background: linear-gradient(to right, #4caf50, #ffeb3b, #f44336);
      border-radius: 4px;
    }
    
    input[type=range]::-webkit-slider-thumb {
      -webkit-appearance: none;
      width: 20px;
      height: 20px;
      background: white;
      border: 2px solid var(--primary);
      border-radius: 50%;
      margin-top: -6px;
      cursor: pointer;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
      transition: all 0.2s ease;
      position: relative;
      z-index: 4;
    }
    
    input[type=range]::-webkit-slider-thumb:hover {
      transform: scale(1.1);
      box-shadow: 0 3px 8px rgba(0, 0, 0, 0.3);
    }
    
    input[type=range]::-moz-range-track {
      height: 8px;
      background: linear-gradient(to right, #4caf50, #ffeb3b, #f44336);
      border-radius: 4px;
    }
    
    input[type=range]::-moz-range-thumb {
      width: 20px;
      height: 20px;
      background: white;
      border: 2px solid var(--primary);
      border-radius: 50%;
      cursor: pointer;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
      transition: all 0.2s ease;
      position: relative;
      z-index: 4;
    }
    
    .slider-track {
      position: absolute;
      top: 16px;
      left: 0;
      right: 0;
      height: 8px;
      background: linear-gradient(to right, #4caf50, #ffeb3b, #f44336);
      border-radius: 4px;
      z-index: 1;
    }
    
    .range-value {
      text-align: center;
      font-size: 15px;
      font-weight: 500;
      color: var(--primary);
      margin-top: 12px;
    }
    
    .btn {
      display: block;
      width: 100%;
      padding: 12px;
      font-size: 16px;
      font-weight: 500;
      background: var(--gradient);
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 15px;
    }
    
    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(106, 90, 205, 0.3);
    }
    
    .btn:active {
      transform: translateY(0);
    }
    
    .result {
      margin-top: 20px;
      padding: 20px;
      border-radius: 16px;
      background-color: rgba(255, 255, 255, 0.9);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
      text-align: center;
      animation: fadeIn 0.5s ease;
      backdrop-filter: blur(5px);
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    .result-title {
      font-size: 22px;
      font-weight: 700;
      color: var(--primary);
      margin-bottom: 12px;
    }
    
    .result-score {
      font-size: 32px;
      font-weight: 700;
      color: var(--accent);
      margin-bottom: 15px;
    }
    
    .result-category {
      display: inline-block;
      padding: 6px 14px;
      border-radius: 20px;
      font-weight: 500;
      margin-bottom: 12px;
    }
    
    .category-very-low {
      background-color: #e8f5e9;
      color: var(--very-low);
    }
    
    .category-low {
      background-color: #f1f8e9;
      color: var(--low);
    }
    
    .category-medium {
      background-color: #fffde7;
      color: #f9a825;
    }
    
    .category-high {
      background-color: #fff3e0;
      color: var(--high);
    }
    
    .category-very-high {
      background-color: #ffebee;
      color: var(--very-high);
    }
    
    .result-description {
      font-size: 15px;
      line-height: 1.5;
      margin-bottom: 20px;
    }
    
    .restart-btn {
      background: transparent;
      color: var(--primary);
      border: 2px solid var(--primary);
      padding: 8px 16px;
      border-radius: 8px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .restart-btn:hover {
      background: var(--primary);
      color: white;
    }
    
    .page-indicator {
      text-align: center;
      margin-bottom: 15px;
      font-size: 15px;
      color: #666;
    }
    
    .pagination {
      display: flex;
      justify-content: space-between;
      margin-top: 15px;
    }
    
    .pagination-btn {
      padding: 8px 16px;
      background: var(--light);
      color: var(--primary);
      border: 1px solid var(--primary);
      border-radius: 8px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .pagination-btn:hover {
      background: var(--primary);
      color: white;
    }
    
    .pagination-btn:disabled {
      background: #e9ecef;
      color: #adb5bd;
      border-color: #adb5bd;
      cursor: not-allowed;
    }
    
    .type-results {
      display: flex;
      flex-direction: column;
      gap: 15px;
      margin-top: 20px;
      margin-bottom: 20px;
    }
    
    .type-item {
      background-color: rgba(255, 255, 255, 0.7);
      border-radius: 10px;
      padding: 15px;
      box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
    }
    
    .type-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 8px;
    }
    
    .type-title {
      font-weight: 600;
      font-size: 16px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .type-score {
      font-weight: 700;
      font-size: 18px;
    }
    
    .type-bar-container {
      width: 100%;
      height: 8px;
      background-color: #e9ecef;
      border-radius: 4px;
      overflow: hidden;
    }
    
    .type-bar {
      height: 100%;
      border-radius: 4px;
      transition: width 1s ease;
    }
    
    .sensory-color {
      color: var(--sensory);
    }
    
    .empathy-color {
      color: var(--empathy);
    }
    
    .analytical-color {
      color: var(--analytical);
    }
    
    .recovery-color {
      color: var(--recovery);
    }
    
    .sensory-bg {
      background-color: var(--sensory);
    }
    
    .empathy-bg {
      background-color: var(--empathy);
    }
    
    .analytical-bg {
      background-color: var(--analytical);
    }
    
    .recovery-bg {
      background-color: var(--recovery);
    }
    
    .type-description {
      font-size: 14px;
      color: #666;
      margin-top: 8px;
    }
    
    .toggle-btn {
      background: transparent;
      border: none;
      color: var(--primary);
      font-size: 14px;
      font-weight: 500;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 5px;
      margin-top: 10px;
      padding: 5px 10px;
      border-radius: 4px;
      transition: all 0.2s ease;
    }
    
    .toggle-btn:hover {
      background-color: rgba(106, 90, 205, 0.1);
    }
    
    .toggle-icon {
      transition: transform 0.3s ease;
    }
    
    .rotate {
      transform: rotate(180deg);
    }
    
    .type-details {
      background-color: rgba(255, 255, 255, 0.5);
      border-radius: 8px;
      padding: 12px;
      margin-top: 10px;
      font-size: 14px;
      line-height: 1.5;
      color: #333;
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.5s ease, padding 0.5s ease, margin 0.5s ease;
    }
    
    .type-details.show {
      max-height: 500px;
      padding: 12px;
      margin-top: 10px;
    }
    
    .type-details ul {
      padding-left: 20px;
      margin-top: 8px;
    }
    
    .type-details li {
      margin-bottom: 5px;
    }
    
    .sensitivity-meter {
      display: flex;
      justify-content: space-between;
      margin: 20px 0;
      position: relative;
      width: 95%;
      margin-left: auto;
      margin-right: auto;
    }
    
    .sensitivity-level {
      flex: 1;
      text-align: center;
      padding: 10px 0;
      font-size: 13px;
      font-weight: 500;
      position: relative;
      z-index: 1;
    }
    
    .sensitivity-level:first-child {
      border-radius: 20px 0 0 20px;
    }
    
    .sensitivity-level:last-child {
      border-radius: 0 20px 20px 0;
    }
    
    .level-very-low {
      background-color: rgba(76, 175, 80, 0.2);
      color: var(--very-low);
    }
    
    .level-low {
      background-color: rgba(139, 195, 74, 0.2);
      color: var(--low);
    }
    
    .level-medium {
      background-color: rgba(255, 235, 59, 0.2);
      color: #f9a825;
    }
    
    .level-high {
      background-color: rgba(255, 152, 0, 0.2);
      color: var(--high);
    }
    
    .level-very-high {
      background-color: rgba(244, 67, 54, 0.2);
      color: var(--very-high);
    }
    
    .active-level {
      font-weight: 700;
      box-shadow: 0 0 0 2px rgba(255, 105, 180, 0.5);
    }
    
    .bottom-spacer {
      height: 60px;
    }
    
    .type-level {
      display: inline-block;
      padding: 3px 8px;
      border-radius: 12px;
      font-size: 12px;
      font-weight: 500;
      margin-left: 8px;
    }
    
    .type-level-very-low {
      background-color: rgba(76, 175, 80, 0.15);
      color: var(--very-low);
    }
    
    .type-level-low {
      background-color: rgba(139, 195, 74, 0.15);
      color: var(--low);
    }
    
    .type-level-medium {
      background-color: rgba(255, 235, 59, 0.15);
      color: #f9a825;
    }
    
    .type-level-high {
      background-color: rgba(255, 152, 0, 0.15);
      color: var(--high);
    }
    
    .type-level-very-high {
      background-color: rgba(244, 67, 54, 0.15);
      color: var(--very-high);
    }
    
    .share-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      background: var(--gradient);
      color: white;
      border: none;
      border-radius: 25px;
      padding: 10px 20px;
      font-size: 15px;
      font-weight: 500;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-bottom: 15px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      position: relative;
    }
    
    .share-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
    }
    
    .share-btn:active {
      transform: translateY(0);
    }
    
    .share-icon {
      display: inline-block;
      width: 18px;
      height: 18px;
    }
    
    .copy-notification {
      position: absolute;
      top: -40px;
      left: 50%;
      transform: translateX(-50%);
      background-color: rgba(0, 0, 0, 0.7);
      color: white;
      padding: 6px 12px;
      border-radius: 20px;
      font-size: 14px;
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.3s, visibility 0.3s;
      white-space: nowrap;
      display: flex;
      align-items: center;
      gap: 5px;
    }
    
    .copy-notification.show {
      opacity: 1;
      visibility: visible;
    }
    
    @media (max-width: 600px) {
      .container {
        padding: 15px;
      }
      
      h1 {
        font-size: 24px;
      }
      
      .question-text {
        font-size: 15px;
      }
      
      .question {
        padding: 12px;
        margin-bottom: 15px;
      }
      
      .sensitivity-level {
        font-size: 11px;
        padding: 8px 0;
      }
      
      .bottom-spacer {
        height: 80px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>🌎 나는 HSP 일까? 🤨</h1>
      <div class="progress-container">
        <div class="progress-bar" id="progress"></div>
      </div>
    </header>
    
    <form id="hspForm">
      <div id="questions"></div>
      
      <div class="pagination">
        <button type="button" id="prevBtn" class="pagination-btn" disabled>이전</button>
        <div class="page-indicator" id="pageIndicator">1/5</div>
        <button type="button" id="nextBtn" class="pagination-btn">다음</button>
      </div>
      
      <button type="submit" class="btn" id="submitBtn" style="display: none;">결과 확인하기</button>
    </form>
  </div>
  
  <div class="result" id="result" style="display: none;">
    <button class="share-btn" id="shareBtn">
      <svg class="share-icon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="18" cy="5" r="3"></circle>
        <circle cx="6" cy="12" r="3"></circle>
        <circle cx="18" cy="19" r="3"></circle>
        <line x1="8.59" y1="13.51" x2="15.42" y2="17.49"></line>
        <line x1="15.41" y1="6.51" x2="8.59" y2="10.49"></line>
      </svg>
      이 테스트 공유하기
      <div class="copy-notification" id="copyNotification">복사 완료 ✅</div>
    </button>
    
    <div class="result-title">HSP 자가진단 결과</div>
    <div class="result-score" id="resultScore"></div>
    <div id="resultCategory" class="result-category"></div>
    
    <div class="sensitivity-meter" id="sensitivityMeter">
      <div class="sensitivity-level level-very-low">매우 낮음</div>
      <div class="sensitivity-level level-low">낮음</div>
      <div class="sensitivity-level level-medium">보통</div>
      <div class="sensitivity-level level-high">높음</div>
      <div class="sensitivity-level level-very-high">매우 높음</div>
    </div>
    
    <div class="result-description" id="resultDescription"></div>
    
    <div class="type-results">
      <div class="type-item">
        <div class="type-header">
          <div class="type-title sensory-color">
            <span>🔊</span> 감각형 HSP
            <span class="type-level" id="sensoryLevel"></span>
          </div>
          <div class="type-score" id="sensoryScore">0/5</div>
        </div>
        <div class="type-bar-container">
          <div class="type-bar sensory-bg" id="sensoryBar" style="width: 0%"></div>
        </div>
        <div class="type-description">
          외부 자극(소리, 빛, 냄새 등)에 민감하게 반응하는 정도
        </div>
        <button class="toggle-btn" onclick="toggleDetails('sensoryDetails', this)">
          <span class="toggle-text">특징 보기</span> <span class="toggle-icon">▼</span>
        </button>
        <div class="type-details" id="sensoryDetails">
          <strong>감각형 HSP의 특징:</strong>
          <ul>
            <li>소음, 강한 빛, 혼잡한 환경에 쉽게 압도됨</li>
            <li>특정 질감, 냄새, 맛에 강한 반응을 보임</li>
            <li>카페인, 약물, 알코올에 민감하게 반응</li>
            <li>갑작스러운 소리나 자극에 쉽게 놀람</li>
            <li>물리적 환경(온도, 습도 등)의 변화를 빠르게 감지</li>
            <li>다른 사람들이 느끼지 못하는 미묘한 감각적 변화를 인지</li>
          </ul>
          <p style="margin-top: 10px;">감각형 HSP는 외부 자극을 더 강하게 처리하며, 이로 인해 일상 환경에서도 쉽게 피로감을 느낄 수 있습니다. 조용하고 편안한 환경을 조성하는 것이 도움이 됩니다.</p>
        </div>
      </div>
      
      <div class="type-item">
        <div class="type-header">
          <div class="type-title empathy-color">
            <span>💭</span> 공감형 HSP
            <span class="type-level" id="empathyLevel"></span>
          </div>
          <div class="type-score" id="empathyScore">0/5</div>
        </div>
        <div class="type-bar-container">
          <div class="type-bar empathy-bg" id="empathyBar" style="width: 0%"></div>
        </div>
        <div class="type-description">
          타인의 감정과 분위기에 민감하게 반응하는 정도
        </div>
        <button class="toggle-btn" onclick="toggleDetails('empathyDetails', this)">
          <span class="toggle-text">특징 보기</span> <span class="toggle-icon">▼</span>
        </button>
        <div class="type-details" id="empathyDetails">
          <strong>공감형 HSP의 특징:</strong>
          <ul>
            <li>타인의 감정 상태를 직관적으로 감지</li>
            <li>다른 사람의 고통이나 불편함을 자신의 것처럼 느낌</li>
            <li>예술, 음악, 문학에 깊은 감동을 받음</li>
            <li>갈등 상황이나 부정적인 뉴스에 강하게 영향받음</li>
            <li>타인의 기분에 따라 자신의 기분도 쉽게 변화</li>
            <li>사회적 분위기나 집단의 에너지를 빠르게 감지</li>
          </ul>
          <p style="margin-top: 10px;">공감형 HSP는 타인과의 정서적 연결이 강하며, 이는 깊은 인간관계를 형성하는 데 도움이 됩니다. 다만 감정적 소진을 방지하기 위한 경계 설정이 중요합니다.</p>
        </div>
      </div>
      
      <div class="type-item">
        <div class="type-header">
          <div class="type-title analytical-color">
            <span>🧠</span> 분석형 HSP
            <span class="type-level" id="analyticalLevel"></span>
          </div>
          <div class="type-score" id="analyticalScore">0/5</div>
        </div>
        <div class="type-bar-container">
          <div class="type-bar analytical-bg" id="analyticalBar" style="width: 0%"></div>
        </div>
        <div class="type-description">
          깊은 사고와 내적 처리에 관한 정도
        </div>
        <button class="toggle-btn" onclick="toggleDetails('analyticalDetails', this)">
          <span class="toggle-text">특징 보기</span> <span class="toggle-icon">▼</span>
        </button>
        <div class="type-details" id="analyticalDetails">
          <strong>분석형 HSP의 특징:</strong>
          <ul>
            <li>정보를 깊고 철저하게 처리하는 경향</li>
            <li>복잡한 문제나 개념에 대해 오래 생각함</li>
            <li>결정을 내리기 전에 모든 가능성을 고려</li>
            <li>세부 사항과 뉘앙스를 놓치지 않음</li>
            <li>철학적, 심리적, 존재적 질문에 깊은 관심</li>
            <li>상황이나 대화의 더 깊은 의미를 찾으려 함</li>
          </ul>
          <p style="margin-top: 10px;">분석형 HSP는 정보를 더 깊이 처리하고 통찰력이 뛰어납니다. 이는 창의적 문제 해결과 깊은 이해에 도움이 되지만, 때로는 과도한 분석으로 인한 결정 지연이나 불안을 경험할 수 있습니다.</p>
        </div>
      </div>
      
      <div class="type-item">
        <div class="type-header">
          <div class="type-title recovery-color">
            <span>🌱</span> 회복형 HSP
            <span class="type-level" id="recoveryLevel"></span>
          </div>
          <div class="type-score" id="recoveryScore">0/5</div>
        </div>
        <div class="type-bar-container">
          <div class="type-bar recovery-bg" id="recoveryBar" style="width: 0%"></div>
        </div>
        <div class="type-description">
          스트레스와 회복에 관한 정도
        </div>
        <button class="toggle-btn" onclick="toggleDetails('recoveryDetails', this)">
          <span class="toggle-text">특징 보기</span> <span class="toggle-icon">▼</span>
        </button>
        <div class="type-details" id="recoveryDetails">
          <strong>회복형 HSP의 특징:</strong>
          <ul>
            <li>스트레스 상황 후 혼자만의 시간이 필요함</li>
            <li>자극이 많은 환경에서 쉽게 피로해짐</li>
            <li>스트레스가 신체적 증상(두통, 소화 문제 등)으로 나타남</li>
            <li>충분한 휴식과 회복 시간이 필수적</li>
            <li>일과 휴식의 균형이 중요함</li>
            <li>조용한 환경에서 에너지를 재충전</li>
          </ul>
          <p style="margin-top: 10px;">회복형 HSP는 자극과 스트레스에 대한 회복 능력과 관련이 있습니다. 적절한 자기 관리와 경계 설정을 통해 과도한 자극으로부터 자신을 보호하는 것이 중요합니다.</p>
        </div>
      </div>
    </div>
    
    <button class="restart-btn" id="restartBtn">다시 테스트하기</button>
  </div>
  
  <div class="bottom-spacer"></div>

  <script>
    const questions = [
      "시끄러운 카페나 음식점에서 대화하기 힘들다고 느낀다.",
      "커피 한 잔만 마셔도 밤에 잠을 이루기 어렵다.",
      "갑자기 울리는 전화벨 소리에 심장이 쿵 내려앉는 느낌이 든다.",
      "친구가 말로 표현하지 않아도 기분이 안 좋다는 것을 알아차린다.",
      "백화점이나 마트에서 쇼핑을 오래 하면 금방 지친다.",
      "감동적인 영화나 음악을 접하면 쉽게 눈물이 난다.",
      "옷 태그가 살에 닿으면 신경이 쓰여 잘라버리는 편이다.",
      "다른 사람들보다 감정 기복이 크다고 느낀다.",
      "스트레스를 받으면 바로 두통이나 소화불량이 찾아온다.",
      "사람들과 어울린 후에는 혼자만의 시간이 꼭 필요하다.",
      "단체 채팅방에 알림이 많이 오면 부담스럽고 확인하기 싫다.",
      "하루 종일 사람들과 어울린 후에는 '충전'이 필요하다.",
      "영화관에서 옆 사람이 팝콘 먹는 소리가 크게 들린다.",
      "메뉴를 고르는 데 시간이 오래 걸리는 편이다.",
      "대화 후에 \"내가 말을 잘못했나?\"라고 자주 되돌아본다.",
      "친구가 새로운 헤어스타일을 했을 때 다른 사람보다 먼저 알아챈다.",
      "문자나 카톡을 받고 상대방의 숨은 의도를 곰곰이 생각한다.",
      "잠들기 전에 상상 속에서 다양한 이야기를 만들어낸다.",
      "친구들과 만나면 인생이나 사회에 대한 깊은 대화를 나누고 싶다.",
      "여행 가기 전에 계획을 세세하게 짜놓아야 마음이 편하다.",
      "발표나 중요한 일을 앞두면 실패하는 상황을 자꾸 상상하게 된다.",
      "영화를 본 후 다른 사람들보다 더 오래 생각하고 분석하는 편이다.",
      "다른 사람들은 괜찮아하는 형광등 깜빡임이나 냄새에 예민하게 반응한다.",
      "주말에는 혼자 집에서 조용히 시간을 보내는 것이 재충전에 도움이 된다.",
      "집안의 작은 변화(가구 위치, 새로운 소품)도 금방 알아차린다.",
      "뉴스에서 슬픈 사건을 접하면 하루 종일 마음이 무겁다.",
      "배고프면 다른 사람들보다 더 빨리 예민해지고 짜증이 난다.",
      "목에 꽉 끼는 옷이나 거친 소재의 옷을 입으면 하루 종일 불편하다.",
      "주변 사람이 우울해하면 나도 같이 기분이 가라앉는다.",
      "갑작스러운 일정 변경이 생기면 적응하는 데 시간이 필요하다."
    ];

    // 질문 유형 분류
    const questionTypes = {
      sensory: [0, 1, 2, 4, 6, 12, 22, 24, 27], // 감각형 HSP
      empathy: [3, 5, 7, 16, 25, 28], // 공감형 HSP
      analytical: [14, 15, 17, 18, 21], // 분석형 HSP
      recovery: [8, 9, 10, 11, 13, 19, 20, 23, 26, 29] // 회복형 HSP
    };

    const meanings = {
      1: "전혀 아니다",
      2: "아니다",
      3: "보통이다",
      4: "그렇다",
      5: "매우 그렇다"
    };

    // 5단계 민감도 구분
    const sensitivityLevels = [
      { max: 75, category: "매우 낮음", class: "category-very-low", description: "당신은 HSP 성향이 매우 낮은 편입니다. 외부 자극에 거의 영향을 받지 않으며, 스트레스가 많은 환경에서도 쉽게 적응합니다. 감각적 자극을 처리하는 데 어려움이 거의 없고, 다양한 환경에서 편안함을 느낄 수 있습니다." },
      { max: 90, category: "낮음", class: "category-low", description: "당신은 HSP 성향이 낮은 편입니다. 대부분의 외부 자극에 크게 영향을 받지 않으며, 다양한 환경에 적응하는 능력이 있습니다. 때때로 특정 자극에 민감할 수 있지만, 일상생활에 큰 영향을 주지는 않습니다." },
      { max: 110, category: "보통", class: "category-medium", description: "당신은 HSP 성향이 보통 수준입니다. 상황에 따라 민감하게 반응할 수 있지만, 대체로 균형 잡힌 감각 처리 능력을 가지고 있습니다. 때로는 감각적 자극에 민감할 수 있으나, 적절히 대처하는 방법을 알고 있을 가능성이 높습니다." },
      { max: 130, category: "높음", class: "category-high", description: "당신은 HSP 성향이 높은 편입니다. 외부 자극에 민감하게 반응하며, 다른 사람들보다 더 깊게 정보를 처리하는 경향이 있습니다. 풍부한 내적 세계와 예민한 감각을 가지고 있으며, 이는 창의성과 공감 능력의 원천이 될 수 있습니다. 자기 관리와 적절한 휴식이 중요합니다." },
      { max: 150, category: "매우 높음", class: "category-very-high", description: "당신은 HSP 성향이 매우 높은 편입니다. 외부 자극에 매우 민감하게 반응하며, 정보를 매우 깊고 복잡하게 처리합니다. 뛰어난 공감 능력과 직관, 창의성을 가지고 있지만, 쉽게 압도되거나 소진될 수 있습니다. 자신의 민감성을 이해하고 적절한 경계를 설정하는 것이 매우 중요합니다." }
    ];

    // 유형별 점수 수준 구분
    const typeLevels = [
      { percent: 40, level: "매우 낮음", class: "type-level-very-low" },
      { percent: 55, level: "낮음", class: "type-level-low" },
      { percent: 70, level: "보통", class: "type-level-medium" },
      { percent: 85, level: "높음", class: "type-level-high" },
      { percent: 100, level: "매우 높음", class: "type-level-very-high" }
    ];

    // 페이지네이션 관련 변수
    const questionsPerPage = 6;
    let currentPage = 1;
    const totalPages = Math.ceil(questions.length / questionsPerPage);
    
    // 사용자 응답을 저장할 객체
    const userAnswers = {};

    const questionsContainer = document.getElementById('questions');
    const resultContainer = document.getElementById('result');
    const progressBar = document.getElementById('progress');
    const form = document.getElementById('hspForm');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    const submitBtn = document.getElementById('submitBtn');
    const pageIndicator = document.getElementById('pageIndicator');
    const restartBtn = document.getElementById('restartBtn');
    const shareBtn = document.getElementById('shareBtn');
    const copyNotification = document.getElementById('copyNotification');

    // 테스트 공유하기 함수
    shareBtn.addEventListener('click', function() {
      const shareUrl = "https://kimcho2.tistory.com/m/20";
      
      // 클립보드에 복사
      navigator.clipboard.writeText(shareUrl)
        .then(() => {
          // 복사 완료 알림 표시
          copyNotification.classList.add('show');
          
          // 3초 후 알림 숨기기
          setTimeout(() => {
            copyNotification.classList.remove('show');
          }, 2000);
        })
        .catch(err => {
          console.error('클립보드 복사 실패:', err);
          alert('링크 복사에 실패했습니다. 직접 주소를 복사해주세요: ' + shareUrl);
        });
    });

    // 특징 펼쳐보기 토글 함수
    function toggleDetails(id, button) {
      const details = document.getElementById(id);
      const icon = button.querySelector('.toggle-icon');
      const toggleText = button.querySelector('.toggle-text');
      
      details.classList.toggle('show');
      icon.classList.toggle('rotate');
      
      if (details.classList.contains('show')) {
        toggleText.textContent = '특징 접기';
      } else {
        toggleText.textContent = '특징 보기';
      }
    }

    // 질문 생성 함수
    function createQuestions() {
      questionsContainer.innerHTML = '';
      
      const startIndex = (currentPage - 1) * questionsPerPage;
      const endIndex = Math.min(startIndex + questionsPerPage, questions.length);
      
      for (let i = startIndex; i < endIndex; i++) {
        const questionDiv = document.createElement('div');
        questionDiv.className = 'question';
        
        const id = `q${i}`;
        const value = userAnswers[id] || 3; // 저장된 값이 있으면 사용, 없으면 기본값 3
        
        questionDiv.innerHTML = `
          <div class="question-text">${i + 1}. ${questions[i]}</div>
          <div class="slider-container">
            <div class="slider-track"></div>
            <input type="range" min="1" max="5" value="${value}" name="${id}" id="${id}" oninput="updateValue(this)" />
            <div class="range-value">선택: <span id="${id}_val">${meanings[value]}</span></div>
          </div>
        `;
        
        questionsContainer.appendChild(questionDiv);
      }
      
      // 페이지 표시 업데이트
      pageIndicator.textContent = `${currentPage}/${totalPages}`;
      
      // 버튼 상태 업데이트
      prevBtn.disabled = currentPage === 1;
      
      if (currentPage === totalPages) {
        nextBtn.style.display = 'none';
        submitBtn.style.display = 'block';
      } else {
        nextBtn.style.display = 'block';
        submitBtn.style.display = 'none';
      }
      
      // 진행 상태 업데이트
      updateProgress();
    }

    // 슬라이더 값 업데이트 함수
    function updateValue(slider) {
      const value = slider.value;
      document.getElementById(`${slider.id}_val`).textContent = meanings[value];
      
      // 사용자 응답 저장
      userAnswers[slider.id] = parseInt(value);
      
      updateProgress();
    }

    // 현재 페이지의 응답 저장
    function saveCurrentPageAnswers() {
      const startIndex = (currentPage - 1) * questionsPerPage;
      const endIndex = Math.min(startIndex + questionsPerPage, questions.length);
      
      for (let i = startIndex; i < endIndex; i++) {
        const id = `q${i}`;
        const slider = document.getElementById(id);
        if (slider) {
          userAnswers[id] = parseInt(slider.value);
        }
      }
    }

    // 진행 상태 업데이트 함수
    function updateProgress() {
      const totalQuestions = questions.length;
      let answeredQuestions = 0;
      
      // 모든 응답 확인
      for (const key in userAnswers) {
        if (userAnswers[key] !== 3) { // 기본값이 아닌 경우만 카운트
          answeredQuestions++;
        }
      }
      
      const progress = (answeredQuestions / totalQuestions) * 100;
      progressBar.style.width = `${progress}%`;
    }

    // 이전 페이지 버튼
    prevBtn.addEventListener('click', () => {
      if (currentPage > 1) {
        saveCurrentPageAnswers(); // 현재 페이지 응답 저장
        currentPage--;
        createQuestions();
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    });

    // 다음 페이지 버튼
    nextBtn.addEventListener('click', () => {
      if (currentPage < totalPages) {
        saveCurrentPageAnswers(); // 현재 페이지 응답 저장
        currentPage++;
        createQuestions();
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    });

    // 유형별 점수 계산 함수
    function calculateTypeScores() {
      const scores = {
        sensory: 0,
        empathy: 0,
        analytical: 0,
        recovery: 0
      };
      
      // 각 유형별 점수 계산
      for (const type in questionTypes) {
        let typeTotal = 0;
        questionTypes[type].forEach(qIndex => {
          const id = `q${qIndex}`;
          if (userAnswers[id]) {
            typeTotal += userAnswers[id];
          } else {
            typeTotal += 3; // 응답하지 않은 문항은 기본값 3으로 처리
          }
        });
        scores[type] = typeTotal;
      }
      
      return scores;
    }

    // 유형별 수준 결정 함수
    function determineTypeLevel(score, maxScore) {
      const percent = (score / maxScore) * 100;
      
      for (let i = 0; i < typeLevels.length; i++) {
        if (percent <= typeLevels[i].percent) {
          return typeLevels[i];
        }
      }
      
      return typeLevels[typeLevels.length - 1]; // 최대값보다 큰 경우 마지막 레벨
    }

    // 유형별 결과 표시 함수
    function displayTypeResults(scores) {
      // 감각형 HSP
      const sensoryMax = questionTypes.sensory.length * 5;
      const sensoryPercent = (scores.sensory / sensoryMax) * 100;
      document.getElementById('sensoryScore').textContent = `${scores.sensory}/${sensoryMax}`;
      document.getElementById('sensoryBar').style.width = `${sensoryPercent}%`;
      
      // 감각형 수준 표시
      const sensoryLevel = determineTypeLevel(scores.sensory, sensoryMax);
      const sensoryLevelEl = document.getElementById('sensoryLevel');
      sensoryLevelEl.textContent = sensoryLevel.level;
      sensoryLevelEl.className = `type-level ${sensoryLevel.class}`;
      
      // 공감형 HSP
      const empathyMax = questionTypes.empathy.length * 5;
      const empathyPercent = (scores.empathy / empathyMax) * 100;
      document.getElementById('empathyScore').textContent = `${scores.empathy}/${empathyMax}`;
      document.getElementById('empathyBar').style.width = `${empathyPercent}%`;
      
      // 공감형 수준 표시
      const empathyLevel = determineTypeLevel(scores.empathy, empathyMax);
      const empathyLevelEl = document.getElementById('empathyLevel');
      empathyLevelEl.textContent = empathyLevel.level;
      empathyLevelEl.className = `type-level ${empathyLevel.class}`;
      
      // 분석형 HSP
      const analyticalMax = questionTypes.analytical.length * 5;
      const analyticalPercent = (scores.analytical / analyticalMax) * 100;
      document.getElementById('analyticalScore').textContent = `${scores.analytical}/${analyticalMax}`;
      document.getElementById('analyticalBar').style.width = `${analyticalPercent}%`;
      
      // 분석형 수준 표시
      const analyticalLevel = determineTypeLevel(scores.analytical, analyticalMax);
      const analyticalLevelEl = document.getElementById('analyticalLevel');
      analyticalLevelEl.textContent = analyticalLevel.level;
      analyticalLevelEl.className = `type-level ${analyticalLevel.class}`;
      
      // 회복형 HSP
      const recoveryMax = questionTypes.recovery.length * 5;
      const recoveryPercent = (scores.recovery / recoveryMax) * 100;
      document.getElementById('recoveryScore').textContent = `${scores.recovery}/${recoveryMax}`;
      document.getElementById('recoveryBar').style.width = `${recoveryPercent}%`;
      
      // 회복형 수준 표시
      const recoveryLevel = determineTypeLevel(scores.recovery, recoveryMax);
      const recoveryLevelEl = document.getElementById('recoveryLevel');
      recoveryLevelEl.textContent = recoveryLevel.level;
      recoveryLevelEl.className = `type-level ${recoveryLevel.class}`;
      
      // 애니메이션 효과를 위한 지연 설정
      setTimeout(() => {
        document.getElementById('sensoryBar').style.width = `${sensoryPercent}%`;
        document.getElementById('empathyBar').style.width = `${empathyPercent}%`;
        document.getElementById('analyticalBar').style.width = `${analyticalPercent}%`;
        document.getElementById('recoveryBar').style.width = `${recoveryPercent}%`;
      }, 100);
    }

    // 민감도 수준 표시 함수
    function displaySensitivityLevel(totalScore) {
      // 민감도 수준 결정
      let levelIndex = 0;
      for (let i = 0; i < sensitivityLevels.length; i++) {
        if (totalScore <= sensitivityLevels[i].max) {
          levelIndex = i;
          break;
        }
        
        // 최대값보다 큰 경우 마지막 레벨
        if (i === sensitivityLevels.length - 1) {
          levelIndex = i;
        }
      }
      
      // 해당 레벨 활성화
      const levels = document.querySelectorAll('.sensitivity-level');
      levels[levelIndex].classList.add('active-level');
      
      return levelIndex;
    }

    // 폼 제출 처리
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      
      // 마지막 페이지 응답 저장
      saveCurrentPageAnswers();
      
      let totalScore = 0;
      
      // 모든 질문의 점수 합산
      for (let i = 0; i < questions.length; i++) {
        const id = `q${i}`;
        if (userAnswers[id]) {
          totalScore += userAnswers[id];
        } else {
          totalScore += 3; // 응답하지 않은 문항은 기본값 3으로 처리
        }
      }
      
      // 결과 표시
      const resultScore = document.getElementById('resultScore');
      const resultCategory = document.getElementById('resultCategory');
      const resultDescription = document.getElementById('resultDescription');
      
      resultScore.textContent = `총점: ${totalScore}점`;
      
      // 민감도 수준 표시
      const levelIndex = displaySensitivityLevel(totalScore);
      const level = sensitivityLevels[levelIndex];
      
      // 카테고리 및 설명 설정
      resultCategory.textContent = level.category;
      resultCategory.className = `result-category ${level.class}`;
      resultDescription.textContent = level.description;
      
      // 유형별 점수 계산 및 표시
      const typeScores = calculateTypeScores();
      displayTypeResults(typeScores);
      
      // 결과 표시
      document.querySelector('.container').style.display = 'none';
      resultContainer.style.display = 'block';
      
      // 페이지 상단으로 스크롤
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // 다시 테스트하기 버튼
    restartBtn.addEventListener('click', () => {
      // 모든 응답 초기화
      for (let i = 0; i < questions.length; i++) {
        userAnswers[`q${i}`] = 3;
      }
      
      // 진행 상태 초기화
      progressBar.style.width = '0%';
      
      // 첫 페이지로 돌아가기
      currentPage = 1;
      createQuestions();
      
      // 민감도 레벨 활성화 상태 초기화
      const levels = document.querySelectorAll('.sensitivity-level');
      levels.forEach(level => level.classList.remove('active-level'));
      
      // 폼 표시, 결과 숨김
      document.querySelector('.container').style.display = 'block';
      resultContainer.style.display = 'none';
    });

    // 초기 질문 생성
    createQuestions();
  </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'964429fca674ea04',t:'MTc1MzM2NzkzNS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

