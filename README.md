# Ensayo-diagrama-Mermaid

graph TD
    %% Módulos Principales
    subgraph ST-DFS-CA: Arquitectura Táctica de Fusión de Sensores
        A[Módulo de Detección/Sensores]
        B[Módulo de Procesamiento Central (IA/ML)]
        C[Módulo de Alimentación Eléctrica]
        D[Módulo de Comunicaciones/GPS]
        E[Módulo de Interacción/Visualización]
    end

    %% Módulos de Hardware Externo/Periféricos
    subgraph Subsistema Mecánico (Alojamiento Táctico)
        A --- S_M[Alojamiento (Maleta Rugerizada/Trípode)]
        B --- S_M
        C --- S_M
        D --- S_M
        E --- S_M
    end

    %% Conexiones de Energía (Alimentación Eléctrica)
    C -- Alimentación DC (3.3V/5V/12V) --> A
    C -- Alimentación DC (3.3V/5V/12V) --> B
    C -- Alimentación DC (3.3V/5V/12V) --> D
    C -- Alimentación DC (3.3V/5V/12V) --> E

    %% Conexiones de Datos y Señales
    
    %% Del Sensor al Procesamiento Central
    A -- Señales de RF Crudas (Digital/IQ) --> B
    A -- Datos Acústicos Crudos (Digital/Audio) --> B
    A -- Video/Imágenes Crudas (IP/USB3) --> B

    %% Flujos de Información y Control
    D -- Datos de Posición (GNSS) --> B
    D -- Comando/Datos de Red (IP/WiFi) --> E
    B -- Datos de Pista/Clasificación (Track-Fusion) --> E
    B -- Control de PTZ (Comando Serial/IP) --> A
    E -- Interfaz de Usuario/Comando --> B

    %% Leyenda de Enlaces
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px

    %% Definición de Estilos (para mejor discriminación)
    linkStyle 0 stroke:#006400,stroke-width:2px,color:#006400; %% C->A (Alimentación)
    linkStyle 1 stroke:#006400,stroke-width:2px,color:#006400; %% C->B (Alimentación)
    linkStyle 2 stroke:#006400,stroke-width:2px,color:#006400; %% C->D (Alimentación)
    linkStyle 3 stroke:#006400,stroke-width:2px,color:#006400; %% C->E (Alimentación)
    
    linkStyle 4 stroke:blue,stroke-width:2px,stroke-dasharray: 5 5; %% A->B (RF Cruda)
    linkStyle 5 stroke:blue,stroke-width:2px,stroke-dasharray: 5 5; %% A->B (Acústica Cruda)
    linkStyle 6 stroke:blue,stroke-width:2px,stroke-dasharray: 5 5; %% A->B (Video Crudo)

    linkStyle 7 stroke:red,stroke-width:2px; %% D->B (GNSS)
    linkStyle 8 stroke:red,stroke-width:2px; %% D->E (Red)

    linkStyle 9 stroke:purple,stroke-width:2px; %% B->E (Track/Clasificación)
    linkStyle 10 stroke:purple,stroke-width:2px; %% B->A (Control PTZ)
    linkStyle 11 stroke:purple,stroke-width:2px; %% E->B (Comando Usuario)

    %% Leyenda de Módulos
    A -- Módulo de Sensores (SDR, Micrófonos, Cámara)
    B -- Procesador (Jetson/SBC) con Lógica IA/Fusión (MATLAB/Python)
    C -- Batería y Gestión de Energía
    D -- Comunicaciones (WiFi, GPS)
    E -- Interfaz (Pantalla Táctil)
