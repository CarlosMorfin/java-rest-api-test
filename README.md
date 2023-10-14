# java-rest-api-test

### Al abordar esta tarea, seguí un enfoque estructurado para garantizar el éxito de la solución:

1. **Investigación Inicial:** Comencé por leer la documentación mencionada en la prueba para comprender cómo funcionaban las herramientas necesarias. Esto me permitió obtener una visión general de los conceptos y las tecnologías involucradas.

2. **División del Pipeline:** Decidí dividir el pipeline en dos trabajos (jobs) que se ejecutan a partir de diferentes eventos. Esta división ayudó a organizar y simplificar la implementación.

3. **Resolución de Errores:** Durante la implementación, me encontré con varios desafíos y errores. Utilicé recursos en línea y la documentación relevante para abordar estos problemas de manera efectiva. Esto implicó investigar y comprender la causa raíz de los errores y aplicar soluciones adecuadas.

4. **Primer Job (build-and-tests):** Este trabajo se ejecuta cuando se abre o reabre un pull request. Su objetivo es construir y probar la aplicación. Se asegura de que las pruebas pasen antes de continuar.

5. **Segundo Job (build-and-package):** Este trabajo se ejecuta solo cuando se fusiona un pull request en la rama principal. Su tarea principal es construir el archivo JAR de la aplicación y almacenarlo en los paquetes de GitHub.

6. **Configuración del archivo pom.xml:** En el archivo pom.xml, configuré la URL del repositorio de GitHub Packages de una manera más dinámica. En lugar de incluir directamente el nombre de usuario "CarlosMorfin", utilicé la variable ${env.GITHUB_ACTOR} para representar dinámicamente al usuario u organización que ejecuta el flujo de trabajo. Esto permite una configuración más flexible y reutilizable.

7. **Lectura Adicional de la Documentación:** Cuando me encontré con la necesidad de ajustar la configuración en el archivo pom.xml, profundicé en la documentación de GitHub Actions. Esto me ayudó a comprender las variables predeterminadas de GitHub que pueden utilizarse para configurar el archivo de manera más eficiente.

### Preguntas de la practica y sus respuestas:

1. **¿Consideras útil agrega la acción de caché al workflow?**
Considero que no, ya que en este caso en los dos jobs es necesario ejecutar las pruebas y es necesario el build pero los jobs se ejecutan en eventos diferentes y tendria que tener en cache los builds por el rango de tienpo entre el pull request y el merge.

2. **¿Es posible desplegar automáticamente el artefacto guardado en Packages con Github Actions?**
Si, ya agregue un ejemplo de parte de como seria en el serviocio de Elastic BeansTalk.

3. **¿Qué modificaciones consideras que se tendrían que realizar a los workflows para trabajar con imágenes de contenedores, siguiendo las mejores prácticas que conozcas?**
4. **¿Qué pasos y/o herramientas utilizarías para entender las plantillas de Cloudformation y evaluar que ajustes se tendrían que realizar a la etapa de despliegue?**
jhkdss
