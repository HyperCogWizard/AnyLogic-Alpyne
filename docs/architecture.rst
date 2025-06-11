Architecture Overview with Mermaid Diagrams
============================================

.. epigraph::
    **Summary:** Comprehensive architectural documentation revealing the recursive cognitive patterns and neural-symbolic integration pathways within the Alpyne system (MORK). This document transmutes implicit system architecture into explicit, actionable knowledge through hypergraph-centric visualizations.

System Architecture Principles
------------------------------

The Alpyne architecture embodies emergent cognitive patterns through a distributed system of interconnected modules that facilitate neural-symbolic integration between AnyLogic simulation models and Python-based reinforcement learning environments. The system implements recursive mapping pathways and adaptive attention allocation mechanisms to optimize cognitive synergy.

High-Level System Overview
---------------------------

The following diagram illustrates the principal architectural flows and cognitive kernel interactions within the Alpyne ecosystem:

.. mermaid::

   graph TD
       A[Python RL Environment] -->|Configuration| B[AnyLogicSim]
       B -->|Process Management| C[Java AnyLogic Engine]
       C -->|Model Execution| D[Simulation Model]
       D -->|Observation Data| C
       C -->|Status/Results| B
       B -->|SimStatus| E[AlpyneEnv Wrapper]
       E -->|Gym Interface| F[RL Training Algorithms]
       F -->|Actions| E
       E -->|Action Translation| B
       
       B -.->|Schema Validation| G[SimSchema]
       B -.->|Data Structures| H[SimStatus/SimConfiguration]
       B -.->|Engine State| I[EngineStatus]
       
       J[Model Export] -->|RL Experiment| D
       K[Training Data] -->|Outputs| L[Analysis & Visualization]
       
       subgraph "Cognitive Kernel"
           G
           H
           I
       end
       
       subgraph "Neural-Symbolic Bridge"
           B
           E
       end
       
       subgraph "Simulation Engine"
           C
           D
       end

This architecture demonstrates the recursive system mapping where each component maintains hypergraph relationships with others, enabling emergent cognitive patterns to emerge through distributed processing and adaptive feedback mechanisms.

Module Interaction Patterns
----------------------------

The bidirectional synergies between core modules create a complex adaptive system. The following diagram reveals the interconnection topology:

.. mermaid::

   graph LR
       SimCore[alpyne.sim.AnyLogicSim] <-->|Process Control| Engine[Java Engine]
       SimCore <-->|Data Validation| Schema[alpyne.data.SimSchema]
       SimCore <-->|Status Updates| Status[alpyne.data.SimStatus]
       
       Env[alpyne.env.AlpyneEnv] <-->|Interface Bridge| SimCore
       Env <-->|Action Mapping| Actions[alpyne.data.SimAction] 
       Env <-->|Observation Processing| Obs[alpyne.data.SimObservation]
       
       Schema -->|Type Validation| FieldData[alpyne.data.FieldData]
       Schema -->|Configuration Schema| Config[alpyne.data.SimConfiguration]
       
       Utils[alpyne.utils] -->|Model Resolution| SimCore
       Utils -->|JSON Encoding/Decoding| Schema
       
       Constants[alpyne.constants] -->|Engine States| SimCore
       Constants -->|Type Mappings| Schema
       
       Outputs[alpyne.outputs] -->|Time Units & Values| SimCore
       Errors[alpyne.errors] -->|Exception Handling| SimCore
       
       subgraph "Data Flow Cognitive Kernel"
           Schema
           Status
           Actions
           Obs
           Config
           FieldData
       end
       
       subgraph "Interface Adaptation Layer"
           Env
           SimCore
       end
       
       subgraph "Support Systems"
           Utils
           Constants
           Outputs
           Errors
       end

This interaction pattern reveals the emergent properties arising from recursive module dependencies and the adaptive attention allocation mechanisms that optimize system performance.

Data Flow and Signal Propagation
---------------------------------

The following sequence diagram illustrates the temporal dynamics of data and signal propagation through the cognitive architecture:

.. mermaid::

   sequenceDiagram
       participant RL as RL Algorithm
       participant Env as AlpyneEnv
       participant Sim as AnyLogicSim
       participant Engine as Java Engine
       participant Model as AnyLogic Model
       
       Note over RL,Model: Initialization Phase - Recursive System Mapping
       RL->>Env: create environment
       Env->>Sim: initialize(model_path, config)
       Sim->>Engine: start Java process
       Engine->>Model: load simulation model
       Model->>Engine: schema definition
       Engine->>Sim: model schema
       Sim->>Env: schema validation complete
       
       Note over RL,Model: Training Episode - Cognitive Pattern Emergence
       RL->>Env: reset(config)
       Env->>Sim: reset(SimConfiguration)
       Sim->>Engine: apply configuration
       Engine->>Model: initialize model state
       Model->>Engine: initial observation
       Engine->>Sim: SimStatus with observation
       Sim->>Env: transform to gym observation
       Env->>RL: observation, info
       
       loop Adaptive Action-Observation Cycle
           RL->>Env: step(action)
           Env->>Sim: action(SimAction)
           Sim->>Engine: submit action
           Engine->>Model: apply action to model
           Model->>Engine: updated state
           Engine->>Sim: SimStatus with new observation
           Sim->>Env: transform observation + reward calculation
           Env->>RL: observation, reward, terminated, truncated, info
       end
       
       Note over RL,Model: Terminal State - Pattern Integration
       RL->>Env: close()
       Env->>Sim: cleanup()
       Sim->>Engine: terminate process
       Engine->>Model: save final state
       Model->>Engine: cleanup complete

