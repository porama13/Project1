<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>เกมตอบคำถาม - Project1</title>
  <style>
    body { font-family: 'Prompt', sans-serif; text-align: center; margin: 50px; }
    input, button { font-size: 1rem; margin: 10px; padding: 10px; }
  </style>
</head>
<body>

  <h1>เกมตอบคำถาม</h1>

  <label>ชื่อของคุณ: <input type="text" id="nameInput" /></label><br><br>

  <button onclick="playGame()">เล่นเกม</button>
  <p id="scoreDisplay">คะแนนของคุณ: -</p>

  <button onclick="submitScore()">ส่งคะแนน</button>

  <script>
    let score = 0;

    function playGame() {
      // เกมจำลองสุ่มคะแนน (แทนคำถามจริง)
      score = Math.floor(Math.random() * 11); // 0–10
      document.getElementById("scoreDisplay").textContent = "คะแนนของคุณ: " + score;
    }

    function submitScore() {
      const name = document.getElementById("nameInput").value.trim();
      if (!name) {
        alert("กรุณากรอกชื่อก่อนส่งคะแนน");
        return;
      }

      const endpoint = "https://script.google.com/a/macros/anw.ac.th/s/AKfycbyfpUONMdCqSTM4wCy6JL0-cghFPeJksoMMbQ--7KsHFEZzb6Y6xwafvi8-h5XxXH7MFA/exec"; // แทนด้วย URL ของคุณ

      fetch(endpoint, {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ name: name, score: score })
      })
      .then(response => response.json())
      .then(data => {
        alert("ส่งคะแนนเรียบร้อยแล้ว!");
        console.log("บันทึกสำเร็จ:", data);
      })
      .catch(error => {
        console.error("เกิดข้อผิดพลาด:", error);
        alert("ส่งคะแนนไม่สำเร็จ");
      });
    }
  </script>

</body>
</html>
