# -<!DOCTYPE html>
<html lang="ar">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>موقع التغذية الصحية</title>
  <link rel="stylesheet" href="styles.css">
</head>

<body>

  <header>
    <h1>موقع التغذية الصحية</h1>
    <nav>
      <ul>
        <li><a href="#home">الرئيسية</a></li>
        <li><a href="#nutrition-info">معلومات عن التغذية</a></li>
        <li><a href="#tips">نصائح يومية</a></li>
        <li><a href="#calculator">حساب السعرات</a></li>
      </ul>
    </nav>
  </header>

  <section id="home">
    <h2>مرحبًا بكم في موقع التغذية الصحية</h2>
    <p>هنا ستجد كل ما تحتاجه عن التغذية السليمة للحفاظ على صحتك وتحسين نمط حياتك.</p>
  </section>

  <section id="nutrition-info">
    <h2>معلومات عن التغذية</h2>
    <p>التغذية الجيدة هي أساس الصحة الجيدة. الأطعمة الصحية تساعد في تحسين الطاقة، المزاج، وصحة الجسم بشكل عام.</p>
  </section>

  <section id="tips">
    <h2>نصائح يومية</h2>
    <ul>
      <li>تناول الفواكه والخضروات يوميًا للحفاظ على صحة جسمك.</li>
      <li>اشرب الكثير من الماء لتعزيز الهضم وصحة الجلد.</li>
      <li>تجنب السكريات المصنعة وبدلها بالفواكه الطبيعية.</li>
    </ul>
  </section>

  <section id="calculator">
    <h2>حساب السعرات الحرارية</h2>
    <form id="calorieForm">
      <label for="weight">الوزن (كجم):</label>
      <input type="number" id="weight" name="weight" required>
      <br><br>
      <label for="height">الطول (سم):</label>
      <input type="number" id="height" name="height" required>
      <br><br>
      <label for="age">العمر:</label>
      <input type="number" id="age" name="age" required>
      <br><br>
      <label for="activity">مستوى النشاط:</label>
      <select id="activity" name="activity">
        <option value="low">منخفض</option>
        <option value="moderate">متوسط</option>
        <option value="high">مرتفع</option>
      </select>
      <br><br>
      <button type="button" onclick="calculateCalories()">احسب السعرات</button>
    </form>
    <p id="result"></p>
  </section>

  <footer>
    <p>حقوق النشر © 2024. كل الحقوق محفوظة.</p>
  </footer>

  <script src="script.js"></script>
</body>

</html>
<!DOCTYPE html>
<html lang="ar">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>موقع التغذية الصحية</title> <!-- تغذية سليمة -->
  <link rel="stylesheet" href="styles.css">
</head>

<body>
  <!-- باقي محتوى الموقع -->
</body>

</html>

body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
  text-align: center;
}

header {
  background-color: #28a745;
  color: white;
  padding: 20px;
}

nav ul {
  list-style: none;
  padding: 0;
}

nav ul li {
  display: inline;
  margin: 0 15px;
}

nav ul li a {
  color: white;
  text-decoration: none;
}

section {
  padding: 20px;
  background-color: white;
  margin: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

footer {
  background-color: #333;
  color: white;
  padding: 10px;
}

#calculator {
  background-color: #f8f9fa;
  padding: 20px;
  border-radius: 10px;
  margin-top: 20px;
}
function calculateCalories() {
  var weight = document.getElementById("weight").value;
  var height = document.getElementById("height").value;
  var age = document.getElementById("age").value;
  var activity = document.getElementById("activity").value;

  if (weight && height && age) {
    var bmr;

    // معادلة BMR (Basal Metabolic Rate)
    bmr = 10 * weight + 6.25 * height - 5 * age + 5;

    var calories;
    if (activity === "low") {
      calories = bmr * 1.2;
    } else if (activity === "moderate") {
      calories = bmr * 1.55;
    } else if (activity === "high") {
      calories = bmr * 1.9;
    }

    document.getElementById("result").innerText =
      "السعرات الحرارية اليومية المطلوبة: " +
      Math.round(calories) +
      " سعر حراري.";
  } else {
    document.getElementById("result").innerText = "من فضلك أدخل كل البيانات.";
  }
}
