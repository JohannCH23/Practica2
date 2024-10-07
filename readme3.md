#Practica 2
 
1-Comproba que a tes a imaxe httpd.
Para comprobar que temos unha imaxe, executamos o comando (docker images | grep httpd). Con isto veremos se temos a imaxe específica.

<h3>2-Crea un contenedor de nome 'asir_httpd'.</h3>
Para crear o contedor executamos o comando (docker run -d --name "Nome" -p "portos: " httpd). Con isto, crearemos o contedor cos seus respectivos portos e imaxe.

3-Mapea o porto 80 do contenedor có 8080 da túa máquina.
Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.



4-Mostra unha páxina html aloxada no apache2 dende o teu navegador.

5-Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000.

6-Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.

7-Comproba que los dous servidores mostran a mesma páxina.

