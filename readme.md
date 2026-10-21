!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Lista de Tarefas</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: #f2f4f8;
    }

    h1 { text-align: center; }

    input, button {
      padding: 10px;
      font-size: 16px;
    }

    input { width: 65%; }

    li {
      margin: 10px 0;
      padding: 10px;
      background: white;
      display: flex;
      justify-content: space-between;
    }
  </style>
</head>
<body>
  <h1>Minha Lista de Tarefas</h1>

  <input id="campoTarefa" placeholder="Digite uma tarefa">
  <button onclick="adicionarTarefa()">Adicionar</button>

  <ul id="lista"></ul>

  <script>
    function adicionarTarefa() {
      const campo = document.getElementById("campoTarefa");
      const texto = campo.value.trim();

      if (texto === "") {
        alert("Digite uma tarefa primeiro!");
        return;
      }

      const tarefa = document.createElement("li");
      tarefa.textContent = texto;

      const botao = document.createElement("button");
      botao.textContent = "Excluir";
      botao.onclick = function() {
        tarefa.remove();
      };

      tarefa.appendChild(botao);
      document.getElementById("lista").appendChild(tarefa);
      campo.value = "";
    }
  </script>
</body>
</html>
