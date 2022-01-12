# Architecture without end state



##

[#quantumtalent/practica-dev](bear://x-callback-url/open-tag?name=quantumtalent/practica-dev)

* Crear un vocabulario commun
  * Cuando nombramos algo estamos creando un concepto y debe aprenderse
  * Debemos ser conscientes del costo que implica construir una arquitectura buena
* Como empezar?
  * Explorar el espacio del problema
  * Diagrama de contexto para ver los limites
  * Mirar a todos los roles
  * Clients y usuarios clave
    * Usuarios que usaran el sistema
    * People who pay the bills
  * Buscar en lo que queremos enfocarnos y lo que podemos usar de afuera
  * Diagramas para comunicar (text to diagram plantUML)
  * Views y viewpoints
  * Casos de usos para los stake holders
  * Interacción y despliegue para Desarrollo
  * Contratos.
  * Diagrama de contexto
* Que va adentro y qué no?
  * Si usamos otros API va dentro del diagrama
  * Runtime es instrinseco al sistema
    * Digital ocean
  * Cosas externas como si hay otros desarrollos que afectan y se están desarrollando en paralelo
  * Cada flecha es una interfaz
  * La falta de mapear las interfaces genera Loss of Data o Corrupt Data
* Para cada role
  * Identificar a los implicados (stakeholders)
  * Las necesidades
* Para cada API
  * Sync or async
  * Transport
  * Protocols
  * Test
  * Api Table
    * Hacer un cuadro con la información necesaria para Test y definir las API
    * ID, Name, Initiation, Sync, Frame, Size, Transport, Framing, Encoding, Semantics
* Arch Qualities
  * Observador Runtime
  * Performance
  * Latency for each transaction
  * Security
  * Integridad de datos
  * Availability
  * Probabilidad de cumplir una tarea
  * Usability
  * GUI
  * Scalability
  * Capacidad a cambio
  * Portabilidad
  * Integrability with other systems
  * Reusability
  * Testing
  * _Solo una cualidad puede ser de importancia_
* Ranking de qualidades
  * Importante para guiar tradeof later
  * Responder a cuales son las cualidades más importantes?
  * Arch Requirements
    * Dramatic alters the architecture
    * Causes addition of new moving paths
    * With out it system fails (ARQ KILLERS)
    * ARQ Constraints
      * Son mas que requerimientos
      * Son factores externos que nos forzar a actuar diferente
      * Son menos únicos que los requerimientos y se puede vivir con ellos
* Decompose the system
  * Componente (micro servicio) que se puede desplegar en cualquier lado
  * Evaluar la descomposición
  * Evaluar el flujo
  * Antropomo-formizar los roles
    * Information Hiding
    * Ayuda a la compensability al uniformizar las interfaces
  * Para descomponer debemos usar cosas estándares
  * URL
    * Un servicio puede responder a varios (mas genérico) usando eventos
    * Views you can use
      * C4 ( [c4model.com](http://c4model.com) )
        * Context
        * Container (zoom of the context)
        * Component (desicion hiding)
  * Classes
  * Dataflow Diagram
    * Permite ver ciclos y flujo de la información
    * Es bueno para mostrar a otras personas
    * Sirve para detectar cuellos de botella
* ARQ es un proceso continuo
  * Tiempo es fundamental
  * Build time
  * System Lifespan
  * Change time after launch
  * Que cosa limita el lifespan?
    * Depende del contexto
  * Minimum marketable feature
  * Decompose systems by isolated MMF
    * MMF y pull AWS por que marcan los cambios en funcionalidad
* Beneficios
  * Clearly show dependencies
  * Sequencing features
  * Read. Principles of product development flow
* Yagni or not?
  * i.e. Hats on lobsters
* Analizando el acoplamiento
  * Operacional
  * Desarrollo
  * Semantico
  * Funcional
  * Cadenas de acoplamiento
  * SKU
    * Representa a un individuo
    * Representa una cantidad Batch de un objeto
  * Price point
    * Es una medida de unidad
  * Otro tipo de acoplamiento son los long arrows
    * Hay que ser específicos a mas pasos para que sea mas ponderable
  * Cohesion
    * Metrica L-con score
  * Visualización en base a grafos
  * Test coverage
  * Orthogonal
    * You keep using that word
    * Watermelon projects
    * Encontrar una ponderación y una distribución al sistema y a los qualities a priorizar y según eso escoger historias
* Ortogonal in software
  * Policy service
  * Entity service
* API Design
  * Booleans in API implies an state
* Plug testing ( verificar los contratos)
  * Verifica si el servicio se cae si recibe un 400 de otro servicio sin un formato establecido
  * Random inputs
  * Data incompleta
  * Data anonima
