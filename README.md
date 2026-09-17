
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Date Invitation 💗</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #ffe0ec, #f7d9ff, #fff0f5);
  color: #803b63;
}

.card {
  background: rgba(255,255,255,0.92);
  width: 100%;
  max-width: 440px;
  padding: 35px 25px;
  border-radius: 30px;
  text-align: center;
  box-shadow: 0 15px 50px #c77ba533;
}

.heart {
  font-size: 55px;
  animation: beat 1.2s infinite;
}

@keyframes beat {
  50% { transform: scale(1.12); }
}

h1 {
  font-size: 30px;
  margin: 15px 0;
}

p {
  color: #a16c88;
  line-height: 1.6;
}

button, input, select {
  font: inherit;
}

button {
  border: none;
  cursor: pointer;
  border-radius: 16px;
  padding: 15px;
  font-weight: bold;
  transition: 0.2s;
}

button:hover {
  transform: translateY(-2px);
}

.buttons {
  display: flex;
  gap: 12px;
  margin-top: 25px;
}

.buttons button {
  flex: 1;
}

.yes {
  background: #e65b9a;
  color: white;
}

.no {
  background: #f8e8f0;
  color: #a34c78;
}

#formPage {
  display: none;
}

.field {
  text-align: left;
  margin: 17px 0;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
}

input, select {
  width: 100%;
  padding: 14px;
  border: 1px solid #efc4d9;
  border-radius: 13px;
  background: #fff8fb;
  color: #803b63;
  outline: none;
}

input:focus, select:focus {
  border-color: #e65b9a;
}

.submit {
  width: 100%;
  background: #e65b9a;
  color: white;
  margin-top: 15px;
}

#result {
  display: none;
  margin-top: 20px;
  padding: 15px;
  background: #fff0f6;
  border-radius: 15px;
  overflow-wrap: anywhere;
}

.back {
  background: transparent;
  color: #a34c78;
  margin-top: 10px;
}

.footer {
  margin-top: 25px;
  font-size: 12px;
  color: #c08aa5;
}
</style>
</head>

<body>

<div class="card">

  <section id="firstPage">
    <div class="heart">💗</div>

    <h1>Will you go out with me?</h1>

    <p>
      I have something special in mind...
      <br>
      Would you like to spend a day with me? ✨
    </p>

    <div class="buttons">
      <button class="yes" onclick="showForm()">
        Yes! 💖
      </button>

      <button class="no" onclick="sayNo()">
        No 🙈
      </button>
    </div>

    <p id="message"></p>
  </section>

  <section id="formPage">
    <div class="heart">🌷</div>

    <h1>Let's plan our date!</h1>
    <p>Choose a day and let's make a lovely memory.</p>

    <form id="dateForm">

      <div class="field">
        <label for="date">Date 📅</label>
        <input type="date" id="date" required>
      </div>

      <div class="field">
        <label for="time">Time ⏰</label>
        <input type="time" id="time" required>
      </div>

      <div class="field">
        <label for="place">Choose our date 💕</label>
        <select id="place" required>
          <option value="">Select a place</option>
          <option>🎬 Watch a movie</option>
          <option>🍽️ Dinner together</option>
          <option>☕ Cafe hopping</option>
          <option>🌆 Evening walk</option>
          <option>🎡 Fun activities</option>
        </select>
      </div>

      <div class="field">
        <label for="location">Location 📍</label>
        <input
          type="text"
          id="location"
          placeholder="Enter a location"
          required
        >
      </div>

      <button class="submit" type="submit">
        Confirm Our Date 💗
      </button>

    </form>

    <div id="result"></div>

    <button class="back" onclick="goBack()">
      ← Back
    </button>
  </section>

  <div class="footer">
    Made with love 💌
  </div>

</div>

<script>
let noCount = 0;

const messages = [
  "Are you sure? 🥺",
  "Please think about it! 💗",
  "I'll make it a lovely day! 🌷",
  "One more chance? 🥹",
  "Pretty please? 💖"
];

function sayNo() {
  document.getElementById("message").textContent =
    messages[noCount % messages.length];

  noCount++;
}

function showForm() {
  document.getElementById("firstPage").style.display = "none";
  document.getElementById("formPage").style.display = "block";
}

function goBack() {
  document.getElementById("formPage").style.display = "none";
  document.getElementById("firstPage").style.display = "block";
}

document.getElementById("dateForm").addEventListener("submit", function(e) {
  e.preventDefault();

  const date = document.getElementById("date").value;
  const time = document.getElementById("time").value;
  const place = document.getElementById("place").value;
  const location = document.getElementById("location").value;

  const result = document.getElementById("result");

  result.style.display = "block";
  result.innerHTML =
    "<h3>It's a date! 💖</h3>" +
    "<p>📅 " + date + "</p>" +
    "<p>⏰ " + time + "</p>" +
    "<p>" + place + "</p>" +
    "<p>📍 " + location + "</p>" +
    "<p>Can't wait to see you! 🌷</p>";
});
</script>

</body>
</html>
