<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caça ao Tesouro do Amor</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pacifico&family=Roboto:wght@300&display=swap');

        body {
            font-family: 'Roboto', sans-serif;
            background-color: #ffe6e6;
            color: #333;
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-family: 'Pacifico', cursive;
            color: #ff3366;
            font-size: 3em;
            margin-bottom: 20px;
            animation: fadeIn 2s ease-in;
        }

        p, h2 {
            font-size: 1.2em;
            color: #444;
            margin-bottom: 15px;
        }

        input {
            padding: 10px;
            font-size: 1em;
            border: 2px solid #ff3366;
            border-radius: 5px;
            outline: none;
            transition: 0.3s ease;
        }

        input:focus {
            border-color: #ff6699;
            box-shadow: 0 0 10px #ff6699;
        }

        button {
            background-color: #ff3366;
            color: white;
            padding: 10px 20px;
            font-size: 1em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #ff6699;
        }

        #ticket {
            margin-top: 20px;
            border: 3px dashed #ff3366;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            animation: bounceIn 2s ease-in;
        }

        .hidden {
            display: none;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes bounceIn {
            0% { transform: scale(0.8); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>

    <h1>Caça ao Tesouro do Amor</h1>
    <p>Siga as dicas e reviva momentos especiais até chegar à sua surpresa final!</p>

    <div id="game">
        <p id="question"></p>
        <input type="text" id="answer" placeholder="Digite sua resposta aqui">
        <button onclick="checkAnswer()">Enviar</button>
    </div>

    <div id="final" class="hidden">
        <h2>Parabéns! Você chegou ao destino final!</h2>
        <p>Agora siga para a Sala VIP do Cinemark. Estou esperando com uma surpresa especial! ❤️</p>
        <img id="ticket" src="ingresso.png" alt="Ingresso Cinemark" width="300">
        <p>Feliz Aniversário, meu amor! ❤</p>
    </div>

    <script>
        const steps = [
            {
                question: "Dica 1: Este é o lugar que fomos com amigos no começo do namoro. Nós testamos a câmera de um computador juntinhos...",
                answer: "fastshop"
            },
            {
                question: "Dica 2: Este lugar simboliza compromisso. Você foi chamado de magrelo, e eu de dedo gordo kkk...",
                answer: "star joias"
            },
            {
                question: "Dica 3: Onde sempre comemos nossos lanches, no segundo andar...",
                answer: "burger king"
            },
            {
                question: "Dica 4: Entramos aqui só para curiar as coisas de esporte.",
                answer: "decathlon"
            }
        ];

        let currentStep = 0;

        function displayStep() {
            document.getElementById('question').textContent = steps[currentStep].question;
        }

        function checkAnswer() {
            const userAnswer = document.getElementById('answer').value.toLowerCase().trim();
            if (userAnswer === steps[currentStep].answer) {
                currentStep++;
                if (currentStep < steps.length) {
                    displayStep();
                    document.getElementById('answer').value = '';
                } else {
                    document.getElementById('game').classList.add('hidden');
                    document.getElementById('final').classList.remove('hidden');
                }
            } else {
                alert('Ops, tente de novo!');
            }
        }

        displayStep();
    </script>
</body>
</html>
