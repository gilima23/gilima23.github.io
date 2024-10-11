<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caça ao Tesouro do Amor</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            color: #333;
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #ff4f5a;
            font-size: 2.5em;
        }
        #question {
            font-size: 1.2em;
            margin-bottom: 20px;
        }
        #answer {
            padding: 10px;
            width: 80%;
            font-size: 1em;
        }
        button {
            padding: 10px 20px;
            font-size: 1em;
            background-color: #ff4f5a;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #e5434b;
        }
        #final {
            display: none;
        }
        .hidden {
            display: none;
        }
        img {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<h1>Caça ao Tesouro do Amor</h1>
<p>Siga as pistas e reviva momentos especiais até encontrar sua surpresa final!</p>

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
