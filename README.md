# README - Transformações e Junções de Dados

Este documento descreve as transformações e junções realizadas na base de dados para preparar os dados para análise no Power BI.

## 1. Substituição do Tipo de Dados da Coluna `Salary`

- **Tabela**: `employee`
- **Operação**: Alteração do tipo de dados
- **Descrição**: A coluna `Salary` foi alterada para o tipo de dados `Número Decimal` para garantir que os valores monetários sejam corretamente representados e manipulados.

## 2. Substituição do Valor `NULL` na Coluna `superSSN`

- **Tabela**: `employee`
- **Operação**: Substituição de valores `NULL`
- **Descrição**: Todos os valores `NULL` na coluna `superSSN` foram substituídos por `0`. Isso foi feito para evitar problemas com valores nulos durante a junção de tabelas e para simplificar a análise.

## 3. Substituição de Valores Inválidos na Coluna `Hours`

- **Tabela**: `works_on`
- **Operação**: Substituição de valores inválidos
- **Descrição**: Valores inválidos, como datas, foram substituídos por `0` na coluna `Hours`. Essa correção assegura que a coluna contenha apenas valores numéricos, representando corretamente o número de horas trabalhadas.

## 4. Mesclagem das Tabelas `employee` e `departament`

- **Tabela**: `employee` e `departament`
- **Operação**: Mesclagem de tabelas
- **Descrição**: As tabelas `employee` e `departament` foram mescladas com base na coluna `Dept No`. Isso permite associar os colaboradores aos seus respectivos departamentos e obter informações adicionais sobre os departamentos.

### Instruções no Power BI

1. Abra o Editor de Consultas no Power BI Desktop.
2. Selecione a tabela `employee`.
3. Clique em "Nova Consulta" > "Mesclar Consultas".
4. Selecione a tabela `departament` e junte usando a coluna `Dept No`.
5. Mantenha as colunas necessárias e remova as desnecessárias.

## 5. Criação da Coluna `Full Name`

- **Tabela**: `employee`
- **Operação**: Mesclagem de colunas
- **Descrição**: Foi criada uma nova coluna `Full Name` combinando `First Name` e `Last Name` para fornecer uma representação completa do nome dos colaboradores.

### Instruções no Power BI

1. No Editor de Consultas, selecione a tabela `employee`.
2. Clique em "Adicionar Coluna" > "Coluna Personalizada".
3. Insira a fórmula para combinar o nome e sobrenome:
   ```powerquery
   [First Name] & " " & [Last Name]
