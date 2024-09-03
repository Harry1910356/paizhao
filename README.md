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
    class Elmyfreq {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    class pedestal_ts_mtanhfit {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    class mtanh_ped {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    class pedestal_ts_plot {
        input : out
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    class detectOutliers{
        input : out
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    class dW_ELM_DML {
        input : out
        output : T, Rho, P profiles after fitting
        function: get the elmy signal information 
    }
    
    pedestal_ts_fit --> FunctionB : calls
    FunctionA --> Elmyfreq : calls
    pedestal_ts_default --> FunctionD : calls
    Elmyfreq --> pedestal_ts_mtanhfit : calls
    pedestal_ts_mtanhfit --> mtanh_ped : calls
