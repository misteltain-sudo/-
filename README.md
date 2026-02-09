<!DOCTYPE html>
<html>
<head>
  <title>찐 아카이브</title>
  <link href="https://fonts.googleapis.com/css2?family=Pretendard&display=swap" rel="stylesheet">
  <style>
 body {
  font-family: 'Pretendard', sans-serif;
  text-align: center;
  background-color: white;
  color: #D8F6FF;
}
  .gallery img {
    width: 200px;
    margin: 10px;
    border-radius : 10px;
  }

  .gallery img {
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

.header {
  background-image: url("background.png");
  background-size: cover;
  background-position: center;
  aspect-ratio: 4/1;
  max-height: 300px;

  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin: 0 auto;
  width: 100%;
}

.header h1 {
   margin: 0;
 text-align: center;
}

.slideshow {
  position: relative;
  width: 40%; 
  max-width: 600px;
  height: 600px;
  margin: 20px auto; 
  overflow: hidden;
  border-radius: 10px; 

  position: relative;
}

.slide {
  width: 100%;
  height: 100%;
  object-fit: contain;
  display: none; 
  border-radius: 10px;
  margin: 0 auto;
}

.slide-container {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

</style>

</head>

<body>
  <div class="header">
   <h1>찐's 아카이브</h1>
</div>
  <div class="slideshow">
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
  slides.forEach((slide) => (slide.style.display = "none"));
  slideIndex++;
  if (slideIndex > slides.length) { slideIndex = 1; }
  slides[slideIndex - 1].style.display = "block";
  setTimeout(showSlides, 3000);
}

showSlides();


</script>



</body>


</html>
