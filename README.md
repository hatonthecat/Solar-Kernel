# Soap-Kernel
Serial(ly) Operating Application Processor Kernel

This project seeks to develop a kernel for user applications in memory constrained microcontrollers, using message passing, similar to or based on the microkernel used in Minix 3: https://en.wikipedia.org/wiki/Minix_3#Architecture

The acronym SOAP is defined as:

Serial: applications and its tasks (threads, are run mutually exclusive of any other processes. Technically, no other processes are in queue while one application is in run time. The exception would be queues for context switching, which occurs only as a reformat of the operating system image- and this would be only as frequent as the user toggles between applications. Developing a syscall process to allow context switching without restarting is a future goal. See Minix video: https://youtu.be/MG29rUtvNXg?t=2462 
This experimental process uses:

"A manager to request a process (e.g. Old-FS) to get ready

Old-FS finishes its work and queues new work

Manager creates New-FS process with new code

LLVM puts tables inside New-FS listing its data objects

New-FS contacts Old-FS and asks for state it needs

The state is transferred one object at a time

When all state is transferred, Third-FS is created

It talks to New-FS and tries to recreate Old-FS

If they agree New-FS becomes FS, else revert to Old-FS

....

Much better than Ksplice"

The difference from that approach to SOAP is that this kernel would be designed to toggle between different applications in a serial manner, rather than update a kernel for running multiple system processes (such as a background process, like an email server) Since this would be a serial application processor, no other processes would likely be running anyways.

Thus, this could be a simplified process, depending on the applications switching over- some processes may benefit from clearing a cache/address for an application no longer needed. On the other hand, replacing the entire filesystem may effectively reboot the machine and there would be a noticeable lag in the display at the very least. That said, this process could be explored more to determine what can be retained during a context switch.

Operating: The kernel's purpose is an userland operating system. However, it is operating only a single application at a time, and device drivers, including networking, are not run as parallel nor as background processes, except in cases where it may be part of the application - i.e. a peripheral device such as a mouse or display driver. Initially, this system is being developed for non-networking and 2D graphics with a simple GUI.

Application: The kernel and one application will fit the size of a microcontroller's SRAM- i.e 300KB-2MB- and will run one application at a time.
However, the choice of microcontroller is highly specific for the initial purpose of this project-for use in solar powered mobile devices. See the original project application for details: https://github.com/EI2030/Low-power-E-Paper-OS

As a result, the type of microcontroller would need to be one that uses extremely low power, and is in mass-production enough (like the Intel 386, which was the choice of hardware for the original linux kernel). The Ambiq Micro company has sold over 100 million devices, and the Apollo line of MCUs appears to be a stable line of products for the foreseeable future. While portability in such a kernel is sought, the reality is porting a single kernel/OS to a MCU requires significant development time, therefore adopting a hardware that is readily available can avoid the need to make multiple ports in the short-term. Furthermore, the Apollo3 and Apollo4 processors contain 384KB-2.5MB of Ram, with 48mhz-192mhz of processing power, far more operations/sec/Wh than many microcontrollers at much less the energy use. https://ambiq.com/why-ambiq/ Future software portability like Rump is definitely an idea:https://man.netbsd.org/NetBSD-7.0/rump.3

but SOAP kernel development is primarily a size-based design constraint. 

Processor: This refers both to hardware and software. The microcontroller is the hardware processor, while the kernel is just a process manager, as in Minix 3. The function of the microkernel is not to store drivers, but to pass messages through the I/O into user mode to retrieve and load an application. The majority of a typical kernel's functions (as in a monolithic kernel) would be stored on ROM- due to the limited space on RAM.   

The function of the kernel is to be both predictable (hard real time) and operate with interactive user inputs. It aims to utilize the benefits of RTOS and hybridize it with user's syscalls. This can only happen via context switching, and neither process can operate in parallel (at least in a single hardware core microcontroller).

