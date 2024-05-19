<!DOCTYPE html>
<html lang="fi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Angry Birds -tyylinen peli</title>
    <style>
        body { margin: 0; padding: 0; overflow: hidden; }
        canvas { display: block; background: url('background.png') no-repeat center center; background-size: cover; }
        #score {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 24px;
            font-family: Arial, sans-serif;
            color: white;
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 5px;
        }
        #title {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 24px;
            font-family: Arial, sans-serif;
            color: white;
            background: rgba(0, 0, 0, 0.5);
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div id="title">Hepobirds</div>
    <div id="score">Pisteet: 0</div>
    <canvas id="gameCanvas"></canvas>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        // Lataa lintukuva
        const birdImage = new Image();
        birdImage.src = 'bird.png'; // Viittaa projektikansiossa olevaan lintukuvaan

        // Lataa possukuva
        const pigImage = new Image();
        pigImage.src = 'pig.png'; // Viittaa projektikansiossa olevaan possukuvaan

        let score = 0;

        birdImage.onload = () => {
            pigImage.onload = () => {
                animate();
            };
        };

        class Bird {
            constructor() {
                this.radius = 20;
                this.x = 150;
                this.y = canvas.height - 100;
                this.initialX = this.x;
                this.initialY = this.y;
                this.velocityX = 0;
                this.velocityY = 0;
                this.isDragging = false;
                this.isFlying = false;
                this.image = birdImage;
                this.imageWidth = 40;  // Aseta kuvasi leveys
                this.imageHeight = 40; // Aseta kuvasi korkeus
            }

            draw() {
                ctx.drawImage(this.image, this.x - this.imageWidth / 2, this.y - this.imageHeight / 2, this.imageWidth, this.imageHeight);
            }

            update() {
                if (this.isFlying) {
                    this.x += this.velocityX;
                    this.y += this.velocityY;
                    this.velocityY += 0.2; // Gravity

                    // Bounce off the ground
                    if (this.y + this.radius > canvas.height) {
                        this.y = canvas.height - this.radius;
                        this.velocityY *= -0.7;
                        this.velocityX *= 0.7;
                    }

                    // Bounce off the sides
                    if (this.x + this.radius > canvas.width || this.x - this.radius < 0) {
                        this.velocityX *= -0.7;
                    }

                    // Stop if velocity is very low
                    if (Math.abs(this.velocityX) < 0.1 && Math.abs(this.velocityY) < 0.1 && this.y + this.radius >= canvas.height) {
                        this.reset();
                    }
                }
            }

            reset() {
                this.x = this.initialX;
                this.y = this.initialY;
                this.velocityX = 0;
                this.velocityY = 0;
                this.isFlying = false;
            }
        }

        class Block {
            constructor(x, y, width, height) {
                this.x = x;
                this.y = y;
                this.width = width;
                this.height = height;
                this.isHit = false;
                this.pig = null;
                this.isFalling = false;
                this.velocityY = 0;
            }

            draw() {
                if (!this.isHit) {
                    ctx.fillStyle = 'brown';
                    ctx.fillRect(this.x, this.y, this.width, this.height);
                    if (this.pig && !this.pig.isFalling) {
                        ctx.drawImage(this.pig.image, this.x + (this.width - this.pig.width) / 2, this.y - this.pig.height, this.pig.width, this.pig.height);
                    }
                } else if (this.isFalling) {
                    this.y += this.velocityY;
                    this.velocityY += 0.5; // Gravity
                    if (this.y + this.height > canvas.height) {
                        this.y = canvas.height - this.height;
                        this.isFalling = false;
                        if (this.pig) {
                            this.pig.isFalling = true;
                        }
                    }
                }
            }

            checkCollision(bird) {
                const distX = Math.abs(bird.x - this.x - this.width / 2);
                const distY = Math.abs(bird.y - this.y - this.height / 2);

                if (distX > (this.width / 2 + bird.radius) || distY > (this.height / 2 + bird.radius)) {
                    return false;
                }

                if (distX <= (this.width / 2) || distY <= (this.height / 2)) {
                    return true;
                }

                const dx = distX - this.width / 2;
                const dy = distY - this.height / 2;
                return (dx * dx + dy * dy <= (bird.radius * bird.radius));
            }
        }

        class Pig {
            constructor() {
                this.image = pigImage;
                this.width = 30;
                this.height = 30;
                this.isFalling = false;
                this.x = 0;
                this.y = 0;
                this.velocityY = 0;
            }

            draw() {
                if (this.isFalling) {
                    this.y += this.velocityY;
                    this.velocityY += 0.5; // Gravity
                    if (this.y + this.height > canvas.height) {
                        this.y = canvas.height - this.height;
                        this.isFalling = false;
                        score++;
                        document.getElementById('score').innerText = 'Pisteet: ' + score;
                    }
                    ctx.drawImage(this.image, this.x, this.y, this.width, this.height);
                }
            }
        }

        const bird = new Bird();
        const blocks = [
            new Block(canvas.width - 150, canvas.height - 60, 100, 50),
            new Block(canvas.width - 150, canvas.height - 120, 100, 50),
            new Block(canvas.width - 150, canvas.height - 180, 100, 50),
            new Block(canvas.width - 150, canvas.height - 240, 100, 50),
            new Block(canvas.width - 150, canvas.height - 300, 100, 50),
            new Block(canvas.width - 150, canvas.height - 360, 100, 50),

            new Block(canvas.width - 300, canvas.height - 60, 100, 50),
            new Block(canvas.width - 300, canvas.height - 120, 100, 50),
            new Block(canvas.width - 300, canvas.height - 180, 100, 50),
            new Block(canvas.width - 300, canvas.height - 240, 100, 50),
            new Block(canvas.width - 300, canvas.height - 300, 100, 50),
            new Block(canvas.width - 300, canvas.height - 360, 100, 50),

            new Block(canvas.width - 450, canvas.height - 60, 100, 50),
            new Block(canvas.width - 450, canvas.height - 120, 100, 50),
            new Block(canvas.width - 450, canvas.height - 180, 100, 50),
            new Block(canvas.width - 450, canvas.height - 240, 100, 50),
            new Block(canvas.width - 450, canvas.height - 300, 100, 50),
            new Block(canvas.width - 450, canvas.height - 360, 100, 50),

            new Block(canvas.width - 300, canvas.height - 420, 100, 50)
        ];

        // Lisää possuja palikoiden päälle
        blocks[5].pig = new Pig();
        blocks[5].pig.x = blocks[5].x + (blocks[5].width - blocks[5].pig.width) / 2;
        blocks[5].pig.y = blocks[5].y - blocks[5].pig.height;

        blocks[11].pig = new Pig();
        blocks[11].pig.x = blocks[11].x + (blocks[11].width - blocks[11].pig.width) / 2;
        blocks[11].pig.y = blocks[11].y - blocks[11].pig.height;

        blocks[17].pig = new Pig();
        blocks[17].pig.x = blocks[17].x + (blocks[17].width - blocks[17].pig.width) / 2;
        blocks[17].pig.y = blocks[17].y - blocks[17].pig.height;

        function drawSlingshot() {
            ctx.beginPath();
            ctx.moveTo(150, canvas.height - 100);
            if (bird.isDragging) {
                ctx.lineTo(bird.x, bird.y);
            } else {
                ctx.lineTo(150, canvas.height - 100);
            }
            ctx.strokeStyle = 'black';
            ctx.lineWidth = 5;
            ctx.stroke();
            ctx.closePath();
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            drawSlingshot();
            bird.update();
            bird.draw();
            blocks.forEach(block => {
                if (block.checkCollision(bird)) {
                    block.isHit = true;
                    block.isFalling = true;
                    if (block.pig) {
                        block.pig.isFalling = true;
                    }
                    bird.reset();
                }
                block.draw();
                if (block.pig) {
                    block.pig.draw();
                }
            });
            requestAnimationFrame(animate);
        }

        canvas.addEventListener('mousedown', (e) => {
            const dist = Math.sqrt((e.clientX - bird.x) ** 2 + (e.clientY - bird.y) ** 2);
            if (dist < bird.radius) {
                bird.isDragging = true;
                bird.isFlying = false;
            }
        });

        canvas.addEventListener('mousemove', (e) => {
            if (bird.isDragging) {
                bird.x = e.clientX;
                bird.y = e.clientY;
            }
        });

        canvas.addEventListener('mouseup', (e) => {
            if (bird.isDragging) {
                bird.isDragging = false;
                bird.isFlying = true;
                bird.velocityX = (bird.initialX - e.clientX) * 0.2;  // Voimakkaampi ritsa
                bird.velocityY = (bird.initialY - e.clientY) * 0.2;  // Voimakkaampi ritsa
            }
        });
    </script>
</body>
</html>
