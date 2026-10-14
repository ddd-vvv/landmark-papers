# Content
* Also known as **electrical potential difference**, **electric presure** or **electric tension**, is the difference in [[Electric potential|electric potential]] between two points.
# Diagram
```mermaid
flowchart TD
    %% Global Styling
    classDef main fill:#1e293b,stroke:#475569,stroke-width:1.5px,color:#f8fafc;
    classDef cause fill:#1e3a8a,stroke:#3b82f6,stroke-width:1.5px,color:#eff6ff;
    classDef core fill:#78350f,stroke:#f59e0b,stroke-width:2px,color:#fef3c7;
    classDef result fill:#14532d,stroke:#22c55e,stroke-width:1.5px,color:#f0fdf4;
    classDef law fill:#581c87,stroke:#a855f7,stroke-width:1.5px,color:#faf5ff;

    %% 1. Physical Origin
    subgraph STAGE1["1. PHYSICAL ORIGIN · CHARGE SEPARATION"]
        direction LR
        P1["Positive Potential (+)<br/><i>High Electric Potential Energy</i>"]
        P2["Negative Potential (−)<br/><i>Low Electric Potential Energy</i>"]
        P1 -.->|"Electric Field (E)"| P2
    end

    %% 2. Core Definition
    V{{"⚡ VOLTAGE · V<br/>Electric Potential Difference<br/>ΔV = W / q  [Joules / Coulomb = Volts]"}}

    %% 3. Driving Mechanism
    subgraph STAGE2["2. ACTION · DRIVING FORCE"]
        direction TB
        EMF["Electromotive Force (EMF)<br/><i>Energy supplied per unit charge</i>"]
        PRESS["Electric Pressure<br/><i>Pushes charges through medium</i>"]
        EMF ==> PRESS
    end

    %% 4. Governing Principles (Ohm's Law)
    subgraph STAGE3["3. CIRCUIT RELATIONSHIPS · OHM'S LAW"]
        direction LR
        I["Current (I)<br/><i>Flow Rate (Amperes)</i>"]
        R["Resistance (R)<br/><i>Opposition (Ohms)</i>"]
        FORMULA["V = I · R<br/>I = V / R"]
        I --- FORMULA --- R
    end

    %% 5. System Output
    WORK[/"💡 Work Done & Power Dissipation<br/>P = V · I  [Watts]"/]

    %% Flow Pipeline
    STAGE1 ==>|"Creates Potential Gradient"| V
    V ==>|"Acts As"| STAGE2
    STAGE2 ==>|"Drives Free Charges Across Load"| STAGE3
    STAGE3 ==>|"Delivers Energy to Circuit"| WORK

    %% Apply Classes
    class P1,P2 cause;
    class V core;
    class EMF,PRESS main;
    class I,R,FORMULA law;
    class WORK result;
```