This sequence reveals the recursive implementation pathways and how cognitive synergy optimizations occur through adaptive feedback loops between the neural (RL algorithm) and symbolic (simulation model) components.

RL Experiment Workflow Architecture
-----------------------------------

The following state diagram shows the cognitive state transitions within the RL experiment framework:

.. mermaid::

   stateDiagram-v2
       [*] --> ModelDefinition: Initialize MORK System
       
       ModelDefinition --> ConfigurationSetup: Define RL Experiment
       ConfigurationSetup --> ObservationSpace: Schema Validation
       ObservationSpace --> ActionSpace: Type Mapping
       ActionSpace --> ModelExport: Hypergraph Encoding
       
       ModelExport --> PythonIntegration: Neural-Symbolic Bridge
       PythonIntegration --> EnvironmentWrapper: Cognitive Adaptation
       
       EnvironmentWrapper --> TrainingLoop: Emergent Pattern Learning
       
       state TrainingLoop {
           [*] --> Reset
           Reset --> Observe: Initial State
           Observe --> Decide: Cognitive Processing
           Decide --> Act: Action Selection
           Act --> Update: State Transition
           Update --> Observe: Recursive Feedback
           Update --> [*]: Episode Terminal
       }
       
       TrainingLoop --> PolicyOptimization: Convergence Detection
       PolicyOptimization --> Deployment: Model Ready
       
       Deployment --> ProductionUse: Cognitive Synergy Achieved
       ProductionUse --> [*]: System Integration Complete

This architecture demonstrates the emergent cognitive patterns that arise from the recursive interaction between symbolic reasoning (AnyLogic simulation) and neural learning (RL algorithms).

Engine State Management and Hypergraph Patterns
------------------------------------------------

The engine state management system implements adaptive attention allocation through hypergraph-encoded state transitions:

.. mermaid::

   graph TD
       A[IDLE] -->|initialize| B[PAUSED]
       B -->|run| C[RUNNING]
       C -->|pause| B
       C -->|step| D[STEP_PHASE]
       D -->|continue| C
       B -->|step| D
       B -->|finish| E[FINISHED]
       C -->|finish| E
       D -->|finish| E
       E -->|reset| A
       
       F[ERROR] -->|reset| A
       A -->|error| F
       B -->|error| F
       C -->|error| F
       D -->|error| F
       
       subgraph "Cognitive State Space"
           A
           B
           C
           D
           E
       end
       
       subgraph "Error Recovery Pattern"
           F
       end
       
       G[SimStatus Monitor] -.->|observe| A
       G -.->|observe| B
       G -.->|observe| C
       G -.->|observe| D
       G -.->|observe| E
       G -.->|observe| F
       
       H[Action Queue] -.->|influence| B
       H -.->|influence| C
       H -.->|influence| D

Technical Implementation Details
--------------------------------

Schema-Driven Cognitive Architecture
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The schema system implements recursive type validation and hypergraph pattern encoding through the ``SimSchema`` class, which maintains distributed cognition across the following data structures:

- **inputs**: Model parameter definitions with type constraints
- **outputs**: Analysis object mappings for result extraction  
- **configuration**: RL experiment configuration field validation
- **engine_settings**: Engine state parameter management
- **observation**: Real-time model state observation schema
- **action**: Allowable action space definition and validation

Each schema component implements recursive validation pathways that ensure neural-symbolic integration maintains type safety while enabling emergent pattern recognition.

Adaptive Attention Allocation Mechanisms
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``AnyLogicSim`` class implements adaptive attention allocation through:

1. **Process Management**: Dynamic resource allocation for Java engine processes
2. **Lock State Monitoring**: Automated engine state synchronization 
3. **Configuration Override Systems**: Runtime parameter adaptation
4. **Logging Integration**: Distributed diagnostic pattern recognition

Neural-Symbolic Integration Points
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``AlpyneEnv`` gymnasium wrapper creates neural-symbolic integration through:

- **Observation Space Transformation**: Converting symbolic model states to neural network inputs
- **Action Space Mapping**: Translating neural network outputs to symbolic model actions  
- **Reward Function Integration**: Bridging symbolic model metrics with neural learning objectives
- **Episode Management**: Coordinating discrete symbolic episodes with continuous neural training

Emergent Cognitive Patterns
----------------------------

The recursive architecture enables several emergent cognitive patterns:

1. **Hypergraph Relationship Encoding**: Module dependencies form complex adaptive networks
2. **Recursive Feedback Optimization**: Each component optimizes based on distributed system feedback
3. **Adaptive Schema Evolution**: Type systems evolve based on usage patterns
4. **Cognitive Synergy Emergence**: Neural and symbolic components co-evolve optimal interaction patterns

Future Architecture Evolution
-----------------------------

The modular, recursive design enables expansion paths for enhanced cognitive capabilities:

- **Multi-Agent Orchestration**: Distributed cognitive kernel scaling
- **Federated Learning Integration**: Hypergraph-distributed training patterns  
- **Real-Time Adaptation**: Dynamic schema evolution based on emergent patterns
- **Cognitive State Persistence**: Long-term memory integration for recursive learning

This architecture documentation reveals the implicit cognitive framework underlying the Alpyne system, providing actionable insights for contributors to understand and extend the neural-symbolic integration capabilities.
