# PROVA_BD
AVALIAÇÃO BANCO DE DADOS
 Resolução da Prova Prática Banco de Dados

## 1ª Questão
Faça um comando SQL para matricular o aluno "Pedro César" no  curso de informática.Os dados devem ser inseridos na tabela TB_MATRÍCULA.

```sql
select * from tb_aluno
insert into tb_aluno(codigo_aluno, nome_aluno, ano_nasc, email, sexo)
values ('4', 'Pedro César', '1995-06-04', 'pedro@provaSQL.com.br', 'M')
select * from tb_matricula
insert into tb_matricula(codigo_curso, codigo_aluno)
values ('4', '4')
```
## Resultado 

![q1sql](https://user-images.githubusercontent.com/114403979/206186429-af1a1a67-b402-4d8d-9c29-eb38b7826505.png)
<br/>
![q1sql](https://user-images.githubusercontent.com/114403979/206186442-0047b5c9-f95d-4b70-99e5-2033b8503a11.png)


## 2ª Questão
Escreva um comando SQL que retorne os nomes dos alunos e do(s) cursos em que estão matriculados.Os dados deverão estar ordenados pelo nome do curso.  

```sql
select tb_aluno.nome_aluno, tb_curso.nome_curso
from tb_aluno
inner join tb_matricula
on tb_aluno.codigo_aluno = tb_matricula.codigo_aluno
inner join tb_curso
on tb_curso.codigo_curso = tb_matricula.codigo_curso
```
## Resultado 

![q2sql](https://user-images.githubusercontent.com/114403979/206186499-aa04cc46-34ac-4e64-b51f-1843522f754f.png)


## 3ª Questão
Crie um comando SQL que retorne o e-mail de todos os alunos maiores de idade.

```sql
select email
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![q3sql](https://user-images.githubusercontent.com/114403979/206186533-a190cc9f-05e8-4611-a4ea-f29c2c64f3d8.png)


## 4ª Questão
Desenvolva um comando SQL que mostre o total de alunos.

```sql
select count(codigo_aluno)
from tb_aluno
```
## Resultado 

![q4sql](https://user-images.githubusercontent.com/114403979/206186568-aa8d2e99-5bd3-437c-a59c-e5c1cbec1640.png)


## 5ª Questão
Escreva um comando SQL para listar o total de alunos matriculados em cada curso.

```sql
select tb_curso.nome_curso,
codigo_curso + codigo_aluno as numero_alunos
from tb_curso
inner join tb_aluno
on tb_aluno.codigo_aluno = tb_curso.codigo_curso
```
## Resultado 


![q5sql](https://user-images.githubusercontent.com/114403979/206186607-70f17862-97dd-4c9e-8318-ca044ccb31a5.png)

## 6ª Questão
Desenvolva um comando SQL que retorne o nome de todos os alunos maiores que 18 anos.

```sql
select nome_aluno
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![q6sql](https://user-images.githubusercontent.com/105735037/206178292-be49f604-890b-494c-9a4b-07f093e433c1.PNG)

## 7ª Questão
Faça um comando SQL que retorne o nome de todas as mulheres. 

```sql
select nome_aluno, sexo
from tb_aluno where sexo = 'F'
```
## Resultado 

![q7sql](https://user-images.githubusercontent.com/114403979/206186706-6570fca1-5caa-41d0-8a2f-c71fc50761dd.png)


## 8ª Questão
Faça um comando SQL que retorne o nome de todas as mulheres matriculadas no curso de Medicina.

```sql
select tb_aluno.nome_aluno as mulheres_em_medicina
from tb_aluno
inner join tb_matricula
on tb_matricula.codigo_aluno = tb_aluno.codigo_aluno
and tb_matricula.codigo_curso = 1
and tb_aluno.sexo = 'F'
```
## Resultado 

![q8sql](https://user-images.githubusercontent.com/114403979/206186751-fd47532f-a7c7-4ba0-ac4a-5aa069914f5b.png)


## 9ª Questão
Faça um comando SQL que retorne os nomes dos cursos ordenados por ordem alfabética.

```sql
select nome_curso
from tb_curo order by nome_curso asc
```
## Resultado 

![q9sql](https://user-images.githubusercontent.com/114403979/206186768-c63918de-50f1-41da-a721-61b891b4f73e.png)

## 10ª Questão
Crie o enunciado de uma consulta SQL que utiliza "junção" (com resposta).

```sql
select ano_nasc,tb_curso.nome_curso,tb_aluno.nome_aluno
from tb_aluno
inner join tb_curso
on tb_aluno.cod_aluno = tb_curso.cod_curso
order by nome_curso asc 
```
## Resultado 
![q10sql](https://user-images.githubusercontent.com/104003510/206247087-8d9edbac-8794-418b-b4c2-034bb61a5c69.jpg)

# Resolução da Prova Teórica

## 1ª Questão
### Defina: SQL.
#### SQL (Structured Query Language) é utilizada para executar um comando em Bancos de Dados relacionais, isto é, baseado em tabelas.

## 2ª Questão
### Faça um relacionamento cronológico sobre SQL.
#### SQL significa Linguagem de Consulta Estruturada. SQL é uma linguagem de programação padrão projetada para armazenar, recuperar, gerenciar ou manipular dados em um sistema de gerenciamento de banco de dados relacional (DBMS). SQL é devido a um padrão ISO em 1987. SQL é a linguagem de banco de dados mais amplamente implementada e suportada por sistemas de banco de dados relacionais populares, como MySQL, SQL Server e Oracle. No entanto, alguns recursos do padrão SQL são implementados de maneira diferente em diferentes sistemas de banco de dados. O SQL foi originalmente desenvolvido na IBM no início dos anos 1970 como SEQUEL (Structured English Query Language) e mais tarde foi substituído por SQL (pronuncia-se SQL).

## 3ª Questão
### Liste as principais características de SQL.
#### SQL é uma linguagem padrão para trabalhar com bancos de dados relacionais. Ela é uma linguagem declarativa e que não necessita de profundos conhecimentos de programação para que alguém possa começar a escrever queries. A linguagem SQL é utilizada de maneira relativamente parecida entre os principais bancos de dados relacionais do mercado: Oracle, MySQL, MariaDB, PostgreSQL, Microsoft SQL Server, entre muitos outros. Cada um tem suas características, sendo o MySQL e o PostgreSQL extremamente populares por possuírem versões gratuitas e de código aberto.

## Questão 4:
### Descreva a sintaxe do comando SQL: SELECT. Quais cláusulas são obrigatórias e quais são opcionais?
#### O comando SELECT é utilizado para extrair os dados das tabelas de um banco de dados. Ele pode extrair dados de uma ou mais tabelas ao mesmo tempo, executando desde simples consultas até comandos mais complexos, fazendo buscas, junções, filtros comparativos, ordenações e diversos outros itens.

## Questão 5:
### Qual a importância da linguagem SQL no desenvolvimento de softwares atualmente? Justifique.
#### O SQL Server, criado pela Microsoft, é muito conhecido e utilizado no mercado. A linguagem usada nessa ferramenta é o T-SQL, e oferece recursos avançados e diferenciados para facilitar a atualização de dados e o armazenamento das informações de forma segura e confiável. O SQL Server atua com sistemas integrados de criptografia, permitindo que a visualização ou alteração das informações sejam feitas apenas pelas pessoas responsáveis, o que garante ainda mais segurança e tranquilidade para os usuários e empresários. É uma alternativa comumente utilizada em lojas online, instituições governamentais, bancos e indústrias dos mais diversos portes.
