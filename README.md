# KAMP4HMI

KAMP4HMI extends KAMP for human-machine-interface (HMI) models. It provides EMF models, generated editors, and modification marks for HMI interaction flows that are related to IEC software artefacts.

## Installation

Install KAMP4HMI from the KAMP update-site page:

```text
https://kamp-research.github.io/KAMP/kamp4hmi/
```

For a complete setup, use the composite update site instead:

```text
https://kamp-research.github.io/KAMP/all/
```

In Eclipse, open `Help > Install New Software...`, paste the update-site URL into `Work with`, select the KAMP4HMI feature, and finish the wizard. Restart Eclipse after installation.

## Dependencies

KAMP4HMI is part of the KAMP extension ecosystem and depends on:

- KAMP core for base change-propagation and modification mark infrastructure.
- KAMP4IEC model concepts, because HMI elements refer to IEC repository artefacts such as function blocks and methods.
- Eclipse Modeling Framework (EMF), EMF.Edit, and generated EMF editor support.
- Palladio build dependencies from the Palladio 5.2.1 update sites.
- Eclipse Platform/PDE dependencies from the Eclipse 2023-03 target.

KAMP4HMI and KAMP4IEC have circular model dependencies and should be installed from a consistent KAMP update-site set, preferably through KAMP-All.

## Domain

The HMI domain represents user-facing interaction flows around automation systems. It captures actor and system steps, modes, conditions, and control-flow structures such as branches and loops. These models help analyse the consequences of changes in HMI behaviour or related IEC software elements.

## Important Models

- `Kamp4hmiModel.ecore`: HMI process model with `Step`, `ActorStep`, `SystemStep`, `Mode`, `Repository`, `If`, `For`, `HMIElement`, and `Condition`.
- `HMIModificationmarks.ecore`: HMI modification marks such as `HMISeedModifications`, `HMIChangePropagationDueToSoftwareDependency`, `HMIModifyStep`, `HMIModifyActorStep`, and `HMIModifySystemStep`.

## Usage

Use the generated EMF editors to create HMI repositories and interaction flows. Link system steps and modes to the IEC artefacts they affect. When HMI behaviour or linked software changes, represent the initial changes as HMI seed modification marks and use the KAMP workflow to propagate the effects.

In practice, KAMP4HMI should be installed together with KAMP4IEC or through the KAMP-All update site, because IEC concepts are part of the HMI modelling context.
