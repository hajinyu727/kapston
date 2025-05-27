<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LA CUCARACHA</title>
  <style>
    body {
      margin: 0;
      font-family: sans-serif;
      background: #fff;
      color: #333;
    }
    header {
      background: linear-gradient(to right, red, orange, green);
      color: white;
      text-align: center;
      padding: 1rem;
      font-size: 1.5rem;
      font-weight: bold;
    }
    .container {
      padding: 2rem;
      text-align: center;
    }
    .btn {
      display: inline-block;
      margin: 0.5rem;
      padding: 1rem 2rem;
      font-size: 1rem;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.2s;
    }
    .btn:hover {
      transform: scale(1.05);
    }
    .btn.red { background-color: #d32f2f; }
    .btn.orange { background-color: #f57c00; }
    .btn.green { background-color: #388e3c; }
    .hidden { display: none; }
    .back {
      margin-top: 2rem;
      background: #ccc;
      color: #000;
    }
    input, select {
      margin: 0.5rem;
      padding: 0.5rem;
      width: 80%;
      max-width: 400px;
    }
    label {
      display: block;
      margin-top: 1rem;
      font-weight: bold;
    }
    input[type="date"],
    input[type="datetime-local"] {
      -webkit-appearance: none;
      appearance: none;
      cursor: pointer;
    }
    .currency-icons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin: 1rem 0;
    }
    .currency-icons div {
      padding: 1rem;
      border: 1px solid #ccc;
      border-radius: 8px;
      width: 80px;
    }
  </style>
</head>
<body>
  <header>LA CUCARACHA</header>

  <div id="page-language" class="container">
    <h2>언어를 선택해주세요</h2>
    <div id="langButtons"></div>
  </div>

  <div id="page-service" class="container hidden">
    <h2>원하시는 서비스를 선택하세요</h2>
    <button class="btn red" onclick="goToPage('exchange')">💱 수수료 없는 외화 환전</button>
    <button class="btn orange" onclick="goToPage('transport')">🚗 빠른 교통수단 예약</button>
    <button class="btn green" onclick="goToPage('racha')">💳 라차카드 서비스</button>
    <button class="btn red" onclick="goToPage('support')">📞 기타 고객지원</button>
    <button class="btn back" onclick="goBack('language')">🔙 뒤로가기</button>
  </div>

  <div id="page-exchange" class="container hidden">
    <h2>✈ 한국 여행의 시작, 더 간편하게!</h2>
    <p>💸 수수료 0원 외화 환전<br>🚆 버스·지하철·기차 바로 탑승<br>💳 카드 하나로 한국 여행 끝!</p>
    <p>👉 QR코드를 스캔해서 바로 신청하세요!</p>
    <h3>외화를 선택하세요</h3>
    <div class="currency-icons">
      <div>USD</div><div>RMB</div><div>JPY</div><div>VND</div>
      <div>THB</div><div>UZS</div><div>KHR</div><div>PHP</div>
      <div>IDR</div><div>NPR</div>
    </div>
    <button class="btn back" onclick="goBack('service')">🔙 뒤로가기</button>
  </div>

  <div id="page-transport" class="container hidden">
    <h2>교통수단을 선택하세요</h2>
    <button class="btn red" onclick="goToPage('bus')">🚌 버스</button>
    <button class="btn orange" onclick="goToPage('plane')">✈ 비행기</button>
    <button class="btn green" onclick="goToPage('taxi')">🚕 택시</button>
    <button class="btn red" onclick="goToPage('ktx')">🚄 KTX</button>
    <button class="btn back" onclick="goBack('service')">🔙 뒤로가기</button>
  </div>

  <div id="page-bus" class="container hidden">
    <h2>🚌 버스 예약</h2>
    <label>출발지</label>
    <input placeholder="출발지" />
    <label>도착지</label>
    <input placeholder="도착지" />
    <label>날짜</label>
    <input type="date" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>
  <div id="page-plane" class="container hidden">
    <h2>✈ 비행기 예약</h2>
    <label>출발 공항</label>
    <input placeholder="출발 공항" />
    <label>도착 공항</label>
    <input placeholder="도착 공항" />
    <label>날짜</label>
    <input type="date" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>
  <div id="page-taxi" class="container hidden">
    <h2>🚕 택시 예약</h2>
    <label>픽업 위치</label>
    <input placeholder="픽업 위치" />
    <label>도착 위치</label>
    <input placeholder="도착 위치" />
    <label>날짜 및 시간</label>
    <input type="datetime-local" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>
  <div id="page-ktx" class="container hidden">
    <h2>🚄 KTX 예약</h2>
    <label>출발역</label>
    <input placeholder="출발역" />
    <label>도착역</label>
    <input placeholder="도착역" />
    <label>날짜</label>
    <input type="date" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha" class="container hidden">
    <h2>라차카드 서비스</h2>
    <button class="btn red" onclick="goToPage('racha-join')">카드 가입</button>
    <button class="btn orange" onclick="goToPage('racha-point')">포인트 안내</button>
    <button class="btn green" onclick="goToPage('racha-lost')">카드 분실</button>
    <button class="btn orange" onclick="goToPage('racha-guide')">이용 방법</button>
    <button class="btn back" onclick="goBack('service')">🔙 뒤로가기</button>
  </div>

  <!-- 이하 동일하게 유지 (등록/포인트/분실/가이드 등 페이지는 input 변경 사항 없음) -->

  <script>
    const languages = [
      {name: "한국어", class: "green"},
      {name: "English", class: "red"},
      {name: "中文", class: "orange"},
      {name: "日本語", class: "green"},
      {name: "Tiếng Việt", class: "red"},
      {name: "ภาษาไทย", class: "orange"},
      {name: "Oʻzbekcha", class: "green"},
      {name: "ភាសាខ្មែរ", class: "red"},
      {name: "Filipino", class: "orange"},
      {name: "Bahasa Indonesia", class: "green"},
      {name: "नेपाली", class: "red"},
    ];
    const langButtonsContainer = document.getElementById("langButtons");
    languages.forEach(lang => {
      const btn = document.createElement("button");
      btn.textContent = lang.name;
      btn.className = `btn ${lang.class}`;
      btn.onclick = () => goToPage("service");
      langButtonsContainer.appendChild(btn);
    });

    function goToPage(pageId) {
      document.querySelectorAll(".container").forEach(div => {
        div.classList.add("hidden");
      });
      const page = document.getElementById(`page-${pageId}`);
      if (page) page.classList.remove("hidden");
      window.scrollTo(0, 0);
    }

    function goBack(fromPage) {
      const map = {
        language: "language",
        service: "service",
        exchange: "service",
        transport: "service",
        racha: "service",
        "racha-join": "racha",
        "racha-apply": "racha-join",
        "racha-register": "racha-join",
        "racha-point": "racha",
        "racha-lost": "racha",
        "racha-guide": "racha",
        bus: "transport",
        plane: "transport",
        taxi: "transport",
        ktx: "transport",
        support: "service",
      };
      goToPage(map[fromPage] || "language");
    }
  </script>
</body>
</html>
