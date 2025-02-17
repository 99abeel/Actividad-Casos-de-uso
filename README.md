# Actividad-Casos-de-uso

Diagrama de uso:

@startuml
actor Cliente

rectangle "Cajero" {
    usecase "Validar Cliente" as validar
    usecase "Sacar Dinero" as sacar
    usecase "Transferir Dinero" as transferir
    usecase "Ingresar Dinero" as ingresar

    Cliente --> validar
    Cliente --> sacar
    Cliente --> transferir
    Cliente --> ingresar

    sacar --> validar : <<include>>
    transferir --> validar : <<include>>
    ingresar --> validar : <<include>>
}

@enduml
