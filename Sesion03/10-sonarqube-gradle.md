1. Seleccionar job gradle
    1. En la sección Build Environment.
    1. Seleccionar: Execute SonarQubeScanner
    1. En la sección de "Analysis properties"
    ```bash
    sonar.projectKey=labgradle01
    sonar.projectName=labgradle01
    sonar.sources=src/main/kotlin
    sonar.java.binaries=build/classes/
    sonar.tests=src/test/kotlin
    ```    
