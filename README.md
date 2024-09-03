```mermaid
classDiagram
    class pedestal_ts_fit {
        input : shot, time window, parameters
        output : Temperature, density and other profiles after fitting, as well as fitting parameters
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
