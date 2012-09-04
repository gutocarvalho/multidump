# Multidump

Este é um script de dumps de bancos mysql e postgresql.

Você apenas especifica um IP e um usuário, e o script fará dump de todos os bancos que o usuário puder ler.

## Arquivos

### 1) mcore

arquivo com configuracoes do script em forma de variaveis/constantes

### 2) mcorecheck

script com checagens básicas

### 3) mglist

script que gera a lista de bancos disponíveis para dump a partir das listas de sgbds

<pre>
./mglist
</pre>

### 4) mview

script que possibilita ver os bancos disponíveis para dump

<pre>
./mview
</pre>

### 5) mdumpfast

script para fazer dump de um banco específico diretamente

use o mview para pegar o nome do banco e servidor e depois use o mdumpfast

sintaxe:

<pre>
./mdumpfast [tipo] [banco] [servidor] [formato]
</pre>

exemplo de dump em texto puro
<pre>
./dumpfast psgql sisne sisne01 sql > arquivo.sql
</pre>

exemplo de dump compactado
<pre>
./dumpfast mysql otrs otrs01 gzip
</pre>

### 6) mdumpfull

arquivo que faz dump de todos os bancos mysql e pgsql
existentes nas listas geradas pelo mglist, seguindo
sempre as configurações do mcore

<pre>
./dumpfull
</pre>

## Diretorios

### 1) listas

aqui temos os arquivos com a lista de sgbs postgres e mysql

<pre>
  bacula01:/backupservidores/bancos/multidump# ls -l listas/
  total 8
  -rw-r--r-- 1 root root  979 2011-03-22 19:03 sgbds_mysql.txt
  -rw-r--r-- 1 root root 1674 2011-03-22 18:57 sgbds_pgsql.txt
</pre>

### 2) logs

aqui temos os logs de dumps e erros
 
<pre>
  bacula01:/backupservidores/bancos/multidump# ls -l logs/
  total 0
  -rw-r--r-- 1 root root 0 2011-03-22 18:59 erros.txt
</pre>

### 3) dumps

aqui temos os dumps dos bancos em formato gzip

<pre>
  bacula01:/backupservidores/bancos/multidump# ls -l dumps/
  total 3556
  -rw-r--r-- 1 root root     62 2011-03-22 18:50 pgsql.sisnevm01.sisne.20110322.185037.sql.gz
</pre>

### 4) tmp

aqui temos os arquivos gerados pelo mglist


<pre>
  bacula01:/backupservidores/bancos/multidump# ls -l tmp/
  total 8
  -rw-r--r-- 1 root root 1054 2011-03-22 18:59 listabancos_mysql.txt
  -rw-r--r-- 1 root root 1070 2011-03-22 18:59 listabancos_pgsql.txt
</pre>

[s]
Guto
