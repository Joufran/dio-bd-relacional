# dio-bd-relacional

- Introdução aos Bancos de Dados Relacionais e conceitos básicos de SQL.
- Modelagem de tabelas, colunas e registros com operações CRUD.
- Chaves primárias e estrangeiras com modelagem de tabelas relacionadas.
- Normalização de dados, identificando e corrigindo problemas de normalização.
- Consultas avançadas com junções e subconsultas.
- Funções agregadas e agrupamento de resultados com GROUP BY e HAVING.
- Uso de índices para otimização de consultas.

  #Tipos de Bancos de dados

- Relacionais/SQL
- Não Relacionais/NoSQL (Not OnlySQL)
- Orientado a Objetos
- Hierárquico

 #Funconalidades Básicas
 C reate -> criação
 R ead   -> leitura
 U pdate -> atualização
 D elete -> exclusão

#Caracteristicas de um BD Ralacional
- Relacionamento entre tabelas
- Linguagem de Consulta Estruturada (SQL)
- Integridade referencial
- Normalização de dados
- Segurança
- Flexibilidade e extensibilidade
- Suporte a transações ACID
  Atomicidade
  Consistência
  Isolamento
  Durabilidade

 #Organização da SQL
- DQL - Linguagem de Consulta de Dados
  ❏ SELECT;
- DML - Linguagem de Manipulação de Dados
  ❏ INSERT, UPDATE e DELETE;
- DDL - Linguagem de Definição de Dados
  ❏ CREATE, ALTER, DROP;
- DCL - Linguagem de Controle de Dados
  ❏ GRANT, REVOKE
- DTL - Linguagem de Transação de Dados
  ❏ BEGIN, COMMIT, ROLLBACK

  #Conceitos Básicos
  - Os nomes devem começar com uma letra ou com um caractere de sublinhado (_)
  - *** Os nomes podem conter letras, números e caracteres de sublinhado (_).
  - Sensibilidade a maiúsculas e minúsculas

 
    #Modelagem de Banco de Dados
     O Modelo Entidade-Relacionamento (MER) é representado através de diagramas chamados Diagramas Entidade-Relacionamento (DER)

    >Entidades
      As entidades são nomeadas com substantivos concretos ou abstratos que representem de forma clara sua função dentro do domínio.
    >Atributos
      Os atributos são as características ou propriedades das entidades. Eles descrevem informações específicas sobre uma entidade.
    >Relacionamentos
      Os relacionamentos representam as associações entre entidades
    >Cardinalidades
     ❏ Relacionamento 1..1 (um para um)
     ❏ Relacionamento 1..n ou 1..* (um para muitos)
     ❏ Relacionamento n..n ou *..* (muitos para muitos)
    >Tabelas
      Ela é usada para armazenar dados de forma organizada. Cada tabela em um banco de dados relacional tem um nome único e é dividida em colunas e linhas
    >Colunas
      Uma coluna é uma estrutura dentro de uma tabela que representa um atributo específico dos dados armazenados. Cada coluna tem um nome único e um tipo de dados associado que define o tipo de informação que pode ser armazenado nela, como números, textos, datas, etc.
    >Registro
    Um registro, também conhecido como linha ou tupla, é uma instância individual de dados em uma tabela.
    
    #Comandos
    >Create Table
       CREATE TABLE {{nome}} 
        ({{coluna}} {{tipo}} {{opções}} COMMENT 
        {{‘COMENTARIO´}});

     $tipos de Dados
    Os dados podem variar muito entre os diversos SGBD, os mais comuns são:
      ❏ Inteiro (Integer)
      ❏ Decimal/Numérico (Decimal/Numeric)
      ❏ Caractere/Varchar (Character/Varchar)
      ❏ Data/Hora (Date/Time)
      ❏ Booleano (Boolean)
      ❏ Texto longo (Text)
    $opções
      ❏ Restrições de valor:
      ❏ NOT NULL
      ❏ UNIQUE
      ❏ DEFAULT
      ❏ Chaves primárias e estrangeiras
      ❏ Auto Incremento

    >Insert
      INSERT INTO
        {{ nome-tabela }}
        ([ coluna1, coluna2, … ]) *** você pode ocultar as colunas VALUES
        ([ valor-coluna1, valor-coluna2, … ])
    >Select
     >>SELECT {{ lista_colunas}} FROM tabela;
          Onde * retorna todas as colunas

     >>SELECT {{ lista_colunas}} FROM tabela WHERE {{condicao}};

      $Operadores
          ❏ = (igualdade)
          ❏ <> ou != (desigualdade)
          ❏ > (maior que)
          ❏ < (menor que)
          ❏ >= (maior ou igual que)
          ❏ <= (menor ou igual que)
          ❏ LIKE (comparação de padrões)
          ❏ IN (pertence a uma lista de valores)
          ❏ BETWEEN (dentro de um intervalo)
          ❏ AND (e lógico)
          ❏ OR (ou lógico)

    >Update
       UPDATE {{ tabela }}
          SET
          {{ coluna_1 }} = {{ novo_valor_1 }}, {{ coluna_2 }} = {{ novo_valor_2 }}
          WHERE
          {{ condicao }} ;

    >Delete
      DELETE FROM {{ tabela }}
          WHERE {{ condicao }};


    #Alterando e Excluindo Tabelas
    Usuários com endereços longos não estão conseguindo realizar cadastro no sistema
      Opções:
      ● Recriar a tabela, migrar os dados e excluir a tabela 
      anterior
      ● Alterar estrutura da tabela

    >Drop Table
      O comando DROP TABLE é usado no SQL - para remover uma tabela existente de um banco de dados relacional.
      Ele exclui permanentemente a tabela
          DROP TABLE {{tabela}}
    
    >Alter Table
      A cláusula ALTER TABLE é usada no SQL para modificar a estrutura de uma tabela existente em um banco de dados relacional. 
        Ela permite:
          ❏ Adicionar, alterar ou excluir colunas
          ❏ Modificar as restrições, índices
          ❏ Renomear a tabela entre outras alterações
    
    #Chaves Primárias
     - Identifica exclusivamente
     - Não pode conter valores nulos (NULL)
     - Uma tabela pode ter apenas uma chave primária.
