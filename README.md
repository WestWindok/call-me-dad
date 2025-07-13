# call-me-dad
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="UTF-8">
  <title>你必须叫爸爸才能退出</title>
  <style>
    body {
      font-family: "微软雅黑", sans-serif;
      background-color: #f0f0f0;
      text-align: center;
      padding-top: 100px;
    }
    h1 {
      font-size: 26px;
      color: #333;
    }
    button {
      padding: 15px 25px;
      font-size: 18px;
      margin: 20px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
    }
    #exitBtn {
      background-color: #ff4d4f;
      color: white;
    }
    #dadBtn {
      background-color: #52c41a;
      color: white;
    }
    #message {
      margin-top: 40px;
      font-size: 20px;
      color: #1890ff;
    }
  </style>
</head>
<body>

  <h1>你必须叫爸爸才能退出</h1>

  <button id="exitBtn">退出</button>
  <button id="dadBtn">爸爸</button>

  <div id="message"></div>

  <script>
    let exitCount = 0;
    const exitBtn = document.getElementById('exitBtn');
    const dadBtn = document.getElementById('dadBtn');
    const message = document.getElementById('message');

    exitBtn.addEventListener('click', () => {
      exitCount++;
      if (exitCount >= 3) {
        exitBtn.remove();
        message.textContent = "退出按钮消失了😈";
      } else {
        message.textContent = `你真的想退出吗？你点了 ${exitCount} 次`;
      }
    });

    dadBtn.addEventListener('click', () => {
      message.textContent = "你终于肯叫爸爸了，现在你可以退出了👋";
      setTimeout(() => {
        location.href = "https://baidu.com"; // 可替换为任何跳转地址
      }, 2000);
    });
  </script>

</body>
</html>
