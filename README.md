<!DOCTYPE html>
<html lang="pt-BR">
  </head>

<meta charset="UTF-8">
<title>Calculadora de Média</title>
<style>
  body{
  font-family:Arial, sans-serif;
  max-width:400px;
  margin:20px auto;
}
.form-group{
  margin-bottom:15px;
  }
label{
  display: block;
  margin-bottom: 5px;
}
input{
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}
button{
  width:100%;
  padding: 10px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}
#resultado{
  margin-top: 15px;
  font-weight: bold;
}
</style>
</head>
<body>
  <h2>Calcular Média do Aluno</h2>
  <div class="form-group">
    <label for="nota1">Nota 1:</label>
    <input type="number" id="nota1" step="0.1" placeholder="Ex:7.0">
    <label for="nota2">Nota 2:</label>
    <input type="number" id="nota2" step="0.1" placeholder="Ex: 8.5">
    <button onclick="calcularMedia()">Calcular Média</button>
  <div id="resultado"></div>
  <script>
    function calcularMedia(){
      // Captura os valores digitados nos inputs
      const n1 =parseFloat(document.getElementById('nota1').value);
      const n2 =parseFloat(document.getElementById('nota2').value);
      const resultadoDiv = document.getElementById('resultado');
      //validação simples
      if (isNaN(n1) || isNaN(n2)){
        resultadoDiv.innerText = "por favor preencha ambas notas.";
        resultadoDiv.style.color = "red";
        return;
      }
      //Cálculo da média
      const media = (n1 + n2) / 2;
      const status = media >= 7.0 ? "Aprovado" : "Reprovado";
      // Exibição do resultado
      resultadoDiv.style.color = media >= 7.0 ? "green" : "red";
      resultadoDiv.innerText = `Média: ${media.toFixed(2)} - Status: ${status}`;
    }
  </script>
</body>
</html>
