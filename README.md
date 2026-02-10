<html>
<head>
  <title>찐 아카이브</title>
  <link href="https://fonts.googleapis.com/css2?family=Pretendard&display=swap" rel="stylesheet">
  <meta name="viewport"
    content="width=device-width,
    initial-scale=1.0">
  <style>
 body {
  font-family: 'Pretendard', sans-serif;
  text-align: center;
  background-color: white;
  color: #D8F6FF;
}

.header {
  background-image: url("background.png");
  background-size: cover;
  background-position: center;
  aspect-ratio: 4/1;
  max-height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  width: 100%;
}

.header h1 {
  margin: 0;
}

.slider {
  width: 90%;
  max-width: 400px;
  aspect-ratio: 4/5;
  margin: 40px auto;
  position: relative;
  overflow: hidden;
}

.slide {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.slide.active {
 opacity: 1;
 }

.gallery img {
  width: 200px;
  margin: 10px;
  border-radius: 10px;
  transition: transform 0.2s;
}

.gallery img:hover {
  transform: scale(1.1);
}

@media screen and (max-width: 600px) {
  .header {
    aspect-ratio: 2/1;
  }

  h1 {
    font-size: 1.5rem;
  }

  .slider {
    aspect-ratio: 4/5;
  }
}
.board-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
  max-width: 900px;
  margin: 40px auto;
}

.board {
  background: #f5f5f5;
  padding: 15px;
  border-radius: 12px;
  width: 100%;
  aspect-ratio: 1/1;
  overflow: hidden;
}

.board h2 {
  margin-bottom: 10px;
  color: #333;
}

.board img {
  width: 100%;
  heigt: 70%;
  object-fit: cover;
  border-radius: 8px;
}
@media screen and (max-width: 600px) {
  .board-grid {
    grid-template-columns: 1fr;
  }
}

</style>

</head>

<body>
  <div class="header">
   <h1>찐's 아카이브</h1>
</div>
  <div class="slider">
   <img class="slide" src="slide_one.png">
   <img class="slide" src="slide_two.png">
</div>

<div class="board-grid">

  <div class="board">
    <h2>팬아트</h2>
    <img src="first.draw.png">
    <img src="two.png">
  </div>

  <div class="board">
    <h2>사진</h2>
    <img src="three.png">
    <img src="four.png">
  </div>

  <div class="board">
    <h2>1Q 1A</h2>
    <img src="first.draw.png">
  </div>

  <div class="board">
    <h2>일상사진</h2>
    <img src="two.png">
  </div>

</div>

<script>
window.onload = function () {

  let slideIndex = 0;
  const slides = document.querySelectorAll(".slide");

  function showSlides() {
    slides.forEach(slide => slide.classList.remove("active"));
    slides[slideIndex].classList.add("active");

    slideIndex++;
    if (slideIndex >= slides.length) slideIndex = 0;

    setTimeout(showSlides, 3000);
  }

  showSlides();

}

<a href="board1.html" class="board">
  <h2>팬아트</h2>
  <img src="first.draw.png">
</a>

</script>



</body>


</html>
