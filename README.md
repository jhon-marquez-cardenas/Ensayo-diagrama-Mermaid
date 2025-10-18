# Ensayo-diagrama-Mermaid

graph TD
    %% ==============================
    %% MÓDULOS PRINCIPALES
    %% ==============================
    subgraph ST_DFS_CA["ST-DFS-CA: Arquitectura Táctica de Fusión de Sensores"]
        A["Módulo de Detección / Sensores"]
        B["Módulo de Procesamiento Central (IA / ML)"]
        C["Módulo de Alimentación Eléctrica"]
        D["Módulo de Comunicaciones / GPS"]
        E["Módulo de Interacción / Visualización"]
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
    A -- "Señales de RF Crudas (Digital / IQ)" --> B
    A -- "Datos Acústicos Crudos (Digital / Audio)" --> B
    A -- "Video / Imágenes Crudas (IP / USB3)" --> B

    D -- "Datos de Posición (GNSS)" --> B
    D -- "Comando / Datos de Red (IP / WiFi)" --> E
    B -- "Datos de Pista / Clasificación (Track-Fusion)" --> E
    B -- "Control de PTZ (Comando Serial / IP)" --> A
    E -- "Interfaz de Usuario / Comando" --> B

    %% ==============================
    %% ESTILOS DE NODOS
    %% ==============================
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#ccf,stroke:#333,stroke-width:2px

    %% ==============================
    %% ESTILOS DE ENLACES
    %% ==============================
    linkStyle 0 stroke:#006400,stroke-width:2px,color:#006400
    linkStyle 1 stroke:#006400,stroke-width:2px,color:#006400
    linkStyle 2 stroke:#006400,stroke-width:2px,color:#006400
    linkStyle 3 stroke:#006400,stroke-width:2px,color:#006400

    linkStyle 4 stroke:blue,stroke-width:2px,stroke-dasharray:5 5
    linkStyle 5 stroke:blue,stroke-width:2px,stroke-dasharray:5 5
    linkStyle 6 stroke:blue,stroke-width:2px,stroke-dasharray:5 5

    linkStyle 7 stroke:red,stroke-width:2px
    linkStyle 8 stroke:red,stroke-width:2px

    linkStyle 9 stroke:purple,stroke-width:2px
    linkStyle 10 stroke:purple,stroke-width:2px
    linkStyle 11 stroke:purple,stroke-width:2px

