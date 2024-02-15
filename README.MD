# Conexão do Python com o Mysql

!["Imagem Python com MySQL"](https://www.learntek.org/blog/wp-content/uploads/2019/06/Mysql-python.png)

## Divre de comunicação com o mysql
Para estabelecer a comunicação entre o Python e o banco Mysql, iremos usar o seguinte drive:
<a href="https://pypi.org/project/mysql-connector-python/#history">https://pypi.org/project/mysql-connector-python/#history</a>


### Comando para instalar 
``` python
    python -m pip install mysql-connector-python
```
---
### Configuração do banco de dados Mysql
O nosso banco de dados esta em um container de docker, para acessa-lo será necessario criar o container. Então faremos os seguintes comandos em um servidor Fderoa com o docker instalado

#### Criação do volume
``` shell
mkdir dadosclientes 
```
#### Criação do container
<center>
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTNT_a8nqBIuQaGrqxrao1jngeC3Xyl-kctCw&usqp=CAU"
height="100" width="100">
<center> 

``` shell
docker run --name srv-mysql -v ~/dadosclientes:/var/lib/mysql -p 3784:3306 -e MYSQL_ROOT_PASSWORD=senac@123 -d mysql
```
### Criação banco de dados da tabela clientes
```sql 
create database banco;

use banco;

create table Clientes(
clientes_id int auto_increment primary key,
nome_clientes varchar(50) not null,
email varchar(100) not null unique,
telefone varchar(20) 
);
```