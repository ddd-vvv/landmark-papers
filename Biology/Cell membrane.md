# Content
* Also known as the **plasma membrane** or **cytoplasmic membrane**.
* Is a [[Semipermeable biological membrane|semipermeable biological membrane]] that separates and protects the interior of a [[Cell|cell]] from the outside enviroment.
# Diagram
```mermaid
flowchart TD
    %% Global Styling
    classDef lipid fill:#1e293b,stroke:#3b82f6,stroke-width:1.5px,color:#f8fafc;
    classDef protein fill:#581c87,stroke:#a855f7,stroke-width:1.5px,color:#faf5ff;
    classDef carb fill:#78350f,stroke:#f59e0b,stroke-width:1.5px,color:#fef3c7;
    classDef transport fill:#0f766e,stroke:#14b8a6,stroke-width:1.5px,color:#f0fdfa;
    classDef core fill:#1e1e2e,stroke:#64748b,stroke-width:2px,color:#ffffff;
    classDef barrier fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#fee2e2;

    %% 1. Core Model
    MODEL{{"🌊 FLUID MOSAIC MODEL<br/><i>Dynamic Amphipathic Bilayer (~7-10 nm)</i>"}}

    %% 2. Structural Lipid Matrix
    subgraph STAGE1["1. LIPID BILAYER MATRIX · PERMEABILITY BARRIER"]
        direction TB
        subgraph PL["Phospholipids"]
            direction LR
            HEAD["Polar Heads<br/><i>Hydrophilic (Glycerol + Phosphate)</i>"]
            TAIL["Nonpolar Tails<br/><i>Hydrophobic (Fatty Acid Chains)</i>"]
            HEAD --- TAIL
        end
        CHOL["Cholesterol Modules<br/><i>Membrane Fluidity Buffer (Rigidity vs Flexibility)</i>"]
        PL --- CHOL
    end

    %% 3. Protein Components
    subgraph STAGE2["2. MEMBRANE PROTEINS · FUNCTIONAL MACHINERY"]
        direction LR
        INT["Integral / Transmembrane<br/><i>Channels, Carriers, Receptors</i>"]
        PER["Peripheral Proteins<br/><i>Signaling & Cytoskeletal Anchors</i>"]
        INT --- PER
    end

    %% 4. Glycocalyx & Carbohydrates
    subgraph STAGE3["3. GLYCOCALYX · EXTERNAL SURFACE COAT"]
        direction LR
        GLY_L["Glycolipids<br/><i>Lipid-anchored Sugars</i>"]
        GLY_P["Glycoproteins<br/><i>Protein-anchored Sugars</i>"]
        GLY_L --- GLY_P
    end

    %% 5. Transport Selectivity Layer
    subgraph STAGE4["4. SELECTIVE TRANSPORT MECHANISMS"]
        direction TB
        DIFF["Passive Transport<br/><i>Simple Diffusion (O₂, CO₂) · Osmosis (H₂O via Aquaporins)</i>"]
        FAC["Facilitated & Active Transport<br/><i>Voltage/Ligand Channels · ATP Pumps (Na⁺/K⁺-ATPase)</i>"]
        DIFF --- FAC
    end

    %% 6. Physiological Role
    ROLE[/"🛡️ CORE CELLULAR FUNCTIONS<br/>Homeostasis · Cell Recognition & Signaling · Electrochemical Gradient Formation"/]

    %% Main Pipeline Flow
    MODEL ==>|"Constitutes"| STAGE1
    STAGE1 ==>|"Hosts Embedded Elements"| STAGE2
    STAGE2 ==>|"Extends Outer Recognition Domain"| STAGE3
    STAGE1 & STAGE2 ==>|"Governs"| STAGE4
    STAGE4 ==>|"Maintains Cellular Life"| ROLE

    %% Apply Classes
    class MODEL core;
    class STAGE1,HEAD,TAIL,CHOL lipid;
    class STAGE2,INT,PER protein;
    class STAGE3,GLY_L,GLY_P carb;
    class STAGE4,DIFF,FAC transport;
    class ROLE barrier;
```