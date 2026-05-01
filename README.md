```mermaidclassDiagram
    class Cliente {
        +String id_cliente
        +String nombre
        +String correo
        +String telefono
        +crearTicket()
    }

    class Ticket {
        +int id_ticket
        +String descripcion
        +String categoria
        +DateTime fecha_creacion
        +String estado
        +asignarAgente()
    }

    class Agente {
        +int id_agente
        +String nombre
        +String area_especializacion
        +actualizarTicket()
    }

    class HistorialSeguimiento {
        +int id_historial
        +DateTime fecha_hora
        +String comentario
        +String estado_previo
        +String estado_nuevo
    }

    Cliente "1" -- "0..*" Ticket : reporta
    Agente "1" -- "0..*" Ticket : responsable_de
    Ticket "1" -- "0..*" HistorialSeguimiento : tiene
    Agente "1" -- "0..*" HistorialSeguimiento : registra
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
