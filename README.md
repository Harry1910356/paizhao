```mermaid
classDiagram
    class pedestal_ts_fit {
        attribute1 : String
        asdada()  
    }
    class FunctionB {
        +functionB()
    }
    class FunctionC {
        +functionC()
    }
    class FunctionD {
        +functionD()
    }
    class FunctionE {
        +functionE()
    }
    
    pedestal_ts_fit --> FunctionB : calls
    FunctionA --> FunctionC : calls
    FunctionB --> FunctionD : calls
    FunctionC --> FunctionD : calls
    FunctionD --> FunctionE : calls
