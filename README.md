# VHDL Unsigned Integer Counter Overflow
This example demonstrates a potential issue with unsigned integer counters in VHDL. The `counter.vhdl` file shows a simple counter that increments with each clock edge.  However, because the `INTEGER` type is used without explicit checks for overflow, the counter will wrap around from 15 back to 0.  The `counter_fixed.vhdl` file provides a solution to address this behavior.

## Issues
* **Unsigned Integer Overflow:** The `INTEGER` type in VHDL is unbounded by default and could lead to unexpected results if the intended behavior was to saturate at the maximum value (15 in this case).

## Solutions
* **Using a saturated counter:** Implement a check to prevent the counter from exceeding its maximum value.
* **Using a different data type:** Consider using `UNSIGNED` with a specific range. This provides explicit bounds for the counter.

This example highlights the importance of carefully selecting data types and handling potential overflow scenarios in VHDL for reliable designs.