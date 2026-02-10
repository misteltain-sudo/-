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
  width: 100%;
  max-width: 800px;
  aspect-ratio: 4/5
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

#popup {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.8);
  justify-content: center;
  align-items: center;
}

#popup img {
  max-width: 90%;
  max-height: 90%;
}

@media screen and (max-width: 600px) {
  .header {
    aspect-ratio: 2/1;
  }

  h1 {
    font-size: 1.5rem;
  }

  .slider {
    height: 200px;
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
<div class="gallery">
  <img src="first.draw.png" onclick="openPopup(this.src)">
  <img src="two.png" onclick="openPopup(this.src)">
  <img src="three.png" onclick="openPopup(this.src)">
  <img src="four.png" onclick="openPopup(this.src)">
</div>


<div id="popup" onclick="closePopup()">
  <img id="popup-img">
</div>
<script>
function openPopup(src) {
  document.getElementById("popup-img").src = src;
  document.getElementById("popup").style.display = "flex";
}

function closePopup() {
  document.getElementById("popup").style.display = "none";
}
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

</script>



</body>


</html>
