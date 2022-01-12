# Notas sobre Infraestructura



##

[#quantumtalent/practica-dev](bear://x-callback-url/open-tag?name=quantumtalent/practica-dev)

[qconf](https://www.amazon.com/clouddrive/share/Dw0u0h863wT5pMYdNiwvbOPXgoDN5OvGHybN5wqjhJS)

### Devops for database

* Beneficios
* Mejor CI / CD
* Rapido
* Mejor
* Barato
* Estabilidad de la base de datos _(2018, state of devops report)_
  * Incrementa la responsabilidad y ownership
  * No tener documentada la BD es como no tener documentando el sistema
* Que es Devops para DB
  * Responsabilidad de los desarrolladores tanto en los esquemas, carga y rendimiento
  * Mejora la solución de problemas y reparaciones de la BD
  * Los esquemas como código ayudan a una mejor migración y backups
  * Tener un pipe de despliegue automatico para la DB, así como la migración de la misma.
  * Tener entornos de desarrollo automáticamente generados.
* Elementos
  * Personas
  * Se necesita expertos no validadores
  * El equipo debe volverse experto
  * No hay DBA sino DBRE
    * [https://www.xaprb.com/talks](https://www.xaprb.com/talks)
* Cultura
  * Velocidad (fail) vs Adaptación (success)
  * No es un artefacto
  * Incluir a todos en las consequências y beneficios
  * Crear un camino de baja resistencia
  * El dolor debe ser compartido si no no existe el cambio
* Leadership support
  * Liderazgo horizontal que ayuda a los demás y que es el baso comunicativo
  * Comunicación y confianza
  * Norte para dirigir a todos , proposito
  * Un apoyo constante a todos los miembros
  * Feedback
* Procesos
  * Orientación del equipo
  * Los equipos trabajan mejor como equipos de producto
  * Siempre el proceso primero
  * Plan y Roadmap
  * Un backlog simple
  * Devops poco a poco
  * Transparencia
* Herramientas
  * Despliegues automáticos
  * No hacer trabajo manual (usar cronjobs)
  * Integración continua
  * Monitoreo (usar las 7 golden signals CELT-USE)
  * Observabilidad, ver cuando y donde hay problemas y como resolverlos
  * Shared Knowledge and process, wikis, diagramas y documentación.

### Reactive DDD

* Cuando tenemos muchos servicios no podemos ver el impacto de eliminar uno o no
* Clusterizar los servicios según el dominio
* Hacer que los servicios funcionen en base a eventos como triggers
* Encontrar las entidades que modelan el modelo de negocio y mapear la BD con las entidades y los servicios

### The Service Mesh

* Es un control centralizado
* Rapido de cambiar
* Permite consistencia
* Istio → Service mesh

### Servicios autónomos

* Versiones de todo es muy importante
* Cada servicio tiene su propia base de datos
* Respecto a otros servicios
  * Circuit Breaker → Hystrix
* Autenticacion
  * Loggin
  * Service visibility
    * zipkin
    * Opentracing

### Servicios Kubernetes

* Es una abstracción que define un conjunto lógico de PODS y una política para acceder sellos
* Permite auto escalamiento
* Tener en cuenta que siempre la base de datos puede ser un cuello de botella
* Si un servicio se cae solo debe tener un rango de efecto limitado
  * AWS Step function
  * Camunda
  * UBER Cedence
  * Zeebe
  * Netflix Conductor
* Monitorear los timeouts
  * Orquestadores → kafka

### Migraciones

* Encapsular reads y write to DB
* Evitar funcionalidades duplicadas
* Reemplazar los accesos a bases de datos
* Generalizar funcionalidades
* Adaptadores a la BD y hacer _shadow_
* Active récord adapter
* Migrar por endpoint o atributos
* Se debe tener un modelo bottom top
* Quitar funcionalidades del monolito
  * luego cambiarlos servicios a micro servicios
* Tener automatizado
  * Generación de código
* Testing
* Monitoreo
* OpenAPI

### Emerging architecture

* [Arquitectura Evolutiva WSO2 - Resume](bear://x-callback-url/open-note?title=Arquitectura%20Evolutiva%20WSO2%20%2D%20Resume\&x-error=bear%3A%2F%2Fx%2Dcallback%2Durl%2Fcreate%3Ftitle%3DArquitectura%2520Evolutiva%2520WSO2%2520%252D%2520Resume)
* Clusterizar en base al scope de los servicios
* Concepto de célula para conjunto de servicios especializados [wso2.com/architecture](http://wso2.com/architecture)
* Evolutionary API
  * Usar funciones fitness
  * Usar el contexto en los requests
  * No tener servicios diferentes apuntando a la mismas tablas.

### Descomponiendo un monolito

* Hay que desacoplar las dependencias
* Agrupar según funcionalidad
* Iniciar por servicios pequeños

### Chaos engineering

* Experimentos para revelar vulnerabilidades
* Pre-requisistos
  * Monitoreo y observability
  * On - code incident management
  * Costo of discontinuous service per hour
* Casos de uso
* Strengthens of new productos
* Infraestructura
* Logs
* Auto scaling
* Siempre tratar de minimizar Blast Radius
* Que medir?
  * CPU
  * IO
  * RPI
  * Memory
  * Availaibility
* Debemos tener
  * Escenario
  * Hipotesis
  * Experimento
  * Condiciones de parada

### How to build production ready micro-services

* book: _production ready micro-services Susan J Fauler_
* Tenants of readiness
* Estabilidad
  * Estable dev cicle , testing CI CD
  * Estable deploy cicle
  * Canary , AB, Green Blue, feature flags
* Reliability
* Dependency management
* On-boarding deprecation procedures
* Control de acceso
* Documentacion
* Deprecacion
* Routing y discovery
* Escalabilidad
* Trafico de red
* Contenedores
* Peformance
* Evaluación constante de rendimiento
* Capacity
* Tolerancia a fallos
* Avoiding single points of failure
* Caos Eng.
  * Disaster recovery
  * Disaster recovery plans
  * Incident management
  * Monitoring
* Dashboard para servicios y infraestructura
* Alertas automáticas
* Loggin
* DOD y DOR
* automatizar las validaciones
* Evangelizar a todos para que se cumplan
* Documentación centralizada
* wikis
* API
* Bases de conocimiento
* Codigo
* Diagramas por servicio
* Mesure Guidelines
* Service score card automatizado
