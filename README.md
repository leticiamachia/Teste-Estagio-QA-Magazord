# Teste-QA-Magazord
Teste técnico para vaga de Estágio em Testes (Qualidade de Software) - Magazord.

# Parte 1: Validação de Dados Cadastrais (Sistema de Gerenciamento de Usuários)
Criar Casos de Teste para validar a entrada de dados nos seguintes campos de cadastro do sistema: 
- Nome completo
- E-mail
- Número de telefone
- Data de nascimento
- Endereço (com campos para rua, cidade, estado e CEP)

Os testes devem garantir que cada campo aceite apenas dados válidos, rejeite formatos incorretos e exiba mensagens de erro quando necessário.

## Casos de Teste — Nome Completo

| **ID** | **Título** | **Objetivo** | **Pré-condição** | **Passos** | **Resultados Esperados** |
|--------|-------------|---------------|------------------|-------------|---------------------------|
| **Casos de dados válidos** |  |  |  |  |  |
| CT-001 | Validar nome com letras e espaços | Garantir que o campo aceite credenciais válidas de nome completo (letras e espaços). | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria Silva de Oliveira”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-002 | Validar nome com acentos | Garantir que o sistema aceite caracteres acentuados. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Mariá Silva de Oliveira”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-003 | Validar nome com hífen | Garantir que o sistema aceite nomes compostos com hífen. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria-Clara Silva de Oliveira”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-004 | Validar nome com trema | Garantir que o sistema aceite caracteres com o trema. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria Müller de Oliveira”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-005 | Validar nome em letras minúsculas | Garantir que o sistema aceite nomes escritos apenas em minúsculas. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “maria silva de oliveira”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros; sistema pode ajustar para o padrão de maiúsculas/minúsculas. |
| CT-006 | Validar nome em letras maiúsculas | Garantir que o sistema aceite nomes escritos apenas em maiúsculas. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “MARIA SILVA DE OLIVEIRA”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros; sistema pode ajustar para o padrão de maiúsculas/minúsculas. |
| **Casos de dados inválidos** |  |  |  |  |  |
| CT-007 | Rejeitar nome com números | Garantir que o sistema não aceite números no campo nome. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria 123”.<br>3. Clicar em Salvar. | Mensagem de erro "Nome inválido" exibida e nenhum dado gravado no banco de dados. |
| CT-008 | Rejeitar nome com caracteres especiais | Garantir que o sistema não aceite símbolos e caracteres especiais. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria@Silva”.<br>3. Clicar em Salvar. | Mensagem de erro "Nome inválido" exibida e nenhum dado gravado no banco de dados. |
| CT-009 | Rejeitar nome com apenas primeiro nome | Garantir que o sistema exija nome completo. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “Maria”.<br>3. Clicar em Salvar. | Mensagem de erro "Informe o nome completo" exibida e nenhum dado gravado no banco de dados. |
| CT-010 | Rejeitar campo vazio | Garantir obrigatoriedade do preenchimento do campo. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Deixar o campo em branco.<br>3. Clicar em Salvar. | Mensagem de erro "Campo obrigatório" exibida e nenhum dado gravado no banco de dados. |
| CT-011 | Rejeitar campo com apenas espaços | Garantir que o sistema não aceite apenas espaços em branco. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “  ”.<br>3. Clicar em Salvar. | Mensagem de erro "Campo obrigatório" exibida e nenhum dado gravado no banco de dados. |
| **Casos de limite** |  |  |  |  |  |
| CT-012 | Validar limite mínimo de caracteres | Garantir que o sistema não aceite nomes com apenas 1 caractere. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir “A”.<br>3. Clicar em Salvar. | Mensagem de erro "Nome inválido" exibida e nenhum dado gravado no banco de dados. |
| CT-013 | Validar limite máximo de caracteres | Garantir que o sistema aplique limite máximo de tamanho ao campo. | Usuário na tela de cadastro | 1. Clicar no campo Nome.<br>2. Inserir nome com 200 caracteres.<br>3. Clicar em Salvar. | Mensagem de erro ou truncamento conforme regra definida. |


## Casos de Teste — E-mail

