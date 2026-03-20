<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Calculadora</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body { 
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #121212;
    }

    .calculadora {
      background: #1f1f2e;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 40px rgba(0,0,0,0.6);
    }

    #display {
      width: 100%;
      height: 70px;
      font-size: 28px;
      text-align: right;
      padding: 10px;
      margin-bottom: 15px;
      border: none;
      border-radius: 8px;
      background: #fff;
    }

    .botoes {
      display: grid;
      grid-template-columns: repeat(4, 70px);
      gap: 10px;
    }

    button {
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #2e2e44;
      color: white;
      transition: 0.2s;
    }

    button:hover {
      background: #444466;
    }

    .igual {
      background: #00bfff;
    }

    .igual:hover {
      background: #009acd;
    }

    .limpar {
      background: #ff4d4d;
    }

    .limpar:hover {
      background: #cc0000;
    }
  </style>
</head>

<body>

  <div class="calculadora">
    <input type="text" id="display" disabled>

    <div class="botoes">
      <button onclick="limpar()" class="limpar">C</button>
      <button onclick="adicionar('/')">/</button>
      <button onclick="adicionar('*')">*</button>
      <button onclick="adicionar('-')">-</button>
      <button onclick="adicionar(',')">,</button>
      <button onclick="adicionar('%')">%</button>
      <button onclick="adicionar('.')">.</button>
      <button onclick="adicionar('$')">$</button>

      <button onclick="adicionar('7')">7</button>
      <button onclick="adicionar('8')">8</button>
      <button onclick="adicionar('9')">9</button>
      <button onclick="adicionar('+')">+</button>

      <button onclick="adicionar('4')">4</button>
      <button onclick="adicionar('5')">5</button>
      <button onclick="adicionar('6')">6</button>
      <button onclick="calcular()" class="igual">=</button>

      <button onclick="adicionar('1')">1</button>
      <button onclick="adicionar('2')">2</button>
      <button onclick="adicionar('3')">3</button>
      <button onclick="adicionar('0')">0</button>
      
      
    </div>
  </div>

  <script>
    function adicionar(valor) {
      document.getElementById("display").value += valor;
    }

    function limpar() {
      document.getElementById("display").value = "";
    }

    function calcular() {
      const display = document.getElementById("display");
      try {
        display.value = eval(display.value);
      } catch (erro) {
        display.value = "Erro";
      }
    }
  </script>

</body>
</html>
