# Rhinestone-carpenter
Dancing twister

![buh](https://github.com/nicolasbaez/Rhinestone-carpenter/blob/main/xp014.gif)
```javascript
w = k = 500;
setup = (_) => createCanvas(w, w, WEBGL);
draw = (_) => {
  colorMode(HSB, 6);
  rotateX(k);
  rotateY(k / 2);
  clear();
  stroke(abs(sin(k)) * 3, 6, 9);
  noFill();
  beginShape();
  for (j = -w / 3; j <= w / 3; j += 9) {
    r = sin(k + j) * w * 0.2;
    for (i = 0; i < 2 * PI; i += 0.3) vertex(r * cos(i), r * sin(i), j);
  }
  endShape();
  k += 0.05;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp014.gif", 126, { delay: 0, units: "frames" });
  }
};

