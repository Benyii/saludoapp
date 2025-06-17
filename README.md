
# SaludoApp

## 📌 Descripción del proyecto

SaludoApp es una aplicación Java simple creada con Maven que saluda al usuario por su nombre, mostrando el mensaje `Hola, <nombre>!`. El proyecto incluye pruebas unitarias con JUnit y automatización del ciclo de build mediante Jenkins.

*Proyecto desarrollado como parte de un bootcamp de formación en herramientas DevOps, orientado a la práctica de integración continua y automatización de procesos con tecnologías estándar del entorno Java.*

---

## 📦 Herramientas utilizadas

- Java (JDK) 11.0.27
- Maven	3.8.6
- JUnit	4.13.2
- Jenkins
- Git

## ⚙️ Pasos principales realizados
- Instalación de JDK 11 y Maven 3.8.6 en entorno WSL.
- Configuración de Jenkins en Linux con integración hacia herramientas locales.
- Creación del proyecto Maven.
- Implementación de la clase App.java con el método saludar(nombre).
- Desarrollo de una prueba unitaria en JUnit validando el saludo.
- Subida del repositorio a GitHub con rama principal main.
- Creación de un pipeline en Jenkins utilizando Jenkinsfile versionado.
- Pipeline con etapas: checkout automático, compilación, pruebas unitarias y empaquetado.

---

## ▶️ Comandos usados con Maven

### Creación del proyecto:
```bash
mvn archetype:generate -DgroupId=com.equipo.saludo -DartifactId=saludoapp -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
mvn clean compile
mvn test
```

---

## 📁 Estructura del proyecto

```bash
saludoapp/
├── pom.xml
├── Jenkinsfile
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/equipo/saludo/App.java
│   └── test/
│       └── java/
│           └── com/equipo/saludo/AppTest.java
```

---

## Preguntas finales

1. ¿Qué beneficios concretos viste al automatizar la construcción con Jenkins?

Automatizar con Jenkins permite detectar errores de compilación o pruebas automáticamente en cada push. Ahorra tiempo, elimina pasos manuales y asegura que el código esté siempre validado antes de seguir a producción.

2. ¿Qué parte del proceso crees que sería más crítica en un equipo grande?

Las pruebas y validaciones automáticas (mvn test) son clave en equipos grandes. Aseguran que nadie rompa el código sin darse cuenta. También es importante el uso de ramas y pipelines que validen cada cambio antes de integrarse.

3. ¿Cómo Jenkins asegura calidad antes de hacer despliegues?

A través del pipeline, Jenkins puede compilar, ejecutar pruebas, validar formato de código y generar reportes. Si algo falla, se detiene el proceso. 

4. ¿Qué cambiarías en este pipeline para prepararlo para producción?

Agregaría validaciones de código, generación de reportes, notificaciones de correo, pruebas más completas y un paso de despliegue con verificación de ambiente (dev, QA, prod) mediante perfiles de Maven como en la actividad guiada anterior.
