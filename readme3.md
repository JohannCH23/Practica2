<title> #Practica 2 - Johan Erazo </title>
 
<h2> 1-Comproba que a tes a imaxe httpd.</h2>
Para comprobar que temos unha imaxe, executamos o comando (docker images | grep httpd). Con isto veremos se temos a imaxe específica.

<h2>2-Crea un contenedor de nome 'asir_httpd'.</h2>
Para crear o contedor executamos o comando (docker run -d --name "Nome" -p "portos: " httpd). Con isto, crearemos o contedor cos seus respectivos portos e imaxe.

<h2> 3-Mapea o porto 80 do contenedor có 8080 da túa máquina.
Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.</h2>
Primeiro teremos que crear o directorio co comando (mkdir "Nome"). Despois imos á carpeta creada con (cd "Nome do directorio"). De paso, creamos o ficheiro baleiro co comando (touch "nome"). 

Agora arrincamos o contedor coa ruta requirida co comando (docker run -d --name "Nome" -p "Portos: " -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd).

<h2> 4-Mostra unha páxina html aloxada no apache2 dende o teu navegador.</h2>
Para mostrar a páxina que temos no ficheiro HTML, temos que executar o comando (docker run -p 8080:80 -v /home/johan/htdocs:/usr/local/apache2/htdocs httpd). Co comando executado, o contedor poñerase en funcionamento en primeiro plano e poderemos ver a páxina que creamos no navegador, colocando "localhost:8080".

<h2> 5-Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000. </h2>
Para isto, creamos primeiro o contedor coa mesma ruta que o outro que fixemos anteriormente, da seguinte maneira:  
(docker run -d --name asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs httpd).

Agora executamos o outro comando para correr o contedor en primeiro plano:  
(docker run -p 8000:80 -v /home/johann/htdocs:/usr/local/apache2/htdocs httpd). 

Con este contedor en funcionamento, abrimos o navegador e buscámolo con "localhost:8000".

<h2> 6-Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.</h2>
Facemos os mesmos pasos que no punto 5, só que cambiando o porto ao requirido e o nome do contedor. Así:  
(docker run -d --name asir_web2 -p 8090:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs httpd).

<h2> 7-Comproba que los dous servidores mostran a mesma páxina. </h2>
Para isto, podemos abrir dúas terminais e executar os comandos para corrélos nos mesmos portos de antes coas seguintes instrucións:

- Para o primeiro contedor:  
(docker run -p 8000:80 -v /home/johann/htdocs:/usr/local/apache2/htdocs httpd)
  
- Para o segundo contedor:  
(docker run -p 8090:80 -v /home/johann/htdocs:/usr/local/apache2/htdocs httpd)

Despois, abrimos o navegador en dúas pestanas distintas e buscamos os localhost cos portos correspondentes.
