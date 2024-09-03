```mermaid
classDiagram
    class pedestal_ts_fit {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
                 with fitting parameters
        function: main funtion
    }
    class pedestal_ts_default {
        input : None
        output : the initial parameters
        function: set parameters for fitting
    }
    class FunctionC {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
    }
    class FunctionD {
        +functionD()
    }
    class FunctionE {
        +functionE()
    }
    
    pedestal_ts_fit --> FunctionB : calls
    FunctionA --> FunctionC : calls
    pedestal_ts_default --> FunctionD : calls
    FunctionC --> FunctionD : calls
    FunctionD --> FunctionE : calls
