<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>LA CUCARACHA</title>
  <style>
    input[type="date"],
input[type="datetime-local"] {
  width: 90%;
  max-width: 400px;
  min-width: 250px;
  font-size: 1rem;
  padding: 0.75rem;
  box-sizing: border-box;
}
    body {
      margin: 0;
      font-family: sans-serif;
      background: #fff;
      color: #333;
      overflow-x: hidden;
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
      padding: 1.5rem;
      text-align: center;
      max-width: 100%;
      box-sizing: border-box;
    }
    .btn {
      display: block;
      margin: 0.5rem auto;
      padding: 1rem;
      font-size: 1rem;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      width: 90%;
      max-width: 300px;
      transition: transform 0.2s;
      box-sizing: border-box;
    }
    .btn:hover {
      transform: scale(1.05);
    }
    .btn.red { background-color: #d32f2f; }
    .btn.orange { background-color: #f57c00; }
    .btn.green { background-color: #388e3c; }
    .hidden { display: none; }
    .back {
      margin-top: 1rem;
      background: #ccc;
      color: #000;
    }
    input, select {
      margin: 0.5rem auto;
      padding: 0.75rem;
      width: 90%;
      max-width: 400px;
      font-size: 1rem;
      display: block;
      box-sizing: border-box;
    }
    .currency-icons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      margin: 1rem 0;
    }
    .currency-icons div {
      padding: 0.75rem;
      border: 1px solid #ccc;
      border-radius: 8px;
      width: 70px;
      font-size: 0.9rem;
      background: #f9f9f9;
    }
  </style>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
<script src="https://cdn.jsdelivr.net/npm/flatpickr">document.addEventListener("DOMContentLoaded", function () {
  flatpickr("input[type='date'], input[type='datetime-local']", {
    dateFormat: "Y-m-d",
    enableTime: false,
    locale: "ko" // 한국어 설정 필요시
  });

  flatpickr("input[type='datetime-local']", {
    enableTime: true,
    dateFormat: "Y-m-d H:i",
    locale: "ko"
  });
});</script>
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
    <input placeholder="출발지" />
    <input placeholder="도착지" />
    <input type="date" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>

  <div id="page-plane" class="container hidden">
    <h2>✈ 비행기 예약</h2>
    <input placeholder="출발 공항" />
    <input placeholder="도착 공항" />
    <input type="date" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>

  <div id="page-taxi" class="container hidden">
    <h2>🚕 택시 예약</h2>
    <input placeholder="픽업 위치" />
    <input placeholder="도착 위치" />
    <input type="datetime-local" />
    <button class="btn">예약하기</button>
    <button class="btn back" onclick="goBack('transport')">🔙 뒤로가기</button>
  </div>

  <div id="page-ktx" class="container hidden">
    <h2>🚄 KTX 예약</h2>
    <input placeholder="출발역" />
    <input placeholder="도착역" />
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

  <div id="page-racha-join" class="container hidden">
    <h2>라차카드 가입/등록</h2>
    <button class="btn red" onclick="goToPage('racha-apply')">카드를 신청하시겠습니까?</button>
    <button class="btn orange" onclick="goToPage('racha-register')">카드를 등록하시겠습니까?</button>
    <button class="btn back" onclick="goBack('racha')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha-apply" class="container hidden">
    <h2>카드 신청</h2>
    <input placeholder="이름" />
    <input placeholder="카드를 받을 주소" />
    <input type="email" placeholder="이메일" />
    <button class="btn red">신청하기</button>
    <button class="btn back" onclick="goBack('racha-join')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha-register" class="container hidden">
    <h2>카드 등록</h2>
    <input placeholder="이름" />
    <input type="email" placeholder="이메일" />
    <input placeholder="생년월일" />
    <input placeholder="카드 포스틱 6자리 숫자" />
    <input placeholder="카드 번호" />
    <input placeholder="카드 결제일 (MM/YY)" />
    <button class="btn orange">등록하기</button>
    <button class="btn back" onclick="goBack('racha-join')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha-point" class="container hidden">
    <h2>포인트 조회</h2>
    <input placeholder="카드 번호 입력" />
    <button class="btn red">조회</button>
    <p>현재 포인트: 3,500P</p>
    <button class="btn back" onclick="goBack('racha')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha-lost" class="container hidden">
    <h2>카드 분실 안내</h2>
    <p>카드 분실 시 고객센터로 즉시 연락해주세요.<br>전화: 1234-5678 / 이메일: help@lacucaracha.com</p>
    <button class="btn back" onclick="goBack('racha')">🔙 뒤로가기</button>
  </div>

  <div id="page-racha-guide" class="container hidden">
    <h2>자주 묻는 질문 (Q&A)</h2>
    <p><strong>Q. 당일 예매도 가능한가요?</strong><br>A. 1일 뒤 출발부터 최대 한 달 이내까지 가능해요.</p>
    <p><strong>Q. 청소년도 할인 가능한가요?</strong><br>A. 어른 요금만 할인이 가능해요.</p>
    <p><strong>Q. 적립금은 언제 적립되나요?</strong><br>A. 기차 출발 다음날 적립되며 기간은 1년간 유효해요.</p>
    <button class="btn back" onclick="goBack('racha')">🔙 뒤로가기</button>
  </div>

  <div id="page-support" class="container hidden">
    <h2>상담원 연결 안내</h2>
    <p>도움이 필요하신가요? 전화 또는 채팅으로 상담원을 만나보세요.</p>
    <button class="btn back" onclick="goBack('service')">🔙 뒤로가기</button>
  </div>

  <script>
    const languages = [
      {name: "한국어", class: "red"},
      {name: "English", class: "orange"},
      {name: "中文", class: "green"},
      {name: "日本語", class: "red"},
      {name: "Tiếng Việt", class: "orange"},
      {name: "ภาษาไทย", class: "green"},
      {name: "Oʻzbekcha", class: "red"},
      {name: "ភាសាខ្មែរ", class: "orange"},
      {name: "Filipino", class: "green"},
      {name: "Bahasa Indonesia", class: "red"},
      {name: "नेपाली", class: "orange"},
    ];
    const langButtonsContainer = document.getElementById("langButtons");
    languages.forEach(lang => {
      const btn = document.createElement("button");
      btn.textContent = lang.name;
      btn.className = "btn " + lang.class;
      btn.onclick = () => goToPage("service");
      langButtonsContainer.appendChild(btn);
    });

    function goToPage(pageId) {
      document.querySelectorAll(".container").forEach(div => {
        div.classList.add("hidden");
      });
      const page = document.getElementById("page-" + pageId);
      if (page) page.classList.remove("hidden");
      window.scrollTo(0, 0);
    }

    function goBack(fromPage) {
      const map = {
        language: "language",
        service: "language",
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
