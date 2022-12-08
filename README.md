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
alter table tb_matricula
add codigo_matricula serial primary key 

select count(codigo_matricula) as totalalunos from tb_matricula
```
## Resultado 


![q5sql](https://user-images.githubusercontent.com/120126255/206542518-ac1a02ef-1043-436d-a46a-67165022b018.png)

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
select tb_aluno.nome_aluno, tb_curso.nome_curso from tb_aluno 
inner join tb_matricula on tb_aluno.codigo_aluno = tb_matricula.codigo_aluno
inner join tb_curso on tb_curso.codigo_curso = 1
```
## Resultado 
![q10sql](https://user-images.githubusercontent.com/120126255/206542636-fc7ac280-0417-4446-a662-987e6ef522e2.png)

# Resolução da Prova Teórica

## 1ª Questão
### Defina: SQL.
#### SQL (Structured Query Language) é utilizada para executar um comando em Bancos de Dados relacionais, isto é, baseado em tabelas.

## 2ª Questão
### Faça um relacionamento cronológico sobre SQL.
#### SQL significa Linguagem de Consulta Estruturada. SQL é uma linguagem de programação padrão projetada para armazenar, recuperar, gerenciar ou manipular dados em um sistema de gerenciamento de banco de dados relacional (DBMS). SQL é devido a um padrão ISO em 1987. SQL é a linguagem de banco de dados mais amplamente implementada e suportada por sistemas de banco de dados relacionais populares, como MySQL, SQL Server e Oracle. No entanto, alguns recursos do padrão SQL são implementados de maneira diferente em diferentes sistemas de banco de dados. O SQL foi originalmente desenvolvido na IBM no início dos anos 1970 como SEQUEL (Structured English Query Language) e mais tarde foi substituído por SQL (pronuncia-se SQL).

## 3ª Questão
### Liste as principais características de SQL.
#### o SQL, por ter sido criado para proporcionar um nível de abstração e distanciamento da tecnologia efetivamente utilizada para armazenar fisicamente os dados, pode ser utilizado para acessar bancos de dados relacionais, ou mesmo outros formatos de arquivos não relacionais (arquivos de texto, planilhas Excel, bancos de dados Access, ou tecnologias mais antigas de mainframe são alguns dos acoplamentos possíveis de bancos de dados com a linguagem SQL, desde que tenha sido desenvolvido o "driver" apropriado para SQL acessar o formato citado, mesmo os bancos de dados não possuem esta sintaxe, por isso o SQL tornou-se um padrão da indústria para interoperabilidade. O SQL tem vários dialetos, dependendo do fabricante - SQL Server da Microsoft, Oracle, Sybase, MySQL, etc. Normalmente, os comandos de linguagem mais básicos são semelhantes em todos os dialetos. Quando você começa a usar recursos mais avançados ou raros, o risco de diferença de sintaxe entre os dialetos é maior. O SQL pode ser considerado parcialmente uma linguagem não procedural, no sentido de que o usuário não determina especificamente como os dados devem ser extraídos do banco de dados, mas simplesmente escreve expressões lógicas para a extração dos dados. O motor SQL, juntamente com o módulo de otimização de consultas, é o que desenha automaticamente um plano de execução, baseado em heurísticas e estatísticas, que deve trazer os dados da forma mais rápida, embora também seja possível algum controle do usuário sobre isso, para direcionar o comportamento de uma certa maneira, se necessário.

## Questão 4:
### Descreva a sintaxe do comando SQL: SELECT. Quais cláusulas são obrigatórias e quais são opcionais?
#### O comando SELECT é usado para extrair dados de tabelas no banco de dados. Ele pode extrair dados de uma ou mais tabelas ao mesmo tempo, executar consultas simples a comandos mais complexos, realizar pesquisas, junções, comparações, filtragem, classificação e muitos outros itens.
Além disso é permitido recuperar dados de um objeto do Banco de Dados, como uma tabela, view e, em alguns casos, uma stored procedure (alguns bancos de dados permitem a criação de procedimentos que retornam valor). A sintaxe mais básica do comando é: definindo as colunas da tabela que queremos retornar com SELECT e o nome da tabela com FROM
## Questão 5:
### Qual a importância da linguagem SQL no desenvolvimento de softwares atualmente? Justifique.
#### Um dos grandes benefícios de aprender SQL é que a linguagem pode ser encontrada em uma larga variedade de aplicativos, empresas e domínios. As maiores empresas de tecnologia como Amazon e Facebook usam SQL para consultar e analisar dados. Uma pesquisa em sites de carreiras revelará que há uma demanda muito maior pra profissionais que conhecem SQL. Com a modernização dos processos de negócios e o uso de ferramentas de negócios específicas, a quantidade de dados gerados em todo o mundo aumenta exponencialmente a cada ano. Mas,os Bancos de Dados atualmente armazenam grandes quantidades de dados e a maioria deles usa SQL como linguagem padrão. Se você souber usar a linguagem SQL, poderá encontrar as respostas que procura em bilhões de linhas de dados em segundos, o que certamente levaria muito mais tempo com o Excel, por isso a sua importância.
