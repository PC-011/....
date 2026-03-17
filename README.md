classDiagram
    direction TB  %% de arriba hacia abajo

    class Empresa_Seguros {
    }

    class Empleado {
        +empleado_id PK
        +nombre
        +dirección
        +banco
        +especialidad
    }

    class Cliente {
        +cliente_id PK
        +nombre
        +dirección
        +salario
        +oficio
    }

    class Seguro {
        +seguro_id PK
        +tipo
        +prima
        +vigencia
    }

    class Venta_Seguro {
        +cliente_id FK
        +empleado_id FK
        +seguro_id FK
    }

    %% Relaciones
    Empleado ||--o{ Cliente : "atiende (1:N)"
    Cliente }o--|| Venta_Seguro : "realiza (N:M)"
    Seguro ||--o{ Venta_Seguro : "se vende (1:N)"
    Empleado ||--o{ Venta_Seguro : "vende (1:N)"

    Empresa_Seguros ..> Empleado : "contrata"
    Empresa_Seguros ..> Cliente : "asegura"
    Empresa_Seguros ..> Seguro : "ofrece"

