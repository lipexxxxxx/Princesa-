<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Te Amo Princesa</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #000;
            font-family: 'Segoe UI', sans-serif;
            cursor: pointer;
        }

        .center-text {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: #ff69b4;
            font-size: 50px;
            font-weight: bold;
            text-shadow: 2px 2px 10px #fff;
        }

        .floating-text {
            position: absolute;
            color: #fff;
            font-size: 20px;
            opacity: 0.7;
            animation: float 10s linear infinite;
            pointer-events: none;
            text-shadow: 1px 1px 5px #ff69b4;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="center-text">Te amo princesa</div>

    <script>
        // Função para criar texto flutuando
        function createFloatingText(x = Math.random() * window.innerWidth) {
            const text = document.createElement('div');
            text.className = 'floating-text';
            text.innerText = 'Te amo';
            text.style.left = `${x}px`;
            text.style.top = `${window.innerHeight}px`;
            text.style.fontSize = `${Math.random() * 20 + 15}px`;
            text.style.opacity = Math.random() * 0.5 + 0.5;
            document.body.appendChild(text);

            // Remover texto após animação
            setTimeout(() => {
                text.remove();
            }, 10000);
        }

        // Criar textos automáticos no fundo
        setInterval(() => {
            createFloatingText();
        }, 500);

        // Criar texto no clique
        document.addEventListener('click', (e) => {
            createFloatingText(e.clientX);
        });
    </script>

</body>
</html>
