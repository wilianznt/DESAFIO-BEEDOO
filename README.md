# DESAFIO BEEDOO

## Introdução

Este repositório contém o desafio para o módulo de curso do Beedoo. O objetivo é criar user stories e casos de teste para o módulo, documentar as decisões tomadas, e fornecer evidências de teste.

  ## User Stories
  
  ### Feature: Cadastro e Gerenciamento de Curso
  
  Como um usuário do sistema  
  Eu quero cadastrar, editar e excluir cursos  
  Para gerenciar a lista de cursos disponíveis
  
  #### História 1: Cadastro de Curso
  **Como** um usuário  
  **Eu quero** cadastrar um novo curso  
  **Para que** ele apareça na lista de cursos disponíveis
  
  **Critérios de Aceitação:**
  - O curso deve ser adicionado à lista de cursos.
  - Uma mensagem de confirmação de sucesso deve ser exibida.
  
  **Decisões Tomadas:**
  - O cadastro deve incluir validação para todos os campos obrigatórios.
  - O sistema deve fornecer feedback claro em caso de erros.
  
  #### História 2: Edição de Curso
  **Como** um usuário  
  **Eu quero** editar os detalhes de um curso existente  
  **Para que** eu possa atualizar as informações conforme necessário
  
  **Critérios de Aceitação:**
  - Os detalhes do curso devem ser atualizados corretamente na lista de cursos.
  - As alterações devem ser salvas e refletidas na lista de cursos.
  
  **Decisões Tomadas:**
  - A edição deve permitir a modificação de todos os campos do curso.
  - O sistema deve confirmar que as alterações foram salvas com sucesso.
  
  #### História 3: Exclusão de Curso
  **Como** um usuário  
  **Eu quero** excluir um curso  
  **Para que** ele não apareça mais na lista de cursos
  
  **Critérios de Aceitação:**
  - O curso deve ser removido da lista de cursos.
  - Uma mensagem de confirmação de exclusão deve ser exibida.
  
  **Decisões Tomadas:**
  - A exclusão deve ser confirmada pelo usuário para evitar exclusões acidentais.
  - O sistema deve garantir que o curso seja removido permanentemente da lista.
  
  ## Cenários de Teste
  
  ### Feature: Cadastro e Gerenciamento de Curso
  
  Como um usuário do sistema  
  Eu quero cadastrar, editar e excluir cursos  
  Para gerenciar a lista de cursos disponíveis
  
  #### Cenário: Cadastro de curso com sucesso
  Dado que estou na página de cadastro de curso  
  Quando eu preencho todos os campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então o curso deve ser adicionado à lista de cursos  
  E eu devo ver uma mensagem de confirmação de sucesso
  
  #### Cenário: Cadastro de curso sem preencher campos obrigatórios
  Dado que estou na página de cadastro de curso  
  Quando eu não preencho nenhum campo obrigatório  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver mensagens de erro indicando quais campos são obrigatórios
  
  #### Cenário: Cadastro de curso com nome inválido
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "Nome do Curso" com um nome que contém caracteres inválidos  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que o nome do curso é inválido
  
  #### Cenário: Cadastro de curso com URL de imagem inválida
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "URL da Imagem de Capa" com um link para uma imagem inválida  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que a URL da imagem é inválida
  
  #### Cenário: Cadastro de curso com data de fim anterior à data de início
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "Data de Início" com uma data futura  
  E preencho o campo "Data de Fim" com uma data anterior à data de início  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que a data de fim deve ser posterior à data de início
  
  #### Cenário: Cadastro de curso com descrição muito longa
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "Descrição do Curso" com um texto que excede o limite de caracteres permitidos  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que a descrição é muito longa
  
  #### Cenário: Cadastro de curso com número de vagas inválido
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "Número de Vagas" com um valor fora do intervalo permitido (ex.: 1001)  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que o número de vagas é inválido
  
  #### Cenário: Cadastro de curso com caracteres especiais no nome
  Dado que estou na página de cadastro de curso  
  Quando eu preencho o campo "Nome do Curso" com caracteres especiais não permitidos  
  E preencho os outros campos obrigatórios com dados válidos  
  E clico no botão "Cadastrar Curso"  
  Então eu devo ver uma mensagem de erro indicando que o nome do curso contém caracteres especiais inválidos
  
  #### Cenário: Cadastro de curso com dados válidos e upload de imagem
  Dado que estou na página de cadastro de curso  
  Quando eu preencho todos os campos obrigatórios com dados válidos  
  E faço o upload de uma imagem de capa válida  
  E clico no botão "Cadastrar Curso"  
  Então o curso deve ser adicionado à lista de cursos  
  E a imagem de capa deve ser exibida corretamente
  
  #### Cenário: Excluir um curso da lista
  Dado que estou na lista de cursos  
  Quando eu clico no botão "Excluir" ao lado de um curso  
  E confirmo a exclusão  
  Então o curso deve ser removido da lista  
  E uma mensagem de confirmação de exclusão deve ser exibida
  
  #### Cenário: Excluir um curso que não existe
  Dado que estou na lista de cursos  
  Quando eu tento excluir um curso que não existe  
  Então o sistema deve exibir uma mensagem de erro apropriada
  
  #### Cenário: Editar um curso existente
  Dado que estou na lista de cursos  
  E eu clico no botão "Editar" ao lado de um curso  
  Quando eu sou redirecionado para a página de edição do curso  
  E vejo os campos preenchidos com os dados atuais do curso  
  Quando eu faço as seguintes alterações:
    | Nome do Curso   | Descrição do Curso  | Instrutor        | URL da Imagem de Capa   | Data de Início | Data de Fim | Número de Vagas | Tipo de Curso |
    | Curso Editado   | Nova descrição.     | Wilian Costa    | http://example.com/nova_imagem.jpg | 02/08/2024 | 02/09/2024 | 20             | Online        |
  E clico no botão "Salvar Alterações"  
  Então as alterações devem ser salvas com sucesso  
  E a lista de cursos deve ser atualizada com os novos dados
  
  #### Cenário: Voltar para a página anterior
  Dado que estou na página de cadastro ou edição  
  Quando eu clico no botão "Voltar"  
  Então eu devo ser redirecionado para a página anterior
  
  ## Passo-a-Passo para Execução dos Casos de Teste
  
  <!-- Inclua o passo-a-passo para cada cenário de teste -->
  
  ## Planilha de Casos de Teste
  
  [Link para o Google Docs](https://docs.google.com/document/d/1q5b2KqKWFFtigfrT_EpPFKitzo2oyC3alVeyq0GFIJk/edit?usp=sharing) "Cenários de teste em Gherkin"
  
  [Link para a Google Planilhas](https://docs.google.com/spreadsheets/d/187CRE161XUz98D7ZtxIcpMZF0YjO4gzBUfMdjm-Lquk/edit?usp=sharing) "Casos de teste/Dados de validação"
  ## Evidências de Teste
  
  - [Evidência 1](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/1#issue-2442752510)
  - [Evidência 2](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/2#issue-2442781237)
  - [Evidência 3](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/3#issue-2445122214)
  - [Evidência 4](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/4#issue-2445125354)
  - [Evidência 5](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/5#issue-2445128223)
  - [Evidência 6](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/6#issue-2445131008)
  - [Evidência 7](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/7#issue-2445133893)
  - [Evidência 8](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/8#issue-2445137175)
  - [Evidência 9](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/9#issue-2445139743)
  - [Evidência 10](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/10#issue-2445142526)
  - [Evidência 11](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/11#issue-2445149189)
  - [Evidência 12](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/12#issue-2445419731)
  - [Evidência 13](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/13#issue-2445421567)
  - [Evidência 14](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/14#issue-2445423630)
  - [Evidência 15](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/15#issue-2445424884)
  - [Evidência 16](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/16#issue-2445495424)
  - [Evidência 17](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/17#issue-2445503997)
  - [Evidência 18](https://github.com/wilianznt/DESAFIO-BEEDOO/issues/18#issue-2445506091)
  ## Contribuições
  
  Para contribuir com este projeto, por favor, siga as instruções e adicione suas sugestões ou correções.
  
  ## Licença
  
  Este projeto está licenciado sob a [Licença XYZ](LICENCA_URL).
  
