# Pipeline Sample API

- Es un proyecto que tiene como finalidad automatizar el testeo del codigo ingresado al repositorio, utilizando el framework Lippia.

### Consideraciones
- El proyecto contiene la carpeta .github/workflows donde se encuentran dos archivos de automatización de pipelines "Actions" que se ejecutan segun donde se haga el commit o el merge:
- Cuando el commit se realiza a main o master el test se ejecuta automaticamente con el archivo Workflow-API-Auto.yml
- Cuando el commit se realiza a otro branch el test se debe ejecutar manualmente, corriendo el archivo Workflow-API-Manual.yml

### Como se usa
- Un nuevo commit en el repositorio dispara el pipeline, iniciando las pruebas pertinentes.

- Antes de disparar el pipeline se deben configurar las siguientes variables de entorno dentro del archivo .github/workflows/Workflow-API-Auto.yml en "jobs: testing: env:", los valores de dichas variables se encuentran en el archivo POM.xml:
  * **TAG**: lleva el nombre de la prueba
  * **TESTTYPE**:  determina el tipo de pruebas a realizar
  * **LANG**: determina el idioma

- Si los test requieren variables adicionales o diferentes, se debe modificar esta sección del archivo para reflejar el cambio.
- En caso de que el commit sea realizado a un branch que no sea main o master, se deberá ejecutar manualmente el pipeline correspondiente al archivo .github/workflows/Workflow-API-Manual.yml declarando las variables o seleccionando las mismas en el contexto de ejecuición.
- Si hiciera falta modificar estas variables se pueden modificar al comienzo del archivo en el apartado "inputs:" y en el apartado "env:" para que coincidan.

- Se puede seleccionar una variable del tipo "Choice" para darle al usuario la opción de elegir entre opciones prefijadas, o usar variables tipo "input" para dejar un campo de texto libre. 
