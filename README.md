# Despesas App

Este projeto consiste em um aplicativo de registro de despesas, onde é possível cadastrar, pesquisar e remover despesas.

## Arquivos JavaScript

### `despesa.js`

Este arquivo contém a definição da classe `Despesa`. A classe possui um construtor que recebe os dados da despesa (ano, mês, dia, tipo, descrição e valor) e os armazena em propriedades correspondentes. A classe também possui um método `validarDados()` que verifica se todos os campos da despesa foram preenchidos corretamente.

### `bd.js`

Este arquivo contém a definição da classe `Bd` (abreviação de Banco de Dados). A classe é responsável por interagir com o armazenamento local (localStorage) do navegador para gravar, recuperar, pesquisar e remover despesas. O construtor da classe verifica se já existe um identificador (`id`) no localStorage e, caso contrário, define-o como 0. A classe possui métodos como `getProximoId()` para obter o próximo identificador disponível, `gravar()` para salvar uma despesa no localStorage, `recuperarTodosRegistros()` para recuperar todas as despesas cadastradas, `pesquisar()` para filtrar as despesas com base em critérios de pesquisa e `remover()` para excluir uma despesa do localStorage.

### `script.js`

Este arquivo contém as funções responsáveis pela interação com o HTML. A função `cadastrarDespesa()` é chamada quando o usuário clica no botão de cadastro e cria uma nova instância da classe `Despesa` com os dados preenchidos pelo usuário. A função verifica se os dados são válidos chamando o método `validarDados()` da classe `Despesa` e, em caso positivo, chama o método `gravar()` da classe `Bd` para salvar a despesa no localStorage. Em seguida, exibe uma mensagem de sucesso ou erro ao usuário.

A função `carregaListaDespesas()` é responsável por exibir as despesas cadastradas na tabela HTML. Ela recebe um array de despesas e um filtro opcional. Se nenhum array for fornecido, ele recupera todas as despesas do localStorage chamando o método `recuperarTodosRegistros()` da classe `Bd`. Em seguida, itera sobre as despesas e cria as linhas da tabela HTML.

A função `pesquisarDespesa()` é acionada quando o usuário clica no botão de pesquisa. Ela obtém os critérios de pesquisa preenchidos pelo usuário, cria uma instância da classe `Despesa` com esses critérios e chama o método `pesquisar()` da classe `Bd`, passando a instância da despesa como argumento. Em seguida, chama a função `carregaListaDespesas()` com o resultado da pesquisa para exibir as despesas filtradas na tabela HTML.

## Contribuição

Sinta-se à vontade para contribuir com melhorias para este projeto. Basta seguir as diretrizes de contribuição e enviar um pull request.

