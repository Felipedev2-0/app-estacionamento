<template>
    <div id="carro-table">
      <div>
        <div class="carro-table-heading">
          <div class="order-id">#:</div>
          <div>Nome da Pessoa:</div>
          <div>Nome do Carro:</div>
          <div>Placa do Carro:</div>
          <div>Horário de Entrada:</div>
          <div>Ações:</div>
        </div>
      </div>
  
      <div id="carro-table-rows">
        <div class="carro-table-row">
          <div class="order-number">1</div>
          <div>Leo</div>
          <div>Corsa</div>
          <div>PDR4E84</div>
          <div>08:00h</div>
  
          <div class="actions">
            <select name="status" class="status">
              <option value="">Status Carro</option>
            </select>
  
            <button class="delete-btn">Deletar</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Dashboard"
  }
  </script>
  
  <style scoped>
  /* Container principal */
  #carro-table {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px; /* Adicionei padding para dar espaçamento interno */
    background-color: #f8f8f8; /* Adicionei um fundo para destacar o conteúdo */
    border-radius: 8px; /* Bordas arredondadas */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Sombra para dar um efeito de elevação */
  }
  
  /* Cabeçalho da tabela */
  .carro-table-heading {
    display: flex;
    justify-content: space-between; /* Espaço igual entre as colunas */
    align-items: center;
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid rgba(53, 30, 180, 1);
    background-color: #3f7fbf; /* Fundo azul */
    color: white; /* Texto branco */
  }
  
  /* Linhas da tabela */
  .carro-table-row {
    display: flex;
    justify-content: space-between; /* Espaço igual entre as colunas */
    align-items: center;
    padding: 12px;
    border-bottom: 1px solid rgba(53, 30, 180, 1);
  }
  
  .carro-table-row:nth-child(even) {
    background-color: #e9e9e9; /* Fundo alternado para as linhas pares */
  }
  
  /* Colunas de IDs */
  .order-id, .order-number {
    width: 5%;
    text-align: center; /* Centraliza o texto */
  }
  
  /* Colunas padrão */
  .carro-table-heading div:not(.order-id),
  .carro-table-row div:not(.order-number) {
    width: 18%; /* Ajuste da largura para somar 100% */
    text-align: center; /* Centraliza o texto */
  }
  
  /* Ações */
  .actions {
    display: flex;
    align-items: center;
    justify-content: space-around; /* Distribui espaço entre os elementos */
    width: 19%; /* Ajusta para corresponder às outras colunas */
  }
  
  /* Select de status */
  select {
    padding: 8px 12px;
    margin-right: 8px;
    border-radius: 4px;
    border: 1px solid #ccc;
  }
  
  /* Botão de deletar */
  .delete-btn {
    background-color: #bf3f3f;
    color: white;
    font-weight: bold;
    padding: 8px 12px;
    font-size: 14px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }
  
  .delete-btn:hover {
    background-color: tomato;
    transform: scale(1.05); /* Leve aumento ao passar o mouse */
  }
  </style>
  