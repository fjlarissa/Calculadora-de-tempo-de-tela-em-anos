<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Vida em Pixels</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

    <style>
        /* CSS Reset e Estilos Gerais */
        body {
            /* Aplicando a fonte Poppins */
            font-family: 'Poppins', sans-serif;
            font-weight: 300;
            background-color: #ffffff;
            color: #000000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        /* Contêiner principal */
        .container {
            background-color: #ffffff;
            padding: 40px;
            border-radius: 20px;
            border: 1px solid #000000;
            text-align: center;
            max-width: 450px;
            width: 100%;
        }

        /* Título */
        h1 {
            font-weight: 600;
            font-size: 2.2em; /* Aumentei um pouco para dar mais destaque ao nome */
            margin-bottom: 15px;
        }

        /* Parágrafo de descrição */
        p {
            font-size: 1em;
            line-height: 1.5;
            margin-bottom: 25px;
        }

        /* Campo de inserção de número */
        input[type="number"] {
            font-family: 'Poppins', sans-serif;
            width: 100%;
            padding: 15px;
            border: 1px solid #000000;
            border-radius: 12px;
            font-size: 1em;
            box-sizing: border-box;
        }

        /* Remove as setas do campo de número */
        input[type=number]::-webkit-inner-spin-button, 
        input[type=number]::-webkit-outer-spin-button { 
            -webkit-appearance: none; 
            margin: 0; 
        }
        input[type=number] {
            -moz-appearance: textfield;
        }

        /* Botão */
        button {
            font-family: 'Poppins', sans-serif;
            font-weight: 400;
            background-color: #000000;
            color: #ffffff;
            padding: 15px 30px;
            border: none;
            border-radius: 12px;
            font-size: 1.1em;
            cursor: pointer;
            margin-top: 20px;
            width: 100%;
            transition: transform 0.2s ease, opacity 0.2s ease;
        }

        button:hover {
            opacity: 0.85;
        }
        
        button:active {
            transform: scale(0.98);
        }

        /* Área do resultado */
        #resultado {
            margin-top: 30px;
            font-size: 1.15em;
            font-weight: 400;
            min-height: 50px;
            line-height: 1.4;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Vida em Pixels</h1>
        <p>Descubra quantos anos da sua vida você passará em frente a telas, com base no seu uso diário (expectativa de vida de 80 anos).</p>

        <input type="number" id="horasDiarias" placeholder="Horas por dia em frente a telas">

        <button onclick="calcularTempo()">Calcular</button>

        <div id="resultado"></div>
    </div>

    <script>
        function calcularTempo() {
            const horasDiariasInput = document.getElementById('horasDiarias');
            const horasDiarias = horasDiariasInput.value;
            const resultadoDiv = document.getElementById('resultado');

            if (horasDiarias === '' || horasDiarias < 0 || horasDiarias > 24) {
                resultadoDiv.innerHTML = "Por favor, insira um valor válido entre 0 e 24.";
                return;
            }

            const expectativaDeVida = 80;
            const anosPerdidos = (horasDiarias / 24) * expectativaDeVida;

            resultadoDiv.innerHTML = `Com ${horasDiarias} horas diárias, você passará o equivalente a <strong>${anosPerdidos.toFixed(1)} anos</strong> de sua vida em frente a uma tela.`;
        }
    </script>

</body>
</html>
