# java-rest-api-test

### Al abordar esta tarea, seguí un enfoque estructurado para garantizar el éxito de la solución:

1. **Investigación Inicial:** Comencé por leer la documentación mencionada en la prueba para comprender cómo funcionaban las herramientas necesarias. Esto me permitió obtener una visión general de los conceptos y las tecnologías involucradas.

2. **División del Pipeline:** Decidí dividir el pipeline en dos trabajos (jobs) que se ejecutan a partir de diferentes eventos. Esta división ayudó a organizar y simplificar la implementación.

3. **Resolución de Errores:** Durante la implementación, me encontré con varios desafíos y errores. Utilicé recursos en línea y la documentación relevante para abordar estos problemas de manera efectiva. Esto implicó investigar y comprender la causa raíz de los errores y aplicar soluciones adecuadas.

4. **Primer Job (build-and-tests):** Este trabajo se ejecuta cuando se abre o reabre un pull request. Su objetivo es construir y probar la aplicación. Se asegura de que las pruebas pasen antes de continuar.

5. **Segundo Job (build-and-package):** Este trabajo se ejecuta solo cuando se fusiona un pull request en la rama principal. Su tarea principal es construir el archivo JAR de la aplicación y almacenarlo en los paquetes de GitHub.

6. **Configuración del archivo pom.xml:** En el archivo pom.xml, configuré la URL del repositorio de GitHub Packages de una manera más dinámica. En lugar de incluir directamente el nombre de usuario "CarlosMorfin", utilicé la variable ${env.GITHUB_ACTOR} para construir la url dinámicamente donde se depositaria el jar del build. Esto permite una configuración más flexible y reutilizable.

7. **Lectura Adicional de la Documentación:** Cuando me encontré con la necesidad de ajustar la configuración en el archivo pom.xml, profundicé en la documentación de GitHub Actions, lo cual me ayudó a comprender las variables predeterminadas de GitHub que pueden utilizarse para configurar el archivo de manera más eficiente.

### Preguntas de la practica y sus respuestas:

1. **¿Consideras útil agrega la acción de caché al workflow?**
Sí, es útil agregar la acción de caché al workflow. Esto permite evitar la ejecución de una nueva construcción en cada ejecución del flujo de trabajo, lo que ahorra tiempo y recursos. Sin embargo, es importante investigar cómo configurar correctamente la caché, especialmente cuando los trabajos se ejecutan para diferentes eventos, para garantizar un funcionamiento eficiente.

2. **¿Es posible desplegar automáticamente el artefacto guardado en Packages con Github Actions?**
Sí, es posible desplegar automáticamente un artefacto almacenado en GitHub Packages utilizando GitHub Actions. En esta practica solo agregue un paso para hacer esto.

3. **¿Qué modificaciones consideras que se tendrían que realizar a los workflows para trabajar con imágenes de contenedores, siguiendo las mejores prácticas que conozcas?**
Crear un Dockerfile en el directorio del proyecto para definir la construcción de la imagen, utilizar un usuario no privilegiado en el contenedor en lugar de "root" para mejorar la seguridad, escanear la imagen en busca de vulnerabilidades de seguridad utilizando algunas herramientas para este proposito, configurar un trabajo adicional en el flujo de trabajo para compilar la imagen del contenedor y almacenar la imagen en un registro de contenedores.

4. **¿Qué pasos y/o herramientas utilizarías para entender las plantillas de Cloudformation y evaluar que ajustes se tendrían que realizar a la etapa de despliegue?**
* Comenzaría revisando la documentación y el repositorio donde se encuentran las plantillas de CloudFormation para obtener contexto de su funcionamiento. 
* Utilizaría AWS CloudFormation Designer, para visualizar y editar  plantillas para facilitar la comprensión de la estructura y recursos.
* Analizaría los requisitos específicos del despliegue, como la red, los servicios, el acceso, etc. Esto para ayudarme a identificar los ajustes necesarios en las plantillas.
* Realizaría las ediciones necesarias en las plantillas de CloudFormation para cumplir con los requisitos identificados
* Antes de la implementación, realizaría pruebas de las plantillas para asegurarme de que funcionen correctamente y sin errores.