| **ID**   | **Título**                          | **Objetivo**                                               | **Pré-condição**              | **Passos**                                                                 | **Resultados Esperados** |
|----------|--------------------------------------|------------------------------------------------------------|--------------------------------|----------------------------------------------------------------------------|---------------------------|
| **Casos de dados válidos** |  |  |  |  |  |
| CT-001   | Validar e-mail com formato padrão    | Garantir que o sistema aceite endereços de e-mail válidos no formato padrão. | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria.silva@gmail.com”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-002   | Validar e-mail com caracteres numéricos | Garantir que o sistema aceite e-mails contendo números.   | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria123@gmail.com”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-003   | Validar e-mail com subdomínio        | Garantir que o sistema aceite e-mails com subdomínios válidos. | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria.silva@magazord.com.br”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-004   | Validar e-mail em letras maiúsculas  | Garantir que o sistema aceite e-mails digitados apenas em maiúsculas. | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “MARIA.SILVA@GMAIL.COM”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros; sistema pode ajustar para minúsculas automaticamente. |
| **Casos de dados inválidos** |  |  |  |  |  |
| CT-005   | Rejeitar e-mail sem arroba           | Garantir que o sistema rejeite e-mails sem o caractere “@”. | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria.silva.com”.<br>3. Clicar em Salvar. | Mensagem de erro “E-mail inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-006   | Rejeitar e-mail sem domínio          | Garantir que o sistema rejeite e-mails sem domínio após o “@”. | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria@”.<br>3. Clicar em Salvar. | Mensagem de erro “E-mail inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-007   | Rejeitar e-mail com espaços          | Garantir que o sistema rejeite e-mails contendo espaços.    | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Inserir “maria silva@gmail.com”.<br>3. Clicar em Salvar. | Mensagem de erro “E-mail inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-008   | Rejeitar e-mail com caracteres especiais inválidos | Garantir que o sistema rejeite e-mails com caracteres não permitidos. | Usuário na tela de cadastro | 1. Clicar no campo E-mail.<br>2. Inserir “maria!silva@gmail.com”.<br>3. Clicar em Salvar. | Mensagem de erro “E-mail inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-009   | Rejeitar campo vazio                 | Garantir obrigatoriedade do preenchimento do campo E-mail.  | Usuário na tela de cadastro    | 1. Clicar no campo E-mail.<br>2. Deixar o campo em branco.<br>3. Clicar em Salvar. | Mensagem de erro “Campo obrigatório” exibida e nenhum dado gravado no banco de dados. |
| **Casos de limite** |  |  |  |  |  |
| CT-010   | Validar limite mínimo de caracteres  | Garantir que o sistema não aceite e-mails com menos de 5 caracteres. | Usuário na tela de cadastro | 1. Clicar no campo E-mail.<br>2. Inserir “a@b.c”.<br>3. Clicar em Salvar. | Mensagem de erro “E-mail inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-011   | Validar limite máximo de caracteres  | Garantir que o sistema aplique limite máximo de tamanho ao campo E-mail. | Usuário na tela de cadastro | 1. Clicar no campo E-mail.<br>2. Inserir um e-mail com mais de 100 caracteres.<br>3. Clicar em Salvar. | Mensagem de erro ou truncamento conforme regra definida. |


## Casos de Teste — Número de Telefone

| **ID**   | **Título**                          | **Objetivo**                                               | **Pré-condição**              | **Passos**                                                                 | **Resultados Esperados** |
|----------|--------------------------------------|------------------------------------------------------------|--------------------------------|----------------------------------------------------------------------------|---------------------------|
| **Casos de dados válidos** |  |  |  |  |  |
| CT-001   | Validar telefone com 11 dígitos (formato celular) | Garantir que o sistema aceite números de telefone válidos com 9 dígitos. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “47991234567”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-002   | Validar telefone com espaços         | Garantir que o sistema aceite números de telefone válidos com espaços. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “47 99123 4567”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-003   | Validar telefone com DDD e hífen     | Garantir que o sistema aceite números de telefone válidos com DDD e hífen. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “(47) 99123-4567”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-004   | Validar telefone com código de país  | Garantir que o sistema aceite números com código internacional. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “+55 (47) 99123-4567”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-005   | Validar telefone em formato internacional sem parênteses e hífen | Garantir que o sistema aceite números no formato “+5547991234567”. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “+5547991234567”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| **Casos de dados inválidos** |  |  |  |  |  |
| CT-006   | Rejeitar telefone com letras         | Garantir que o sistema não aceite letras no campo telefone. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “47AB912345”.<br>3. Clicar em Salvar. | Mensagem de erro “Telefone inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-007   | Rejeitar telefone com caracteres especiais inválidos | Garantir que o sistema não aceite símbolos não permitidos. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “47#99123*4567”.<br>3. Clicar em Salvar. | Mensagem de erro “Telefone inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-008   | Rejeitar telefone com caracteres repetidos inválidos | Garantir que o sistema não aceite números como “11111111111”. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “11111111111”.<br>3. Clicar em Salvar. | Mensagem de erro “Telefone inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-009   | Rejeitar campo vazio                 | Garantir obrigatoriedade do preenchimento do campo Telefone. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Deixar o campo em branco.<br>3. Clicar em Salvar. | Mensagem de erro “Campo obrigatório” exibida e nenhum dado gravado no banco de dados. |
| CT-010   | Rejeitar campo com apenas espaços    | Garantir que o sistema não aceite apenas espaços em branco. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “   ”.<br>3. Clicar em Salvar. | Mensagem de erro "Campo obrigatório" exibida e nenhum dado gravado no banco de dados. |
| **Casos de limite** |  |  |  |  |  |
| CT-011   | Validar limite mínimo de dígitos     | Garantir que o sistema não aceite números de telefone com menos de 11 dígitos. | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “4799123”.<br>3. Clicar em Salvar. | Mensagem de erro “Telefone inválido” exibida e nenhum dado gravado no banco de dados. |
| CT-012   | Validar limite máximo de dígitos     | Garantir que o sistema não aceite números de telefone com mais de 19 caracteres (+55 (47) 99123-4567). | Usuário na tela de cadastro    | 1. Clicar no campo Telefone.<br>2. Inserir “4799123456789123456789”.<br>3. Clicar em Salvar. | Mensagem de erro “Telefone inválido” exibida e nenhum dado gravado no banco de dados. |


