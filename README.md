# Bash

![](.img/bash.jpeg)

## Descargar dominios muertos de diciembre del 2020

1. `codigo.sh`

	```bash
	#!/bin/bash
	#s="http://static.hupo.com/expdomain_myadmin/2020-02-21%EF%BC%88%E5%9B%BD%E9%99%85%E5%9F%9F%E5%90%8D%EF%BC%89.txt";
	a="http://static.hupo.com/expdomain_myadmin/2020-12-";
	b="%EF%BC%88%E5%9B%BD%E9%99%85%E5%9F%9F%E5%90%8D%EF%BC%89.txt";
	mkdir dominios
	cd dominios
	for i in {1..31}
	do
		if [ $i -lt 10 ]
		then
			wget $a'0'$i$b
		else
			wget $a$i$b
		fi
	done
	```

2. Archivos .txt descargados  

	![](.img/txt.png)  

3. Contenido de uno de los archivos .txt  

	![](.img/dominios.png)  

## Subir varios archivos a github

1. Tengo un juego que pesa como 600 MB pero github permite un maximo de 50 MB por subida, asi que he dividido el juego

	```bash
	CounterStrike-aa
	CounterStrike-ab
	CounterStrike-ac
	CounterStrike-ad
	CounterStrike-ae
	CounterStrike-af
	CounterStrike-ag
	CounterStrike-ah
	CounterStrike-ai
	CounterStrike-aj
	CounterStrike-ak
	CounterStrike-al
	CounterStrike-am
	```

2. `codigo.sh`

	```bash
	#!/bin/bash
	for letra in {a..l}; 
	do 
	cp /home/lilberick/Downloads/Counter/CounterStrike-a$letra /home/lilberick/Downloads/Juegos/CounterStrike1.6ZombieApocalypse/JuegoDividido
	cd /home/lilberick/Downloads/Juegos/CounterStrike1.6ZombieApocalypse
	git add .
	git commit -m "file $letra"
	git push origin
	done 
	```
