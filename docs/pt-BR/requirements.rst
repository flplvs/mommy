Especificação de Requisitos
===============

Navegação
------------------

:Documentos: `README <https://github.com/flplvs/mommy/tree/main/docs/pt-BR>`_ - Especificação de Requisitos
:Idiomas: `en-US <https://github.com/flplvs/mommy/blob/main/docs/en-US/requirements.rst>`_ - pt-BR

Requisitos Não-Funcionais
------------------

RNF 01
^^^^^^^^^^^^^^^^^^^^^
Deve rodar na World Wide Web.

RNF 02
^^^^^^^^^^^^^^^^^^^^^
Para desenvolver o projeto, deve-se utilizar as tecnologias: HTML, CSS, JavaScript,
Python e Flask.

RNF 03
^^^^^^^^^^^^^^^^^^^^^
Todas as páginas devem ser responsivas.

RNF 04
^^^^^^^^^^^^^^^^^^^^^
O sistema deve armazenar os dados persistentes em um banco de dados relacional.

RNF 05
^^^^^^^^^^^^^^^^^^^^^
O id dos usuários e dos meses devem ser armazenados sendo um UUID aleatório ao invés
de números crescentes.

RNF 06
^^^^^^^^^^^^^^^^^^^^^
O sistema deve gravar/trafegar a senha do usuário utilizando o algoritmo de
criptografia bcrypt.

RNF 07
^^^^^^^^^^^^^^^^^^^^^
Sair do ar em caso de ineficiência, retornando apenas ao ser reparado.

Requisitos Funcionais
------------------

RF 01
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário entre em sua conta.

- O formulário deve possuir os campos: ``email`` e ``password``.
- O campo ``email`` deve permitir o mínimo de 6 e o máximo de 254 caracteres.
- O campo ``password`` deve permitir o mínimo de 8 e o máximo de 38 caracteres.
- Os campos do formulário devem ser obrigatórios.
- Os campos com dados inválidos devem ser destacados.
- Os toasts devem ser exibidos nas tentativas mal sucedidas.
- O usuário deve ser redirecionado para o painel caso a tentativa seja bem sucedida.

RF 02
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário crie uma conta.

- O formulário deve possuir os campos: ``email``, ``password`` e ``confirm_password``.
- O campo ``email`` deve permitir o mínimo de 6 e o máximo de 254 caracteres.
- O campo ``password`` deve permitir o mínimo de 8 e o máximo de 38 caracteres.
- O campo ``confirm_password`` deve permitir o mínimo de 8 e o máximo de 38 caracteres.
- Os campos do formulário devem ser obrigatórios.
- Os toasts devem ser exibidos nas tentativas bem e mal sucedidas.
- O usuário deve ser redirecionado para a página de login caso a tentativa seja
  bem sucedida.

RF 03
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário adicione peças no mês.

- O formulário deve possuir os campos: ``name``, ``stones``, ``made`` e ``value``.
- O campo ``name`` deve permitir o mínimo de 2 e o máximo de 32 caracteres.
- O campo ``stones`` deve limitar o número para o mínimo de 1 e o máximo de 400.
- O campo ``made`` deve limitar o número para o mínimo de 1 e o máximo de 300.
- O campo ``value`` deve aceitar apenas os valores "0.025" e "0.040".
- Os campos do formulário devem ser obrigatórios.
- Os toasts devem ser exibidos nas tentativas bem e mal sucedidas.
- O usuário deve ser redirecionado para o painel nas tentativas bem e mal sucedidas.

RF 04
^^^^^^^^^^^^^^^^^^^^^
O sistema deve listar todas as peças adicionadas no mês.

- Os dados devem ser: ``registration date``, ``name``, ``stones``, ``value``,
  ``qty of prototypes``, ``qty of stones`` and ``profit``.

RF 05
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário remova peças que estão adicionadas no mês.

- O usuário deve ser consultado com uma confirmação antes da remoção.
- Os toasts devem ser exibidos nas tentativas bem e mal sucedidas.
- O usuário deve ser redirecionado para o painel nas tentativas bem e mal sucedidas.

RF 06
^^^^^^^^^^^^^^^^^^^^^
O sistema deve exibir o resumo do mês.

- Os dados devem ser: ``month``, ``total prototypes``, ``total stones`` and ``profit``.

RF 07
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário encerre o mês.

- O usuário deve ser consultado com uma confirmação antes do encerramento.
- O novo mês do usuário deve ser o mês atual do servidor caso ele seja
  encerrado do dia 1 ao dia 5.
- O novo mês do usuário deve ser o mês seguinte do servidor caso ele seja
  encerrado antes do dia 1 e depois do dia 5.
- O usuário não pode ter permissão de encerrar o mês caso o mês do usuário seja
  o mês seguinte do servidor.
- Os toasts devem ser exibidos nas tentativas bem e mal sucedidas.
- O usuário deve ser redirecionado para o painel nas tentativas bem e mal sucedidas.

RF 08
^^^^^^^^^^^^^^^^^^^^^
O sistema deve permitir que o usuário compartilhe seus meses com outras pessoas.

- A página de compartilhamento deve exibir todos os meses do usuário.
- Ao clicar sobre um mês, deve-se abrir uma página seguindo os requisitos
  ``RF 04`` e ``RF 06``.
- O usuário deve ter a possibilidade de copiar o link de sua página de
  compartilhamento.
