# Content
* Also known as a **nerve impulse** or "**spike**" when in a [[Neuron|neuron]] is a series of quick changes in [[Voltage|voltage]] across a [[Cell membrane|cell membrane]].
* This occurs when the [[Membrane potential|membrane potential]] of a specific [[Cell|cell]] rapidly rises and falls.
## Diagram
```mermaid
flowchart TD
    %% Global Styling
    classDef rest fill:#1e293b,stroke:#475569,stroke-width:1.5px,color:#f8fafc;
    classDef thresh fill:#78350f,stroke:#f59e0b,stroke-width:2px,color:#fef3c7;
    classDef depol fill:#1e3a8a,stroke:#3b82f6,stroke-width:1.5px,color:#eff6ff;
    classDef peak fill:#7f1d1d,stroke:#ef4444,stroke-width:2px,color:#fee2e2;
    classDef repol fill:#581c87,stroke:#a855f7,stroke-width:1.5px,color:#faf5ff;
    classDef hyper fill:#14532d,stroke:#22c55e,stroke-width:1.5px,color:#f0fdf4;

    %% 1. Baseline State
    subgraph STAGE1["1. RESTING MEMBRANE POTENTIAL · -70 mV"]
        direction LR
        PUMP["Na⁺/K⁺-ATPase Pump<br/><i>3 Na⁺ Out / 2 K⁺ In (ATP)</i>"]
        LEAK["K⁺ Leak Channels Open<br/><i>High K⁺ permeability</i>"]
        PUMP --- LEAK
    end

    %% 2. Trigger Point
    THRESH{{"⚡ THRESHOLD REACHED · -55 mV<br/>All-or-None Response Triggered"}}

    %% 3. Depolarization Phase
    subgraph STAGE2["2. DEPOLARIZATION (RISING PHASE) · -55 mV to +30 mV"]
        direction TB
        NA_OPEN["Voltage-Gated Na⁺ Channels Open"]
        NA_INFLUX["Massive Rapid Na⁺ Influx into Axon"]
        NA_OPEN ==> NA_INFLUX
    end

    %% 4. Peak & Reversal
    PEAK{{"🔺 PEAK POTENTIAL · +30 to +40 mV<br/>Na⁺ Inactivation Gates Close · Voltage-Gated K⁺ Channels Open"}}

    %% 5. Repolarization Phase
    subgraph STAGE3["3. REPOLARIZATION (FALLING PHASE) · +30 mV to -70 mV"]
        direction TB
        K_OPEN["Voltage-Gated K⁺ Channels Fully Activated"]
        K_EFFLUX["Rapid K⁺ Efflux out of Axon"]
        K_OPEN ==> K_EFFLUX
    end

    %% 6. Hyperpolarization & Reset
    subgraph STAGE4["4. HYPERPOLARIZATION & REFRACTORY PERIOD · -75 to -90 mV"]
        direction LR
        UNDERSHOOT["Undershoot (K⁺ Channels Slow to Close)"]
        REFRACT["Absolute & Relative Refractory Period"]
        UNDERSHOOT --- REFRACT
    end

    %% Final Recovery State
    RECOVER[/"🔄 Restoration to Resting Potential (-70 mV)<br/>Na⁺/K⁺ Pump restores electrochemical gradients"/]

    %% Main Pipeline Flow
    STAGE1 ==>|"Excitatory Graded Potentials (EPSPs)"| THRESH
    THRESH ==>|"Voltage-Gated Na⁺ Activation"| STAGE2
    STAGE2 ==>|"Overshoot Reached"| PEAK
    PEAK ==>|"Inactivation of Na⁺ / Activation of K⁺"| STAGE3
    STAGE3 ==>|"Delayed K⁺ Channel Closure"| STAGE4
    STAGE4 ==>|"Ion Rebalancing (ATP Consumed)"| RECOVER
    RECOVER -.->|"Ready for Next Impulse"| STAGE1

    %% Class Attachments
    class STAGE1,PUMP,LEAK rest;
    class THRESH thresh;
    class STAGE2,NA_OPEN,NA_INFLUX depol;
    class PEAK peak;
    class STAGE3,K_OPEN,K_EFFLUX repol;
    class STAGE4,UNDERSHOOT,REFRACT hyper;
    class RECOVER rest;
```