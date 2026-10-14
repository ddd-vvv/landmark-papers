# Content
* Also known as **trans membrane potential** or **membrane voltage**.
* Is the difference in [[Electric potential|electric potential]] between the interior and the exterior of a biological [[Cell|cell]].
# Diagram
```mermaid
flowchart TD
    %% Global Styling
    classDef main fill:#1e293b,stroke:#475569,stroke-width:1.5px,color:#f8fafc;
    classDef ion fill:#1e3a8a,stroke:#3b82f6,stroke-width:1.5px,color:#eff6ff;
    classDef math fill:#581c87,stroke:#a855f7,stroke-width:1.5px,color:#faf5ff;
    classDef force fill:#78350f,stroke:#f59e0b,stroke-width:1.5px,color:#fef3c7;
    classDef state fill:#14532d,stroke:#22c55e,stroke-width:1.5px,color:#f0fdf4;
    classDef core fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#fee2e2;

    %% 1. Core Definition
    CORE{{"⚡ MEMBRANE POTENTIAL · Vm<br/>Voltage Difference Across the Cell Membrane<br/>Vm = Vin − Vout  [mV]"}}

    %% 2. Underlying Asymmetry (Chemical Gradients)
    subgraph STAGE1["1. ION DISTRIBUTION & GRADIENTS"]
        direction LR
        OUT["Extracellular (High):<br/>• Na⁺ (~145 mM)<br/>• Cl⁻ (~110 mM)"]
        IN["Intracellular (High):<br/>• K⁺ (~140 mM)<br/>• Organic Anions A⁻"]
        OUT --- IN
    end

    %% 3. Driving Forces
    subgraph STAGE2["2. ELECTROCHEMICAL DRIVING FORCE"]
        direction TB
        CHEM["Chemical Gradient<br/><i>Diffusion via concentration difference</i>"]
        ELEC["Electrical Gradient<br/><i>Electrostatic charge attraction/repulsion</i>"]
        CHEM <==>|"Dynamic Balance"| ELEC
    end

    %% 4. Governing Equations
    subgraph STAGE3["3. MATHEMATICAL MODELS"]
        direction LR
        NERNST["Nernst Equation<br/><i>Single-ion equilibrium potential (E_ion)</i>"]
        GHK["Goldman-Hodgkin-Katz (GHK)<br/><i>Considers Na⁺, K⁺, Cl⁻ permeabilities (P_ion)</i>"]
        NERNST --- GHK
    end

    %% 5. Functional States
    subgraph STAGE4["4. PHYSIOLOGICAL MANIFESTATIONS"]
        direction TB
        RMP["Resting Membrane Potential<br/><i>~ -70 mV (Dominated by K⁺ leak)</i>"]
        GRAD["Graded Potentials<br/><i>Localized, variable amplitude (EPSP/IPSP)</i>"]
        AP["Action Potentials<br/><i>All-or-none propagating impulses</i>"]
        RMP --> GRAD --> AP
    end

    %% Pipeline Connections
    STAGE1 ==>|"Establishes"| STAGE2
    STAGE2 ==>|"Determines Net Flux"| CORE
    CORE ==>|"Quantified By"| STAGE3
    STAGE3 ==>|"Governs Cellular Dynamics"| STAGE4

    %% Apply Classes
    class CORE core;
    class STAGE1,OUT,IN ion;
    class STAGE2,CHEM,ELEC force;
    class STAGE3,NERNST,GHK math;
    class STAGE4,RMP,GRAD,AP state;
```