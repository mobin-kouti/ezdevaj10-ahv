<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>سامانه استعلام وضعیت وام ازدواج</title>
<style>
  body {
    font-family: Tahoma, sans-serif;
    background-color: #f0f4f8;
    text-align: center;
    padding: 30px;
    direction: rtl;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }
  header {
    margin-bottom: 20px;
  }
  header img {
    width: 100px;
    height: auto;
  }
  input[type="text"] {
    font-size: 18px;
    padding: 10px;
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-bottom: 15px;
  }
  button {
    font-size: 18px;
    padding: 10px 25px;
    background-color: #470434;
    border: none;
    border-radius: 5px;
    color: white;
    cursor: pointer;
  }
  button:hover {
    background-color: #93103e;
  }
  .result {
    margin-top: 30px;
    font-size: 20px;
    font-weight: bold;
    color: #333;
  }
  .error {
    color: red;
  }
  footer {
    margin-top: auto;
    padding: 15px;
    background-color: #d9e7ff;
    font-size: 16px;
    color: #b4980c;
    border-top: 1px solid #ffea00;
    margin-top: 40px;
  }
</style>
</head>
<body>

<header>
  <!-- اگر لوگوی واقعی داری اینجا لینک عکسش را بگذار -->
  <img src="" alt="لوگوی وام ازدواج" />
</header>

<h2>سامانه استعلام وضعیت وام ازدواج کوتی</h2>

<input type="text" id="nationalId" placeholder="کد ملی را وارد کنید" maxlength="10" />
<br />
<button onclick="checkStatus()">استعلام وضعیت</button>

<div id="result" class="result"></div>

<footer>
  ثبت نام وام ازدواج و فرزند آوری
   <strong>کــوتی</strong><br />
  نشانی: اهواز، نهضت آباد، انتهای خیابان انوشه، خیابان امت، دفتر ازدواج کوتی<br />
  تلفن: ۰۹۱۶۹۰۸۴۰۶۰
</footer>

<script>
  // داده شبیه‌سازی‌شده برای تست (کد ملی و وضعیت وام)
  const loanData = {
    "1746513276": "ثبت نام وام شما انجام شد بانک ملی شعبه نهضت آباد جهت تحویل مدارک به دفتر مزاجعه فرمایید",
    "0098765432": "وام شما در مرحله بررسی مدارک است.",
    "1234567890": "وام شما رد شده است.",
    "9876543210": "وام شما هنوز ثبت نشده است."
  };

  function checkStatus() {
    const id = document.getElementById('nationalId').value.trim();
    const resultDiv = document.getElementById('result');
    
    // اعتبارسنجی اولیه کد ملی (فقط طول 10 رقم)
    if (!/^\d{10}$/.test(id)) {
      resultDiv.innerHTML = '<span class="error">لطفا کد ملی ۱۰ رقمی صحیح وارد کنید.</span>';
      return;
    }

    if (loanData[id]) {
      resultDiv.textContent = loanData[id];
    } else {
      resultDiv.textContent = "کد ملی وارد شده در سیستم وام ازدواج ثبت نشده است.";
    }
  }
</script>

</body>
</html># kouti