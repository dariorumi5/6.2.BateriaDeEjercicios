# 6.2.BateriaDeEjercicios
```mermaid
classDiagram
    class Usuario {
        -String nombreUsuario
        -String contraseña
        +String correo
        +cambiarPassword(String nueva)
        -validarEmail()
    }
```

```mermaid
classDiagram
    class Persona {
        nombre String
        DNI String
    }

    class Estudiante {
        numeroExpediente int
        notaMedia double
    }

    Persona <|-- Estudiante
```

```mermaid
classDiagram
    class Computadora{
}
    class PlacaBase{
}
    class Raton{
}
    %% Composición (fuerte)
    Computadora *-- PlacaBase : contiene

    %% Agregación (débil)
    Computadora o-- Raton : usa
```

```mermaid
classDiagram
    class CentroComercial {
    }

    class Tienda {
    }

    CentroComercial "1" o-- "1..*" Tienda
```

```mermaid
classDiagram
    class MetodoPago {
        <<interface>>
        +procesar(double importe)
    }

    class Tarjeta {
        +procesar(double importe)
    }

    class Paypal {
        +procesar(double importe)
    }

    class Carrito {
        +pagar(MetodoPago miMetodo)
    }

    MetodoPago <|.. Tarjeta
    MetodoPago <|.. Paypal
    Carrito --> MetodoPago : usa
```

```mermaid
classDiagram
    class Recurso {
        -id int
        -titulo String
        +prestar()
        +devolver()
    }

    class Libro {
        isbn String
    }

    class Revista {
        numeroEdicion int
    }

    class Usuario {
        nombre String
        numCarnet int
    }

    Recurso <|-- Libro
    Recurso <|-- Revista

    Usuario "1" --> "0..*" Recurso : presta
```

