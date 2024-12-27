# Recongif_computing
Designed a top module for the overall design using different computational units, with the feedback paths from the storage units using corner cases concepts

## Project Title
Hierarchical Modular Design with Custom Computational Units and Multiplexers

## Table of Contents
1. [Project Overview](#project-overview)
2. [Design Details](#design-details)
   - [Block Diagram](#block-diagram)
   - [Subcomponents](#subcomponents)
3. [Functionality](#functionality)
4. [Results](#results)
   - [Schematics](#schematics)
   - [Waveforms](#waveforms)
5. [Testing and Validation](#testing-and-validation)
6. [How to Run the Project](#how-to-run-the-project)

## Tools used
Xilix Vivado

## Programming language 
VHDL

## Project Overview
This project demonstrates a hierarchical modular design using custom computational units (CUs) and multiplexers (2x1 and 4x1) to perform arithmetic and logical operations. The top module integrates several subcomponents to form a complex system capable of feedback operations and iterative computations.

## Design Details

### Block Diagram
The top module is represented with color-coded components:
- **Pink**: 2x1 MUXes
- **Orange**: 4x1 MUXes
- **Yellow**: External inputs
- **Green**: Storage units
- **Blue and Purple**: Feedback paths

Key parameters:
- `d_w`: 4 (data width)
- `rows`: 4
- `cols`: 4

### Subcomponents
#### 4x1 Multiplexer
- Selects input based on the operation.
- Truth table defines the output for given inputs and select lines.

#### 2x1 Multiplexer
- Used for intermediate CU input selection.
- Truth table governs the select-line-based output.

#### Computational Unit (CU)
- Performs operations like AND, OR, XOR, Addition, Multiplication, etc.
- Supports logical shifts and comparisons.

#### Storage Units (A, B, OP, Y)
- Designed using D flip-flops.
- Outputs depend on clock and enable signals.

## Functionality
The design uses feedback loops to connect outputs from one computation to the next iteration. The system is organized into rows and columns where intermediate results are stored in feedback paths and reused in subsequent operations.

Operations include:
- Arithmetic: ADD, SUB, MULT
- Logical: AND, OR, XOR
- Shift: SLL, SRL, ROL, ROR
- Comparison: EQUAL, GREATER_THAN

## Results

### Schematics
Detailed schematics for the top module and subcomponents illustrate:
- MUX configurations
- CU operations
- Feedback loops

### Waveforms
Simulations validate the correctness of the design. Matching calculated and simulated outputs confirm functionality.

## Testing and Validation
Each component was tested independently with predefined test cases. Outputs for both individual and integrated modules passed validation criteria.

Example test case for CU:
| A    | B    | Operation | Expected Output | Simulated Output | Test Result |
|------|------|-----------|-----------------|------------------|-------------|
| 1010 | 0011 | AND       | 0010            | 0010             | Pass        |

