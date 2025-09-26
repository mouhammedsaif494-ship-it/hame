

```html
<!DOCTYPE html>
<html>
<head>
  <title>لعبة ألغاز بسيطة</title>
</head>
<body>
  <h2>لعبة ألغاز ذهنية</h2>
  <div id="question"></div>
  <input type="text" id="answer" placeholder="اكتب إجابتك هنا" />
  <button onclick="checkAnswer()">إرسال</button>
  <div id="result"></div>
  <script>
    const questions = [
      {q: "عدد أصابع اليد الواحدة؟", a: "5"},
      {q: "ما هو لون السماء نهارًا؟", a: "أزرق"},
      {q: "كم عدد أيام الأسبوع؟", a: "7"}
    ];
    let index = 0;
    let score = 0;

    const questionEl = document.getElementById('question');
    const answerEl = document.getElementById('answer');
    const resultEl = document.getElementById('result');

    function showQuestion(){
      if(index < questions.length){
        questionEl.textContent = questions[index].q;
        answerEl.value = '';
        resultEl.textContent = '';
      } else {
        questionEl.textContent = "انتهت اللعبة! نقاطك: " + score;
        answerEl.style.display = 'none';
        document.querySelector('button').style.display = 'none';
      }
    }

    function checkAnswer(){
      let userAnswer = answerEl.value.trim();
      if(userAnswer === questions[index].a){
        resultEl.textContent = "صح! 🎉";
        score++;
      } else {
        resultEl.textContent = "غلط! الإجابة هي: " + questions[index].a;
      }
      index++;
      setTimeout(showQuestion, 1500);
    }

    showQuestion();
  </script>
</body>
</html>
```

