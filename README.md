```mermaid
classDiagram
    class pedestal_ts_fit {
        input : shot, time window, parameters
        output : T, Rho, P profiles after fitting
                 with fitting parameters
        function: main funtion（with extra fitting）
    }
    class pedestal_ts_default {
        input : None
        output : the initial parameters
        function: set parameters for fitting
    }
    class Elmyfreq {
        input : shot, time window,plot or not, level,tlag
        output : Elm information
        function: gets ELM times and frequencies
    }
    class pedestal_ts_mtanhfit {
        input : shot, time window, elmcycle，parameter
        output : data after fitting
        function: Filter the data and perform mtanh fitting
    }
    class mtanh_ped {
        input : [5 tanh fitting parameters],s (sqrt(psi_norm))
        output : fitting function, Jacobian, 1st &2nd derivative
        function: modified tanh function used for pedestal fits
    }
    class pedestal_ts_plot {
        input : the data from "load expfit_xxx.mat"
        output : the fitting picture for tempreture and rho
        function: get the fitting picture
    }
    class detectOutliers{
        input : s (sqrt(psi_norm)),tempreture
        output : the indices for the outliers
        function: identify outliers to delete them later
    }
    class dW_ELM_DML {
        input : shot,time window,plot or not 
        output : change and value of plasma energy
        function: get energy loss due to ELMs
    }
    
    pedestal_ts_fit --> pedestal_ts_mtanhfit : calls
    pedestal_ts_mtanhfit --> Elmyfreq : calls
    pedestal_ts_mtanhfit --> dW_ELM_DML : calls
    pedestal_ts_mtanhfit --> detectOutliers : calls
    pedestal_ts_mtanhfit --> mtanh_ped : calls
    
