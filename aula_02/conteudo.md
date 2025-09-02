# Continuação aula_01

oque diferencia SGBD's?
A forma como os serviços são oferecidos e se são completos ou não

O acesso controlado tem relaçãocom quais privilégios o usuário tem nobanco de dados!

Alguns critérops de segurança como criptografia e acesso controlado são usados para proteger um banco de dados

Restrições de integeridade é definido pelo usuário e validado pelo SGBD
Ex: Campos obrigatórios em formulários Web (Chamado de Not Null em SQL) ou definição de unicidade de um campo (chamado de Unique em SQL)

Esquema -> Estruturalógica da base de dados
Instâncias -> É o conteúdo da base de dados em um determinado ponto

A arquitetura de banco de dados geralmente é 'em três esquemas (three-schema)'
Meta -> separar as aplicações da base de dados física
1° nível (Externo) -> descreve a visão da base de dados de um grupo deusuários (podemos dizer que é o caso de uso geral do sistema)
2° nível (Conceitual) -> descreve a estrutura da base de dados inteira
3° nível (Interno) -> descreve o armazenamento físico do banco de dados

"A arquitetura Três-Esquemas pode ser utilizada para explicar conceitos de independência de dados, que podem ser definidos como a capacidade de alterar o esquema de um nível sem ter que alterar o esquema no próximo nível superior."

-> Independência lógica de dados: capacidade de alterar o esquema conceitual sem mudar esquemas externos. Ex: Pode-se mudar o esquema conceitual para expandir a base de dados, com a adição de novos tipos de registros. Mudar um campo de nome para primeiroNome e sobrenome
-> Independência física: capacidade de alterar o esquema interno sem alteraro o esquema conceitual. Ex: Alteração na organização do esquema físico. modificação do tipo de atributo (de string para text)

Modelos de dados/níveis de abstração (de cima para baixo) [ESTÃO NO SEGUNDO NÍVEL DA ARQUITETURA 3 ESQUEMAS]

-> nível conceitual: forma mais natural e próximos do ambiente do cliente e dos fatos 
-> nível lógico: descreve de froma lógica de como os dados são armazenados no BD e suas relações
-> nível físico: descreve por linguágem específica como os dados serão armazenados

# FIM SLIDE 01 

Modelo conceitual de dados -> processo de criação a partir de REQUISITOS EXTRAÍDOS PARA UM DETERMINADO SOFTWARE

O nível conceitual é o primeiro em abstração, tem que se fazer o entendimento do que acontece no mundo real e levar para o projeto

Um banco de dados é projetado com uma coleção de entidades e seus relacionamentos

Mas afinal, o que é uma entidade?
É um objeto que existe e é distinguível de outros objetos por seus atributos

Atributos: porpriedades descritivas processadas por todos os membros de um conjunto de entidades
Ex: cliente(id_cliente, nome_cliente, rua_cliente, cidade_cliente)

Domínio: conjunto valores permitidos para cada atributo
Ex: para um atributo nome, se espera receber um nome e não uma data ou preço

Os atributos podem ser divididos em:
simples: indivisível,atômico para a aplicação(ex: nome)
compostos: pode ser separado/dividido para a aplicação(ex: pnome e sobrenome)
de valor único: a entidade só pode possuir um dele (ex:data de nascimento)
valores múltiplos: a entidade pode possuir mais de um dele (ex: numero de telefone)
derivados: são obtidos a partir de outros atributos (ex: idade a partir da data de nascimento)
Identificador: conjunto de um ou mais atributos cujos valores determinam unicamente cada entidade

Ex entidade
+---------+ 
| Cliente |
+---------+

+---------------------+
| id_cliente (*)      |  
| nome                |  
| |-- prenome         |  
| |-- sobrenome       |         Legenda:
| data_nascimento     |         (*) = Atributo identificados
| telefones (1,n)     |         (1,n)= Atributo multivalorado
| endereco            |         |--  = Indica atributos compostos
| |-- cep             |  
| |-- estado          |  
| |-- cidade          |  
| |-- rua             |  
|     |-- Nome        |
|     |-- Numero      |
|     |-- complemento |
+---------------------+

Os relacionamentos servem para poder gerar troca de informações entre entidades (ex: professor leciona disciplina, aluno se matricula em disciplinas)

Conjunto de relacionamento pode conter atributos próprios (ex: em uma relação depoósito(nome_cliente, numero_conta) cria o atributo e guarda 'data_acesso')

relacionamento é representado visualmente como um **losangos**

grau de relacionamento é a quantidade de conjuntos de entidades que participam do relacionamento (grande parte é binário)

Cardinalidade: é a relação entre uma entidade dentro de de uma relação na forma (minimo,maximo) **[o minimo é 0 ou 1 e o máximo assume 1 ou n]**

pegamos o maior valor da cardinalidade para determinar o relacionamento entre as entidades da relação

em cardinalidade de relacionamentos, "->" significa um e "--" significa muitos, ou seja, entidade1 <- relacionamento -> entidade2 == um para um

Existe casos de auto-relacionamentos, como por ex, eu tenho a entidade funcionário (com cargos diferentes) que se relaciona com ela mesma por uma relação 'trabalha' entre os cargos operários e gerentes (adicionando o rótulo)

+-------------+     (o,n) operarios       _ _ _ _    
|             | -----------------------  /        \
| Funcionário |     (0,1) gerente       / Trabalha \
|             | ----------------------- \ para     /
+-------------+                          \ _ _ _ _/

conjunto de entidades fraco é um conjunto que depende de outro, como por exemplo a entidade empréstimo que tem a relação pagamento_empréstimo e gera a entidade pagamento, ou seja, pagamento é uma entidade que depende da relação com espréstimo (representado por uma linha dupla) e o identificador é chamdo de identificador parcial