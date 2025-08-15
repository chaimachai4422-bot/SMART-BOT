<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>مساعد حياتك</title>
<style>
  body { font-family: Arial, sans-serif; margin: 0; background-color: #f4f4f9; color: #333; }
  header { background: linear-gradient(90deg, #6a11cb, #2575fc); color: white; text-align: center; padding: 20px; font-size: 24px; font-weight: bold; display: flex; align-items: center; justify-content: center; gap: 10px; }
  header img { height: 40px; }
  main { padding: 20px; }
  section { background: white; border-radius: 12px; padding: 15px; margin-bottom: 20px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
  h2 { color: #2575fc; margin-top: 0; }
  button { background: #2575fc; color: white; border: none; padding: 10px 15px; border-radius: 6px; cursor: pointer; }
  button:hover { background: #6a11cb; }
  .game-link { display: inline-block; margin: 5px; padding: 8px 12px; background: #eee; border-radius: 6px; text-decoration: none; color: #333; }
  .game-link:hover { background: #ddd; }
</style>
</head>
<body>
<header>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4f/Iconic_image_for_AI.png/48px-Iconic_image_for_AI.png" alt="شعار مساعد حياتك">
  <span>💡 مساعد حياتك – ذكاء + تسلية</span>
</header>
<main>
  <section>
    <h2>المساعد الذكي</h2>
    <input type="text" id="userInput" placeholder="اسأل: ماذا أطبخ؟ أين أذهب؟" style="width: 80%; padding: 10px;">
    <button onclick="askAI()">إرسال</button>
    <div id="response" style="margin-top: 15px;"></div>
  </section>

  <section>
    <h2>اقتراحات يومية</h2>
    <ul id="dailyTips"></ul>
  </section>

  <section>
    <h2>ألعاب مجانية</h2>
    <a class="game-link" href="https://playtictactoe.org/" target="_blank">تيك تاك تو</a>
    <a class="game-link" href="https://sudoku.com/" target="_blank">سودوكو</a>
    <a class="game-link" href="https://www.chess.com/play/computer" target="_blank">شطرنج</a>
    <a class="game-link" href="https://www.crazygames.com/" target="_blank">ألعاب متنوعة</a>
  </section>
</main>
<script>
const KB = {
  food: ["بيتزا منزلية", "شوربة عدس", "معكرونة بالخضار", "كسكس بالخضار", "شاورما"],
  places: ["المول القريب", "الحديقة العامة", "مقهى هادئ", "شاطئ البحر", "سينما"],
  ideas: ["مشاهدة فيلم", "لعب لعبة جماعية", "قراءة كتاب", "رياضة خفيفة"],
  quotes: ["ابتسم، فالحياة أجمل بابتسامتك.", "ابدأ يومك بطاقة إيجابية.", "كل يوم فرصة جديدة."]
};

function askAI(){
  const input = document.getElementById('userInput').value;
  let reply = "";
  if(input.includes("أطبخ")) reply = جرب: ${KB.food[Math.floor(Math.random()*KB.food.length)]};
  else if(input.includes("أذهب")) reply = يمكنك زيارة: ${KB.places[Math.floor(Math.random()*KB.places.length)]};
  else if(input.includes("أفعل") || input.includes("أنشطة")) reply = جرّب: ${KB.ideas[Math.floor(Math.random()*KB.ideas.length)]};
  else reply = "لم أفهم السؤال، جرب سؤال عن الطعام أو الأماكن أو الأنشطة.";
  document.getElementById('response').innerText = reply;
}

function loadDailyTips(){
  const tips = [KB.food[0], KB.places[1], KB.quotes[2]];
  document.getElementById('dailyTips').innerHTML = tips.map(t => <li>${t}</li>).join('');
}

window.onload = loadDailyTips;
</script>
</body>
</html>
