# Pipeline Sample API

- Es un proyecto que tiene como finalidad automatizar el testeo del codigo ingresado al repositorio, utilizando el framework Lippia.

### Consigna
- Crear un pipeline que ejecute el test en dos escenarios que dependen del branch al cual se realice el commit:
-Cuando el commit se realiza a main o master el test se ejecuta automaticamente.
-Cuando el commit se realiza a otro branch el test se ejecuta manualmente.

### Como se usa
- Un nuevo commit en el repositorio dispara el pipeline, iniciando las pruebas pertinentes.

- Antes de disparar el pipeline se deben configurar las siguientes variables de entorno dentro del archivo .gitlab-ci.yml en "rules", los valores de dichas variables se encuentran en el archivo POM.xml:
  * **TAG**: lleva el nombre de la prueba
  * **TESTTYPE**:  determina el tipo de pruebas a realizar
  * **LANG**: determina el idioma

- En caso de que el commit sea realizado a un branch que no sea main o master, la declaracion de las variables, y la ejecucion del pipeline deben ser realizadas de forma manual.
