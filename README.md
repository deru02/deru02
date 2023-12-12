function setup() {
  createCanvas(400, 400);
  angleMode(DEGREES); // Ustawienie jednostki na stopnie
}

function draw() {
  background(220);

  // Ustawienie środka rysowania na środek canvasa
  translate(width / 2, height / 2);

  // Pobranie aktualnego czasu
  let hr = hour();
  let min = minute();
  let sec = second();

  // Ustawienie kątów dla wskazówek
  let secAngle = map(sec, 0, 60, 0, 360);
  let minAngle = map(min, 0, 60, 0, 360);
  let hrAngle = map(hr % 12, 0, 12, 0, 360);

  // Narysowanie tarczy zegara
  strokeWeight(8);
  noFill();
  ellipse(0, 0, 300, 300);

  // Narysowanie wskazówki sekund
  push();
  rotate(secAngle);
  stroke(255, 0, 0);
  line(0, 0, 100, 0);
  pop();

  // Narysowanie wskazówki minut
  push();
  rotate(minAngle);
  stroke(0, 255, 0);
  line(0, 0, 75, 0);
  pop();

  // Narysowanie wskazówki godzin
  push();
  rotate(hrAngle);
  stroke(0, 0, 255);
  line(0, 0, 50, 0);
  pop();

  // Narysowanie środka tarczy zegara
  stroke(0);
  strokeWeight(12);
  point(0, 0);
}
