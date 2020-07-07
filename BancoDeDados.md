# Banco de Dados

SGDBS: Sistemas para gerenciamento e estruturação de dados, possibilitando velocidade e controle de acesso, isolamento de dados e durabilidade.

Entidades: Tabelas
Registros/Tuplas: Linhas
Colunas
Chave PK (Primária) ou FK (Foreigner - herança da chave primária de outra tabela).

MER: modelo de entidade e relacionamento. (1, n) (1, 1)
Modelo lógico: implementação no sistema de banco de dados
DER: Diagrama de Entidade e Relacionamento

## SQL (Structured Query Language)

- Sum()

Select Sum(ven.quantidade) as QTotal,
       Sum(ven.valor) as VTotal
from item_ven
Where ven.valor > 5

Fazendo relacionamento:

Select Sum(ven.quantidade) as QTotal,
       Sum(ven.valor) as VTotal,
       pro.descricao
from item_venda ven ¹
JOIN produto pro ²
ON pro.codigo = ven.cod_produto ³
Where ven.valor > 5

¹ Cria um alias para a tabela
² Junta duas tabelas 
³ Compara os códigos das duas tabelas para relacioná-las

- Having: Se comporta como where mas serve para filtrar o retorno da operação.

Having Sum(ven.valor) >= 10

- Index: pequena tabela extraida da tabela original contendo apenas os conteúdos que deseja procurar. Mais apropriado para consultas pontuais.

Select 
Where profissao = 1
and genero = "M"

### Transactions: o que pode ser feito em uma sessão no banco de dados.

1. Início: Insert, delete, update

2. Resolução: Commit (confirmar as alterações no banco), Rollback (desistência da operação, retornando para como era antes).

3. Fim: Novos dados (commit) ou dados Originais (rollback)

ACID
* Atomicidade: Todas as operações devem ser executadas com sucesso, toda ação deve ter um fim mesmo que seja interrompida. 

* Consistência: Na transação deve ser garantido a unicidade de chaves, restriçõe de integridade lógica, etc.

* Isolamento: Várias transações podem acontecer simultaneamenta, consultar e alterar um mesmo registro deve ser respeitado de acordo com ordem de chegada, execução. 

* Durabilidade: Após o commit, mesmo com erro no sistema, queda de energia, etc. as alterações devem ser aplicadas. Normalmente os SGDB's mantém logs para quando ele ser reiniciado, aplique as ações.

