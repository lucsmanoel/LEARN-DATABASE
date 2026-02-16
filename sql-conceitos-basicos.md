# Acessar SQL: Conceitos Básicos, Vocabulário e Sintaxe

**Aplica-se a:** Access para Microsoft 365, Access 2024, Access 2021, Access 2019, Access 2016  

---

## 📘 Introdução

Quando você deseja recuperar dados de um banco de dados, usa a linguagem SQL (Structured Query Language).  

O SQL é uma linguagem que se assemelha ao inglês e é usada por programas de banco de dados para consultar e manipular dados.

Cada consulta criada no Microsoft Access utiliza SQL nos bastidores.

Compreender SQL ajuda você a:

- Criar consultas mais eficientes
- Corrigir consultas com erro
- Entender como o Access processa dados

---

# 🧠 O que é SQL?

SQL é uma linguagem padrão internacional usada para trabalhar com bancos de dados relacionais.

Ela permite:

- Consultar dados
- Filtrar registros
- Agrupar informações
- Ordenar resultados
- Criar e modificar estruturas de banco de dados

Exemplo simples:

```sql
SELECT Last_Name
FROM Contacts
WHERE First_Name = 'Mary';
```

Esse comando retorna os sobrenomes dos contatos cujo primeiro nome é Mary.

---

## 📌 Observação

SQL também pode ser usado para criar ou modificar tabelas e índices.  
Essa parte da linguagem é chamada de:

**DDL (Data Definition Language – Linguagem de Definição de Dados)**

Este documento foca apenas em consultas SELECT.

---

# 🔎 Estrutura Básica de uma Consulta SQL

Uma instrução SQL normalmente segue esta estrutura:

```sql
SELECT campo
FROM tabela
WHERE criterio;
```

---

# 🧱 Cláusulas Principais do SQL

| Cláusula  | Função | Obrigatória |
|-----------|--------|-------------|
| SELECT    | Define quais campos serão exibidos | ✅ |
| FROM      | Define de qual tabela vêm os dados | ✅ |
| WHERE     | Define critérios/filtros | ❌ |
| ORDER BY  | Ordena os resultados | ❌ |
| GROUP BY  | Agrupa resultados | ❌* |
| HAVING    | Filtra resultados agrupados | ❌ |

\*Obrigatória quando houver funções de agregação com campos não agregados.

---

# 🗂 SELECT, FROM e WHERE

## Exemplo:

```sql
SELECT [E-mail Address], Company
FROM Contacts
WHERE City = "Seattle";
```

Essa consulta:

- Seleciona Email e Empresa
- Da tabela Contacts
- Onde a cidade é Seattle

---

# 🔢 ORDER BY (Ordenação)

A cláusula `ORDER BY` define a ordem dos resultados.

### Ordem Crescente (padrão)

```sql
ORDER BY Company;
```

### Ordem Decrescente

```sql
ORDER BY Company DESC;
```

### Ordenando por múltiplos campos

```sql
ORDER BY Company DESC, [E-mail Address];
```

---

# 📊 GROUP BY (Agrupamento)

Usado quando queremos resumir dados com funções agregadas.

Exemplo:

```sql
SELECT COUNT([E-mail Address]), Company
FROM Contacts
GROUP BY Company;
```

Aqui estamos contando quantos e-mails existem por empresa.

---

# 🎯 HAVING (Filtro para dados agrupados)

Usado junto com GROUP BY para filtrar resultados agregados.

```sql
SELECT COUNT([E-mail Address]), Company
FROM Contacts
GROUP BY Company
HAVING COUNT([E-mail Address]) > 1;
```

Retorna apenas empresas que possuem mais de 1 contato.

---

# 🔄 UNION (Combinar Consultas)

Combina os resultados de duas consultas SELECT.

Regras:

- Mesmo número de colunas
- Tipos de dados compatíveis

## Sintaxe:

```sql
SELECT campo1
FROM tabela1
UNION
SELECT campo1
FROM tabela2;
```

## UNION ALL (inclui duplicados)

```sql
SELECT name, price, warranty_available, exclusive_offer
FROM Products
UNION ALL
SELECT name, price, guarantee_available, exclusive_offer
FROM Services;
```

---

# 🧩 Conceitos Importantes

## Identificadores
Nomes de tabelas e campos.

## Operadores
Exemplos:
- =
- >
- <
- >=
- <=
- <>
- LIKE

## Constantes
Valores fixos, como:
- 'Texto'
- 10
- NULL

## Expressões
Combinação de campos, operadores e funções.

---

# 📌 Resumo Final

SQL no Access permite:

- Consultar dados com SELECT
- Filtrar com WHERE
- Ordenar com ORDER BY
- Agrupar com GROUP BY
- Filtrar agregações com HAVING
- Combinar consultas com UNION

Entender esses conceitos torna a criação de consultas mais eficiente e profissional.

---

# 📎 Referências

Documentação oficial Microsoft Support:
https://support.microsoft.com/pt-br/topic/acessar-sql-conceitos-básicos-vocabulário-e-sintaxe-444d0303-cde1-424e-9a74-e8dc3e460671

---


