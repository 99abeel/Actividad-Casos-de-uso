# Actividad-Casos-de-uso

### 1. Crea el diagrama de uso haciendo uso de platuml, representado los actores y casos de uso que identifiques en los requisitos.

Diagrama de uso:
```
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

```

------
### 2. Describe, haciendo uso de la plantilla, al menos el caso de uso "Sacar dinero", con las interacciones que tiene entre el actor y el caso de uso.

El caso de uso "Sacar Dinero" permite a un cliente retirar dinero de su cuenta mediante un cajero automático (para poder hacerlo tiene que estar validado). El proceso empieza cuando el cliente selecciona la opción "Sacar Dinero" e ingresa la cantidad que quiere. El sistema verifica que el cliente tenga saldo suficiente y que no se supere el límite diario de retiro, si todo se cumple el cajero da el dinero, actualiza el saldo e imprime un comprobante. Si el saldo es insuficiente o supera el límite diario, el cajero muestra un mensaje de error y solicita una nueva cantidad o cancela la operacion. 
