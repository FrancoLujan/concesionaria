# Concesionaria - Arquitectura de Microservicios 🚗

Bienvenido al repositorio de **Concesionaria**, un sistema backend robusto diseñado para gestionar la operatoria de una agencia de vehículos. Este proyecto implementa una arquitectura basada en **microservicios**, facilitando la escalabilidad, el mantenimiento y la resiliencia del sistema.

---

## 🛠 Tecnologías Utilizadas

El sistema está desarrollado íntegramente en el ecosistema **Java**. De acuerdo a las mejores prácticas, se hace uso de las siguientes tecnologías y herramientas:

* **[Java](https://docs.oracle.com/en/java/)**: Lenguaje principal de desarrollo (96% del código base).
* **[Spring Boot / Spring Cloud](https://spring.io/)**: Framework base utilizado para la creación ágil de los microservicios, inyección de dependencias y configuración del API Gateway.
* **Docker & Docker Compose**: Contenerización de cada servicio y orquestación local para levantar todo el entorno con un solo comando.
* **GitLab CI/CD**: Canalización de integración y despliegue continuo configurado a través del archivo `.gitlab-ci.yml`.

---

## 🏗 Estructura del Proyecto y Servicios

La aplicación se divide en múltiples módulos independientes, cada uno con una responsabilidad única dentro del dominio de la concesionaria:

1.  **`api-gateway`**: Actúa como el punto de entrada único para todas las peticiones del cliente (Front-end o móviles). Se encarga del enrutamiento hacia los microservicios correspondientes y de la seguridad perimetral.
2.  **`geolocalizacion`**: Microservicio responsable de calcular, registrar o gestionar la ubicación de los vehículos (útil para rastreo de test drives o logística de la agencia).
3.  **`notificaciones`**: Sistema asíncrono diseñado para despachar alertas, correos electrónicos o mensajes (por ejemplo, confirmación de turnos, recordatorios, etc.).
4.  **`pruebas`**: Módulo core de la agencia para gestionar los vehículos de *Test Drive*, reservas y seguimiento de clientes interesados en probar un auto.
5.  **`logs`**: Servicio centralizado o configuración dedicada para la trazabilidad, registro de eventos (auditoría) y monitoreo de la salud del sistema.

---

## 🚀 Instalación y Ejecución Local

### Prerrequisitos
* [Docker](https://www.docker.com/) y Docker Compose instalados en tu máquina.
* [Java Development Kit (JDK)](https://docs.oracle.com/en/java/) (versión 11 o superior, según la configuración del proyecto) si deseas compilar y ejecutar los servicios manualmente sin contenedores.
* Maven o Gradle (dependiendo del gestor utilizado en cada módulo).

### Despliegue rápido con Docker

El proyecto está preparado para ejecutarse completamente de forma contenida gracias a `docker-compose.yml`.

1.  **Clonar el repositorio**:
    ```bash
    git clone https://github.com/FrancoLujan/concesionaria.git
    cd concesionaria
    ```

2.  **Levantar la infraestructura**:
    Este comando compilará (si es necesario) y levantará todos los microservicios y bases de datos asociadas en segundo plano.
    ```bash
    docker-compose up -d --build
    ```

3.  **Verificar el estado**:
    Asegúrate de que todos los servicios estén corriendo correctamente:
    ```bash
    docker-compose ps
    ```

4.  **Detener los servicios**:
    ```bash
    docker-compose down
    ```

---

## 📖 Documentación Adicional

Para más detalles sobre los componentes del framework utilizado en este proyecto, siempre es recomendable consultar la documentación oficial:
* [Documentación de Spring Framework y Spring Boot](https://spring.io/)
* [Documentación Oficial de Java](https://docs.oracle.com/en/java/)

---

*Desarrollado para gestionar eficientemente el backend de una agencia de pruebas y concesionaria de vehículos.*
