To-Do List App
Este projeto é uma aplicação simples de lista de tarefas desenvolvida com HTML, JavaScript e Tailwind CSS. Ele foi criado como parte da aula de Frontend da Unifaat.

Funcionalidades
A aplicação permite:

Visualizar uma lista de tarefas pré-definidas.

Adicionar novas tarefas à lista.

Remover tarefas individualmente.

Como Rodar
Para executar este projeto localmente, siga os passos abaixo:

Clone o repositório:

git clone https://github.com/luan-tavares/unifaat-frontend-tf-aula01-server-html-jsdom.git

Entre na pasta do projeto:

cd unifaat-frontend-tf-aula01-server-html-jsdom

Abra o arquivo index.html no seu navegador de preferência.

Alternativamente, se você tiver um servidor web local (como o live-server do Node.js), pode executá-lo a partir da pasta public para garantir que o projeto funcione corretamente.

Explicação do Código (app.js)
O arquivo app.js é o coração da aplicação. Ele é responsável por toda a manipulação do DOM (Document Object Model) e a lógica da lista de tarefas.

1. Estrutura Inicial
// Aguarda o carregamento do DOM para garantir que os elementos HTML existam.
document.addEventListener('DOMContentLoaded', () => {
    // ...
});

Isso garante que o script só será executado depois que toda a estrutura HTML da página estiver carregada.

2. Elementos HTML
const listWrapper = document.getElementById('list-wrapper');
const addButton = document.getElementById('add-button');
const newTodoInput = document.getElementById('new-todo-input');

Aqui, o script seleciona os principais elementos da página usando seus IDs, permitindo que o JavaScript os manipule.

3. Renderização da Lista
function renderTodos() {
    listWrapper.innerHTML = '';
    const ul = document.createElement('ul');

    toDos.forEach(todoText => {
        const li = createTodoItem(todoText);
        ul.appendChild(li);
    });

    listWrapper.appendChild(ul);
}

A função renderTodos() é responsável por gerar dinamicamente a lista de tarefas. Ela limpa a lista existente e a reconstrói a partir do array toDos.

4. Adicionar Novas Tarefas
addButton.addEventListener('click', (event) => {
    event.preventDefault();
    const newTodoText = newTodoInput.value.trim();

    if (newTodoText) {
        const li = createTodoItem(newTodoText);
        const ul = listWrapper.querySelector('ul');
        if (ul) {
            ul.appendChild(li);
        }
        newTodoInput.value = '';
    }
});

Quando o botão "Adicionar" é clicado, este código previne a submissão do formulário, pega o valor do input, cria um novo item na lista e limpa o campo de texto.

5. Deletar Tarefas
A função createTodoItem() cria o botão "deletar" para cada item da lista e adiciona um event listener que remove o elemento <li> pai quando clicado.

deleteButton.addEventListener('click', () => {
    li.remove();
});

Esta é a lógica que permite a remoção de tarefas.