## Casos de Teste — Data de Nascimento

| **ID**   | **Título**                          | **Objetivo**                                               | **Pré-condição**              | **Passos**                                                                 | **Resultados Esperados** |
|----------|--------------------------------------|------------------------------------------------------------|--------------------------------|----------------------------------------------------------------------------|---------------------------|
| **Casos de dados válidos** |  |  |  |  |  |
| CT-001   | Validar data no formato padrão       | Garantir que o sistema aceite datas válidas no formato padrão (dd/mm/aaaa). | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “10/10/2000”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-002   | Validar data com zeros à esquerda    | Garantir que o sistema aceite datas com zeros à esquerda.  | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “01/01/2000”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| CT-003   | Validar data sem barras              | Garantir que o sistema aceite datas digitadas sem separadores (ddmmaaaa). | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “01012000”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros; sistema pode formatar automaticamente para “01/01/2000”. |
| CT-004   | Validar data abreviada               | Garantir que o sistema aceite datas digitadas sem zeros à esquerda (d/m/aaaa). | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “1/1/2000”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros; sistema pode formatar automaticamente para “01/01/2000”. |
| CT-005   | Validar data em formato alternativo  | Garantir que o sistema aceite datas válidas no formato MDY (aaaa/mm/dd). | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “2000/12/31”.<br>3. Clicar em Salvar. | Cadastro aceito sem erros e dados gravados no banco de dados. |
| **Casos de dados inválidos** |  |  |  |  |  |
| CT-006   | Rejeitar data com letras             | Garantir que o sistema não aceite letras no campo data de nascimento. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “um/dez/2000”.<br>3. Clicar em Salvar. | Mensagem de erro “Data inválida” exibida e nenhum dado gravado no banco de dados. |
| CT-007   | Rejeitar data inexistente            | Garantir que o sistema não aceite datas inexistentes.      | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “31/02/2020”.<br>3. Clicar em Salvar. | Mensagem de erro “Data inválida” exibida e nenhum dado gravado no banco de dados. |
| CT-008   | Rejeitar data com caracteres especiais inválidos | Garantir que o sistema não aceite símbolos não permitidos. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “10@10@2000”.<br>3. Clicar em Salvar. | Mensagem de erro “Data inválida” exibida e nenhum dado gravado no banco de dados. |
| CT-009   | Rejeitar campo vazio                 | Garantir obrigatoriedade do preenchimento do campo Data de Nascimento. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Deixar o campo em branco.<br>3. Clicar em Salvar. | Mensagem de erro “Campo obrigatório” exibida e nenhum dado gravado no banco de dados. |
| CT-010   | Rejeitar campo com apenas espaços    | Garantir que o sistema não aceite apenas espaços em branco. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “   ”.<br>3. Clicar em Salvar. | Mensagem de erro "Campo obrigatório" exibida e nenhum dado gravado no banco de dados. |
| **Casos de limite** |  |  |  |  |  |
| CT-011   | Validar limite mínimo (idade muito baixa) | Garantir que o sistema não aceite cadastro de usuários com idade inferior a 18 anos. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “01/01/2010”.<br>3. Clicar em Salvar. | Mensagem de erro “Idade mínima não permitida” exibida e nenhum dado gravado no banco de dados. |
| CT-012   | Validar limite máximo (idade muito alta) | Garantir que o sistema não aceite datas que indiquem idade superior a 120 anos. | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “01/01/1900”.<br>3. Clicar em Salvar. | Mensagem de erro “Idade inválida” exibida e nenhum dado gravado no banco de dados. |
| CT-013   | Validar data futura                  | Garantir que o sistema não aceite datas futuras.           | Usuário na tela de cadastro    | 1. Clicar no campo Data de Nascimento.<br>2. Inserir “01/01/2030”.<br>3. Clicar em Salvar. | Mensagem de erro “Data inválida” exibida e nenhum dado gravado no banco de dados. |
