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

Another way of viewing this kernel is taking a more broad view of computers, from a historical perspective. If one asks, "what is a computer?"
https://en.wikipedia.org/wiki/Computer

From Wikipedia: "A computer is a digital electronic machine that can be programmed to carry out sequences of arithmetic or logical operations (computation) automatically. Modern computers can perform generic sets of operations known as programs. These programs enable computers to perform a wide range of tasks."

Early computers were meant to be used only for calculations. Simple manual instruments like the abacus have aided people in doing calculations since ancient times. Early in the Industrial Revolution, some mechanical devices were built to automate long tedious tasks, such as guiding patterns for looms. More sophisticated electrical machines did specialized analog calculations in the early 20th century. The first digital electronic calculating machines were developed during World War II. The first semiconductor transistors in the late 1940s were followed by the silicon-based MOSFET (MOS transistor) and monolithic integrated circuit (IC) chip technologies in the late 1950s, leading to the microprocessor and the microcomputer revolution in the 1970s. The speed, power and versatility of computers have been increasing dramatically ever since then, with transistor counts increasing at a rapid pace (as predicted by Moore's law), leading to the Digital Revolution during the late 20th to early 21st centuries.

It's often easy to forget of magnitudes of computational  advances have occurred in the past 100 years, from the early mechanical, to the vacuum tubes, to the transistors, and then ICs. The amount of information that can be processed today on a computer in 1 second is more that can be ready in several lifetimes. 

Humans do have a need for assisted computational devices- i.e. electronic calculators and beyond. Around 2015, an article was written that provided a very good summary  of how far computing has travelled: https://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/

The concept of this kernel is to develop an operating system that can provide a minimized input/output amount of computation at a rate that a human can process, and not much faster. Hence the reason for a "single task, serial operating system." It's not that humans cannot multi-task, but the hardware designed today creates a socioeconomic barrier to entry, not just monetary access, but because it relies on energy/Whs as a de facto subscription model to largely centralized utilities.

To summarize, the soap kernel is a minimum input/output human interface device (HID) Human, in that it is designed for a human's capabilities when performing more analytical interation with a program, rather than a transactional interaction. For example, this would benefit those who read and annotate academic papers more than someone who is trading stocks. There are already a lot of e-readers like Kindle that do this, but Kindles do not need to rely on battery alone, and solar powered Kindles are definitely a better alternative. The basic Kindles today rely on 
a	Freescale/NXP i.MX6 SoloLite 1 GHz processor, a low power arm processor. This product has a niche use because the refresh rate is limited, but advances in display technology, and optimizations of displays to consume less power while still producing clear, visible text at a rate that a human can analyze, but not rapidly transact in, would provide an immense benefit to solar powered devices, and is an ultimate goal of this kernel's future application. Consider computing today the equivalent of fast food. https://en.wikipedia.org/wiki/Slow_journalism was born out of the frustration that 24hrs news coverage often seizes our attention span unreasonably.

It could be cheap enough to produce a microcontroller, with a small solar panel, lcd screen and keyboard that could be produced for $100, and every person on earth could own one. Unlike a cell phone, which requires upgrades, a portable device that is powered by solar wouldn't necessarily need to be upgraded to serve as a personal digital assistant (PDA). A record 86% of the world owns a smartphone today by one estimate: https://www.zippia.com/answers/what-percentage-of-the-world-has-a-cell-phone-in-2022/
But cell phones are an expensive necessity for many people, and would be a very resource intensive manufacturing cost to replace 10 billion electronic devices every 1-2 years. to be a primary device by 8 billion people worldwide. A calculator I purchased in the 1990s still functions as a solar calculator today. The obsolescence of a portable electronic product is marked primarily by the ability of lithium ion batteries to retain a charge after a number of years, and eventually become obsolete due to mandatory software updates, rather than software that can run in a containerized environment that does not get modified or overwritten. The ability of hardware to be repaired by means of having more modular components that are user-replaceable, can grant a life extension to many electronics. 

Processing power today has reached a transistor node that microcontrollers today can display high resolution outputs from a keyboard/remote that can produce more lines of text in a few seconds that a human can read in several hours . In the 1930s, it might have taken minutes or hours for a large mechanical calculator to calculate Pi to the 1000th decimal. Today, general purpose computing has scaled to billions of transistors, and software has followed. There is hardware available today that can display all the works of Shakespeare in less than a minute using a 240hz monitor, with thousands of pages, at 240 refreshes a second, for 60 seconds- maybe a couple seconds. The question is, do we really need yesterday's supercomputers for all of our portable e-viewing? 

The more I think about this project, it is more an exploration of an economics issue. It seeks to address a gap in access to not just basic ownership of a phone, but a device that can accomplish simple communication and digital processing tasks without needing to devote a sizeable percentage of one's income to a phone plan. In some parts of the world, where one's salary is only a few dollars a month, owning a phone is a larger percentage of one's income than in higher GDP countries (where the cost of rent is also a very high proportion of one's income). consider the discontinuation of 2G cell phone towers in the U.S. It may not have affected many people that they needed to upgrade to a new phone as many already had a 2G or 4G device, but what happens when upgrading a device causes a significant hardship? Sometimes it is possible to do without a phone in urban environments, but in some places, a phone is a lifeline both for both one's ability to stay employed as well-as one's well being. I know I've veered into using the phrase phone quite frequently in the past paragraph. And that may be the most frequently used movile device. But phones are chosen because they are often convenient to carry, as they fit in a pocket, not because laptops are unaffordable to many. That said, what if our next superstar programmer is in a rural village with no internet or power? He or she wouldn't be able to learn coding without a solar panel or wind turbine.  Manufacturing latops with integrated solar panels is a one time transplant of solar to remote regions and creates a decentralized grid of computer access to the last 14% of people in the world without a phone/or electricity. To get there, software needs to be designed to match the low power of microprocessors, using already low power microprocesors.
https://whossavingtheplanet.com/read/innovation/green-coding-sustainability-in-software/2020-10-04 Datacenters have done this for years:
https://www.computerweekly.com/blog/Green-Tech/Green-coding-A-sustainability-practice-all-software-engineers-should-adhere-to
A solar powered laptop/phone would be a proof of concept that green coding can be applied to the microeconomic level, from kernel to the display monitor) to transform our dependency on lithium ion batteries, as well as the need to plug in to outlets at Starbucks.
