# Homework--10

<html>

<head>
    <title>
        p5.js Self-Portrait
    </title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.1.9/p5.min.js"></script>
    <script>
        let x1, x2, y1, y2;
        let speedX1, speedX2, speedY1, speedY2;
        let titleSize, titleSizeIncrement;
        let titleSizeDirection = 1;

        function setup() {
            createCanvas(400, 400);
            x1 = x2 = width / 2;
            y1 = y2 = height / 2;
            speedX1 = random(1, 3);
            speedX2 = random(1, 3);
            speedY1 = random(1, 3);
            speedY2 = random(1, 3);
            titleSize = 22;
            titleSizeIncrement = 1;
        }

        function draw() {
            background(22, 89, 67);

            // Moving shapes along the x-axis
            x1 += speedX1;
            x2 += speedX2;

            if (x1 > width || x1 < 0) {
                speedX1 *= -1;
            }

            if (x2 > width || x2 < 0) {
                speedX2 *= -1;
            }

            // Moving shapes along the y-axis
            y1 += speedY1;
            y2 += speedY2;

            if (y1 > height || y1 < 0) {
                speedY1 *= -1;
            }

            if (y2 > height || y2 < 0) {
                speedY2 *= -1;
            }

            // Moving shapes diagonally
            x1 += speedX1;
            y1 += speedY1;

            if (x1 > width || x1 < 0) {
                speedX1 *= -1;
            }

            if (y1 > height || y1 < 0) {
                speedY1 *= -1;
            }

            // Draw shapes
            fill(255);
            circle(x1, y1, 50);
            circle(x2, y2, 50);
            triangle(220, 320, 150, 220, 275, 220);
            point(245, 90);
            ellipse(245, 135, 30, 45);

            // Animate the title size
            textSize(titleSize);
            text("Evan Wright", 170, 200);
            titleSize += titleSizeIncrement;

            if (titleSize >= 30 || titleSize <= 22) {
                titleSizeIncrement *= -1;
            }
        }
    </script>
</head>

<body>

</body>

</html>


