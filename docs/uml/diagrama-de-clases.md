# Diagrama de clases — Turno de Guardacostas

Muestra las piezas con las que se construirá el juego, sus datos (atributos) y sus acciones (métodos). Cubre todo el juego, que es el módulo del equipo.

```mermaid
classDiagram
    class Juego {
        -puntaje: int
        -nivelActual: int
        -estado: string
        +iniciar()
        +pausar()
        +terminar()
        +avanzarNivel()
    }
    class Nivel {
        -numero: int
        -duracion: int
        -intervaloBarcos: int
        -hayHidrocarburo: bool
        +iniciar()
        +terminar()
    }
    class Barco {
        -posicionX: int
        -velocidad: int
        +moverse()
        +soltarResiduo()
    }
    class Residuo {
        <<abstract>>
        -posicionX: int
        -posicionY: int
        +esLimpiadoPor(herramienta) bool
    }
    class Plastico {
        +desaparecer()
    }
    class Hidrocarburo {
        -tamano: int
        -velocidadExpansion: int
        -contenido: bool
        +expandirse()
        +reducir(porcentaje)
        +contener(segundos)
    }
    class Herramienta {
        <<abstract>>
        -nombre: string
        +usar(residuo)
    }
    class Red
    class BarreraContencion
    class MaterialAbsorbente
    class Jugador {
        -herramientaActiva: Herramienta
        +seleccionarHerramienta(nombre)
        +usarHerramienta(residuo)
    }
    class SaludDelMar {
        -valor: int
        +disminuir(cantidad)
        +recuperar(cantidad)
        +estaEnCero() bool
    }
    class Fauna {
        -tipo: string
        -visible: bool
        +actualizar(salud)
    }
    class FichaEducativa {
        -titulo: string
        -texto: string
        -fuente: string
        +mostrar()
    }

    Juego "1" *-- "3" Nivel
    Juego "1" *-- "1" SaludDelMar
    Juego "1" --> "1" Jugador
    Nivel "1" o-- "*" Barco
    Nivel "1" --> "1" FichaEducativa
    Barco "1" --> "*" Residuo : suelta
    Residuo <|-- Plastico
    Residuo <|-- Hidrocarburo
    Herramienta <|-- Red
    Herramienta <|-- BarreraContencion
    Herramienta <|-- MaterialAbsorbente
    Jugador "1" --> "3" Herramienta : dispone de
    Herramienta ..> Residuo : actúa sobre
    SaludDelMar "1" --> "*" Fauna : actualiza
```

## Cómo leerlo

- **Cada caja** es una clase: el molde de un objeto. El apartado de arriba son sus datos y el de abajo sus acciones.
- **`-` y `+`:** `-` es un dato privado (solo la propia clase lo usa) y `+` es una acción pública (otras clases pueden pedirla).
- **`<<abstract>>`:** una clase abstracta no se usa sola, sirve de base para otras. `Residuo` es la base de `Plastico` e `Hidrocarburo`; `Herramienta` lo es de `Red`, `BarreraContencion` y `MaterialAbsorbente`.
- **Flecha con triángulo vacío (`<|--`):** herencia, "es un tipo de". Una `Red` es un tipo de `Herramienta`.
- **Rombo relleno (`*--`):** composición. `Juego` contiene 3 `Nivel` y 1 `SaludDelMar`, y si el juego termina, también terminan ellos.
- **Rombo vacío (`o--`):** agregación. Un `Nivel` tiene varios `Barco`, pero los barcos tienen existencia propia.
- **Flecha simple (`-->`):** una clase usa o conoce a la otra. `"1"` y `"*"` indican cuántos hay (uno o muchos).
- **Flecha punteada (`..>`):** dependencia. Las herramientas actúan sobre los residuos, pero no los poseen.

## Decisiones de diseño

- **Dos jerarquías con herencia** (residuos y herramientas) porque comparten datos y comportamiento pero cada tipo reacciona distinto. Por ejemplo, `Hidrocarburo` se expande y `Plastico` no.
- **`SaludDelMar` es una clase propia** para que la derrota dependa de un solo lugar.
- **La clase `Fauna` depende de la salud del mar** y no al revés, para que se pueda quitar sin afectar el resto (es el RF-10, de prioridad baja).
