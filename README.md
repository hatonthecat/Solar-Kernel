# Soap-Kernel
Serial(ly) Operating Application Processor Kernel (part of https://hackaday.io/project/177716-the-open-source-autarkic-laptop)

This project seeks to develop a kernel for user applications in memory constrained microcontrollers, using message passing, similar to or based on the microkernel used in Minix 3: https://en.wikipedia.org/wiki/Minix_3#Architecture

A web based package manager (e.g https://tiny.slitaz.org/ ) could also make creating custom ISOs/images more user-friendly: https://groups.google.com/g/minix3/c/gs2z6m7Kj14
Similar to Cubic: https://launchpad.net/cubic


The acronym SOAP is defined as:

Serial: applications and its tasks (threads, are run mutually exclusive of any other processes. Technically, no other processes are in queue while one application is in run time. The exception would be queues for context switching, which occurs only as a reformat of the operating system image- and this would be only as frequent as the user toggles between applications. Developing a syscall process to allow context switching without restarting is a future goal. See Minix video: https://youtu.be/MG29rUtvNXg?t=2462 
This experimental process uses:

"A manager to request a process (e.g. Old-FS) to get ready

Old-FS finishes its work and queues new work Manager creates New-FS process with new code LLVM puts tables inside New-FS listing its data objects New-FS contacts Old-FS and asks for state it needs The state is transferred one object at a time When all state is transferred, Third-FS is created It talks to New-FS and tries to recreate Old-FS If they agree New-FS becomes FS, else revert to Old-FS
....

Much better than Ksplice"

Some other kernel projects include:

https://github.com/vvaltchev/tilck
and 


https://github.com/managarm/managarm

Some interesting words about kernel dev: https://medium.com/@azerella/how-to-become-a-linux-kernel-developer-20774c72ab07

https://en.wikipedia.org/wiki/The_Cathedral_and_the_Bazaar#Lessons_for_creating_good_open_source_software
"Raymond points to 19 "lessons" learned from various software development efforts, each describing attributes associated with good practice in open source software development:[3]

Every good work of software starts by scratching a developer's personal itch."

Kernel dev seems to be my itch. Every so often, I wonder, am I even capable of developing a kernel? By developing, I am referring to the agnostic modification of existing code and programming ideas to splice together some new kernel for a new purpose. New kernels are written to scratch some itch, whether it is a new ISA, application, or service. Thus, scratching an itch is also determining whether someone already scratched this itch, and whether it is platform dependent. Hence, platform independent architecture is more portable, but not entirely portable. 

For example, this paragraph:

"Tilck is a preemptable monolithic (but with compile-time modules) *NIX kernel, implementing about ~100 Linux syscalls (both via int 0x80 and sysenter) on x86. At its core, the kernel is not x86-centric even if it runs only on x86 at the moment. Everything arch-specific is isolated. Because of that, most of kernel's code can be already compiled for any architecture and can be used in kernel's unit tests."

Understanding computer architecture is a necessity to understanding what allows code to be run on more than one arch. Code/Algorithmic efficiency is not a priority to a beginner, unless perhaps constrained memory controllers is part of the development process. Perhaps I am somewhat foolish to embrace kernel research without starting at some point in understanding how integrated circuits process binary bits. 

The motivation of this project is algorithmic efficiency. Although assembly is understood to be "faster," efficiency is relativistic, based on the developer's experience in the context of novel hardware development. Thus, programmatic efficiency can, but does not always take priority. 

The other motivation of this project is autarkic design-"crade to cradle" here is defined as a solar powered energy harvester integrated on a PCB, and a finite number of photons between zero and infinity, required to produce, flip and modify a binary bit of data, in both the central processing unit, and the display (for user applications). 

Thus, this project adopts an Occam's razor approach of conceptualizing the simplest autarkic system. For reference:
Although assembly is understood to be "faster," efficiency is relativistic, based on the developer's experience in the context of novel hardware development. Thus, programmatic efficiency can, but does not always take priority.

https://conceptually.org/concepts/occams-razor

https://en.wikipedia.org/wiki/Occam's_razor

This logic, or approach, is useful in not just problem solving, but concept development. That is, this project isn't seeking to solve a problem, specifically. It could be argued that simpler computers are needed for certain tasks, and that technological convergence needs to deconverge (i.e smart phones should become smartphones). But for the purpose of developing such as system, those arguments are irrelevant. Thus that discussion is could be supplmental on a discussion or issue page. Feel free to raise it here, if the project encounters a philosophical fork in the road. As Yogi Berra once said, "if you encounter a fork in the road, take it." 

Why would I autarkic design parsimonious? Because all computers have all relied on a power input. Before the linux kernel, free software and open source needed a platform. Now open source can be use to develop more open source. In a way, linux is like a self-replicating machine. Thus, I am conscious to how power consumption is necessary to develop software. But that also reveals an odd aspect of linux accessibility:

"According to official statistics, a tad under half of the world population is not connected to the Internet. In Latin America, according to the most recent statistics, close to 30% of the population is not online. Different variables contribute to the problem of the digital divide, but these can be generally parsed into four categories: no coverage or services available; access is too expensive; a lack of digital skills; or, the Internet simply does not offer anything of interest. While the number of people connected does go up every year, the rate of expansion is fairly modest at about 2 or 3% annually, and at the current rate (which is actually slowing) it will take decades to get everyone online who wishes to be.'

https://www.rhizomatica.org/keeping-it-analog-a-framework-for-opting-out-of-connectivity/ 

The linux kernel was developed in 1991. It has been approximately 32 years since it was developed, and has gotten larger and larger over time, often to support many impressive features.

Imagine the world decided in 2023, that there are actually multiple  different approaches reflecting on this progress. On the on hand, you have mainline linux kernel that sees no issue- that perhaps more can be connected and manufacturing will eventually allow everyone who wants a computer to have one.

Another scenario is that there are already billions of computers available to develop energy efficient kernels for purpose-built hardware. What I mean by this is, a significant portion of mainline linux, whether it is a Linux Foundation sponsored project, such as Zephyr, or medium ground between RTOS and userspace-type desktop OS, that chooses to refocus their efforts in helping more users in the developing world get access to computing, whether or not they have interent access. Thus offine OS development is still immensely important, because the above paragraph by Rhizomatica acknowledges the fact that just under half the world is not connected to the internet. This reveals another limitation of existing systems. Internet access also requires a power source. This is may sound obvious to a Westerner, but this reveals an underexamined component of open source development. 

If one reads some of the early writings of Eric Raymond and the Steven Levy, one might think that the early 90s were a time of much more cooperation across the political aisle. I am not implying any public figure's political leanings, nor does it actually matter. What I am trying to emphasize, is the overal mood of open source and free software today. How many developers are interested in developing energy efficiency operating systems, to help more users run hardware that could be used to develop more open source? When one reads an article on even very pro-open source websites, like Hacker News, Slashdot, the Register, CNX Software, they are covering, for the majority, hardware afforded by users in wealthier countries, or users who can afford a system on a chip like a raspberry pi in South America. But these hardware are getting more power intensive. https://www.pidramble.com/wiki/benchmarks/power-consumption The Raspberry Pi A+ used 0.8 Watts. The Rpi4 uses over 5 Watts of power. Who is the Raspberry Pi really interested in catering to?

If there was a greater effort in developing a kernel that could run on a solar powered laptop, it could provide more information than a library with thousands of books. Manufacturing new technology is certainly a power intensive process, but once it is made, the only thing it needs to last 20 years is power. It doesn't need to be watered like a plant. It doesn't need an oil change like a car. Power is the only thing a laptop needs. Maybe it might need a new microSD card or SSD, if the onboard NOR is not corrupt, and if it supports external storage. These kinds of technologies are useful because they do not age as quickly as software designed for performance. If computers can be designed and viewed like books, then there does not need be a desire to compete against against performance machines. 

"Non-Competitive Products means any (i) product or service that is not a Competitive Product (including products or services that are not sold in the Prior Areas, but would be Competitive Products if they were sold in the Prior Areas), (ii) product or service that is being designed, developed, manufactured, used, marketed, offered for sale or sold by Seller or its Affiliates (but excluding the Sold Companies) as of the date of this Agreement (or any improvements, new versions or successors thereof) or (iii) module or component that is incorporated into any product or service described in clause (i) or (ii) of this definition.'
https://www.lawinsider.com/dictionary/non-competitive-products

I find it a curious aspect that much of the software ecosystem is centered around competitive product development. If hardware were designed not to compete against higher performance products, would it appear any less intimidating? If I were to examine the logic of this statement, I could explore several possibilities:

1. Slow hardware has no use today, and people always want faster software.
2. Slow hardware has a use, but it is counterintuitive to develop it because it is expensive.
3. Slow software has a use, and it is worth the cost in the long term.

I should add, that slow hardware is not actually slow, if one can efficiently design a simple 2D CLI/GUI without graphics acceleration for the purpose of displaying text. in the minimum number of pixels to be legible.

https://bbenchoff.github.io/pages/dumb.html
http://www.paperterm.org/notes.html

Why is this important? Computers are just a means of accessing and interacting with information. Today, Foundries can produce 5 nanometer chips that use extremely low computations per joule of energy dissipated: https://en.wikipedia.org/wiki/Koomey%27s_law

Thus, while many environmentally conscious users prefer not to buy new pcs to save on the environment (and they are correct), another aspect of computing is that technology today allows for computing to be autarkic, but due to lack of awareness or interest, leading chip designers can willingly leave out 4 billion users by continuing to develop power hungry devices. To learn programming, one can read a book. But even if a book is available, one cannot interact with a command line interface. Thus the technology today is available to integrate leading edge components (low power Japan Display memory in pixels), Ambiq Apollo4 microcontrollers, to develop autarkic command line interfaces, that give access to the maximum amount of information (whether stored in gigabytes off line on a microSD) or via an online hardware- if the system on a chip has a wireless or ethernet capability. That said, the lowest power mechanism for transferring data -whether it is LPWAN or a usb/cat 5 cable would need to be considered. Thus there is no concerted effort hitherto anywhere to develop this. I seek to be the first to explicitly call for this, since no one else wants to , or believes it is possible.

I think of that fable, by Aesop:
https://en.wikipedia.org/wiki/The_Tortoise_and_the_Hare

In elementary school, our school occasionally had guest speakers, some were motivational speakers in our auditorium. One of them was an acting couple, that told us the story of the the tortoise and the hare. They turned the gym into a racetrack, and one played a bipedal tortoise, and the other one a bipedal hare. The hare ran around the gym, and in his hubris, took a nap at about 75% near the finish line. The tortoise ran, diligently, around the gym, and the hare, sleeping, woke up just as he noticed the hare about the reach the finish line, and started sprinting but lost the race.

Why am I sharing this story? Because it is one of the most inspiring story in my life. A person without internet access may not seem as cool to you. But they could be studying or reading even without a book or internet access, if only they had a computer that could power itself. So when they connect to the internet, they could upload a magnificent software or story (if they are a writer), which may appear out of nowhere, as the have wake up from their slumber. That is my dream. 

-------


The difference from [multi threading] approach to SOAP is that this kernel would be designed to toggle between different applications in a serial manner, rather than update a kernel for running multiple system processes (such as a background process, like an email server) Since this would be a serial application processor, no other processes would likely be running anyways.

Thus, this could be a simplified process, depending on the applications switching over- some processes may benefit from clearing a cache/address for an application no longer needed. On the other hand, replacing the entire filesystem may effectively reboot the machine and there would be a noticeable lag in the display at the very least. That said, this process could be explored more to determine what can be retained during a context switch.

Operating: The kernel's purpose is an userland operating system. However, it is operating only a single application at a time, and device drivers, including networking, are not run as parallel nor as background processes, except in cases where it may be part of the application - i.e. a peripheral device such as a mouse or display driver. Initially, this system is being developed for non-networking and 2D graphics with a simple GUI.

Application: The kernel and one application will fit the size of a microcontroller's SRAM- i.e 300KB-2MB- and will run one application at a time.
However, the choice of microcontroller is highly specific for the initial purpose of this project-for use in solar powered mobile devices. See the original project application for details: https://github.com/EI2030/Low-power-E-Paper-OS

As a result, the type of microcontroller would need to be one that uses extremely low power, and is in mass-production enough (like the Intel 386, which was the choice of hardware for the original linux kernel). The Ambiq Micro company has sold over 100 million devices, and the Apollo line of MCUs appears to be a stable line of products for the foreseeable future. While portability in such a kernel is sought, the reality is porting a single kernel/OS to a MCU requires significant development time, therefore adopting a hardware that is readily available can avoid the need to make multiple ports in the short-term. Furthermore, the Apollo3 and Apollo4 processors contain 384KB-2.5MB of Ram, with 48mhz-192mhz of processing power, far more operations/sec/Wh than many microcontrollers at much less the energy use. https://ambiq.com/why-ambiq/ Future software portability like Rump is definitely an idea:https://man.netbsd.org/NetBSD-7.0/rump.3

but SOAP kernel development is primarily a size-based design constraint. 

Processor: This refers both to hardware and software. The microcontroller is the hardware processor, while the kernel is just a process manager, as in Minix 3. The function of the microkernel is not to store drivers, but to pass messages through the I/O into user mode to retrieve and load an application. The majority of a typical kernel's functions (as in a monolithic kernel) would be stored on ROM- due to the limited space on RAM.   

The function of the kernel is to be both predictable (hard real time) and operate with interactive user inputs. It aims to utilize the benefits of RTOS and hybridize it with user's syscalls. This can only happen via context switching, and neither process can operate in parallel (at least in a single hardware core microcontroller).

Another way of understanding this kernel is taking a more broad view of computers, from a historical perspective. If one asks, "what is a computer?"
https://en.wikipedia.org/wiki/Computer

From Wikipedia: "A computer is a digital electronic machine that can be programmed to carry out sequences of arithmetic or logical operations (computation) automatically. Modern computers can perform generic sets of operations known as programs. These programs enable computers to perform a wide range of tasks....

Early computers were meant to be used only for calculations. Simple manual instruments like the abacus have aided people in doing calculations since ancient times. Early in the Industrial Revolution, some mechanical devices were built to automate long tedious tasks, such as guiding patterns for looms. More sophisticated electrical machines did specialized analog calculations in the early 20th century. The first digital electronic calculating machines were developed during World War II. The first semiconductor transistors in the late 1940s were followed by the silicon-based MOSFET (MOS transistor) and monolithic integrated circuit (IC) chip technologies in the late 1950s, leading to the microprocessor and the microcomputer revolution in the 1970s. The speed, power and versatility of computers have been increasing dramatically ever since then, with transistor counts increasing at a rapid pace (as predicted by Moore's law), leading to the Digital Revolution during the late 20th to early 21st centuries."

It's often easy to forget of magnitudes of computational  advances have occurred in the past 100 years, from the early mechanical, to the vacuum tubes, to the transistors, and then ICs. The amount of information that can be processed today on a computer in 1 second is more that can be read in several lifetimes. 

Humans do have a need for assisted computational devices- i.e. electronic calculators and beyond. Around 2015, an article was written that provided a very good summary  of how far computing has travelled: https://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/

The concept of this kernel is to develop an operating system that can provide a minimized input/output amount of computation at a rate that a human can process, and not much faster. Hence the reason for a "single task, serial operating system." It's not that humans cannot multi-task, but the hardware designed today creates a socioeconomic barrier to entry, not just monetary access, but because it relies on energy/Whs as a de facto subscription model to largely centralized utilities.

To summarize, the soap kernel is a minimum input/output concept for human interface devices (HID). Human, in that it is emphasizes human capabilities/limits by encouraging more analytical interactions with a program (i.e think before you type), rather than a rapidly transactional interaction. There are some Operating systems that have recently explored this idea: https://www.mercuryos.com/
https://en.wikipedia.org/wiki/Human_interface_device
It takes a more classical, longview of how HIDs and GUIs were originally developed, and focuses on a balance between human processing of output data/information, and new inputs. For example, this would benefit those who read and annotate academic papers more than someone who is trading stocks intra-daily. There are already a lot of e-readers like Kindle that do this, but Kindles do not need to rely on battery alone, and solar powered Kindles are definitely a better alternative/supplement. 

The basic Kindles of today rely on a	Freescale/NXP i.MX6 SoloLite 1 GHz processor, a low power arm processor. This product has a niche use because the refresh rate is limited, but advances in display technology, and optimizations of displays to consume less power while still producing clear, visible text at a rate that a human can analyze, but not rapidly transact in, would provide an immense benefit to solar powered devices, and is an ultimate goal of this kernel's future application. Consider computing today the equivalent of fast food. https://en.wikipedia.org/wiki/Slow_journalism was born out of the frustration that 24hrs news coverage often seizes our attention span unreasonably.

It could be cheap enough to produce a microcontroller, with a small solar panel, lcd screen and keyboard that could be produced for $100, and every person on earth could own one. Unlike a cell phone, which requires upgrades, a portable device that is powered by solar wouldn't necessarily need to be upgraded to serve as a personal digital assistant (PDA). A record 86% of the world owns a smartphone today by one estimate: https://www.zippia.com/answers/what-percentage-of-the-world-has-a-cell-phone-in-2022/
But cell phones are an expensive necessity for many people, and would be a very resource intensive manufacturing cost to replace 10 billion electronic devices every 1-2 years. A calculator I purchased in the 1990s still functions as a solar calculator today. The obsolescence of a portable electronic product is marked primarily by the inability of lithium ion batteries to retain a significant charge above 80% after a number of years, and eventually become obsolete due to mandatory software updates, rather than software that can run in a containerized environment that does not get modified or overwritten. The ability of hardware to be repaired by means of having more modular components that are user-replaceable, can grant a life extension to many electronics. 

Processing power today has reached a transistor node that microcontrollers today can display high resolution outputs from a keyboard/remote that can produce more lines of text in a few seconds that a human can read in several hours . In the 1930s, it might have taken minutes or hours for a large mechanical calculator to calculate Pi to the 1000th decimal. Today, general purpose computing has scaled to billions of transistors, and software has followed. There is hardware available today that can display all the works of Shakespeare in less than a minute using a 240hz monitor, with thousands of pages, at 240 refreshes a second, for 60 seconds- maybe a couple seconds. The question is, do we really need yesterday's supercomputers for all of our portable e-viewing? I recently read smartphone review of middrange phones offered the pros and cons of a 90hz refresh rate and suggested, "It's not 120hz." There are 120hz phones https://www.digitaltrends.com/mobile/refresh-rate-smartphone-screen-explainer/ And what's remarkable, is that these features are more sought than a basic phone. https://en.wikipedia.org/wiki/Feature_creep 120hz is one way to use up the extra battery life that a 4 nanometer phone can allow for. Phones have so much processing power today, that we continue to try to add an IMAX theater visor to it before heavens forbid, making it solar powered. 

The more I think about this project, it is more an exploration of an economics issue. It seeks to address a gap in access to not just basic ownership of a phone, but a device that can accomplish simple communication and digital processing tasks without needing to devote a sizeable percentage of one's income to a phone plan. In some parts of the world, where one's salary is only a few dollars a month, owning a phone is a larger percentage of one's income than in higher GDP countries (where the cost of rent is also a very high proportion of one's income). consider the discontinuation of 2G and 3G cell phone towers in the U.S. It may not have affected many people that they needed to upgrade to a new phone as many already had a 4G or 5G device, but what happens when upgrading a device causes a significant hardship? Sometimes it is possible to do without a phone in urban environments, but in some places, a phone is a lifeline both for both one's ability to stay employed as well-as one's well being. I know I've veered into using the phrase phone quite frequently in the past paragraph. And that may be the most frequently used movile device. But phones are chosen because they are often convenient to carry, as they fit in a pocket, not because laptops are unaffordable to many. That said, what if our next superstar programmer is in a rural village with no internet or power? He or she wouldn't be able to learn/practice coding, even if someone donated them an i9 laptop, without a solar panel or wind turbine. Designing and  Manufacturing laptops with integrated solar panels is a one time transplant of solar to remote regions and creates a decentralized grid of computer access to the last 14% of people in the world without a phone/or electricity. To get there, software needs to be designed to match the low power of microprocessors, using already low power microprocesors.
https://whossavingtheplanet.com/read/innovation/green-coding-sustainability-in-software/2020-10-04 Datacenters have done this for years:
https://www.computerweekly.com/blog/Green-Tech/Green-coding-A-sustainability-practice-all-software-engineers-should-adhere-to
A solar powered laptop/phone would be a proof of concept that green coding can be applied to the microeconomic level, from kernel to the display monitor) to transform our dependency on lithium ion batteries, as well as the need to plug in to outlets at Starbucks.
