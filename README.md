# Soap-Kernel
Serial Operating Application Processor Kernel

This project seeks to develop a kernel for user applications in memory constrained microcontrollers, using message passing, similar to the microkernel used in Minix 3: https://en.wikipedia.org/wiki/Minix_3#Architecture

The acronym SOAP is defined as:

Serial: applications and its tasks (threads, are run mutually exclusive of any other processes. Technically, no other processes are in queue while one application is in run time. Context switching occurs only as a reformat of the operating system image. Developing a syscall process to allow context switching without restarting is a future goal. See Minix video: https://youtu.be/MG29rUtvNXg?t=2462 
This experimental process uses:

"A manager to request a process (e.g. Old-FS) to get ready

Old-FS finishes its work and queues new work

Manager creates New-FS process with new code

LLVM puts tables inside New-FS listing its data objects

New-FS contacts Old-FS and asks for state it needs

The state is transferred one object at a time

When all state is transferred, Third-FS is created

It talks to New-FS and tries to recreaite Old-FS

If they agree New-FS becomes FS, else revert to Old-FS

....

Much better than Ksplice"

The difference from that approach to SOAP is that this kernel would be designed to run different applications, rather than update a kernel for running multiple system process (such as a background process, like an email server) Since this would be a serial application processor, not other processes would likely be running anyways.

Thus, this could be a simplified process, depending on the applications switching over- some processes may benefit from clearing a cache/address for an application no longer needed. On the other hand, replacing the entire filesystem may effectively reboot the machine and there would be a noticeable lag in the display at the very least. That said, this process could be explored more to determine what can be retained during a context switch.

Operating: The kernel's purpose is an operating system. However, it is operating only a single application at a time, and device drivers, including networking, are not run as parallel nor as background processes, except in cases where it may be part of the application - i.e. a peripheral device such as a mouse or display driver. Initially, this system is being developed for non-networking and 2D graphics with a simple GUI.

Application: The kernel and one application will fit the size of a microcontroller's SRAM- i.e 300KB-2MB- and will run one application at a time.

Processor: This refers both to hardware and software. The microcontroller is the hardware, while the kernel is just a process manager, as in Minix 3. The function of the microkernel is not to store drivers, but to pass messages through the I/O into user mode to retrieve and load an application. The majority of a typical kernel's functions (as in a monolithic kernel) would be stored on ROM- due to the limited space on RAM.   

The function of the kernel is to be both predictable (hard real time) and operate with interactive user inputs. This can only happen via context switching, and neither process can operate in parallel (at least in a single hardware core microcontroller).

