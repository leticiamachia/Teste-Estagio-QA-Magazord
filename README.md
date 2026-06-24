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
