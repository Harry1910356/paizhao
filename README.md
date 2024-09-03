```mermaid
classDiagram
    Animal <|-- Duck
    Animal <|-- Fish
    Animal <|-- Zebra
    class Animal{
      +int age
      +String gender
      +isMammal()
      +mate()
    }
    class Duck{
      +String beakColor
      +swim()
      +quack()
    }
