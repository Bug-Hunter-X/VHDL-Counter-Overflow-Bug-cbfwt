# VHDL Counter Overflow Bug
This repository demonstrates a common error in VHDL code: counter overflow.  The `buggy_counter.vhd` file contains a counter that increments without checking for the upper bound, which can lead to unexpected behavior. The `fixed_counter.vhd` demonstrates a corrected version.

## Bug Description
The `buggy_counter` entity uses a simple counter that increments with every rising clock edge.  It lacks bounds checking, meaning once the counter reaches its maximum value (15), the next increment will cause an overflow, resulting in unpredictable behavior.  This might manifest as unexpected values at the `count_out` port or even simulation errors.

## Solution
The `fixed_counter.vhd` demonstrates a robust solution by adding an `if` condition inside the `rising_edge(clk)` section to check if the current count has reached the upper limit. If it has, the counter is reset to 0, preventing overflow. This ensures correct functionality and prevents unexpected behaviors.
