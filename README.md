<html lang="th">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>เกมการ์ดคิดวิเคราะห์หลักการตลาด 4P</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Prompt:wght@400;600&display=swap');

  body {
    font-family: 'Prompt', sans-serif;
    background: linear-gradient(135deg, #89f7fe 0%, #66a6ff 100%);
    text-align: center;
    padding: 25px 15px;
    color: #333;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
  }

  h1, h2, h3, h4 {
    margin: 30px 0 30px;
    font-weight: 600;
    color: #2c3e50;
  }

  h1 {
    font-size: 2.8rem;
  }

  h2 {
    font-size: 2rem;
  }

  h3 {
    font-size: 1.3rem;
  }

  h4 {
    font-size: 1.1rem;
    color: #555;
  }

  .card, .start-screen, .end-screen {
    background: white;
    margin: 15px auto;
    padding: 60px 180px;
    border-radius: 20px;
    box-shadow:
      0 8px 16px rgba(0,0,0,0.15),
      inset 0 0 10px rgba(102, 166, 255, 0.2);
    max-width: 720px;
    width: 100%;
    position: relative;
    transition: box-shadow 0.3s ease;
  }

  .card:hover, .start-screen:hover, .end-screen:hover {
    box-shadow:
      0 12px 24px rgba(0,0,0,0.25),
      inset 0 0 20px rgba(102, 166, 255, 0.3);
  }

  button {
    margin: 12px 10px;
    padding: 14px 28px;
    font-size: 17px;
    font-weight: 600;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    background: linear-gradient(45deg, #4facfe, #00f2fe);
    color: white;
    box-shadow: 0 4px 12px rgba(0, 255, 255, 0.4);
    transition: background 0.3s ease, transform 0.15s ease;
    user-select: none;
  }

  button:hover {
    background: linear-gradient(45deg, #00f2fe, #4facfe);
    transform: translateY(-3px);
    box-shadow: 0 6px 15px rgba(0, 255, 255, 0.6);
  }

  button:active {
    transform: translateY(1px);
    box-shadow: 0 2px 6px rgba(0, 255, 255, 0.3);
  }

  input {
    padding: 14px 18px;
    border-radius: 14px;
    width: 70%;
    max-width: 350px;
    font-size: 17px;
    border: 2px solid #4facfe;
    outline-color: #00f2fe;
    transition: border-color 0.3s ease;
    box-shadow: inset 1px 1px 8px rgba(102, 166, 255, 0.2);
  }

  input:focus {
    border-color: #00f2fe;
    box-shadow: 0 0 8px #00f2fe;
  }

  #timer {
    font-size: 20px;
    color: #e74c3c;
    font-weight: 700;
    margin-top: 15px;
    letter-spacing: 1.2px;
    text-shadow: 1px 1px 3px rgba(255, 255, 255, 0.7);
  }

  #score {
    font-size: 22px;
    color: #27ae60;
    font-weight: 700;
    margin: 15px 0;
    text-shadow: 1px 1px 3px rgba(255, 255, 255, 0.7);
  }

  #feedback {
    font-size: 20px;
    font-weight: 700;
    margin-top: 18px;
    height: 30px;
    color: #34495e;
    transition: color 0.3s ease;
  }

  #explosion {
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: rgba(255, 69, 58, 0.9);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 20px;
    font-size: 50px;
    color: #ffd700;
    font-weight: 900;
    z-index: 10;
    display: none;
    flex-direction: column;
    text-shadow: 2px 2px 6px #000;
    user-select: none;
  }

  #explosion img {
    width: 160px;
    margin-bottom: 18px;
    filter: drop-shadow(0 0 6px #ffd700);
  }

  table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0 8px;
    margin-top: 22px;
    font-size: 1.05rem;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    border-radius: 12px;
    overflow: hidden;
  }

  thead tr {
    background: linear-gradient(90deg, #4facfe, #00f2fe);
    color: white;
  }

  th, td {
    padding: 12px 18px;
    text-align: center;
  }

  tbody tr {
    background: #fff;
    transition: background-color 0.3s ease;
    box-shadow: 0 3px 6px rgba(0,0,0,0.05);
    border-radius: 10px;
  }

  .correct-row {
    background-color: #d4edda !important;
    color: #155724;
    font-weight: 600;
    box-shadow: 0 4px 8px #a1d99b;
  }

  .incorrect-row {
    background-color: #f8d7da !important;
    color: #721c24;
    font-weight: 600;
    box-shadow: 0 4px 8px #f5b7b1;
  }

  /* Responsive */
  @media (max-width: 768px) {
    .card, .start-screen, .end-screen {
      padding: 25px 20px;
      max-width: 95%;
    }

    button {
      width: 90%;
      max-width: 280px;
      margin: 10px auto;
      display: block;
    }

    input {
      width: 90%;
      max-width: none;
      margin-bottom: 15px;
    }
  }
</style>
</head>
<body>

<div class="start-screen" id="startScreen">
  <h1>🎓 เกมการ์ดคิดวิเคราะห์ </h1>
  <h1>(หลักการตลาด 4P)</h1>
  <p>ป้อนเลขที่ ชื่อผู้เล่น:</p>
  <input id="playerName" placeholder="เช่น 00 ปรมา" />
  <br><br>
  <button onclick="startGame()">เริ่มเกม</button>
</div>

<div class="card" id="questionCard" style="display:none;">
  <h1>🧩 สถานการณ์</h1>
  <h3 id="situation" style="white-space: pre-line;"></h3>
  <h1>🔎 ความต้องการ</h1>
  <h3 id="requirement" style="white-space: pre-line;"></h3>
  <h1>💡 แนวทางแก้ไข</h1>
  <h3 id="solution" style="white-space: pre-line;"></h3>
  <h4>แนวทางนี้เหมาะสมหรือไม่?</h4>
  <button onclick="checkAnswer(true)">✅ เหมาะสม</button>
  <button onclick="checkAnswer(false)">❌ ไม่เหมาะสม</button>
  <p id="feedback"></p>
  <p id="score">คะแนน: 0</p>
  <p id="timer"></p>

  <div id="explosion">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d7/Explosion_icon.svg/240px-Explosion_icon.svg.png" alt="Explosion" />
    <div>💥 หมดเวลาหมดเกม! 💥</div>
  </div>
</div>

<div class="end-screen" id="endScreen" style="display:none;">
  <h1>🎉 จบเกม!</h1>
  <h2 id="finalScore"></h2>

  <h3>📋 สรุปผลการตอบคำถาม</h3>
  <table>
    <thead>
      <tr>
        <th>ข้อ</th>
        <th>คำตอบของผู้เล่น</th>
        <th>คำตอบที่ถูกต้อง</th>
        <th>ผลลัพธ์</th>
      </tr>
    </thead>
    <tbody id="answerSummary"></tbody>
  </table>

  <!--<h3>🏆 อันดับผู้เล่น</h3>
  <ol id="rankingList"></ol>
  <button onclick="startGameFromEnd()">🔁 เริ่มการแข่งขันใหม่</button>
  <button onclick="clearRanking()">🗑️ เคลียร์อันดับ</button>
  <br>-->
  <button onclick="goToHome()">🏠 กลับหน้าแรก</button>
</div>

<script>
  const correctSound = new Audio("https://cdn.pixabay.com/audio/2021/08/04/audio_fce2b2a5df.mp3");
  const wrongSound = new Audio("https://cdn.pixabay.com/audio/2022/03/15/audio_d166fe4c1d.mp3");

  const allQuestions = [
    {
      situation: `บริษัทผลิตเครื่องดื่มเพื่อสุขภาพแห่งหนึ่งพบว่าผลิตภัณฑ์ของตนไม่ค่อยได้รับความนิยมในกลุ่มวัยรุ่น 
เนื่องจากบรรจุภัณฑ์ดูธรรมดาและไม่ดึงดูดใจผู้บริโภคเป้าหมายที่ชอบดีไซน์ทันสมัยและแปลกใหม่`,
      requirement: `ปรับปรุงภาพลักษณ์ผลิตภัณฑ์เพื่อดึงดูดกลุ่มลูกค้าวัยรุ่น`,
      solution: `ออกแบบบรรจุภัณฑ์ใหม่ให้ทันสมัยและมีสีสันสดใส`,
      correct: true
    },
    {
      situation: `ร้านค้าออนไลน์ที่จำหน่ายเครื่องใช้ไฟฟ้าพบว่า ลูกค้าระบุว่าค่าจัดส่งสูงเกินไป และมีการเปรียบเทียบกับคู่แข่งที่คิดค่าจัดส่งถูกกว่า 
ทำให้ยอดขายสินค้าลดลงในช่วงเทศกาล`,
      requirement: `ปรับกลยุทธ์การตั้งราคาค่าจัดส่งเพื่อเพิ่มยอดขายในช่วงเทศกาล`,
      solution: `กำหนดค่าจัดส่งแบบเหมาแพงขึ้นในช่วงเทศกาลเพื่อเพิ่มกำไร`,
      correct: false
    },
    {
      situation: `บริษัทขายเสื้อผ้ากีฬาแห่งหนึ่งต้องการขยายตลาดไปยังต่างจังหวัดที่มีร้านค้าปลีกน้อย และลูกค้าส่วนใหญ่ชอบซื้อสินค้าผ่านร้านค้าท้องถิ่น 
ที่คุ้นเคยมากกว่า`,
      requirement: `เพิ่มช่องทางการจัดจำหน่ายเพื่อเข้าถึงลูกค้าในต่างจังหวัด`,
      solution: `เพิ่มตัวแทนจำหน่ายและจัดกิจกรรมส่งเสริมการขายร่วมกับร้านค้าท้องถิ่น`,
      correct: true
    },
    {
      situation: `ธุรกิจร้านกาแฟแห่งหนึ่งมีโปรโมชั่นลดราคากาแฟในช่วงเช้า แต่ลูกค้าส่วนใหญ่ยังไม่ทราบข้อมูลโปรโมชั่นนี้ จึงไม่เข้าร่วมโปรโมชั่นมากเท่าที่ควร`,
      requirement: `ประชาสัมพันธ์โปรโมชั่นลดราคาให้เข้าถึงกลุ่มเป้าหมายมากขึ้น`,
      solution: `แจกใบปลิวในร้านเพียงอย่างเดียวโดยไม่ใช้ช่องทางออนไลน์`,
      correct: false
    },
    {
      situation: `บริษัทผลิตอุปกรณ์กีฬาได้ออกสินค้าใหม่ที่มีคุณสมบัติพิเศษที่แตกต่างจากคู่แข่ง แต่ยังไม่มีการโปรโมทอย่างทั่วถึง 
ทำให้ยอดขายยังไม่เป็นไปตามเป้า`,
      requirement: `เพิ่มยอดขายโดยการสื่อสารจุดเด่นของสินค้าใหม่สู่ลูกค้า`,
      solution: `ใช้สื่อโซเชียลมีเดียและการตลาดแบบอินฟลูเอนเซอร์เพื่อโปรโมทสินค้า`,
      correct: true
    },
    {
      situation: `ร้านอาหารแห่งหนึ่งตั้งราคาอาหารสูงกว่าร้านคู่แข่งในพื้นที่เดียวกัน โดยไม่ได้ให้บริการที่แตกต่างหรือมีคุณภาพดีขึ้น จึงทำให้ลูกค้าหันไปใช้บริการร้านอื่นมากขึ้น`,
      requirement: `ตั้งราคาที่เหมาะสมกับคุณภาพและตลาดในพื้นที่`,
      solution: `ลดราคาลงโดยไม่ปรับปรุงคุณภาพหรือบริการ`,
      correct: false
    },
    {
      situation: `บริษัทจำหน่ายอุปกรณ์อิเล็กทรอนิกส์พบว่า ลูกค้าบางกลุ่มยังไม่สามารถเข้าถึงสินค้าได้สะดวก เพราะไม่มีสาขาในพื้นที่ห่างไกล`,
      requirement: `เพิ่มช่องทางจำหน่ายเพื่อเข้าถึงลูกค้าในพื้นที่ห่างไกล`,
      solution: `เปิดร้านค้าออนไลน์และจัดส่งสินค้าฟรีในพื้นที่เหล่านั้น`,
      correct: true
    },
    {
      situation: `แบรนด์เสื้อผ้าหนึ่งเลือกที่จะใช้โฆษณาเฉพาะทางทีวีในช่วงเวลาที่ไม่เหมาะสม เช่น เวลาตอนดึกซึ่งกลุ่มเป้าหมายไม่ดูทีวี`,
      requirement: `เพิ่มประสิทธิภาพในการประชาสัมพันธ์สินค้า`,
      solution: `เลือกช่องทางโฆษณาออนไลน์ที่กลุ่มเป้าหมายใช้งานบ่อยและเวลาที่เหมาะสม`,
      correct: true
    },
    {
      situation: `บริษัทผลิตสินค้าอุปโภคบริโภคมีการแจกคูปองส่วนลดมากเกินไปจนทำให้กำไรลดลงอย่างมาก แต่ยอดขายเพิ่มขึ้นเพียงเล็กน้อย`,
      requirement: `ปรับโปรโมชั่นเพื่อเพิ่มยอดขายโดยไม่กระทบกำไรอย่างรุนแรง`,
      solution: `แจกคูปองส่วนลดในจำนวนจำกัดและกำหนดเงื่อนไขการใช้คูปองให้ชัดเจน`,
      correct: true
    },
    {
      situation: `ธุรกิจอาหารพร้อมทานพบว่า ลูกค้าในเขตเมืองไม่ค่อยสนใจซื้อสินค้าราคาถูกที่ทำจากวัตถุดิบคุณภาพต่ำ 
ในขณะที่ลูกค้าในชนบทให้ความสำคัญกับราคาเป็นหลักมากกว่า คุณภาพ`,
      requirement: `ปรับกลยุทธ์การตั้งราคาและคุณภาพสินค้าให้เหมาะสมกับตลาดแต่ละกลุ่ม`,
      solution: `ตั้งราคาสูงขึ้นในเขตเมืองโดยใช้วัตถุดิบคุณภาพดี และตั้งราคาถูกในชนบทโดยลดต้นทุนวัตถุดิบ`,
      correct: true
    }
  ];

  let questions = [];
  let current = 0;
  let score = 0;
  let player = "";
  let timer = 90;
  let countdown;
  let gameOver = false;
  let userAnswers = [];

  function startGame() {
    player = document.getElementById("playerName").value.trim();
    if (!player) {
      alert("กรุณาป้อนชื่อผู้เล่น");
      return;
    }
    questions = shuffle([...allQuestions]).slice(0, 10);
    document.getElementById("startScreen").style.display = "none";
    document.getElementById("endScreen").style.display = "none";
    document.getElementById("questionCard").style.display = "block";
    document.getElementById("explosion").style.display = "none";
    score = 0;
    current = 0;
    gameOver = false;
    timer = 90;
    userAnswers = [];
    updateScore();
    updateTimer();
    showQuestion();
    countdown = setInterval(updateTimer, 1000);
  }

  function startGameFromEnd() {
    document.getElementById("playerName").value = player;
    document.getElementById("endScreen").style.display = "none";
    document.getElementById("startScreen").style.display = "block";
  }

  function clearRanking() {
    if (confirm("คุณแน่ใจหรือไม่ที่จะลบอันดับคะแนนทั้งหมด?")) {
      localStorage.removeItem("ranking");
      alert("ลบอันดับคะแนนเรียบร้อยแล้ว");
      document.getElementById("rankingList").innerHTML = "";
    }
  }

  function shuffle(arr) {
    for (let i = arr.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [arr[i], arr[j]] = [arr[j], arr[i]];
    }
    return arr;
  }

  function showQuestion() {
    if (gameOver) return;
    const q = questions[current];
    document.getElementById("situation").innerText = q.situation;
    document.getElementById("requirement").innerText = q.requirement;
    document.getElementById("solution").innerText = q.solution;
    document.getElementById("feedback").innerText = "";
  }

  function checkAnswer(userAnswer) {
    if (gameOver) return;
    const q = questions[current];
    const isCorrect = userAnswer === q.correct;
    userAnswers.push({
      questionIndex: current + 1,
      userAnswer: userAnswer,
      correctAnswer: q.correct,
      isCorrect: isCorrect
    });

    if (isCorrect) {
      score += 10;
      document.getElementById("feedback").style.color = "#27ae60";
      document.getElementById("feedback").innerText = "👍 ถูกต้อง!";
      correctSound.play();
    } else {
      document.getElementById("feedback").style.color = "#e74c3c";
      document.getElementById("feedback").innerText = "👎 ผิด!";
      wrongSound.play();
    }
    updateScore();
    current++;
    if (current >= questions.length) {
      endGame();
    } else {
      setTimeout(() => {
        showQuestion();
      }, 1200);
    }
  }

  function updateScore() {
    document.getElementById("score").innerText = `คะแนน: ${score}`;
  }

  function updateTimer() {
    if (timer <= 0) {
      endGame(true);
      return;
    }
    document.getElementById("timer").innerText = `⏳ เวลาเหลือ: ${timer} วินาที`;
    timer--;
  }

  function endGame(timeOut = false) {
    gameOver = true;
    clearInterval(countdown);
    document.getElementById("questionCard").style.display = "none";
    document.getElementById("endScreen").style.display = "block";
    if (timeOut) {
      document.getElementById("explosion").style.display = "flex";
    }
    document.getElementById("finalScore").innerText = `${player} ได้คะแนน ${score} คะแนน`;

    const tbody = document.getElementById("answerSummary");
    tbody.innerHTML = "";
    userAnswers.forEach((ans) => {
      const tr = document.createElement("tr");
      tr.className = ans.isCorrect ? "correct-row" : "incorrect-row";

      const userAnsText = ans.userAnswer ? "เหมาะสม" : "ไม่เหมาะสม";
      const correctAnsText = ans.correctAnswer ? "เหมาะสม" : "ไม่เหมาะสม";
      const resultText = ans.isCorrect ? "✔️ ถูก" : "❌ ผิด";

      tr.innerHTML = `
        <td>${ans.questionIndex}</td>
        <td>${userAnsText}</td>
        <td>${correctAnsText}</td>
        <td>${resultText}</td>
      `;
      tbody.appendChild(tr);
    });
  }

  function goToHome() {
    document.getElementById("endScreen").style.display = "none";
    document.getElementById("startScreen").style.display = "block";
    document.getElementById("playerName").value = "";
  }
</script>

</body>
</html>
