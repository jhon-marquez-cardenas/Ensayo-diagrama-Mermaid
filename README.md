graph TD
   
    %% ==============================
    %% MÓDULOS PRINCIPALES
    %% ==============================
    subgraph ST_DFS_CA["ST-DFS-CA: Arquitectura Táctica de Fusión de Sensores"]
        A["Módulo de Detección / Sensores [SDR, Micrófonos, Cámara]"]
        B["Módulo de Procesamiento Central [Procesador (Jetson/SBC) con Lógica IA/Fusión (MATLAB/Python)]"]
        C["Módulo de Alimentación [Batería y gestión eléctrica]"]
        D["Módulo de Comunicaciones [WiFi y GPS]"]
        E["Módulo de Interacción / Visualización [Pantalla táctil]"]
    end

    %% ==============================
    %% SUBSISTEMA MECÁNICO
    %% ==============================
    subgraph SUB_MEC["Subsistema Mecánico (Alojamiento Táctico)"]
        S_M["Alojamiento (Maleta Rugerizada / Trípode)"]
    end

    %% Relaciones con el subsistema mecánico
    A --- S_M
    B --- S_M
    C --- S_M
    D --- S_M
    E --- S_M

    %% ==============================
    %% CONEXIONES DE ENERGÍA
    %% ==============================
    C -- "Alimentación DC (3.3V / 5V / 12V)" --> A
    C -- "Alimentación DC (3.3V / 5V / 12V)" --> B
    C -- "Alimentación DC (3.3V / 5V / 12V)" --> D
    C -- "Alimentación DC (3.3V / 5V / 12V)" --> E

    %% ==============================
    %% CONEXIONES DE DATOS Y SEÑALES
    %% ==============================
    A -- "Señales <br/>de RF Crudas <br/>(Digital / IQ)" --> B
    A -- "Datos <br/>Acústicos <br/>Crudos <br/>(Digital /<br/> Audio)" --> B
    A -- "Video / Imágenes <br/>Crudas (IP / USB3)" --> B

    D -- "Datos de Posición (GNSS)" --> B
    D -- "Comando / Datos de Red (IP / WiFi)" --> E
    B -- "Datos de Pista / Clasificación (Track-Fusion)" --> E
    B -- "Control de PTZ (Comando Serial / IP)" --> A
    E -- "Interfaz de Usuario / Comando" --> B

    %% ==============================
    %% ESTILOS DE NODOS
    %% ==============================
    style C fill:#ccffcc,stroke:#333,stroke-width:2px
    style B fill:#b3ecff,stroke:#333,stroke-width:2px

    %% ==============================
    %% ESTILOS DE ENLACES
    %% ==============================
    
    %%CONEXIÓN CON EL SUBSISTEMA MECÁNICO
    linkStyle 0 stroke:brown,stroke-width:2px,stroke-dasharray:20 10
    linkStyle 1 stroke:brown,stroke-width:2px,stroke-dasharray:20 10
    linkStyle 2 stroke:brown,stroke-width:2px,stroke-dasharray:20 10
    linkStyle 3 stroke:brown,stroke-width:2px,stroke-dasharray:20 10
    linkStyle 4 stroke:brown,stroke-width:2px,stroke-dasharray:20 10
    
    %%SEÑALES DE ALIMENTACIÓN ELÉCTRICA
    linkStyle 5 stroke:green,stroke-width:2px,stroke-dasharray:5 5
    linkStyle 6 stroke:green,stroke-width:2px,stroke-dasharray:5 5
    linkStyle 7 stroke:green,stroke-width:2px,stroke-dasharray:5 5
    linkStyle 8 stroke:green,stroke-width:2px,stroke-dasharray:5 5

    %%CONEXIÓN DE DATOS Y SEÑAL
    linkStyle 9 stroke:blue,stroke-width:2px
    linkStyle 10 stroke:blue,stroke-width:2px
    linkStyle 11 stroke:blue,stroke-width:2px

    %%FLUJO DE INFORMACIÓN Y CONTROL
    linkStyle 12 stroke:blue,stroke-width:2px,stroke-dasharray:5 10
    linkStyle 13 stroke:blue,stroke-width:2px,stroke-dasharray:5 10
    linkStyle 14 stroke:blue,stroke-width:2px,stroke-dasharray:5 10
    linkStyle 15 stroke:blue,stroke-width:2px,stroke-dasharray:5 10
    linkStyle 16 stroke:blue,stroke-width:2px,stroke-dasharray:5 10

