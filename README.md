
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Our Date 💗</title>

<style>
*{box-sizing:border-box}
body{
  margin:0;min-height:100vh;padding:20px;
  display:flex;align-items:center;justify-content:center;
  font-family:Arial,sans-serif;
  background:linear-gradient(135deg,#ffe3ef,#f5dfff,#fff5f8);
  color:#9c416f;
}
.card{
  width:100%;max-width:430px;background:white;
  padding:30px 22px;border-radius:28px;
  text-align:center;
  box-shadow:0 15px 50px #b85e8830;
}
.heart{font-size:55px}
h1{font-size:30px;line-height:1.3}
p{color:#a87b94;line-height:1.6}
button,input,select{font:inherit}
button{
  border:0;border-radius:15px;padding:15px;
  cursor:pointer;font-weight:bold;
}
.buttons{display:flex;gap:12px;margin-top:25px}
.buttons button{flex:1}
.yes,.confirm{background:#e65b9a;color:white}
.no,.back{background:#fceaf2;color:#a34c78}
#page2{display:none}
.field{text-align:left;margin:18px 0}
label{display:block;margin-bottom:8px;font-weight:bold}
input,select{
  width:100%;padding:14px;
  border:1px solid #f0c4d8;border-radius:13px;
  background:#fff8fb;color:#803b63;
}
.confirm{width:100%;margin-top:12px}
.back{margin-top:12px}
#result{
  display:none;background:#fff0f6;
  padding:15px;border-radius:16px;margin-top:20px;
}
.footer{margin-top:25px;color:#c28ba7;font-size:13px}
</style>
</head>

<body>
<div class="card">

<section id="page1">
  <div class="heart">💌</div>
  <h1>Will you go out with me?</h1>
  <p>I have a little question for you...<br>Will you spend a special day with me? 💗</p>

  <div class="buttons">
    <button class="yes" onclick="yesClick()">Yes! 💖</button>
    <button class="no" onclick="noClick()">No 🙈</button>
  </div>

  <p id="message"></p>
</section>

<section id="page2">
  <div class="heart">🌷</div>
  <h1>Let's plan our date!</h1>
  <p>Choose your favorite date plan ✨</p>

  <form id="dateForm">
    <div class="field">
      <label for="date">📅 Date</label>
      <input type="date" id="date" required>
    </div>

    <div class="field">
      <label for="time">⏰ Time</label>
      <input type="time" id="time" required>
    </div>

    <div class="field">
      <label for="activity">💕 What should we do?</label>
      <select id="activity" required>
        <option value="">Choose an activity</option>
        <option>🎬 Watch a movie</option>
        <option>🍽️ Dinner together</option>
        <option>☕ Go to a cafe</option>
        <option>🌆 Evening walk</option>
        <option>🎡 Fun activities</option>
      </select>
    </div>

    <div class="field">
      <label for="location">📍 Location</label>
      <input id="location" type="text"
      placeholder="Where should we meet?" required>
    </div>

    <button class="confirm" type="submit">
      Confirm Our Date 💗
    </button>
  </form>

  <div id="result"></div>
  <button class="back" onclick="goBack()">← Back</button>
</section>

<div class="footer">Made with love 💗</div>
</div>

<script>
let count=0;

const messages=[
  "Are you sure? 🥺",
  "Please think about it! 💗",
  "One more chance? 🌷",
  "Pretty please? 🥹",
  "I'll make it a lovely day! 💖"
];

function noClick(){
  document.getElementById("message").textContent=
  messages[count%messages.length];
  count++;
}

function yesClick(){
  document.getElementById("page1").style.display="none";
  document.getElementById("page2").style.display="block";
}

function goBack(){
  document.getElementById("page2").style.display="none";
  document.getElementById("page1").style.display="block";
}

document.getElementById("dateForm").addEventListener("submit",function(e){
  e.preventDefault();

  const date=document.getElementById("date").value;
  const time=document.getElementById("time").value;
  const activity=document.getElementById("activity").value;
  const location=document.getElementById("location").value;

  const result=document.getElementById("result");
  result.style.display="block";
  result.replaceChildren();

  const title=document.createElement("h2");
  title.textContent="It's a date! 💖";
  result.appendChild(title);

  [
    "📅 "+date,
    "⏰ "+time,
    activity,
    "📍 "+location,
    "Can't wait to see you! 🌷"
  ].forEach(function(text){
    const p=document.createElement("p");
    p.textContent=text;
    result.appendChild(p);
  });
});
</script>
</body>
</html>
