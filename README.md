This HTML file creates a canvas where a toy car image moves based on arrow key input, styled to resemble a playful toy store webpage. The car stays within canvas boundaries, and the page includes a simple header and instructions.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toy Store - Moving Toy Car</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9e6ff;
            margin: 0;
            padding: 20px;
        }
        h1 {
            color: #ff4500;
            font-size: 2.5em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }
        p {
            color: #333;
            font-size: 1.2em;
        }
        canvas {
            border: 2px solid #ff4500;
            background-color: #e0f7fa;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Welcome to Toy Galaxy!</h1>
    <p>Use arrow keys to move the toy car around the play area!</p>
    <canvas id="toyCanvas" width="800" height="400"></canvas>

    <script>
        // Get canvas and context
        const canvas = document.getElementById("toyCanvas");
        const ctx = canvas.getContext("2d");

        // Load toy car image
        const toyImage = new Image();
        toyImage.src = "toy_car.png"; // Replace with your toy car image path

        // Toy car properties
        let toy = {
            x: 50, // Starting x position
            y: 50, // Starting y position
            width: 60, // Image width
            height: 40, // Image height
            speedX: 0, // Speed in x direction
            speedY: 0, // Speed in y direction
            speed: 5 // Movement speed
        };

        // Handle key presses
        document.addEventListener("keydown", function(event) {
            if (event.key === "ArrowRight") toy.speedX = toy.speed;
            else if (event.key === "ArrowLeft") toy.speedX = -toy.speed;
            else if (event.key === "ArrowUp") toy.speedY = -toy.speed;
            else if (event.key === "ArrowDown") toy.speedY = toy.speed;
        });

        document.addEventListener("keyup", function(event) {
            if (event.key === "ArrowRight" || event.key === "ArrowLeft") toy.speedX = 0;
            if (event.key === "ArrowUp" || event.key === "ArrowDown") toy.speedY = 0;
        });

        // Animation loop
        function updateToyArea() {
            // Clear canvas
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Update position
            toy.x += toy.speedX;
            toy.y += toy.speedY;

            // Keep toy within canvas bounds
            if (toy.x < 0) toy.x = 0;
            if (toy.x + toy.width > canvas.width) toy.x = canvas.width - toy.width;
            if (toy.y < 0) toy.y = 0;
            if (toy.y + toy.height > canvas.height) toy.y = canvas.height - toy.height;

            // Draw toy car
            ctx.drawImage(toyImage, toy.x, toy.y, toy.width, toy.height);

            // Continue animation
            requestAnimationFrame(updateToyArea);
        }

        // Start animation when image is loaded
        toyImage.onload = function() {
            updateToyArea();
        };
    </script>
</body>
</html>This HTML file creates a canvas where a toy car image moves based on arrow key input, styled to resemble a playful toy store webpage. The car stays within canvas boundaries, and the page includes a simple header and instructions.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toy Store - Moving Toy Car</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9e6ff;
            margin: 0;
            padding: 20px;
        }
        h1 {
            color: #ff4500;
            font-size: 2.5em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }
        p {
            color: #333;
            font-size: 1.2em;
        }
        canvas {
            border: 2px solid #ff4500;
            background-color: #e0f7fa;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            margin-top: 20px;
        }
    </style>
</head>
<body>
