---
title: "AI generated javascript: Variable Petal Lines Animation"
tags:
  - AI, chatbot, Javascript
---

AI generated javascript: Variable Petal Lines Animation

<style>
        canvas {
            background-color: white;
            border: 1px solid #ccc;
        }
        .controls {
            margin: 10px 0;
            font-family: Arial, sans-serif;
        }
        .controls label {
            margin-right: 10px;
        }
</style>
<div class="controls">
        <label for="freqRange">Frequency: <span id="freqValue">1</span></label>
        <input type="range" id="freqRange" min="1" max="24" step="1" value="1">
</div>
<canvas id="animationCanvas" width="600" height="600"></canvas>
<script>

        const canvas = document.getElementById('animationCanvas');
        const ctx = canvas.getContext('2d');
        const freqRange = document.getElementById('freqRange');
        const freqValue = document.getElementById('freqValue');
        
        let FREQ = parseFloat(freqRange.value); // Initialize FREQ from range input
        const nPoints = 240;
        let step = 1;
        let rotationAngle = 0;

        freqRange.addEventListener('input', () => {
            FREQ = parseFloat(freqRange.value); // Update FREQ whenever the slider changes
            freqValue.textContent = FREQ.toFixed(1); // Update displayed value
        });

        function getPoints() {
            const points = [];
            const centerX = canvas.width / 2;
            const centerY = canvas.height / 2;
            const radius = Math.min(centerX, centerY) * 0.9;

            for (let i = 0; i < nPoints; i++) {
                const theta = (2 * Math.PI * i) / nPoints;
                const r = Math.cos(FREQ * theta);
                const x = centerX + radius * r * Math.cos(theta);
                const y = centerY + radius * r * Math.sin(theta);
                points.push({ x, y });
            }

            return points;
        }

        function rotatePoints(points, angle) {
            const rotatedPoints = [];
            const centerX = canvas.width / 2;
            const centerY = canvas.height / 2;
            const rad = angle * (Math.PI / 180); // Convert degrees to radians

            for (const point of points) {
                const x = point.x - centerX;
                const y = point.y - centerY;

                const newX = x * Math.cos(rad) - y * Math.sin(rad);
                const newY = x * Math.sin(rad) + y * Math.cos(rad);

                rotatedPoints.push({
                    x: newX + centerX,
                    y: newY + centerY,
                });
            }

            return rotatedPoints;
        }

        function drawPoints(points) {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = 'blue';

            for (const point of points) {
                ctx.beginPath();
                ctx.arc(point.x, point.y, 3, 0, 2 * Math.PI);
                ctx.fill();
            }
        }

        function drawLines(points, step) {
            ctx.strokeStyle = 'blue';

            for (let i = 0; i < points.length; i++) {
                const j = (i + step) % points.length;
                ctx.strokeStyle = `hsl(${(i / points.length) * 360}, 100%, 50%)`;
                ctx.beginPath();
                ctx.moveTo(points[i].x, points[i].y);
                ctx.lineTo(points[j].x, points[j].y);
                ctx.stroke();
            }
        }

        function animate() {
            const points = getPoints();
            const rotatedPoints = rotatePoints(points, rotationAngle);
            drawPoints(rotatedPoints);
            drawLines(rotatedPoints, step);
            
            step = (step % (nPoints - 1)) + 1; // Increment step
            rotationAngle += 3; // Rotate by 3 degrees

            setTimeout(animate, 200); // Control animation speed
        }

        animate();
</script>
