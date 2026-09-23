# Day 3 Introduction to TL Verilog and Makerchip.
An introduction to TL-Verilog was done and we implemented basic combinational and sequential logic using the same.This day finally ended with an implementation of a sequential cyclic calculator. Makerchip IDE which is an open source tool developed by Redwood EDA was utilised.

TL-Verilog is an extension for System Verilog, moreover it acts as an higher level abstraction for System verilog which makes HDL implementation very easy and error free. Here we deal the design at a transaction level assuming the design as a pipeline, where inputs would be provided and output will be generated at the end of the pipeline.

Advantages :

* Code reduction , and thus less chances of being bug prone.
* In pipelining ,the flip flops,registers and other staged signals are implied from the context.
* It is very easy to stage different sections without impacting the behaviour of the logic.
* Validity feature which provides easier debugging, cleaner design, automated clock gating and better error checking capabilities.

## Lab 1 : Combinational logic
Signals in TL-Verilog do not need declarations and can directly be used in assignments statements.All the signals start with '$' in TL-Verilog. If a signal is used but never assigned, the ide takes care of assigning random values to those signals. This example describes a combinational logic calculator designed using TL-verilog.

![](image/comp_calc.png)
