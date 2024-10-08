```mermaid 
sequenceDiagram
%%    participant user
    actor user
    participant client
    participant controller
    participant service
    participant entity
    participant repository
    
    user->>client: assign ciModule<br/> to television
    activate client
    client->>controller: assignCiModuleToTelevision<br/>(televisionId,ciModuleId)
    activate controller
    controller->>service: assignCiModuleToTelevision<br/>(televisionId,ciModuleId)
    activate service
    service->>repository: televisionRepository.findById(televisionId)
    activate repository
    repository-->>service: returns existingTelevision
    service->>repository: ciModule.findById(ciModuleId)
    repository-->>service: returns existingService
    service->>entity: setCiModule(existingCiModule)
    service->>entity: setTelevision(existingTelevision)<br/>Bi-directional
    service->>repository: save(existingTelevision)
    repository-->>service: returns void
    deactivate repository
    service-->>controller: returns void
    deactivate service
    controller-->>client: returns ResponseEntity.noContent().Build()
    deactivate controller
    client-->>user: ciModule is<br/> assigned to television
    deactivate client
    
```