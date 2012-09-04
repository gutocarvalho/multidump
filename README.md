# Multidump

Este é um script de dumps de bancos mysql e postgresql.

Você apenas especifica um IP e um usuário, e o script fará dump de todos os bancos que o usuário puder ler.

## Arquivos

1) mcore

arquivo com configuracoes do script em forma de variaveis/constantes

2) mcorecheck

script com checagens básicas

3) mglist

script que gera a lista de bancos disponíveis para dump a partir das listas de sgbds

./mglist

4) mview

script que possibilita ver os bancos disponíveis para dump

./mview

5) mdumpfast

script para fazer dump de um banco específico diretamente

use o mview para pegar o nome do banco e servidor e depois use o mdumpfast

sintaxe:

./mdumpfast [tipo] [banco] [servidor] [formato]

exemplos:

./dumpfast psgql sisne sisne01 sql > arquivo.sql
./dumpfast mysql otrs otrs01 gzip

6) mdumpfull

arquivo que faz dump de todos os bancos mysql e pgsql
existentes nas listas geradas pelo mglist, seguindo
sempre as configurações do mcore

./dumpfull

## Diretorios

1) listas

aqui temos os arquivos com a lista de sgbs postgres e mysql

  bacula01:/backupservidores/bancos/multidump# ls -l listas/
  total 8
  -rw-r--r-- 1 root root  979 2011-03-22 19:03 sgbds_mysql.txt
  -rw-r--r-- 1 root root 1674 2011-03-22 18:57 sgbds_pgsql.txt

2) logs

aqui temos os logs de dumps e erros
 
  bacula01:/backupservidores/bancos/multidump# ls -l logs/
  total 0
  -rw-r--r-- 1 root root 0 2011-03-22 18:59 erros.txt

3) dumps

aqui temos os dumps dos bancos em formato gzip

  bacula01:/backupservidores/bancos/multidump# ls -l dumps/
  total 3556
  -rw-r--r-- 1 root root     62 2011-03-22 18:50 pgsql.sisnevm01.sisne.20110322.185037.sql.gz

4) tmp

aqui temos os arquivos gerados pelo mglist

  bacula01:/backupservidores/bancos/multidump# ls -l tmp/
  total 8
  -rw-r--r-- 1 root root 1054 2011-03-22 18:59 listabancos_mysql.txt
  -rw-r--r-- 1 root root 1070 2011-03-22 18:59 listabancos_pgsql.txt


[s]
Guto
