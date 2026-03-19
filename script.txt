function openBox() {
  document.getElementById("box").style.display = "none";
  document.getElementById("music").play();

  document.getElementById("gallery").style.display = "block";
  document.getElementById("message").style.display = "block";
  document.getElementById("games").style.display = "block";

  startSlideshow();
}

let images = ["ss.jpg", "ss1.jpg", "ss2.jpg"];
let i = 0;

function startSlideshow() {
  setInterval(() => {
    i = (i + 1) % images.length;
    document.getElementById("slide").src = images[i];
  }, 2000);
}

function fireworks(e) {
  let fire = document.createElement("div");
  fire.className = "fire";
  fire.style.left = e.clientX + "px";
  fire.style.top = e.clientY + "px";
  document.body.appendChild(fire);

  setTimeout(() => fire.remove(), 1000);
}

function checkGame1(el) {
  if (el.innerText.includes("Sheer")) {
    document.getElementById("result1").innerText = "🎉 Correct!";
  } else {
    document.getElementById("result1").innerText = "❌ Try again!";
  }
}
