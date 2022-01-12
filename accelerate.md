# Accelerate



##

[#quantumtalent/practica-dev](bear://x-callback-url/open-tag?name=quantumtalent/practica-dev)

### Our Goal

* High Performers vs Low Performers
  * High Performers have:
    * 46 time more frequent code deployments
    * 440 times faster lead time from commit to deploy
    * 170 times faster mean time to recover from downtime
    * 5 times lower change failure rate
* Tempo vs Stability
  * Tempo:
    * deployment frequency
    * lead time
  * Stability
    * mean time to recover
    * Failure rate
  * Lowers performers focus on Tempo
    * Result:
      * Larger deployment failures
      * Increase time to restore service
* Flaws in performance measuring
  * focus on outputs rather than outcomes
  * focus on individual or local measures rather than a team or global ones
  * i.e
    * Lines of code
      * Generates bloated software
      * Higher maintenance
      * Higher cost of change
      * Minimizing lines of code isn’t and ideal measure
        * Extreme: one task one line
          * Nobody can understand
    * Velocity
      * Capacity planning tool (_Points of sprint_)
        * used to extrapolate how long will take the team to complete all the work that has been planned and estimated
      * Flaws
        * Relative and team-dependent
        * when velocity is used as measure
          * team work to game velocity
          * inflate their estimates
          * focus on complete many stories as possibles
          * no collaboration
    * Utilization
      * extremely utilization leads
        * lead times approach to infinite
        * very high levels of utilizations , exponentially longer to get anything done

### Main Metrics

* Tiempo de espera (_Lead Time_)
  * Tiempo que toma desde que un cliente hace un pedido hasta que esta satisfecho
  * Dos partes
    * Tiempo de demora en validar y diseñar el producto (_fuzzy front end_)
    * Tiempo que demora en implementar , testing y delivery en producción
      * from first commit to running in production
  * Lower lead time increase feedback
  * Options (from first commit to running in production):
    * Less than one hour
    * Less than one day
    * Between one day and one week MA\* Aprox One Day KE
    * Between one week and one month. MA (LE)
    * Between one month and six months
    * More than six months
* Frecuencia de Despliegues
  * In production environment
  * Small Batches
    * Acelera el feedback
    * Reduce riesgo y costos
    * Mejora la eficiencia
    * Incrementa la motivación
  * Options
    * On demand (multiple deploys per day) \* AVG Master2-Dev3 push to master
    * Between once per hour and once per day MA LE
    * Between once per day and once per week Kev(2)
    * Between once per week and once per month
    * Between once per month and once every six months
    * fewer than once every six months
* Mean time to restore (MTTR)
  * Qué tan rápido el servicio puede ser restaurado?
    * Unplanned outage
    * Service impairment
  * Options:
    * Less than one hour
    * Less than one day \* 4 hours Max LE kev MA
    * Between one day and one week
    * Between one week and one month
    * Between one month and six months
    * More than six months
* Change Fail Percentage (CFP) 30%. 60% 40% 40%
  * Cuando se hacen cambios en los servicios
    * qué porcentaje de error existe en producción?
  * Including
    * Software releases
    * Infraestructure configuration [Notas sobre Infraestructura](bear://x-callback-url/open-note?title=Notas%20sobre%20Infraestructura\&x-error=bear%3A%2F%2Fx%2Dcallback%2Durl%2Fcreate%3Ftitle%3DNotas%2520sobre%2520Infraestructura)
    * Require a hot fix
    * Rollback
    * Fix-forward
    * Patch

### 2017 Metrics

* High performers
  * Lead time: Less than one hour
  * Deployment frequency: On Demand (Multiple deploys per day)
  * MTTR: Less than one hour
  * Change Failure Rate: 0-15%
* Medium performers
  * Deployment frequency: Between once per week and once per month
  * Lead time: Between one week and one month
  * MTTR: Less than one day
  * Change Failure Rate: 0-15%
* Low performers
  * Deployment frequency: Between once per week and once per month
  * Lead time: Between one week and one month
  * MTTR: Between one day and one week
  * Change Failure Rate: 31-45%

### Secondary metrics

* General Process
* Seguridad en datos
  * debe ser transversal a todas las fases
* Investigación

### Habilidades que conducen a acelerar

* Continuous delivery
  * Build Quality in
    * Cease dependence on inspection to achieve quality
  * Work in small batches
    * By splitting work up into much smaller chunks that deliver measurable business outcomes quickly for a small part of our target market, we get essential feedback on the work we are doing so that we can course correct.
  * Computers perform repetitive tasks, people solve problems
  * Relentlessly pursue continuous improvement
    * high performing teams are never satisfied
  * Everyone is responsible
    * Close collaboration
    * Everyone is involved in the software delivery process
  * Comprehensive configuration management
    * Different environments
      * Build
      * Test
      * Deploy
    * Version control
      * Código
      * Configuración de sistema
      * Entornos virtuales
    * Pipelines
  * Continuos Integration
    * High performer teams keep branches short lives (less than one day’s work)
    * Integrate them into Trunk/Master frequently
      * Trunk-based development methods
        * Maximo tres ramas activas en un repositorio
        * Ramas con tiempo de vida corto (máximo un día)
    * Pipelines
  * Continuos testing
    * Automated tests
    * Acceptance test and criteria
    * No one should be saying they are done if no tests were performed
  * Integración continua (CI) ⇒ Entrega continua (CD)
    * Uso de Pipelines
    * Uso de Pull Requests
* Lean Management Practices
  * Limiting work in progress
  * Creating and painting visual displays
    * show:
      * Quality
      * Productiviy
      * Current status of work
    * Monitoring tools
* Testing Automatizado
  * Administration de Data para testing
  * Tipos de testing
    * Pruebas de stress
    * Pruebas unitarias
    * Pruebas de integración
    * Pruebas de sistema
    * Pruebas de caja negra y caja blanca
    * Pruebas de smoke
    * Pruebas de escenario
    * Pruebas de configuración
    * Red team Blue team
* Tener presente la seguridad
  * Revisiones de seguridad
  * InfoSec team para detectar amenazas
    * Procesos
    * Herramientas
    * Politicas
    * Libraries seguras no deprecadas
    * Testing de seguridad como parte de los testing automáticos

### Architecture

* Debe ser poco acoplada
  * Factible de testing y desplegar a demanda sin necesitar orquestaciones con otros servicios
  * Permite a los equipos ser independientes
* Debe empoderar a los equipos
  * El equipo escoge las herramientas
* More detailed information [Arquitectura Evolutiva](bear://x-callback-url/open-note?title=Arquitectura%20Evolutiva\&x-error=bear%3A%2F%2Fx%2Dcallback%2Durl%2Fcreate%3Ftitle%3DArquitectura%2520Evolutiva) [Architecture without end state](bear://x-callback-url/open-note?title=Architecture%20without%20end%20state\&x-error=bear%3A%2F%2Fx%2Dcallback%2Durl%2Fcreate%3Ftitle%3DArchitecture%2520without%2520end%2520state)

### Product and process

* Pedir feedback constante al cliente ⇒ PO
* Transparencia 100%
* Trabajar en small batches
  * Partes pequeñas que pueden ser completadas en un sprint
  * En producción ⇒ genera feedback rápidos
* Experimentación
  * habilidad para de manera independiente:
    * crear
    * actualizar

### Lean Management and monitoring

* Métodos rápidos de aprobación
  * Peer Review
* Monitorear a travez de servicios e infraestructura
* Revisar la salud del sistema pro-activamente
* Work in Process Limits ⇒ disminuye el Burn out
* Communication dentro del equipo
  * Blogs
  * Dashboards
  * Jira, Asana , Notion ⇒ Backlog

### Cultural

* El Aprendizaje es esencial , equivocarse esta bien siempre y cuando sea factible de corregir
* Collaboration
* Proveer recursos y herramientas
* Liderazgo transformador
