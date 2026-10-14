# Content
* A long slender [[Cellular extensions| projection]] of a nerve [[Cell | cell]] or [[Neuron | neuron]] found in most [[Animal| animals]] that typically conducts eletrectrical impulses known as [[Action potentials | action potentials]] away from the [[Soma | nerve cell body]].
* Its function is to transmit information to different neurons, muscles and glands.
## Diagram
```mermaid
flowchart TD
    %% Global Settings
    classDef main fill:#1e293b,stroke:#475569,stroke-width:1.5px,color:#f8fafc;
    classDef trigger fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#fee2e2;
    classDef fiber fill:#0f172a,stroke:#3b82f6,stroke-width:1.5px,color:#f8fafc;
    classDef gap fill:#14532d,stroke:#22c55e,stroke-width:1.5px,color:#f0fdf4;
    classDef term fill:#581c87,stroke:#a855f7,stroke-width:1.5px,color:#faf5ff;
    classDef target fill:#0369a1,stroke:#38bdf8,stroke-width:1.5px,color:#f0f9ff;

    %% 1. Input Stage
    subgraph STAGE1["1. INPUT ZONE · SOMA"]
        direction LR
        DEN["Dendrites<br/>(Inputs)"] --> SOMA["Cell Body & Nucleus<br/>(Integration)"]
    end

    %% 2. Trigger Point
    AH{{"⚡ Axon Hillock<br/>(Action Potential Generation)"}}

    %% 3. Conduction Pathway
    subgraph STAGE2["2. CONDUCTION ZONE · AXON"]
        direction TB
        M1["Myelin Segment (Schwann Cell)"]
        N1(("Node of Ranvier"))
        M2["Myelin Segment (Schwann Cell)"]
        N2(("Node of Ranvier"))
        
        M1 ==>|"Depolarization"| N1
        N1 ==>|"Saltatory Jump"| M2
        M2 ==>|"Depolarization"| N2
    end

    %% 4. Output Stage
    subgraph STAGE3["3. OUTPUT ZONE · SYNAPSE"]
        direction TB
        TERM["Axon Terminal<br/>(Synaptic Boutons)"]
        VES["Synaptic Vesicles<br/>(Neurotransmitters)"]
        TERM --- VES
    end

    %% 5. Effector
    TARGET[/"🎯 Target Cell (Neuron / Muscle / Gland)"/]

    %% Pipeline Connections
    SOMA ==>|"Graded Potentials"| AH
    AH ==>|"Threshold Reached (-55mV)"| M1
    N2 ==>|"Axonal Transport"| TERM
    TERM ==>|"Exocytosis across Cleft"| TARGET

    %% Style Applications
    class SOMA,DEN,M1,M2 main;
    class AH trigger;
    class N1,N2 gap;
    class TERM,VES term;
    class TARGET target;
```