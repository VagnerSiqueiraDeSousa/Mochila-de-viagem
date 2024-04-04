# alura-armazenando-na-web


Este código JavaScript cria uma aplicação simples para gerenciar uma lista de itens, permitindo adicionar, atualizar e deletar itens. Vou explicar o código linha por linha:

const form = document.getElementById('novoItem'); - Esta linha seleciona o formulário com o id "novoItem" no HTML e o armazena na variável form.

const lista = document.getElementById("lista"); - Esta linha seleciona a lista com o id "lista" no HTML e a armazena na variável lista.

const itens = JSON.parse(localStorage.getItem("itens")) || []; - Esta linha tenta obter os itens armazenados no armazenamento local do navegador com a chave "itens". Se não houver itens armazenados, uma lista vazia é atribuída à variável itens.

itens.forEach((elemento) => { criarElementos(elemento); }) - Esta linha percorre a lista de itens recuperados e chama a função criarElementos() para cada item, para exibi-los na lista.

form.addEventListener("submit", (evento) => { ... } - Esta linha adiciona um ouvinte de evento ao formulário para o evento de submissão. Quando o formulário é enviado, a função anônima associada é executada.

Dentro da função do evento de submissão do formulário:

evento.preventDefault(); - Esta linha impede o comportamento padrão de envio do formulário.
const nome = evento.target.elements['nome']; e const quantidade = evento.target.elements['quantidade']; - Estas linhas obtêm os valores dos campos de entrada do formulário.
const existe = itens.find(elemento => elemento.nome === nome.value); - Esta linha verifica se já existe um item na lista com o mesmo nome do item submetido no formulário.
const itemAtual = {...} - Aqui é criado um objeto representando o item submetido no formulário.
O código dentro do bloco if verifica se o item já existe na lista. Se existir, o item é atualizado chamando a função atualizaElemento() e substituindo-o na lista. Caso contrário, o novo item é criado chamando criarElementos() e adicionado à lista.
localStorage.setItem("itens", JSON.stringify(itens)); - Esta linha atualiza o armazenamento local com a lista de itens atualizada.
Por fim, os campos do formulário são limpos.
As funções criarElementos(), atualizaElemento(), botaoDeleta() e deletaElemento() são definidas para criar elementos HTML, atualizar elementos existentes, criar botões de exclusão e excluir elementos da lista, respectivamente.
