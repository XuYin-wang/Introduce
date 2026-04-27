<!DOCTYPE html>
<html lang="ja">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>自己紹介</title>
  <style>
    body {
      margin: 0;
      font-family: "Noto Sans JP", sans-serif;
      overflow: hidden;
    }

    .container {
      position: relative;
      width: 100%;
      height: 100vh;
    }

    .page {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      transition: transform 0.6s ease, opacity 0.6s ease;
    }

    /* 页面1 */
    .page1 {
      background: linear-gradient(135deg, #b5c2ff, #764ba2);
      color: white;
      z-index: 2;
    }

    /* 页面2 */
    .page2 {
      background: linear-gradient(135deg, #ff7eb497, #ff758c);
      color: white;
      transform: translateX(100%);
      z-index: 1;
    }

    /* 页面3 */
    .page3 {
      background: linear-gradient(135deg, #7eadff68, #fbbac5);
      color: white;
      transform: translateX(200%);
      z-index: 1;
    }

    .gallery {
      display: flex;
      gap: 30px;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 30px;
    }

    .item {
      width: 280px;
      text-align: center;
    }

    .item img {
      width: 100%;
      border-radius: 12px;
      box-shadow: 1px 5px 15px rgba(0, 0, 0, 0.2);
      transition: 0.3s;
    }

    .item img:hover {
      transform: scale(1.05);
    }

    h1 {
      font-size: 36px;
      margin-bottom: 20px;
    }

    p {
      max-width: 500px;
      text-align: center;
      line-height: 1.6;
    }

    .btn {
      margin-top: 30px;
      padding: 12px 24px;
      border: none;
      border-radius: 25px;
      background: white;
      color: #333;
      cursor: pointer;
      transition: 0.3s;
    }

    .btn:hover {
      transform: scale(1.1);
      background: #f0f0f0;
    }
  </style>
</head>

<body>

  <div class="container">

    <!-- 页面1 -->
    <div class="page page1" id="page1">
      <h1>こんにちは</h1>
      <p>
        こんにちは、私は王栩隐です。中国人で、現在は愛媛大学で勉強しています。貴社で就職したいと思っています。
      </p>
      <button class="btn" onclick="goPage(2)">次へ →</button>
    </div>

    <!-- 页面2 -->
    <div class="page page2" id="page2">
      <h1>自己紹介</h1>
      <p>
        私の個人ページへようこそ！私は学ぶことと新しいことに挑戦するのが好きな大学生です。<br>
        私の専攻はコンピュータで、将来はIT業界で働きたいと思っています。大学時ウェブデザインを学んだ際、自分自身で webpage を作成することに興味を持ちました。<br>
        趣味はおいしいものを食べること、旅行すること、そしてアニメを見ることです。<br>
      </p>
      <button class="btn" onclick="goPage(1)">← 戻る</button>
      <button class="btn" onclick="goPage(3)">次へ →</button>
    </div>

    <!-- 页面3 -->
    <div class="page page3" id="page3">
      <h1>私の写真</h1>

      <p>
        下は私が旅行中に撮影した写真です。<br>
        美しい物を記録するのが好きです。
      </p>

      <div class="gallery">

        <!-- ケーキ -->
        <div class="item">
          <img src="cake.HEIC" alt="ケーキの写真">
          <h2>ケーキ</h2>
          <p>
            一人旅（四川成都）のときに撮影しました。<br>
            TikTokで見て気になり、行ってみました。
            本当に美味しかったケーキですが、3番目でお腹がぜんぜん入れれんになりました。
          </p>
        </div>

        <!-- 大阪 -->
        <div class="item">
          <img src="osaka.HEIC" alt="大阪の写真">
          <h2>大阪</h2>
          <p>
            神戸周辺で撮った写真です。<br>
            景色が美しく、観光客に人気の場所でした。
            近くにあるタワーからの眺めも素晴らしかったです。
          </p>
        </div>

      </div>

      <button class="btn" onclick="goPage(2)">← 戻る</button>
    </div>


    <script>
      function goPage(page) {
        const pages = [
          document.getElementById('page1'),
          document.getElementById('page2'),
          document.getElementById('page3')
        ];

        pages.forEach((p, index) => {
          p.style.transform = `translateX(${(index - (page - 1)) * 100}%)`;
        });
      }
    </script>

</body>

</html>
