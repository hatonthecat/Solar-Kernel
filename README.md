# Soap-Kernel
Serial Operating Application Processor Kernel

This project seeks to develop a kernel for user applications in memory constrained microcontrollers, using message passing, similar to the microkernel used in Minix 3: https://en.wikipedia.org/wiki/Minix_3#Architecture

The acronym SOAP is defined as:

Serial: applications and its tasks (threads, are run mutually exclusive of any other processes. Technically, no other processes are in queue while one application is in run time. Context switching occurs only as a reformat of the operating system image. Developing a syscall process to allow context switching without restarting is a future goal.

Operating: The kernel's purpose is an operating system. However, it is operating only a single application at a time, and device drivers, including networking, are not run as parallel nor as background processes, except in cases where it may be part of the application - i.e. a peripheral device such as a mouse or display driver. Initially, this system is being developed for non-networking and 2D graphics with a simple GUI.

Application: The kernel and one application will fit the size of a microcontroller's SRAM- i.e 300KB-2MB- and will run one application at a time.

Processor: This refers both to hardware and software. The microcontroller is the hardware, while the kernel is just a process manager, as in Minix 3. The function of the microkernel is not to store drivers, but to pass messages through the I/O into user mode to retrieve and load an application. The majority of a typical kernel's functions (as in a monolithic kernel) would be stored on ROM- due to the limited space on RAM.   

The function of the kernel is to be both predictable (hard real time) and operate with interactive user inputs. This can only happen via context switching, and neither process can operate in parallel (at least in a single hardware core microcontroller).

