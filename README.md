<html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Force, Motion & Energy – Grade 2</title>
<style>
  body {
    font-family: "Comic Sans MS", sans-serif;
    background-color: #fffbee;
    color: #333;
    padding: 25px;
    max-width: 720px;
    margin: auto;
    border: 3px dashed #f5b14d;
    border-radius: 10px;
  }
  h1 { color: #ff7b00; text-align: center; }
  h2 { color: #2a6f9e; }
  button {
    display: block;
    margin: 10px auto;
    padding: 8px 15px;
    background-color: #ffb347;
    color: #fff;
    border: none;
    border-radius: 6px;
    font-size: 16px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.2s;
  }
  button:hover {
    background-color: #ff9933;
    transform: scale(1.05);
  }

  /* Fact box styling */
  .fact {
    text-align: center;
    background-color: #fff3cd;
    border: 1px solid #f5b14d;
    border-radius: 8px;
    padding: 10px;
    margin: 10px auto;
    max-width: 90%;
    opacity: 0;
    transform: translateY(-10px);
    transition: opacity 0.4s ease, transform 0.4s ease;
    display: none;
    position: relative;
  }
  .fact.show {
    display: block;
    opacity: 1;
    transform: translateY(0);
  }
  .fact.hide {
    opacity: 0;
    transform: translateY(-10px);
  }

  /* Lightbulb animation */
  .lightbulb {
    position: absolute;
    top: -25px;
    left: 50%;
    transform: translateX(-50%) scale(0.8);
    font-size: 28px;
    opacity: 0;
    animation: bounce 1.2s ease infinite;
  }
  .fact.show .lightbulb {
    opacity: 1;
    animation: bounce 1.2s ease infinite, fadeIn 0.4s ease forwards;
  }

  /* Quiz styling */
  .quiz {
    margin-top: 30px;
    padding: 15px;
    background-color: #e7f7ff;
    border-radius: 10px;
    border: 2px dashed #5cb0ff;
  }
  .quiz h2 {
    text-align: center;
    color: #007acc;
  }
  .question {
    margin-bottom: 15px;
  }
  .answer {
    display: inline-block;
    background-color: #fff;
    border: 2px solid #ccc;
    border-radius: 6px;
    padding: 5px 10px;
    margin: 5px;
    cursor: pointer;
    transition: 0.2s;
  }
  .answer:hover {
    background-color: #f5f5f5;
    transform: scale(1.05);
  }
  .answer.correct {
    background-color: #c8f7c5;
    border-color: #4caf50;
  }
  .answer.wrong {
    background-color: #f9c0c0;
    border-color: #e74c3c;
  }
  .feedback {
    text-align: center;
    font-weight: bold;
    margin-top: 5px;
  }
  .feedback.correct {
    color: #2e7d32;
  }
  .feedback.wrong {
    color: #c0392b;
  }

  @keyframes bounce {
    0%, 100% { transform: translateX(-50%) translateY(0) scale(1); }
    50% { transform: translateX(-50%) translateY(-10px) scale(1.1); }
  }
  @keyframes fadeIn {
    from { opacity: 0; transform: translateX(-50%) translateY(-5px) scale(0.8); }
    to { opacity: 1; transform: translateX(-50%) translateY(0) scale(1); }
  }
</style>
</head>
<body>

<h1>Let’s Explore Force, Motion & Energy!</h1>

<!-- Section 1 -->
<div class="section">
  <h2>What Is Energy?</h2>
  <p>Energy helps things happen! We use energy when we move, play, or even smile. The sun gives plants energy to grow, and our bodies use energy from food to move and think.</p>
  <button onclick="toggleFact('fact1')">🔍 Reveal a Fun Fact!</button>
  <div id="fact1" class="fact">
    <div class="lightbulb">💡</div>
    ⚡ The Sun is Earth’s biggest source of energy — it gives light, heat, and helps plants grow!
  </div>
</div>

<!-- Section 2 -->
<div class="section">
  <h2>Force and Motion</h2>
  <p>A <strong>force</strong> is a push or a pull. When you push a swing, it moves forward. When you pull your backpack, it moves too! That movement is called <strong>motion</strong>.</p>
  <button onclick="toggleFact('fact2')">🔍 Reveal a Fun Fact!</button>
  <div id="fact2" class="fact">
    <div class="lightbulb">💡</div>
    🌀 Did you know? Gravity is a force that pulls everything toward the ground — that’s why things fall!
  </div>
</div>

<!-- Section 3 -->
<div class="section">
  <h2>How They Work Together</h2>
  <p>A ball sitting still won’t move until a force (like a kick) gives it energy to roll. The energy moves through the ball — that’s motion! Energy, force, and motion are like a team that makes the world move.</p>
  <button onclick="toggleFact('fact3')">🔍 Reveal a Fun Fact!</button>
  <div id="fact3" class="fact">
    <div class="lightbulb">💡</div>
    ⚽ The faster you kick the ball, the more energy you give it — and the farther it goes!
  </div>
</div>

<!-- Show/Hide All -->
<div style="text-align:center; margin-top: 25px;">
  <button onclick="toggleAllFacts()">🌟 Show / Hide All Facts</button>
</div>

<!-- QUIZ SECTION -->
<div class="quiz">
  <h2>🧠 Mini Quiz: Test What You Learned!</h2>

  <div class="question">
    <p><strong>1. What is a force?</strong></p>
    <div class="answer" onclick="checkAnswer(this, true)">A push or a pull</div>
    <div class="answer" onclick="checkAnswer(this, false)">Something we eat</div>
    <div class="answer" onclick="checkAnswer(this, false)">A kind of sound</div>
    <div class="feedback"></div>
  </div>

  <div class="question">
    <p><strong>2. Which one shows motion?</strong></p>
    <div class="answer" onclick="checkAnswer(this, false)">A book on a table</div>
    <div class="answer" onclick="checkAnswer(this, true)">A rolling ball</div>
    <div class="answer" onclick="checkAnswer(this, false)">A sleeping cat</div>
    <div class="feedback"></div>
  </div>

  <div class="question">
    <p><strong>3. What gives plants the energy to grow?</strong></p>
    <div class="answer" onclick="checkAnswer(this, true)">The Sun</div>
    <div class="answer" onclick="checkAnswer(this, false)">The Moon</div>
    <div class="answer" onclick="checkAnswer(this, false)">Rain</div>
    <div class="feedback"></div>
  </div>
</div>

<p style="text-align:center;">⚡ Keep exploring! Where do you see energy, force, and motion today?</p>

<script>
  // Toggle single fact
  function toggleFact(id) {
    const fact = document.getElementById(id);
    const isShowing = fact.classList.contains('show');

    if (!isShowing) {
      fact.style.display = "block";
      requestAnimationFrame(() => fact.classList.add('show'));
      playPopSound();
    } else {
      fact.classList.add('hide');
      fact.classList.remove('show');
      setTimeout(() => {
        fact.style.display = "none";
        fact.classList.remove('hide');
      }, 400);
    }
  }

  // Toggle all facts
  function toggleAllFacts() {
    const facts = document.querySelectorAll('.fact');
    const anyHidden = Array.from(facts).some(f => !f.classList.contains('show'));

    facts.forEach(fact => {
      if (anyHidden) {
        fact.style.display = "block";
        requestAnimationFrame(() => fact.classList.add('show'));
        playPopSound();
      } else {
        fact.classList.add('hide');
        fact.classList.remove('show');
        setTimeout(() => {
          fact.style.display = "none";
          fact.classList.remove('hide');
        }, 400);
      }
    });
  }

  // Quiz checking
  function checkAnswer(el, correct) {
    const question = el.parentElement;
    const feedback = question.querySelector('.feedback');
    const answers = question.querySelectorAll('.answer');
    answers.forEach(a => a.classList.remove('correct', 'wrong'));
    
    if (correct) {
      el.classList.add('correct');
      feedback.textContent = "✅ Correct! Great job!";
      feedback.className = "feedback correct";
      playPopSound();
    } else {
      el.classList.add('wrong');
      feedback.textContent = "❌ Try again!";
      feedback.className = "feedback wrong";
    }
  }

  // Simple pop sound
  function playPopSound() {
    const ctx = new (window.AudioContext || window.webkitAudioContext)();
    const osc = ctx.createOscillator();
    const gain = ctx.createGain();
    osc.type = "triangle";
    osc.frequency.setValueAtTime(800, ctx.currentTime);
    gain.gain.setValueAtTime(0.2, ctx.currentTime);
    osc.connect(gain);
    gain.connect(ctx.destination);
    osc.start();
    osc.stop(ctx.currentTime + 0.15);
  }
</script>

</body>
</html>
