# API de Medicamentos (Java + Spring Boot)

API REST basada en el video "Así de fácil es crear una API Rest en Java con Spring Boot" (Lau Sanabria).
Usa una lista de medicamentos en memoria (sin base de datos).

## Requisitos (instalar en tu computador)
1. **Java 17 o superior** (JDK). Comprueba con: `java -version`
   - Si no lo tienes: descarga el JDK 17 o 21 de https://adoptium.net
2. **Maven NO es obligatorio**: el proyecto trae el "Maven Wrapper" (`mvnw` / `mvnw.cmd`), que se descarga solo.
3. (Opcional) Un IDE: IntelliJ IDEA Community o VS Code con "Extension Pack for Java".
4. (Opcional) Postman para probar los endpoints (o simplemente el navegador).

## Cómo ejecutarla
Abre una terminal dentro de esta carpeta y ejecuta:

- **Windows:** `mvnw.cmd spring-boot:run`
- **Mac / Linux:** `./mvnw spring-boot:run`

La primera vez tarda un poco porque descarga las dependencias. Cuando veas
`Tomcat started on port 3000`, la API está funcionando.

## Endpoints
| Método | URL | Qué hace |
|---|---|---|
| GET | http://localhost:3000/ | Prueba: responde "Hola mundo" |
| GET | http://localhost:3000/medicamentos | Lista todos los medicamentos |
| GET | http://localhost:3000/sintoma?sintoma=Fiebre | Medicamentos indicados para ese síntoma |

Ejemplos de síntomas: `Fiebre`, `Dolor`, `Inflamación`, `Náuseas`, `Diarrea`, `Tos`.
(En esta versión la búsqueda no distingue mayúsculas; en el video sí.)

## Estructura
```
src/main/java/com/example/medicamentos/
├── MedicamentosApplication.java   # punto de entrada (@SpringBootApplication)
├── Medicamento.java               # modelo: nombre, comercial, vía, dosis, indicaciones...
└── MedicamentosController.java    # @RestController con la lista y los 3 endpoints
src/main/resources/application.properties   # server.port=3000
```

## Personalizarla
Como dice el video, puedes cambiar "medicamentos" por libros, películas, cursos, etc.:
cambia la clase `Medicamento` (sus campos) y la lista dentro del controlador.

> Los datos de medicamentos son de ejemplo educativo, no información médica para uso real.
