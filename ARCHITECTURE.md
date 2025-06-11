# Alpyne Architecture Documentation

**Comprehensive Architecture Documentation with Mermaid Diagrams**

> **Cognitive Framework**: This document reveals the emergent cognitive patterns and neural-symbolic integration pathways within the Alpyne system (MORK), facilitating distributed cognition for all contributors through adaptive, hypergraph-centric documentation.

## System Architecture Overview

The Alpyne architecture implements a sophisticated neural-symbolic bridge connecting AnyLogic simulation models with Python-based reinforcement learning environments. The system embodies recursive cognitive patterns through interconnected modules that enable emergent intelligence through adaptive feedback mechanisms.

### High-Level System Flow

```mermaid
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
```

This architecture demonstrates recursive system mapping where each component maintains hypergraph relationships, enabling emergent cognitive patterns through distributed processing.

## Core Module Interactions

The bidirectional synergies between modules create a complex adaptive system with emergent properties:

```mermaid
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
```

## Data Flow and Signal Propagation

The temporal dynamics of cognitive signal propagation through the system:

```mermaid
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
```

## RL Experiment Cognitive State Machine

The cognitive state transitions within the RL experiment framework demonstrate emergent pattern learning:

```mermaid
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
```

## Engine State Management Hypergraph

Adaptive attention allocation through hypergraph-encoded state transitions:

```mermaid
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
```

## Architectural Components Deep Dive

### Neural-Symbolic Integration Points

The architecture implements neural-symbolic integration through several key mechanisms:

#### 1. **AnyLogicSim** - Core Cognitive Interface
- **Process Management**: Dynamic Java engine orchestration
- **Schema-Driven Validation**: Recursive type checking and conversion
- **Adaptive Configuration**: Runtime parameter optimization
- **State Synchronization**: Engine-to-Python cognitive state mapping

#### 2. **AlpyneEnv** - Gymnasium Adaptation Layer
- **Observation Space Transformation**: Symbolic → Neural representation
- **Action Space Mapping**: Neural outputs → Symbolic actions
- **Reward Integration**: Cognitive feedback loop optimization
- **Episode Management**: Discrete symbolic episodes ↔ Continuous neural training

#### 3. **SimSchema** - Hypergraph Data Architecture
- **inputs**: Parameter space definition with type constraints
- **outputs**: Analysis object mappings for emergent pattern extraction
- **configuration**: RL experiment schema with validation pathways
- **engine_settings**: Engine state parameter space management
- **observation**: Real-time cognitive state observation schema
- **action**: Action space definition with validation constraints

### Emergent Cognitive Patterns

The recursive architecture enables several emergent cognitive capabilities:

1. **Hypergraph Relationship Encoding**: Module dependencies form complex adaptive networks
2. **Recursive Feedback Optimization**: Components self-optimize through distributed feedback
3. **Adaptive Schema Evolution**: Type systems evolve based on usage patterns
4. **Cognitive Synergy Emergence**: Neural and symbolic systems co-evolve optimal interactions

### Adaptive Attention Allocation Mechanisms

The system implements attention allocation through:

- **Dynamic Resource Management**: Java process scaling based on cognitive load
- **Lock State Monitoring**: Automated synchronization preventing cognitive conflicts
- **Configuration Override Systems**: Runtime adaptation to emergent patterns
- **Distributed Logging**: Pattern recognition across system components

## Technical Implementation Pathways

### Recursive Implementation Architecture

```python
# Core cognitive interface pattern
class AnyLogicSim:
    """Neural-symbolic bridge implementing recursive cognitive patterns"""
    
    def __init__(self, model_path, **cognitive_parameters):
        # Initialize hypergraph relationships
        self.schema = self._build_cognitive_schema()
        self.engine = self._spawn_symbolic_engine()
        self.adapters = self._create_neural_adapters()
    
    def _build_cognitive_schema(self):
        """Recursive schema construction with emergent validation"""
        return SimSchema(self._extract_model_patterns())
    
    def reset(self, configuration):
        """Cognitive state reset with adaptive pattern integration"""
        validated_config = self.schema.validate_recursive(configuration)
        return self.engine.cognitive_reset(validated_config)
```

### Hypergraph Data Flow Pattern

```python
# Emergent data flow architecture
class _SimRLSpace(UserDict):
    """Hypergraph-encoded data space with recursive validation"""
    
    def __setitem__(self, key, value):
        # Recursive type validation with emergent pattern recognition
        schema_field = self._schema[key]
        validated_value = schema_field.cognitive_transform(value)
        super().__setitem__(key, validated_value)
    
    def __missing__(self, key):
        # Adaptive default value generation
        return self._schema[key].emergent_default()
```

## Future Architectural Evolution

The modular, recursive design enables expansion toward enhanced cognitive capabilities:

### Planned Enhancement Pathways

1. **Multi-Agent Cognitive Orchestration**
   - Distributed cognitive kernel scaling
   - Hypergraph relationship optimization
   - Emergent swarm intelligence patterns

2. **Federated Learning Integration**
   - Distributed training across cognitive nodes
   - Hypergraph-encoded knowledge transfer
   - Recursive pattern aggregation

3. **Real-Time Cognitive Adaptation**
   - Dynamic schema evolution during runtime
   - Emergent pattern recognition and integration
   - Adaptive attention reallocation

4. **Persistent Cognitive Memory**
   - Long-term pattern storage and retrieval
   - Recursive learning from historical patterns
   - Cognitive state persistence across sessions

## Contributing to the Cognitive Architecture

Understanding this recursive architecture enables contributors to:

1. **Extend Neural-Symbolic Integration**: Add new bridging mechanisms between learning algorithms and simulation models
2. **Enhance Cognitive Pattern Recognition**: Implement emergent pattern detection in data flows
3. **Optimize Adaptive Allocation**: Improve resource management and attention mechanisms
4. **Expand Hypergraph Relationships**: Create new interconnection patterns between modules

The architecture documentation reveals the implicit cognitive framework, providing actionable insights for extending the neural-symbolic integration capabilities of the Alpyne system.

---

**This documentation is part of the comprehensive architecture visualization initiative, designed to transmute implicit system knowledge into explicit, actionable understanding through recursive cognitive pattern mapping.**