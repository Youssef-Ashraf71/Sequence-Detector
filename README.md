# Mealy State Machine for Sequence Detection and Pattern Recognition

This project implements a Mealy state machine in Verilog for sequence detection and pattern recognition. The state machine is designed to recognize a specific sequence and produce an output based on the input sequence it receives.

## State Machine Description

The Mealy state machine consists of three states: `zero`, `one1`, and `two1s`, representing different stages of the sequence detection process. The states and their behavior are defined as follows:

1. `zero`: This state represents the initial state and is waiting for the start of the sequence. If the input is '1', it transitions to the `one1` state; otherwise, it remains in the `zero` state.

2. `one1`: In this state, the machine has detected the first '1' in the sequence. If the input is '1', it transitions to the `two1s` state, indicating that two consecutive '1's have been detected. If the input is '0', it returns to the `zero` state.

3. `two1s`: This state indicates that two consecutive '1's have been detected. The machine remains in this state as long as the input is '1'. If the input is '0', it goes back to the `zero` state.

## Input and Output

- **Input**: The state machine takes three inputs:
  - `clk`: Clock signal for synchronous operation.
  - `reset`: Asynchronous reset signal to initialize the state machine to its initial state.
  - `in`: Input signal representing the input sequence. It can be either '0' or '1'.

- **Output**: The state machine has one output:
  - `out`: Output signal that indicates whether the desired sequence has been detected. It is set to '1' when the sequence "11" is detected, and '0' otherwise.

## Usage and Testing

The Verilog module `state_machine_mealy` represents the Mealy state machine implementation. It takes the inputs `clk`, `reset`, and `in`, and produces the output `out`.

The testbench module `state_machine_mealy_tb` is provided to test the state machine. It initializes the inputs `clk`, `reset`, and `in`, and then simulates the operation of the state machine for a sequence of inputs. The testbench performs the following steps:

1. The simulation starts with `reset` set to '1' to ensure a known initial state.
2. After a delay of 6 time units, `reset` is de-asserted (`reset = 1'b0`) to start the state machine operation.
3. The state machine is tested for 10 clock cycles (`i` from 0 to 9).
4. During each clock cycle, a random input value (`in`) is generated.
5. If the output `out` is '1' (sequence "11" detected), the simulation prints a message indicating that the sequence has been detected.

The simulation continues for a total of 50 time units.

## Running the Simulation

To simulate and test the state machine, you can use any Verilog simulation tool, such as ModelSim or Icarus Verilog. The provided testbench can be used to verify the functionality of the Mealy state machine.

Please make sure to set up your simulation environment properly before running the simulation.

Feel free to modify the testbench to test the state machine with different input sequences and verify its behavior.

Remember to analyze and understand the waveforms and output messages generated during simulation to verify the correct functionality of the state machine for different input scenarios.

## Acknowledgments

The implementation of the Mealy state machine and the testbench provided in this project are for educational and illustrative purposes. You can further enhance the state machine and testbench to suit your specific application and requirements.

## Contributors
<table>
  <tr>
    <td align="center">
    <a href="https://github.com/Youssef-Ashraf71" target="_black">
    <img src="https://avatars.githubusercontent.com/u/83988379?v=4" width="150px;" alt="Youssef Ashraf"/>
    <br />
    <sub><b>Youssef Ashraf</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/mouradmagdy" target="_black">
    <img src="https://avatars.githubusercontent.com/u/89527761?v=4" width="150px;" alt="Mourad Magdy"/>
    <br />
    <sub><b>Mourad Magdy</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/Muhannad159" target="_black">
    <img src="https://avatars.githubusercontent.com/u/104541242?v=4" width="150px;" alt="Muhannad Abdallah"/>
    <br />
    <sub><b>Muhannad Abdallah</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/heshamtamer" target="_black">
    <img src="https://avatars.githubusercontent.com/u/100705845?v=4" width="150px;" alt="Hesham Tamer"/>
    <br />
    <sub><b>Hesham Tamer</b></sub></a>
    </td>
      </tr>
 </table>
