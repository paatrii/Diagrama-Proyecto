```mermaid

classDiagram

      Proyecto <|-- "1..*"Ciclo : {ordered}
      Ciclo <|-- "4"Fase : {ordered}
      Ciclo -- Ejecutable
      Fase <|-- "1..*" Iteración : {ordered}
      Iteración -- "1..*"Artefacto : produce
      Iteración <|-- "1..*" Actividad
      Actividad "0..*" <|-- "0..*"Recurso
      Recurso <|-- Material
      Recurso <|-- Humano
      Artefacto <|-- Documento
      Artefacto <|-- Software

      class Proyecto{
         -nombre : String
         - / avance : Float
      }

      class Ciclo{
      }

      class Ejecutable{
         -bytes
        }

     class Fase{
         -tipo : TipoFase
        }

      class TipoFase{
         inicio
         elaboración
         construcción
         transición
      }

      class Iteración{
         -comienzo : Date
      }

       class Actividad{
         -duracion : Integer
         -avance : Float
      }
      
       class Documento{
         -nombre : String
         -ubicacion
      }

       class Software{
         -bytes
      }

      
       class Humano{
         -nombre : String
      }
      
       class Material{
         -inventario : String
      }