# Open Autonomy Safety Case (OASC) - SACM Representation

This repository contains a SACM 2.2 (Structured Assurance Case Metamodel) representation of the Open Autonomy Safety Case.

## Overview

The Open Autonomy Safety Case is a template for demonstrating the safety of autonomous vehicle deployments. It is structured around three main pillars:

1. **"Live It Right"** - Organization is Trustworthy (Goal 3)
2. **"Build It Right"** - Vehicle is Safe to Operate (Goal 4)
3. **"Operate It Right"** - We Operate the Vehicle Safely (Goal 5)

These three pillars support the top-level claim through an "Appeal to Positive Trust Balance" strategy.

## SACM Representation

The safety case is expressed in SACM 2.2 XML format. SACM (Structured Assurance Case Metamodel) is an OMG standard for representing assurance cases in a machine-readable format.

### GSN to SACM Mapping

| GSN Element | SACM Element | Description |
|-------------|--------------|-------------|
| Goal | `Claim` | A proposition to be demonstrated |
| Strategy | `ArgumentReasoning` + `AssertedInference` | Reasoning that links claims |
| Context | `ArtifactReference` + `AssertedContext` | Contextual information |
| Solution/Evidence | `ArtifactReference` + `AssertedEvidence` | Evidence supporting claims |

### File Structure

```
open-autonomy-safety-case.sacm.xml
├── terminologyPackage      # Referenced standards definitions
├── artifactPackage         # Evidence and context artifacts
├── argumentPackage (Main)  # Top-level structure (Goals 1-5)
├── argumentPackage (OrgTrust)     # "Live It Right" (Goal 3 branch)
├── argumentPackage (VehicleSafety) # "Build It Right" (Goal 4 branch)
└── argumentPackage (OpSafety)      # "Operate It Right" (Goal 5 branch)
```

## Safety Case Structure

### Top-Level (Goals 1-5)

```
G1: The autonomous vehicle is safe enough to deploy
    │
    └── S2: Appeal to Positive Trust Balance
            │   (Context: Vehicle, operations, stakeholder requirements)
            │
            ├── G3: Our organization is trustworthy    ["Live It Right"]
            ├── G4: Our vehicle is safe to operate     ["Build It Right"]
            └── G5: We operate the vehicle safely      ["Operate It Right"]
```

### Organization Trustworthiness (Goal 3)

Supported by two strategies:
- **S6: Transparency enables trust** - G8 (assessment sharing), G9 (assessor independence)
- **S7: SMS is best practice** - G10 (policies), G11 (processes), G12 (monitoring)

Key standards referenced:
- UL 4600, 14 CFR Part 5, IATF 16949, German Ethics Commission guidelines

### Vehicle Safety (Goal 4)

Supported by four strategies:
- **S33: Hazard analysis standards** - G37 (comprehensive hazard analysis)
- **S34: Risk mitigation standards** - G38-G42 (standards conformance)
- **S35: Configuration management** - G43 (ISO 10007)
- **S36: Data recording** - G44 (SAE AVSC 00004)

Key standards referenced:
- SAE J3307 (STPA), FMVSS, ISO 26262, ISO/PAS 8800, ISO 21448, ISO 21434

### Operational Safety (Goal 5)

Supported by three strategies:
- **S69: Operational best practices** - G72-G77 (SAE AVSC guidelines)
- **S70: Procedural mitigations** - G78 (residual hazard procedures)
- **S71: Effective safety management** - Connected to SMS claims

Key standards referenced:
- SAE AVSC 00003, 00006, AVSC-I-01, -04, -05, AVSC-D-03

## Referenced Standards

| Standard | Domain |
|----------|--------|
| UL 4600 | Autonomous Products Evaluation |
| ISO 26262 | Functional Safety |
| ISO 21448 | Safety of Intended Functionality (SOTIF) |
| ISO 21434 | Cybersecurity Engineering |
| ISO/PAS 8800 | AI Safety |
| ISO 10007 | Configuration Management |
| FMVSS | Federal Motor Vehicle Safety Standards |
| SAE J3307 | STPA Hazard Analysis |
| SAE AVSC 00003-00006 | AV Safety Guidance |
| 14 CFR Part 5 | Safety Management Systems |
| IATF 16949 | Automotive Quality Management |

## Usage

This SACM representation can be:
- Imported into SACM-compliant tools for visualization and analysis
- Validated against the OMG SACM 2.2 XMI schema
- Extended with organization-specific claims and evidence
- Used as a template for autonomous vehicle safety cases

## References

- [OMG SACM 2.2 Specification](https://www.omg.org/spec/SACM/2.2/About-SACM/)
- [GSN Community Standard](https://scsc.uk/gsn)
- [SAFER Autonomous Systems - Assurance Case Notations](https://etn-sas.eu/2020/06/26/assurance-case-notations/)

## License

This safety case template is provided for reference purposes. Organizations should adapt and extend this template based on their specific vehicles, operations, and regulatory requirements.
