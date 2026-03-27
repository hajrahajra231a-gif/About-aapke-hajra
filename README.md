<!DOCTYPE html>
<html>
<head>
  <title>💖 Hajra Quiz 💖</title>
  <style>
    body {
      font-family: Arial;
      background: linear-gradient(to right, #ff758c, #ff7eb3);
      text-align: center;
      padding: 20px;
    }
    .box {
      background: white;
      padding: 20px;
      border-radius: 20px;
      max-width: 420px;
      margin: auto;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }
    h2 {
      color: #ff4d88;
    }
    button {
      background: #ff4d88;
      color: white;
      padding: 12px;
      border: none;
      border-radius: 10px;
      width: 90%;
      margin-top: 10px;
      cursor: pointer;
    }
    .q {
      text-align: left;
      margin: 15px 0;
    }
  </style>
</head>
<body>

<div class="box">
  <h2>💖 How Well Do You Know Hajra? 💖</h2>

  <input type="text" id="name" placeholder="Enter your name"><br><br>

  <div class="q">
    <p>1. Hajra ka favorite colour?</p>
    <input type="radio" name="q1" value="black"> Black<br>
    <input type="radio" name="q1" value="maroon"> Maroon<br>
    <input type="radio" name="q1" value="blue"> Blue<br>
  </div>

  <div class="q">
    <p>2. Hajra ki favourite dish?</p>
    <input type="radio" name="q2" value="pasta"> Pasta<br>
    <input type="radio" name="q2" value="noodles"> Noodles<br>
    <input type="radio" name="q2" value="pizza"> Pizza<br>
  </div>

  <div class="q">
    <p>3. Hajra ki height?</p>
    <input type="radio" name="q3" value="5'6"> 5'6"<br>
    <input type="radio" name="q3" value="5'4"> 5'4"<br>
    <input type="radio" name="q3" value="5'8"> 5'8"<br>
  </div>

  <div class="q">
    <p>4. Hajra ki best quality kya hai?</p>
    <input type="radio" name="q4" value="caring"> Caring 💕<br>
    <input type="radio" name="q4" value="cute"> Cute 😍<br>
    <input type="radio" name="q4" value="attitude"> Attitude 😎<br>
  </div>

  <div class="q">
    <p>5. Tumhe Hajra kyu pasand hai? 💌</p>
    <input type="text" id="q5" placeholder="Type your answer">
  </div>

  <div class="q">
    <p>6. Tumhe Hajra se kab pyaar hua? (date/time 🫣)</p>
    <input type="text" id="q6" placeholder="Type date & time">
  </div>

  <button onclick="check()">Submit 💖</button>

  <h3 id="result"></h3>
  <p id="msg"></p>
</div>

<script>
function check() {
  let score = 0;
  let name = document.getElementById("name").value;

  let q1 = document.querySelector('input[name="q1"]:checked');
  let q2 = document.querySelector('input[name="q2"]:checked');
  let q3 = document.querySelector('input[name="q3"]:checked');
  let q4 = document.querySelector('input[name="q4"]:checked');
  let q5 = document.getElementById("q5").value;
  let q6 = document.getElementById("q6").value;

  if(q1 && (q1.value == "black" || q1.value == "maroon")) score++;
  if(q2 && q2.value == "pasta") score++;
  if(q3 && q3.value == "5'6") score++;
  if(q4 && q4.value == "caring") score++;
  if(q5.length > 3) score++;
  if(q6.length > 3) score++;

  let text = "";

  if(score >= 5){
    text = "😍 You truly love Hajra!";
  } else if(score >= 3){
    text = "😊 Not bad! You know her well!";
  } else {
    text = "😅 Try again, know her better!";
  }

  document.getElementById("result").innerText =
    name + " your score: " + score + "/6";

  document.getElementById("msg").innerText =
    text + "\n💌 Your message: " + q5;
}
</script>

</body>
</html>
