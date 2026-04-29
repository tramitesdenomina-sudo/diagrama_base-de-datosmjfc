```mermaid
classDiagram
    direction LR
    class Cliente {
        +ID_Cliente (MJ)
        +Nombre
        +Apellido
        +Email
        +Telefono
    }
    class Pedido {
        +ID_Pedido (MJ)
        +Fecha
        +Monto_Total
        +ID_Cliente (FC)
    }
    class Producto {
        +ID_Producto (MJ)
        +Nombre_Producto
        +Precio
        +Stock
    }
    class Detalle_Pedido {
        +ID_Detalle (MJ)
        +ID_Pedido (FC)
        +ID_Producto (FC)
        +Cantidad
    }

    Cliente "1" --> "*" Pedido : Realiza
    Pedido "1" --> "*" Detalle_Pedido : Contiene
    Producto "1" --> "*" Detalle_Pedido : Aparece en
