<img src="./images/logo.gif" alt="logo" width="200"/>

# Basic examples for Vitis HLS

Copyright 2020 Xilinx, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

## C/C++ synthesizable examples

Each includes code sources for top function and testbench, a README, Tcl files.  They are organized in categories denoted by the prefix of the directory in which they reside:
* **_Coding_**: Common coding styles for pointers, loops, arrays, etc...
* **_Algorithm_**: Math and DSP examples
* **_Interface_**: Manage block connectivity to other blocks
* **_Misc._**: Other examples such are RTL blackbox in C++

## New examples in v2020.2
* Vector data types for SIMD programming (load, compute, store with m_axi): [./coding_vectorized](./coding_vectorized)
* Generation of block RAM ECC flags for single and dual errors: [./memory_ecc_flags](./memory_ecc_flags)
* Advanced option to simplify control logic for pipeline control and remove some high fanout nets [./coding_free_running_pipeline](./coding_free_running_pipeline)

## Running the examples

Two Tcl files are provided:
* _x_hls.tcl_: Short script sourced in run_hls.tcl to specify the steps of the flow which will be executed (by default only C simulation and C synthesis are run).  By changing the value of the variable hls_exec it's possible to run C-RTL co-simulation and launch a Vivado implementation
* _run_hls.tcl_: Sets up the project and sources x_hls.tcl mentioned above

To run at the command line, navigate to the example directory, type:
`vitis_hls -f run_hls.tcl`

To load an example design into the Vitis HLS GUI:
* From the "Welcome" screen ("Help"->"Welcome..."), click on "Clone Examples" and clone this repository
* Next, in the "Git Repositories" window pane in the lower left of the GUI, expand the "Working Tree"
* Right click on the example of interest and select "Run and Open HLS project"

## List of examples
Examples | Description
---------|------------
algorithm_2D_convolution_linebuffer|2D convolution implemented using hls::streams and a line buffer to conserve resources.
algorithm_fir_systolic_scalar| systolic fir filter
algorithm_fixed_point_sqrt| square root function based on fixed-point data types
algorithm_floating_mult_power_of_2| floating-point power of 2
algorithm_template_fir_filter| FIR filter using C++ template parameters
algorithm_window_function_fixed_point| Using fixed-point data types
algorithm_window_function_float| Using floating point data types
coding_arbitrary_precision_arith| Defining arbitrary precision number through the ap_int.h library
coding_arbitrary_precision_casting| Casting to/from arbitrary precision data types
coding_C++_templates| C++ templates
coding_dataflow_rewind| Task parallelism woth the dataflow pragma
coding_fixed_point| Fixed-point arithmetic
coding_free_running_pipeline| Free running pipeline logic for lower fanout signals in Vivado
coding_hierarchy_func|An example of adding files as test bench and design files.
coding_hierarchy_func2|An example of adding files as test bench and design files. An example of synthesizing a lower-level block in the hierarchy.
coding_hierarchy_func3|An example of combining test bench and design functions into the same file.
coding_hierarchy_func4|Using the pre-defined macro `__SYNTHESIS__` to prevent code being synthesized.Only use the `__SYNTHESIS__` macro in the code to be synthesized. Do not use this macro in the test bench,because it is not obeyed by C simulation or C RTL co-simulation.
coding_loop_functions|Converting loops into functions for parallel execution.
coding_loop_imperfect|An imperfect loop example.
coding_loop_labels|Using labels to tag loops.
coding_loop_max_bound_trick|Using a maximum bounds to allow loops be unrolled.
coding_loop_perfect|Using a maximum bounds to allow loops be unrolled.
coding_loop_pipeline|Example of loop pipelining.
coding_loop_sequential|Sequential loops.
coding_loop_sequential_assert|Using assert statements.
coding_loop_sequential_dataflow| Loop and dataflow (task parallelism)
coding_loop_variable_bound|A loop with variable bounds.
coding_malloc_removed|Example on removing mallocs from the code.
coding_pointer_arith| Pointer and arithmetic
coding_pointer_basic| Basic use of pointer
coding_pointer_cast_native| Pointer casting
coding_pointer_double| Double pointer
coding_pointer_multi| Multi pointer
coding_pointer_stream_better| Pointer on stream
coding_pointer_stream_good| Pointer on stream
coding_remerge_ii2to1| Coding trick to recoup II of 1 based on 2 sources with II of 2
coding_vectorized| Load-compute-store based on vector data types using the vector_size attribute
interface_axi_lite| AXI-4 Lite on C ports
interface_axi_master| AXI-4 Master memory mapped on C ports
interface_axi_stream_no_side_channel_data| Regular stream without sideband signals
interface_axi_stream_side_channel_data| Adding side-band signals for streams
interface_hls_stream| stream on the C ports
memory_bottleneck| Array accesses that prevent full throughput
memory_bottleneck_resolved| Offers a solution to memory_bottleneck
memory_ecc_flags| Setting a memory to genarate ECC flags for 1-bit nd 2-bit errors
memory_rom_coef_filter| Loading filter coefficients into a memory
memory_rom_lookup_table| Using an array filled with constants as a lookup
memory_rom_lookup_table_math| Presetting a memory with pre-calculated content
memory_ultraram| Inference of an UltraRAM block (URAM)
misc_rtl_as_blackbox| A user supplied Verilog module is swapped for a C function


