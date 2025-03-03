# Jose
Flascards
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flashcards de Músculos de la Cara</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
        }
        .card {
            width: 80%;
            max-width: 500px;
            margin: 50px auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
            cursor: pointer;
        }
        .hidden {
            display: none;
        }
        .btn {
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="card" onclick="toggleAnswer()">
        <h2 id="question">Pregunta</h2>
        <p id="answer" class="hidden">Respuesta</p>
    </div>
    <button class="btn" onclick="nextCard()">Siguiente</button>

    <script>
        const flashcards = [
            { question: "¿Cuáles son los principales grupos de músculos de la cara?", answer: "Músculos de la expresión facial y músculos de la masticación." },
            { question: "¿Qué músculo rodea el ojo y permite su cierre?", answer: "El músculo orbicular de los ojos." },
            { question: "¿Qué músculo permite fruncir el ceño?", answer: "El músculo corrugador del ceño." },
            { question: "¿Qué músculo eleva las cejas y arruga la frente?", answer: "El músculo frontal (parte del occipitofrontal)." },
            { question: "¿Qué músculo cierra los labios y permite besar?", answer: "El músculo orbicular de los labios." },
            { question: "¿Qué músculo eleva la comisura labial y nos hace sonreír?", answer: "El músculo cigomático mayor." },
            { question: "¿Qué músculo ayuda a inflar las mejillas y soplar?", answer: "El músculo buccinador." },
            { question: "¿Cuál es el músculo más fuerte de la masticación?", answer: "El músculo masetero." },
            { question: "¿Qué músculo permite movimientos laterales de la mandíbula?", answer: "El músculo pterigoideo lateral." }
        ];

        let currentCard = 0;

        function showCard(index) {
            document.getElementById('question').innerText = flashcards[index].question;
            document.getElementById('answer').innerText = flashcards[index].answer;
            document.getElementById('answer').classList.add('hidden');
        }

        function toggleAnswer() {
            document.getElementById('answer').classList.toggle('hidden');
        }

        function nextCard() {
            currentCard = (currentCard + 1) % flashcards.length;
            showCard(currentCard);
        }

        showCard(currentCard);
    </script>
</body>
</html>
