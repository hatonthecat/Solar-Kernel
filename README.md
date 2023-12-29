# SOLAR-Kernel

12-28-2023 https://theimaginativeconservative.org/2018/04/teason-clerks-russell-kirk.html

12-29-2023 https://newcriterion.com/issues/1992/12/the-treason-of-the-intellectuals-ldquothe-undoing-of-thoughtrdquo

----

What needs a Real Time Clock?

https://www.quora.com/How-do-computers-work-without-clocks-If-they-dont-use-clocks-how-do-programs-run

"This is a really interesting question.

Almost all modern computers, from huge to tiny, have clocks built into them. In most cases, it is a real-time clock (RTC) deployed as either a small integrated circuit (IC), or built into a larger IC such as a microcontroller. The RTC allows the computer to track the passage of time, and in many cases it is paired with a small battery which allows it to continue tracking time when power is removed. This is how personal computers keep their clocks set even when unplugged (although the ability to set the clock on startup from an internet server has largely supplanted the need for this on many modern systems).

However, small microcontrollers and other embedded systems sometimes use a simpler type of clock which is more of a counter than a clock. These systems generally don't need to “know what time it is"in the time and date sense, but they do need to be able to gauge the passage of time so they can do things on a schedule (for example, checking the voltage on an input pin every 5 seconds). What these smaller systems do is count the number of seconds, milliseconds, nanoseconds, etc. since they last booted up. The controller doesn't care that it's 3:05 PM US Eastern time; it just knows that it last checked that input pin at 16008765 milliseconds, and at 16009265 milliseconds it needs to check again.

That's for modern computers, though. In the early days of personal computers, RTCs were very expensive and almost unheard of in smaller home machines. Computers like the Apple II had no built-in clock whatsoever, and therefore no good way to measure time. Instead, these machines and the software written for them used the frequency of the CPU cycles for anything that required timing. You couldn't tell the Apple II to “wait 5 seconds", but you could tell it to “wait 5,000 cycles" (I'm making that number up). This was true for other things, too. Game consoles like the Atari 2600 and Nintendo Entertainment System used the same concept of counting cycles to approximate a clock."

----





Formerly Soap Kernel, this repository is being renamed to "Serially Operating Light Application Repositories Kernel"

A repository for single application kernels designed to maximize use of RAM while limiting the need of excess RAM, to allow lowest power application processors and system on a chips to run on solar energy.

Serial(ly) Operating Application Processor Kernel (part of https://hackaday.io/project/177716-the-open-source-autarkic-laptop)

This project seeks to develop a kernel for user applications in memory constrained microcontrollers, using message passing, similar to or based on the microkernel used in Minix 3: https://en.wikipedia.org/wiki/Minix_3#Architecture

A web based package manager (e.g https://tiny.slitaz.org/ ) could also make creating custom ISOs/images more user-friendly: https://groups.google.com/g/minix3/c/gs2z6m7Kj14
Similar to Cubic: https://launchpad.net/cubic


The acronym SOAP is defined as:

Serial: applications and its tasks (threads, are run mutually exclusive of any other processes. Technically, no other processes are in queue while one application is in run time. The exception would be queues for context switching, which occurs only as a reformat of the operating system image- and this would be only as frequent as the user toggles between applications. Developing a syscall process to allow context switching without restarting is a future goal. 

----
Inferno (based on Plan 9) 
----

https://en.wikipedia.org/wiki/Inferno_(operating_system)

https://www.vitanuova.com/inferno/docs.html

http://doc.cat-v.org/inferno/4th_edition/limbo_language/limbo 

One approach is similar to XiP ((https://en.wikipedia.org/wiki/Execute_in_place):

https://github.com/dboddie/inferno-freeze-slides/tree/main/pdf
"This paper explores an approach where Dis virtual machine code is retained (‘‘frozen’’) in flash
memory instead of being loaded into precious RAM.'

p.2: "When processing the code section of the module, two things stand out. The amount of memory used to store
the instructions is typically larger than the size of the corresponding code in the original file. In addition,
once the instructions have been decoded, they never change. This suggests that they could be retained in
flash memory in a pre-decoded form through a process of ‘‘freezing’’ at build-time."

https://dboddie.gitlab.io/inferno-diary/2023-08-22.html
Additional papers: https://github.com/dboddie/inferno-freeze-slides/tree/main/pdf
and https://9e.iwp9.org/9iwp9proceedings.pdf

------
Minix
------

 Minix video: https://youtu.be/MG29rUtvNXg?t=2462 
This experimental process uses:

"A manager to request a process (e.g. Old-FS) to get ready

Old-FS finishes its work and queues new work Manager creates New-FS process with new code LLVM puts tables inside New-FS listing its data objects New-FS contacts Old-FS and asks for state it needs The state is transferred one object at a time When all state is transferred, Third-FS is created It talks to New-FS and tries to recreate Old-FS If they agree New-FS becomes FS, else revert to Old-FS
....

Much better than Ksplice"

---
Symbian OS
---
![image](https://user-images.githubusercontent.com/76194453/213937722-b3ee3e59-0b18-4895-9d65-5409c3437bb4.png)

-----

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

---
Motivation
---
https://www.imdb.com/title/tt0037168/characters/nm0115558

https://www.imdb.com/title/tt0037168/?ref_=tt_ch
The Pearl of Death (1944)

"Dr. John H. Watson : Well, how... how does the, uh, the thing work?

Sherlock Holmes : Electricity. The high priest of false security."

https://step-dad.blogspot.com/2010/07/electricity-high-priestess-of-false.html 

" And with the blackout on our block last night that line from that fictional movie resonated quite solidly with all my family members even though they haven't seen that celluloid gem."
"Just the thought of having no air conditioning, no lights, no TV and no Internet had us sitting on the couch collectively having to make conversation that we would normally never have. "

The motivation of this project is algorithmic efficiency. Although assembly is understood to be "faster," efficiency is relativistic, based on the developer's experience in the context of novel hardware development. Thus, programmatic efficiency can, but does not always take priority. 

The other motivation of this project is autarkic design-"crade to cradle" here is defined as a solar powered energy harvester integrated on a PCB, and a finite number of photons between zero and infinity, required to produce, flip and modify a binary bit of data, in both the central processing unit, and the display (for user applications). 

Thus, this project adopts an Occam's razor approach of conceptualizing the simplest autarkic system. For reference:
Although assembly is understood to be "faster," efficiency is relativistic, based on the developer's experience in the context of novel hardware development. Thus, programmatic efficiency can, but does not always take priority.

https://conceptually.org/concepts/occams-razor

https://en.wikipedia.org/wiki/Occam's_razor

This logic, or approach, is useful in not just problem solving, but concept development. That is, this project isn't seeking to solve a problem, specifically. It could be argued that simpler computers are needed for certain tasks, and that technological convergence needs to deconverge (i.e smart phones should become dumbphones again, or there needs to be more dumbphone options in the market). But for the purpose of developing such a system, those arguments are irrelevant. That discussion  could be supplemental on a discussion or issue page. Feel free to raise it here, if the project encounters a philosophical fork in the road. As Yogi Berra once said, "if you encounter a fork in the road, take it." 

Why would I autarkic design parsimonious? Because all computers have all relied on a power input. Before the linux kernel, free software and open source needed a platform. Now open source can be use to develop more open source. In a way, linux is like a self-replicating machine. Thus, I am conscious to how power consumption is necessary to develop software. But that also reveals an odd aspect of linux accessibility:

"According to official statistics, a tad under half of the world population is not connected to the Internet. In Latin America, according to the most recent statistics, close to 30% of the population is not online. Different variables contribute to the problem of the digital divide, but these can be generally parsed into four categories: no coverage or services available; access is too expensive; a lack of digital skills; or, the Internet simply does not offer anything of interest. While the number of people connected does go up every year, the rate of expansion is fairly modest at about 2 or 3% annually, and at the current rate (which is actually slowing) it will take decades to get everyone online who wishes to be.'

https://www.rhizomatica.org/keeping-it-analog-a-framework-for-opting-out-of-connectivity/ 

The linux kernel was developed in 1991. It has been approximately 32 years since it was developed, and has gotten larger and larger over time, often to support many impressive features.

Imagine the world decided in 2023, that there are actually multiple  different approaches reflecting on this progress. On the on hand, you have mainline linux kernel that sees no issue- that perhaps more can be connected and manufacturing will eventually allow everyone who wants a computer to have one.

Another scenario is that there are already billions of computers available to develop energy efficient kernels for purpose-built hardware. What I mean by this is, a significant portion of mainline linux, whether it is a Linux Foundation sponsored project, such as Zephyr, or medium ground between RTOS and userspace-type desktop OS, that chooses to refocus their efforts in helping more users in the developing world get access to computing, whether or not they have internet access.  Thus there IS  an issue. It's like during Hurricane Katrina, and me going on National TV saying "Linus Torvalds doesn't care about powerless computer owners" (in places with no electricity, but also politically powerless) Thus offline OS development is still immensely important, because the above paragraph by Rhizomatica acknowledges the fact that just under half the world is not connected to the internet. This reveals another limitation of existing systems: Internet access also requires a reliable power source. This may sound obvious to a Westerner, but this reveals an underexamined component of open source development. 

If one reads some of the early writings of Eric Raymond and the Steven Levy, one might think that the early 90s were a time of much more cooperation across the political aisle. I am not implying or focusing on any public figure's political leanings, nor does it actually matter. What I am trying to emphasize, is the overall mood of open source and free software today. How many developers are interested in developing energy efficiency operating systems, to help more users run hardware that could be used to develop more open source? When one reads an article on even very pro-open source websites, like Hacker News, Slashdot, the Register, CNX Software, they are covering, for the majority, hardware afforded by users in wealthier countries, or users who can afford a system on a chip like a raspberry pi in South America. But these hardware are getting more power intensive. https://www.pidramble.com/wiki/benchmarks/power-consumption The Raspberry Pi A+ used 0.8 Watts. The Rpi4 uses over 5 Watts of power. Who is the Raspberry Pi really interested in catering to?

If you look at the early mailing lists and writings about the open source and free software movement, a lot of them were young pranksters and hackers wishing to develop an alternative to Microsoft and Apple. Eric Raymond says to a Microsoft employee in an elevator "I'm your worst nightmare." Of course there is an immense joy in creating something to break free from the need to use a proprietary software that has lots of spyware. If you watch the movie Revolution OS, there are anecdotes that confirm the mood against big corps: https://www.youtube.com/watch?v=jw8K460vx1c Free software sacrifices some intellectual property to give more people access (Bruce Perens at 3:37). In this way, I see energy autarkic Hardware design as a continuation of that movement in the 90s. Why? Revenge of the Nerds (pt.2 or 3 or 4 whichever era you've been in). Software has ruled Silicon Valley for 30 years. I think software  overstayed their reign for 10 years. The Teal Photon solar calculator was just produced 10 years after a 50lbs HP-9100A was manufactured in 1968. The Intel Claremont (a 32nm Pentium) was designed to be solar powered in 2011. There hasn't been a 2nd generation solar "computer" (a calculator is a computer, and a computer is a very, very complex calculator) in over 44 years, even though the Teal Photon only took 10 years to solar pwoer a scientific calculator. See: https://iotmote.substack.com/p/remaking-the-nokia-6110-and-psion From 2011, you could say that PowerFirst Hardware could have been developed and become more optimized. So here I am. Revenge of the Hardware Nerds. I am your worst nightmare. Doesn't have the same ring to it as in the 90s.

Now in FOSS they appear to be a divorced couple: 

"'His influence and involvement in Open Source advocacy has, needless to say, been greatly diminished and he is now best known as a notorious Internet crank, leaving Stallman Bruce Perens to fight the ninjas alone.[42][43] He's somewhat aware of his reputation, but still found a curiously egomaniacal way to respond to the charges.[44] The people currently running the Open Source Initiative are trying to politely exorcise his ghost."
https://rationalwiki.org/wiki/Eric_S._Raymond#Biting_the_hand_that_feeds_him_.28and_quite_a_few_others_as_well.29"

In retrospect, all that open source cooperation back then, sounded just like a marriage of convenience. They got the fame they wanted, and went their own ways. Wouldn't it be nice if they reunited, for old times sake, to show the world our country isn't as dysfunctional as it looks? Maybe it doesn't matter. There are two meanings of free software- liberty and gratis. The liberty side will say that the ability to share software should be a right of each owner. And that is true. The gratis meaning concerns the cost. This is a sticky, if not stickier issue. I think after the operating system became both freely available (as in 0) after 3 decades, that there is not enough priority in focusing on lower cost hardware. Why? Practically every new processor from Raspbery Pi to Intel is a 4 core chip. And only one is needed. So after the FOSS veterans got what they wanted, the Global South is still waiting. It's wealthy FOSS developers saying, "I'm giving my source code free away, if you can afford a PC! Good luck! Sorry can't help with that last part" Thank you for joining my platform! Thank you for leaving that other linux fork! Muammar Gaddafi's strategy for keeping his country under his control was to ensure each faction was weak and starved. Rewarding just a few top generals, the oracles of linux development can continue to beg Linus Torvalds and Intel for their blessing, while the lowest classes continue to suffer. If one were truly to believe in a egalitarian internet, the needs of the community must come first, however "basic" a minimum functional computation device can be developed.

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/c5f0a253-24c3-414c-ba1f-b07d2a081b57)

"The job of media is not to inform, but to misinform: Divert public attention from important issues and changes decided by the political and economic elites, by the technique of flood or continuous flood of distractions and insignificant information."

https://www.autocraticforthepeople.com/2012/07/noam-chomsky-top-10-media-manipulation.html

Noam Chomsky - "10 strategies of manipulation" by the media
https://www.demenzemedicinagenerale.net/pdf/14-10-strategies-of-manipulation.pdf 

"Renowned critic and always MIT linguist Noam Chomsky, one of the classic voices of
intellectual dissent in the last decade, has compiled a list of the ten most common and
effective strategies resorted to by the agendas “hidden” to establish a manipulation of the
population through the media.
Historically the media have proven highly efficient to mold public opinion. Thanks to the media
paraphernalia and propaganda, have been created or destroyed social movements, justified
wars, tempered financial crisis, spurred on some other ideological currents, and even given
the phenomenon of media as producers of reality within the collective psyche.

But how to detect the most common strategies for understanding these psychosocial tools
which, surely, we participate? Fortunately Chomsky has been given the task of synthesizing
and expose these practices, some more obvious and more sophisticated, but apparently all
equally effective and, from a certain point of view, demeaning. Encourage stupidity, promote a
sense of guilt, promote distraction, or construct artificial problems and then magically, solve
them, are just some of these tactics.

1. The strategy of distraction
The primary element of social control is the strategy of distraction which is to divert public
attention from important issues and changes determined by the political and economic elites,
by the technique of flood or flooding continuous distractions and insignificant information.
distraction strategy is also essential to prevent the public interest in the essential knowledge
in the area of the science, economics, psychology, neurobiology and cybernetics.
“Maintaining public attention diverted away from the real social problems, captivated by
matters of no real importance. Keep the public busy, busy, busy, no time to think, back to
farm and other animals (quote from text Silent Weapons for Quiet War ).”


So my thinking is, why should I contribute to this giant database project or some super high-level programming language front end that has hundreds of dependencies that someone will never be able to experience themselves unless they are running a quad core 15 watt i3? I really have little interest in that. I think there is enough software for users to navigate their way across the internet to provide services. The phrase "hardware is hard" certainly got its name from this fear by software developers, that it is not just technically hard, but economically hard. I can't blame anyone. But with more awareness, perhaps this can change. Until then, it is still Victorian England in the designer market.

There is a tale of two SBCs. There is the Global North and the Global South. The global north is anyone who can afford a raspberrty pi, and a display, and a keyboard, and a power outlet:  [https://www.youtube.com/watch?v=TifReX38I8M](https://youtu.be/TifReX38I8M?t=123)  The South needs the metaphorical cheaper chicken. ![image](https://user-images.githubusercontent.com/76194453/212409691-5e93354b-5f24-492b-99b1-580a005fd00c.png) This isn't to say that some may only be able to afford a monochromatic laptop if some charity gave it to them for free, and they shouldn't be able to own one more powerful. No, that's not what I'm saying. What I'm saying is that at this pace, it will not be possible to manufacture a system that runs at 5 watts for everyone in the world, because no solar panel can fit on a lpatop that can power 5 watts of cpu power.  

https://networkcultures.org/wp-content/uploads/2015/10/0585-INC_NN10-totaal-RGB.pdf

p.30 "The earliest versions of this reactionary fantasy emphasised the hierarchical division of
labour under Fordism. Although many skills were destroyed by the industrial system, new
specialisms were simultaneously created. Within Fordism, engineers, bureaucrats, teach-
ers and other professionals formed an intermediate layer between management and
the shopfloor[62]. Unlike most employees, this section of the working class received high
incomes and escaped subordination to the assembly-line. Fearful of losing their limited
privileges, some professionals became enthusiastic supporters of reactionary modern-
ism. Instead of fighting for social equality, they dreamt of founding a new aristocracy: the
technocracy"

p.35 

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/76528e49-803f-45d9-85b9-9667738098a5)


[62] | See Tony Elger, ‘Valorisation and “Deskilling”: A Critique of Braverman’, Capital & Class 7 (Spring 1979), pp. 58-99.

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/f5bc6a03-fdd9-499f-a303-2b743ff4b335)

The material-scarcity problem in the "developing" and "undeveloped world" is not necessarily scarcity to Raspberry Pi's. Even if 3 billion Raspberry Pis could be air-dropped for every person on earth without a PC, the scarcity issue that remains is power. Therefore solar-powerable mobile devices are deliberately avoided by the technocratic design class, if Barbrook's thesis remains true to this day.

----
640,000 transistors ought to be enough for anyone
----

"There are two types of people: Those who think VR will change the world—and those who haven’t tried it yet." -Meta Blog:
https://www.meta.com/en-gb/blog/quest/reality-labs-research-display-systems-siggraph-2023-butterscotch-varifocal-flamera/

There's actually three, or four, types of people. The third person, says, wait, VR is Silicon Valley's latest desperate attempt to get people to do away with their Mac M1s and M2s to buy more transistors to interactively compose a text file in 3D space.

The amount of transistors needed to produce a VR headset is going to be in the hundreds of billions.

The first linux operating system ran on the Intel 30386, which had 275,000 transistors.

https://www.quora.com/Why-was-it-so-hard-for-Unix-to-run-on-a-386-CPU-before-Linux
A great point is that UNIX  was still a major competitor (it still is, but the ecosystem changed), until Linux came along. That much software could run on a 386 is no small fact. 

Operating systems such as Slackware <9.1  and Slitaz, could run on it: 
https://tiny.slitaz.org/ 
https://distrowatch.com/?newsid=00777
[https://i.redd.it/9x2py4ba6rg41.jpg ](https://www.reddit.com/r/retrobattlestations/comments/f3gj45/slackware_112_1994_on_my_386sx40/)

Chips like these are more than powerful to send text messages, read bulletin board news, even make voip sessions. Foundries have plenty of wafers to produce a small 275,000 transistor chip for every person on earth. 

Obviously, most people today cannot rely on a 386 processor for most work (even an ARMv6 Raspberry Pi Zero v1.3 is far faster); however, Intel and Ambiq Micro have manufactured solar powered processors that have more FLOPS than a 80386, yet few chip designers have sought to harness this capability of the leading edge foundries to deliver solar powerable Nokia dumb phones and basic terminals for low cost and "low-tech" accessibility for many more individuals in the remotest villages:

https://apnews.com/article/offgrid-solar-electrification-indonesia-0991d77d68f879c4daa12e7d3dfd97ee

What LED lights could do in 2009 (https://archive.nytimes.com/green.blogs.nytimes.com/2009/09/23/bringing-solar-power-to-africas-poor/)
<22nm CPUS can do on solar power in 2022. Ambiq Apollo 5 SoCs are said to be in development with an interest to run linux on 12nm, and 6nm (see: https://user-images.githubusercontent.com/76194453/246301923-84264e2a-edab-47a0-8731-054d0bc3d53b.png). Thus, the movers and shakers in bridging the Digital Divide are not AMD or Intel, who have had the resources to develop a true OLPC, but the "small startups", for lack of a better word. It remains to be seen whether the next few years will result in an influx of portable, and autarkic mobile computers, or, whether this product will be catered to an elite group of tech-consumers. The foundry space is there. The choice, however, is whether the tech-bros at Meta want the foundries to produce their VR chipsets instead of trying to connect the rest of the world first. 

Thus, Chomsky's strategy #2 applies with new tech:

"2. Create problems, then offer solutions

 This method is also called “problem -reaction- solution.”
 It creates a problem, a “situation” referred to cause some reaction in the audience, so this is the principal of the steps that you want to accept.
 For example: let it unfold and intensify urban violence, or arrange for bloody attacks in order that the public is the applicant’s security laws and policies to the detriment of freedom.
 Or create an economic crisis to accept as a necessary evil retreat of social rights and the dismantling of public services."

 The problem is that your Apple Silicon circa 2020 is too old. The Solution is a VR Headset (so you can also forget about the real world):

https://www.reddit.com/r/mildlyinteresting/comments/11p1gzt/homeless_man_in_silicon_valley_with_vr_headset/

https://en.wikipedia.org/wiki/Experience_machine#In_fiction

"It also is a running theme of the 1999 film The Matrix.[13] Agent Smith's account of the early history of the Matrix includes the idea that humans reject a virtual reality that offers them paradise; however, later his informant Cypher is willing to betray his colleagues because he would prefer to be reinserted into an (admittedly less perfect) Matrix as a wealthy and successful man than continue to live in the harsh realities outside the simulation."

How has media changed in the past 180 years? Charles Dickens first visited the United States in 1842:

"Charles Dickens came away from his American experience with a sense of disappointment. To his friend William Macready he wrote "this is not the republic I came to see; this is not the republic of my imagination" (Letters, 1974, v. 3, p. 156). On returning to England Dickens began an account of his American trip which he completed in four months. Not only did Dickens attack slavery in American Notes, he also attacked the American press whom he blamed for the American's lack of general information. In Dickens' next novel, Martin Chuzzlewit, he sends young Martin to America where he continues to vent his feelings for the young republic. American response to both books was extremely negative and passions flared. Dickens made amends during his second visit to America in 1867-68 with a conciliatory speech in New York."

https://www.charlesdickenspage.com/charles-dickens-in-america.html 
How informed are Americans today? https://thehill.com/opinion/education/522725-how-much-do-americans-know-about-the-news/ 
https://www.statista.com/chart/28490/news-consumption-on-social-media/ https://www.youtube.com/watch?v=FFytCr0VKnU

https://www.youtube.com/watch?v=K4XA6amZ8mk 

"Similarly, in 1944 economist Ludwig von Mises described Brave New World as a satire of utopian predictions of socialism: "Aldous Huxley was even courageous enough to make socialism's dreamed paradise the target of his sardonic irony."[39]"

"The highest transistor count in a single chip processor is that of the deep learning processor Wafer Scale Engine 2 by Cerebras. It has 2.6 trillion MOSFETs in 84 exposed fields (dies) on a wafer, manufactured using TSMC's 7 nm FinFET process.[2][3][4][5][6] (2019)" 

With each person having access to telecommunications and information, the world can become more informed, although it is not to suggest that it will lead to utopia or worldwide education/literacy. Rather, the means of access to information can be abundantly produced with no significant barriers to access whenever it is needed- long-range ad-hoc wireless networks as in Spain's Guifi grid (https://en.wikipedia.org/wiki/Guifi.net), and solar powereable PCs running on near/sub threshold voltage (see Ambiq Apollo4 and Intel Claremont). 

One reason developers are probably afraid to make computing extremely accessible with no barrier to entry, is the existential risk to their own occupation:

Companies aware of the WFH trend are already seeking to get the lowest labor costs by outsourcing their workforce overseas. If an employee can work from home, an OLPC (fast enough to do customer service) suddenly has 3 billion extra candidates. Yet, the moral importance of connecting more of the world to the digital commons is far more important than the risk to one's job security. This is what distinguishes the the middlemanagement sympathetic to the shop floor to that of the technocracy that wants to keep the candidate pool as limited as possible. One of the reasons I believe it is important to develop a well-rounded skill set is so that one isn't limited in their craft. While general labor often times involves a lot of lifting, the adaptability of a job in general labor still is a flexible type of work, something that skilled trades become far more inflexible as technologies evolve:

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/28fbfae3-93f2-418d-a77e-ad6d5dcb599f)

The pay scale is of course, another source of fear. The structure of employment and pay, especially with AI leading to further loss of employment, is likely to create a new demand for job security when automation requires less maintenance. It is very possible that existential crises will distill a new form of dialectical materialism, where most forms of high-tech progress gets re-appraised in a fire sale. Social networks that get absorbed by corporate raiders often get sold for pennies on the dollar:

"Here is how platforms die: first, they are good to their users; then they abuse their users to make things better for their business customers; finally, they abuse those business customers to claw back all the value for themselves. Then, they die."

https://boingboing.net/2023/08/02/cory-doctorows-new-book-on-beating-big-tech-at-its-own-game.html

One wonders how much resale value hardware like VR, AR glasses and even self-driving cars will have when the parts cannot be reused without the entire product being totalled: [ https://www.businessinsider.com/why-tesla-cars-get-totaled-insurance-repair-costs-2023-6](https://www.caranddriver.com/news/a42709679/tesla-insurance-fixes-expense/)

Thus, the high-tech world of disposable everything creates a world where backyards will one day becomes the next NIMBY landfills due to the actions of high-mass-produced, un-interoperable, and short-cycle hardware. 

As Pierre Levy once joked,

"Okay, so Plato's Phaedrus is a very important dialogue. He said the exact same thing that you are about to say, but not with machines—with writing. He said, "What? You are going to put all the information we have into a library?" So, you have a library—say, the Library of Alexandria—and the totality of human knowledge is encoded here, and so we don't need professors anymore. Everyone is becoming unemployed. It's terrible! [laughs]. You know, there were more than 3,000 people in Paris in the 18th century whose job it was to bear water to people. Then, they invented plumbing, and ah! They lost their jobs! It's terrible!"

https://www.vice.com/en/article/ypw9vw/how-the-internets-collective-human-intelligence-could-outsmart-ai

Levy understands great changes in collective intelligence intiatives- I'm not referring to super high tech cycles like Stalin in Silicon Valley (as Barbrook describes), but low-tech ubiquity to the point of a universal basic phone, and universal basic computer that can run on extremely low power, so low a tiny amount of sunlight can display text, make phone calls, and send emails. When the flow of information is frictionless, then the best information can be sought and by the best and brightest. 

"People say, "We are going to make computers very smart," and they get all the funding. But what about making humans smarter? Collective intelligence is a research project about making people smarter with computers, and not making computers smarter than people. That's the real definition of collective intelligence."

Thus what Levy is suggesting is, build a ubiquitously connnected world, allow the world to increase their collective intelligence (apparently by assuming more will see the signal in the hive consciousness, through the noise and echo chambers and chain mail and fake news) because 8 billion plus independent agents will autonomously improve their surroundings at a far more effective rate than a world where augmented AI along with trillions of IoT devices try to serve the rich and surveil the poor.

Which isn't to say there isn't an ability for IoT to serve each human, but IoT is not nearly as a basic digital twin as a 2D pixelated screen that can send alphanumeric commands across an IPv6 internet. Thus the first intelligent agent in all independent agent units should always be the human, first and foremost. An IoT can be the eyes and the ears of an agent, enhanced sentinels, but it is not, in most, if not all cases supposed to substitute the driver, as can be seen in many autonomous vehicle flaws/accidents. 

Collective intelligence appears to share concepts similar to "Differential Intellectual Progress," as proposed by Luke Muehlhauser and Anna Salamon:

"Informal discussion

Paul Christiano believes that while accelerating technological progress appears to be one of the best ways to improve human welfare in the next few decades,[5] a faster rate of growth cannot be equally important for the far future because growth must eventually saturate due to physical limits. Hence, from the perspective of the far future, differential technological development appears more crucial.[6][unreliable source?]

Inspired by Bostrom's proposal, Luke Muehlhauser and Anna Salamon suggested a more general project of "differential intellectual progress", in which society advances its wisdom, philosophical sophistication, and understanding of risks faster than its technological power.[7][unreliable source?][8][unreliable source?] Brian Tomasik has expanded on this notion.[9][unreliable source?]"

from (https://en.wikipedia.org/wiki/Differential_technological_development#Informal_discussion) 

 [6] Christiano, Paul (15 Oct 2014). "On Progress and Prosperity". Effective Altruism Forum. Retrieved 21 October 2014. https://forum.effectivealtruism.org/posts/L9tpuR6ZZ3CGHackY/on-progress-and-prosperity

[7] Intelligence Explosion: Evidence and Import (2012): https://web.archive.org/web/20141026105011/http://intelligence.org/files/IE-EI.pdf

[8] Muehlhauser, Luke (2013). Facing the Intelligence Explosion. Machine Intelligence Research Institute. Retrieved 29 November 2013. https://intelligenceexplosion.com/2012/ai-the-problem-with-solutions/

[9] https://longtermrisk.org/differential-intellectual-progress-as-a-positive-sum-project/ "Differential Intellectual Progress as a Positive-Sum Project"
https://longtermrisk.org/files/Differential_Intellectual_Progress_as_a_Positive_Sum_Project.pdf


In Martin Ford's 2015 "Rise of the Robots" (Also the name of a futuristic Super Nintendo Game that I read about in _Nintendo Power_ (the only subscription I had at the time) in the late 90s), 

"What are the jobs of the future? How many will there be? And who will have them? As technology continues to accelerate and machines begin taking care of themselves, fewer people will be necessary. Artificial intelligence is already well on its way to making "good jobs" obsolete: many paralegals, journalists, office workers, and even computer programmers are poised to be replaced by robots and smart software. As progress continues, blue and white collar jobs alike will evaporate, squeezing working -- and middle-class families ever further. At the same time, households are under assault from exploding costs, especially from the two major industries-education and health care-that, so far, have not been transformed by information technology. The result could well be massive unemployment and inequality as well as the implosion of the consumer economy itself. [1]"

"The Guardian's review points out the book gets more speculative as it goes on, and states: "Although it may be difficult to overstate the dangers posed by the new technology", Rise may have managed to do so, but is regardless well worth reading.[6] "

https://en.wikipedia.org/wiki/Rise_of_the_Robots_(book)

https://www.latimes.com/books/jacketcopy/la-ca-jc-martin-ford-20150524-story.html

https://www.youtube.com/watch?v=NZjvYFFVr1s

Pierre Levy's non-resistance to technological change, as demonstrated by his amusement at the ancient professors fear of the embrace of writing and books Library of Alexandria, and his embrace of plumbing in 18th century Paris, suggests non-resistance to accelerationist beliefs:

https://en.wikipedia.org/wiki/Accelerationism 

"Accelerationism is a range of Marxist ideas in critical theory—and reactionary ideas in right-wing ideology—that call for the drastic intensification of capitalist growth, technological change, infrastructure sabotage and other processes of social change to destabilize existing systems and create radical social transformations, otherwise referred to as "acceleration".[1][2][3][4] It has been regarded as an ideological spectrum divided into mutually contradictory left-wing and right-wing variants, both of which support the indefinite intensification of capitalism and its structures as well as the conditions for a technological singularity, a hypothetical point in time where technological growth becomes uncontrollable and irreversible.[5][6][7]"

Alarmist concerns aside, the placement of any single individual in the spectrum should not be assumed. However, this draft explores to what extent that current changes in AI are embraced, and the valves that increase access to internet are resisted by the technocratic class.

"Differential technological development is a strategy of technology governance aiming to decrease risks from emerging technologies by influencing the sequence in which they are developed. On this strategy, societies would strive to delay the development of harmful technologies and their applications, while accelerating the development of beneficial technologies, especially those that offer protection against the harmful ones.[1][2]"

Therefore, there is a clear decision-making process by well-funded venture capitalists on the direction of semiconductor design. They have decided that AI is more important than solar power, therefore this essay/draft can serve as a purely contrarian exercise into questioning why that direction is considered to have more merit. 

---
Tracing the Morris-Benjamin-McLuhan-Barbook Path
---

Walter Benjamin's 1935 “The Work of Art in the Age of Mechanical Reproduction,” could almost be considered a pre-cursor to McLuhan's 1964 essay, "The Medium is the Message".

https://en.wikipedia.org/wiki/The_Work_of_Art_in_the_Age_of_Mechanical_Reproduction I have been thinking of this topic on mass production, because, art and telecommunications began to share mass-production as a more common medium in the 20th century:

"and that in the age of mechanical reproduction and the absence of traditional and ritualistic value, the production of art would be inherently based upon the praxis of politics. "

"In "The Work of Art in the Age of Mechanical Reproduction" (1935), Walter Benjamin presents the thematic basis for a theory of art by quoting the essay "The Conquest of Ubiquity" (1928), by Paul Valéry, to establish how works of art created and developed in past eras are different from contemporary works of art; that the understanding and treatment of art and of artistic technique must progressively develop in order to understand a work of art in the context of the modern time."

I already want to bridge an even earlier critic, to the train- William Morris (1834-1896): https://en.wikipedia.org/wiki/Arts_and_Crafts_movement#Critique_of_industry and Owen Jones (1809–1874)

"Jones declared that ornament "must be secondary to the thing decorated", that there must be "fitness in the ornament to the thing ornamented", and that wallpapers and carpets must not have any patterns "suggestive of anything but a level or plain".[14] A fabric or wallpaper in the Great Exhibition might be decorated with a natural motif made to look as real as possible, whereas these writers advocated flat and simplified natural motifs. Redgrave insisted that "style" demanded sound construction before ornamentation, and a proper awareness of the quality of materials used. "Utility must have precedence over ornamentation."[15]"

The rise of feature-creep and 3D graphical performance today in operating systems is comparable to the "ornament" that Morris and Jones criticized, which users must pay a premium for. Even if the most underpowered Qualcomm or Exynos Chip uses a MaliGPU driver, it taxes the battery life far more than a 2D, spartan-like Nokia phone with Symbian S60. 

Barbrook, likewise, refers to Minitel as a "dumb terminal," but not disparagingly. Rather, he higlights the success of an internet that was able to connect many people, without ornament. While Minitel was of an era, the technology today does not need to evolve so quickly as to become obsolete- while landlines are certainly outdated, 40-50 year old protocols that still exist today could be paired with more efficient semiconductors powering 2d operating systems, low-power screens, and wireless radios.

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/afffe495-3b5a-494b-8112-96ff5989ba9e)

Games and Telecommunications?

"This emphasis on restraint notwithstanding, Stone wants to question the idea that making and playing games in a sustainable way is a question of self-denial. “It's this philosophical push that the environmental movement doesn't have to be about cutting things away,” she says, citing Kate Soper's book Post-Growth Living: For an Alternative Hedonism. “[It's] actually trying to find pleasure in sustainability.” While it might discourage power-hogging graphics techniques such as ray-tracing, games that run on renewable power can also nurture “different forms of experimentation, different things that come about through whatever constraints. Because there are always constraints. Even if you're working at a triple-A studio, there's something constraining the game and making it the way that it is.” " 

https://www.techradar.com/features/the-quest-for-the-solar-powered-gaming-console 

Emphasis on gaming, when Rhizomatica states over 30% of the world has no internet, surely the development of games should take secondary priority over village to infrastructure, much like word processing and BBS was used before MMORPGS?

The roles each theorist was not solely of criticism- some were Quality Assurance- as in Morris. Others were more observers- but each highlighted generational changes to how both information and products were accessed or divided.

"In a culture like ours, long accustomed to splitting and dividing all things as a
means of control, it is sometimes a bit of a shock to be reminded that, in opera-
tional and practical fact, the medium is the message." McLuhan's introductory paragraph begins- thus the frame of the argument begins. Is the medium interesting? Who knows who will want the message? Maybe some reject the message, because the medium is too expensive.

I take the same contrarian approach as Richard Barbrook did at a guest lecture in 1998 at Fordham University, following the tradition of Marshall McLuhan, from his essay, "The Owl of Minerva Flies at Dusk":

"In 1998, as this speculative frenzy was reaching its peak, I was
contacted by Lance Strate from Fordham University in New York who was organising the
50th anniversary celebration of the first time that Marshall McLuhan had taught at this
esteemed institution. ‘We’ve got lots of academics giving papers at our event,’ he told me,
‘but they’re all very respectable. I was wondering whether you could stir things up by creating a suitably wacky McLuhan-style ‘thought probe’ for the conference?’ Intrigued by Lance’s request, I set to work on the lecture which was the starting point for the second
article in this book. Back in the 1960s, McLuhan’s thought probes had provoked his audiences with wild assertions which encouraged them think about contemporary reality in a different way. For instance, in one of his most famous slogans, he emphasised that people
were more influenced by the psychological impact of communications technologies than
their ideological content: ‘the medium is the message’. Much to his delight, McLuhan
had succeeded in outraging both the defenders of bourgeois morality and the devotees of
Bolshevik politics. My task for Lance was now to devise a similarly contrarian proposition.
Since the conventional wisdom in the late-1990s was that the Net was the apotheosis of
free market capitalism, I thought why not argue the exact opposite? The faith of the Californian Ideologists in the unilinear march of history towards hi-tech neoliberalism had long reminded me of Stalinist hymns to the inevitable victory of ‘really existing socialism’
during the Cold War. The widespread flouting of copyright could easily be interpreted as
the imminent demise of commodity production within the emerging information economy. Delighted that I’d found the perfect thought probe, I was ready for my intervention at Fordham’s McLuhan conference. When my turn came, I went up to the podium and began my talk by loudly proclaiming: ‘At the height of the Cold War, the US military funded the creation of the only working model of communism in human history: the Internet!’"

Thus my "thought-probe" is my pastiche (if you view the glass half-full) of the NBC telethon after Hurricane Katrina in 2005. As an environmentalist, I believe in recycling media (détournement) to adapt meanings for an era where there can be a relevant analogy. While it can be said that Ye's statement did not age well, the moment was a rare act of vulnerable and true espression that was not just a hiccup in the annals of history. It did not occur out of nowhere, and therefore its cache resonated because others identified with it:

"Though unrehearsed and emotionally fueled, Kanye’s speech wasn’t nonsense. It was messy because grief is messy. It was complex because the truth is. He’s expected to say something along the lines of whatever passive and inoffensive text Myers read off of the teleprompter, but instead he says, “I hate the way they portray us in the media.” He gives examples. He confesses his own complicity. He states facts. He presents a logical conclusion. I often consider the conditions that create revolutions, and the acts that might be deemed revolutionary. How an average person, not otherwise a political actor, might be an agent of change. How maybe resistance looks like interruption."

^from https://www.thecut.com/2018/03/i-think-about-this-a-lot-kanye-west-at-the-katrina-telethon.html

While the sentence may appear to be a fragment, the low battery indicator is meant to indicate "the powerless", both literal and figurative. In that powerless could be a powerless person, or a person who has an otherwise functioning laptop or cell phone, but with low battery.

Marshall McLuhan's "The Medium is the Message" could be combined with Barbrook's "‘At the height of the Cold War, the US military funded the creation of the only working model of communism in human history: the Internet!’" to suggest that "the message is not accessible to all, because the medium is not accessible to all." It thus could refute the 2nd statement, since it was not completely successful. However, that may have been the intention, as McLuhan also wasn't interested in playing either side.

https://web.mit.edu/allanmc/www/mcluhan.mediummessage.pdf

As the internet arrived in the 90s to the masses, journalists began to write about the commercialization of Linux:

https://archive.nytimes.com/www.nytimes.com/library/tech/99/10/biztech/articles/18linu.html

"Others disagree. "Only the trade press is really squeaking about this," said Eric S. Raymond, president of the Open Source Initiative, a programmer group, because it makes a good story hook when you have nothing real to write about and the advertising department is pressuring you to make closed-software vendors look good.

Raymond added: "The actual Linux developers know better. Fragmentation isn't going to happen, because developers outside of the Linux distributors effectively control all the key pieces." That is because Torvalds and a small group of his colleagues control the Linux standard and subject all modifications to peer review."

Linux was a very clever marketing campaign, something thought of by someone like Don Draper, or Apple's marketing department. 

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/36c7ae4a-37f0-4df0-beef-de240af6fe1c)

Thus Linus is selling Happiness, in a libertarian, neo-liberal market. It certainly works as a [cover](https://www.wired.com/2003/11/linus/):

https://www.computerworld.com/article/2566721/commercialization-of-linux-helps-microsoft--exec-says.html

---
Camping in No-Man's Land, with Academic Dispassion
---

It's one thing to be a fence-sitter, where a moderate is unsure. It's another thing entirely to be perfectly content to observe the war from the academic armchair. Yet, in a place perceived to be so dangeous as a no-man's land, it turns out the trenches that McLuhan and Barbrook found have actually been abandoned since the end of WWI in 1917*. Thus, it is somewhat evolved to take this opinion, where the rest of the world still believes in taking a side, no matter the cause. 

*Technically it hasn't been, although virtue signalling from the comfort of one's basement can often sound tinny. Susan Sontag Directed Waiting For Godot in Sarajevo in 1993. _The Hurt Locker_ was filmed in Jordan, near the Iraqi border, in 2007. Going into or near a warzone to create art takes courage, and creating a play within a play is an effective technique of farce. https://en.wikipedia.org/wiki/Farce 

Wake me up when the AI debate is over. My boredom is not unlike Mr. Burns during WWII: [https://www.youtube.com/watch?v=rldtGYBODrc](https://youtu.be/rldtGYBODrc?t=38)

I think of McLuhan and Barbrook as Situationist-like Don-Drapers. They pose a question, but one that doesn't promote the product, but acknowledges the tradition:

"The Most Radical Gesture is the first major study of the Situationist
International, a revolutionary movement of extraordinary ambition and
influence whose reflections on art, everyday life, pleasure, spontaneity,
the city, and the spectacle have ensured it a vital, but largely hidden, role
in the development of twentieth-century culture and politics.... 
...It suggests that Baudrillard’s reflections on hyperreality are impoverished
reworkings of the situationists’ critical analysis of capitalist society as a
spectacle, and challenges postmodern denials of meaning, reality, and
history by showing that postmodernism itself depends on a tradition which
completely undermines the purposeless pessimism it promotes."
from:
https://monoskop.org/images/2/24/Plant_Sadie_The_Most_Radical_Gesture_The_Situationist_International_in_a_Postmodern_Age.pdf

p.12

"The spectacle is the ‘materialization of ideology’;10 a
society in which the particular perspective of the bourgeoisie is
given a concrete form. It is a society asleep, in hibernation or a state
of suspended animation, for which ‘ideology is no longer a
historical choice, but simply an assertion of the obvious’.11
This absolute realisation of commodity relations produces an
entirely inverted world, in which everything ‘that was directly lived
has become mere representation’,12 a ‘dull reflection’13 of itself.
Mystified by this removal, it is difficult to understand why the world
appears to be so whole, natural, and unremarkable, yet is so
extraordinarily difficult to really engage and feel at home in. ‘The
spectator feels at home nowhere, for the spectacle is everywhere’,
and areas of life which were once untouched by the logic of the
commodity form are now possible only within it."

I have been thinking about the observation of spectacle during the high-profile debates between ex-AI researchers, now critics who believe in just "safety" or "speed bumps" and AI researchers without any restriction.

Much like any other political theater, the critics of AI and the State of the Art (SOTA) researchers engage in a spectacle for all to watch, and yet, both parties benefit, as if in a symbiotic relationship, to the exclusion of other research fields cast aside. While the benefactors of AI research are certainly interested in developing AI to save cost (through automation, downsizing, it is very curious to see how often the most prominent critics are portrayed in the media as framing the conversation between AI and anti-AI, as opposed to representing other non-scientific fields as in the humanities, arts, and non-AI dependent technologies.

During the 2016 campaign, there soon emerged [criticism](https://www.forbes.com/sites/brettedkins/2016/12/13/trump-benefited-from-overwhelmingly-negative-tone-of-election-news-coverage-study-finds/?sh=3520a4fd3202) that the media focused too much on certain candidates, with some going so far as to say it resulted in free publicity. It appears that the media is interested in covering AI with the same habituation, claiming it is news and thus worthy of coverage. At the same time, one can wonder, what if AI were simply ignored? Could the public develop other interests with a balanced focused on other topics? 

To question the utility of SI in the contemporary era, it is also important to examine its origins: https://github.com/users/hatonthecat/projects/3?pane=issue&itemId=35138100 

---
The Cyber dérive
---

https://en.wikipedia.org/wiki/Psychogeography#D%C3%A9rive

"Contemporary psychogeography

Along with détournement, one of the main Situationist practices is the dérive (French: [de.ʁiv], "drift").[3][5][7] The dérive is a method of drifting through space to explore how the city is constructed, as well as how it makes us feel. Guy Debord defined the dérive as "a mode of experimental behavior linked to the conditions of urban society: a technique of rapid passage through varied ambiances."[15] He gave a fuller explanation in "Theory of the Dérive" (1956), first written as a member of the Letterist International:

In a dérive one or more persons during a certain period drop their usual motives for movement and action, their relations, their work and leisure activities, and let themselves be drawn by the attractions of the terrain and the encounters they find there… But the dérive includes both this letting go and its necessary contradiction: the domination of psychogeographical variations by the knowledge and calculation of their possibilities.[16]

The dérive's goals include studying the terrain of the city (psychogeography) and emotional disorientation, both of which lead to the potential creation of Situations.[16]"

A proliferation of psychogeographical groups in the 90s and early 00s was credited to the re-emergence of the London Psychogeographical Association. evoL PsychogeogrAphix 2003

Since the 1990s, as situationist theory became popular in artistic and academic circles, avant-garde, neoist, and revolutionary groups emerged, developing psychogeographical praxis in various ways. Influenced primarily through the re-emergence of the London Psychogeographical Association and the foundation of The Workshop for Non-Linear Architecture, these groups have assisted in the development of a contemporary psychogeography.[17] Between 1992 and 1996 The Workshop for Non-Linear Architecture undertook an extensive programme of practical research into classic (situationist) psychogeography in both Glasgow and London. The discoveries made during this period, documented in the group's journal Viscosity, expanded the terrain of the psychogeographic into that of urban design and architectural performance. Morag Rose has identified three dominant strands in contemporary psychogeography: literary, activist and creative.[18]:29"

Much space today is virtual, and online. Thus the Cyber Dérive.

---
In the 60s, it was the one-way TV. In the 90s, it was the 2-way Internet. The advertising "defender of the free world" can be re-examined since today linux is disproportionately focused on software, and not hardware. In that way, it seeks to downplay and distract attention away from the medium (since it is not accessible to all), towards the message. Thus it is offering the promise to the medium, the same way Starlink is promising internet access to all. But would anyone want their internet to run under a single company, if given the chance? Linux is the message; the medium exists in a walled garden, and the messsage, even if it were accessible, may not even be applicable to those who want it. Thus, for all those who cannot afford the internet, must rely on the newspaper, or the ancient herald:

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/84481e5e-d208-489b-aea5-9cbd68548a1a)

Apple computer shows that a vertically integrated hardware company (VMS is the proper term, which stands for vertically integrated marketing) has benefited from the reality distortion field" https://en.wikipedia.org/wiki/Reality_distortion_field

The success of Linux shows that kernel, OS, and application software ecosystems can also be a vertically integrated marketing system and benefit from the reality distortion field (albeit to a much a much more technical crowd).

Hackaday wrote "The State of the SBC Interface Ecosystem: Is it Time to Design a Standard?" 10/2022: https://hackaday.com/2022/10/05/the-state-of-the-sbc-interface-ecosystem-is-it-time-to-design-a-standard/ 

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/1524c53d-6737-432b-8c6a-dd7fbb05c61e)

One can apply standards to many components of a hardware, and even while 2 competing standards may never reach an agreement, let alone 14, it is a question that even a non technical person can ask: "Can we get along?"

---

There is an emphasis on "smart"technology. "Smart" is a buzzword for new, when it necessitates administrative control over user agency. What is overshadowed by smart is the resourcefulness of dumb technology to allow the smarter user  to exercise agency. From Nathan Schneider's "Homesteading on a SuperHighway: THe California Ideology and Everyday Politics, he deconstructs the California ideology by citing earlier writings forseeing its decline: 

"As the Californian Ideology’s anti-politics established itself on the West Coast, Agre was inverting
it at MIT, calling for technology that invites people into developing skills through everyday politics. He
concludes his essay “The Practical Republic”—the final essay listed on his faculty website before his sudden
departure from public life—like this: “technology is not central; what is central are the choices that we make,
each of us, in laying claim to the rights and responsibilities of citizenship in our own lives” (Agre, 2004,
“Citizenship”). The technology that we need is technology that does not take or demand credit. brown seems
to forget about Instagram on summoning her community there; the homeplace becomes the subject."

from https://ijoc.org/index.php/ijoc/article/view/19342/4234 

Technology that does not take or demand credit, by definition, is a dumb phone, a dumb terminal. A smart phone takes notes, "the delay has been logged", and "notes the time":

https://www.youtube.com/watch?v=S_Yyzqx7hhs



A similar parallel can be seen in the kernel development community. While ostensibly, kernel maintainers are the core of most widely used operating systems of today (Android, linux servers), they also play a role as the sysadmins of operating systems and limitations of hardware that frame the user experience. 

Thus, as in the phrase "Wag the dog", is software ruling hardware, or hardware ruling software? 

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/b30627fd-2e64-4048-9924-81d49ace2752)
 $4B in research is towards SaaS, which could be anything from AI LLMs to mail-to-order Rx apps. By contrast, only $1.3 B (1/3rd) is directly towards hardware. And these are just the startups. While other categories might classify as hardware (such as energy and med devices, there is no indication that renewable mobile devices with integrated solar panels are on the roadmap anywhere.

![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/16c3671c-9cf8-45fc-ab90-840fc67835e1)

While anyone can create a kernel and use any combination of kernel modules, there is still a walled garden effect with ecosystems. GPL and BSD are two types of licenses, and enforcement and forks are another issue. 

Since this repository is about kernels, I will circle back to the original focus: A comic can best explain how kernel processes work:

https://www.oilshell.org/blog/2020/04/comics.html
![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/234bca03-75af-48ed-8344-78f38322b32a)

While application processors offer a userspace environment, its processes, at their core, are very deterministic. The above caption suggests that the machinations of kernel development, are anything but simple. While userspace does allow for some limited navigation, in a poorly designed, bloated operating system, the user is at the mercy of the kernel space (and its design). This isn't to suggest that kernels are bad-in fact these notes wouldn't be possible with a misbehaving kernel supervisor. What these notes seek to explore, however, is how much supervison do users really need, when they can choose more application-specific operating systems, ones that can provide more efficiency, not just in energy (shutting down large swaths of unused kernel drivers), but improving focus until the inevitable context switch is needed (for both the user and the kernel)? To that, I would suggest kernel development be more tailored to individual applications, hence serial operating application processor (SOAP). Ones where "one can have their cake and eat it too" (just not at the same time). Whether that is through external storage or "over-the-air downloads" would depend on the hardware. but in a limited memory and storage environment, the benefits to energy efficiency can allow for autarkic, solar powered chipsets in a fully-portable form factor.

The role of the kernel developer is somewhat like the feudal lord- a parent to a userspace child who will never learn the craft of supervision. Thus, the user in many ways is a serf to the operating system- no say in the scheduling of tasks, no say in the permit to travel to other provinces or ecosystems (unless "portable" and architecture independent source code).

Levy's faith in Collective Intelligence in finding a solution for mass unemployment from the race to the bottom wages being outsourced to the cheapest overseas country isn't because collective intelligence already has a solution for the problems that the employment scarcity that ubiquitous digital access creates, but rather because improved collective intelligence is more likely to create more solutions due to improvements in digital literacy and individual agency.  

---
A Timeline of Wired's Response from Mute Magazine's 1995 Publication of Barbrook's California Ideology (09-01) to Wired's Hit Piece on McLuhan 1-01-1996
---
"The original essay was published in Mute magazine[2] in 1995 and later appeared on the nettime Internet mailing list for debate. " September 1, 1995:

https://en.wikipedia.org/wiki/The_Californian_Ideology#cite_note-Barbrook,_Cameron_1995-2
https://www.metamute.org/editorial/articles/californian-ideology

"In contrast, Wired magazine publisher Louis Rossetto criticized the essay as showing "a profound ignorance of economics".[4]
 
 https://web.archive.org/web/19970614205217/http://www.wmin.ac.uk/media/HRC/ci/calif2.html

On January 1st, 1996, Wired went after Barbrook's shaman, McLuhan: https://www.wired.com/1996/01/saint-marshal/ The Wisdom of Saint Marshall, the Holy Fool

While a good biography of the academic's life, some of the criticisms appear questionable:

"Also, McLuhan was never a cheerleader for the technological elite. "There are many people for whom 'thinking' necessarily means identifying with existing trends," he wrote in a 1974 missive to the The Toronto Star. In this letter, McLuhan warned that electronic civilization was creating conditions in which human life would be treated as an expendable fungus, and he passionately protested against it."

A proper academic/philosopher would not be identifying with a trend, but identifying it, to demonstrate thinking. So I'm not sure why Wired/Wolf thought this was clownish to his role, as it tries to paint him in much of the piece.

Furthermore, it states, "At heart, McLuhan was not a futurist at all but a critic and an academic rebel in the tradition of Henry Adams, another conservative Christian mystic who preferred analyzing large-scale trends to compiling sober catalogs of unenlightening facts." 

Isn't that what Web Analytics do today? Except for the Webadmin? It appears Wired misunderstands the purpose of philosopher...

"Esoteric writing serves several purposes: protecting the philosopher from the retribution of the regime, and protecting the regime from the corrosion of philosophy; it attracts the right kind of reader and repels the wrong kind; and ferreting out the interior message is in itself an exercise of philosophic reasoning.[54][55][56] " from: https://en.wikipedia.org/wiki/Leo_Strauss#On_reading

The article clearly labels McLuhan as a random, irreverent mystic- seeking to label him as a clown 16 years after his death suggests Wired was still afraid of his influence. Richard Feynman was also a notorious prankster, yet there are certainly countless Wired articles where he is lauded in a different regard than McLuhan.

"His characteristic comment during one academic debate has taken on a mythic life of its own. In response to a renowned American sociologist, McLuhan countered: "You don't like those ideas? I got others."
In my hagiographic attempt to be a partial McLuhan's apologist, at least in that intriguing statement, I think he viewed discussion not as a debate, with a pre-conceived arsenal of statements, ready to invoke upon attack, but as a dialectic: https://en.wikipedia.org/wiki/Dialectic


Other responses to the 9-1-95 article on the Internet Archive are also quite a great read:

https://web.archive.org/web/19970614175642/http://www.wmin.ac.uk/media/HRC/ci/calif9.html

https://web.archive.org/web/19970710071823/http://www.wmin.ac.uk/media/HRC/ci/calif10.html

---
Shifting focus from technological and economic ideologies to ideologies of infrastructure

---
"Bricolage is considered the jumbled effect produced by the close proximity of buildings from different periods and in different architectural styles.[6]

It is also a term that is admiringly applied to the architectural work of Le Corbusier, by Colin Rowe and Fred Koetter in their book Collage City, whom they called "a fox in hedgehog disguise," commenting on his wily approach to assembling ideas from found objects of the history of architecture, in contrast to Frank Lloyd Wright, who is called a "hedgehog" for being overly focused on a narrow concept.[7]"
https://en.wikipedia.org/wiki/Bricolage 

James Billington describes an apparatchik as "a man not of grand plans, but of a hundred carefully executed details."[1] The term is often considered derogatory, with negative connotations in terms of the quality, competence, and attitude of a person thus described.[2]

When the internet is referred to the "Information Superhighway", I can't help but think an overpass designed by Robert Moses and LeCorbusier. Silicon Valley has created a homestead for hedgehog apparatchiks, while few have attempted to challenge the concrete legacy of LeCorbusier. What counterpoint thinkers aspire to, is more grand planners, perhaps ones that use more sustainable asphault.  


The Developer as Community Architect
---

In an ideal world where technologies are constantly evolving, job security can be improved with a strong training resource, one that employs more elite developers into community architects, receptive to mixed-space uses on diverse projects instead of being master architects with no input from the users. Quite different from serving a small group of shareholders, software and hardware architects could consult as closely as possible to the end-user with as few liasons as possible to develop technical solutions, much as an architect would design a custom built home for a bespoke customer. 

---
"To prevent undue wreckage in society, the artist tends now to move
from the ivory tower to the control tower of society. Just as higher education is no
longer a frill or luxury but a stark need of production and operational design in the
electric age, so the artist is indispensable in the shaping and analysis and under-
standing of the life of forms, and structures created by electric technology."

"The percussed victims of the new technology have invariably muttered clichés
about the impracticality of artists and their fanciful preferences. But in the past
century it has come to be generally acknowledged that, in the words of Wyndham
Lewis, “The artist is always engaged in writing a detailed history of the future be-
cause he is the only person aware of the nature of the present.”
p.12 "The Medium is the Message"

----
"When NVIDIA purchased mobile-chip designer Arm Holdings from SoftBank last year, NVIDIA CEO Jensen Huang made the bold prediction that in the years ahead, there will be trillions of artificial intelligence (AI)-enabled Internet of Things (IoT) devices. "

https://cacm.acm.org/magazines/2021/7/253454-a-battery-free-internet-of-things/abstract 

First, Big Semis can sell more IoT devices B2B. IoT devices, like a sub-threshold voltag microcontroller like an Ambiq Apollo4. A Congressman represents his constituents. If you have a Congressman representing millions of underserved users who would purchase a solar powered phone, you have a minimum order quantity met, rivalling the MOQ demanded by a foundry. So B2B will see the benefits of near-threshold voltage first, in IoT devices and HPC. But consumers, being distracted by 500Hz monitors at CES, will not know about this for years, unless awareness is brought. This is the technology can produce the next OLPC. The OLPC used an AMD Geode with 1 watt of power and a Pixel Qi at another watt or 2. That's two thousand milliwatts, in the most unfashionably way of explaining it. Solar was destined to fail on that, as it is simply a matter of efficiency. At the very most, a laptop needs to target 5mW. A factor reduction of 400x This is important for several reasons. First, it allows a buffer of net surplus energy to cover the hours of the day that can't be powered by solar. And two, it encourages old fashioned engineering labor- energy TDP being the target here. What ever you can fit and run under that is just a bonus. Start with CLI, and let people's creativity fill in the blanks. I call it permaculture for the brain and PC.

If there was a greater effort in developing a kernel that could run on a solar powered laptop, it could provide more information than a library with thousands of books. Manufacturing new technology is certainly a power intensive process, but once it is made, the only thing it needs to last 20 years is power. It doesn't need to be watered like a plant. It doesn't need an oil change like a car. Power is the only thing a laptop needs. Maybe it might need a new microSD card or SSD after 5 years, if the onboard NOR doesn't get corrupt, and if it supports external storage. These kinds of hardwares are useful because they do not age as quickly as software designed for feature updates and expandability. If computers can be designed and viewed like books, then there does not need be a desire to compete against against performance machines. If designs a computer like an encyclopedia, a toaster, or a book, there is no lock mechanism. A book doesn't need to be locked up. Likewise, there is not enough market demand for digital encyclopedias, because people prefer to close a popup or scroll down from Jimmy Wales banner ad. In the future Jimmy Wales banners and repositories can be hosted from every village willing to carry his flag.

"Non-Competitive Products means any (i) product or service that is not a Competitive Product (including products or services that are not sold in the Prior Areas, but would be Competitive Products if they were sold in the Prior Areas), (ii) product or service that is being designed, developed, manufactured, used, marketed, offered for sale or sold by Seller or its Affiliates (but excluding the Sold Companies) as of the date of this Agreement (or any improvements, new versions or successors thereof) or (iii) module or component that is incorporated into any product or service described in clause (i) or (ii) of this definition.'
https://www.lawinsider.com/dictionary/non-competitive-products

I find it a curious aspect that much of the software ecosystem is centered around competitive product development. If hardware were designed not to compete against higher performance products, would it appear any less intimidating? Developers do not seem to think power consumption is an issue in bridging the digital divide. See this article for confirmation: https://semiengineering.com/a-power-first-approach/ I am starting to see it as the central roadblock.

Speed is a relativistic concept. in a region world with internet for 1 minute a day may be better for receiving information from the outside world than one with no information at all. If i only had 1 minute to send a text a day, I would surely send my most important information. The predominate Global North logic of today, in order of highest importance:

1. Slow hardware has no use today, and people always want faster software.
2. Slow hardware has a use, but it is counterintuitive to develop it in short-term and long-term because it is expensive.
3. Slow hardware has a use, but and it is worth the cost in the long term, when all other options have been exhausted.

I should add, that slow hardware is not actually slow, if one can efficiently design a simple 2D CLI/GUI without graphics acceleration for the purpose of displaying text. in the minimum number of pixels to be legible.

If you've ever watched the Three Stooges, there is a recurring gag where all three stooges try to run through the doorway at the same time:
https://www.youtube.com/watch?v=xbNkoB7gq3k 

Every kernel module, whether it is a printer driver, or support for thousands of drivers that are unused on a portable device, make Linux heavy. What many users need is a linux that provides information in its most minimal form- the architecture 

![image](https://user-images.githubusercontent.com/76194453/213938231-907057fa-cf8d-4ac1-aff6-1230b5db5cbe.png)

![image](https://user-images.githubusercontent.com/76194453/213938331-29ff17c8-ccc5-497c-86bc-b30798010a21.png)

This is how I view the modern, bloated kernel: https://www.theregister.com/2009/09/22/linus_torvalds_linux_bloated_huge/

""I mean, sometimes it's a bit sad that we are definitely not the streamlined, small, hyper-efficient kernel that I envisioned 15 years ago...The kernel is huge and bloated, and our icache footprint is scary. I mean, there is no question about that. And whenever we add a new feature, it only gets worse.""

(link broken: https://www.cnet.com/culture/linus-torvalds-linux-is-bloated/ - link deleted by CNET-the below was quoted from there: 
https://news.ycombinator.com/item?id=17295386 there may be an archived copy somewhere.

https://www.theregister.com/2023/09/28/kubecon_shanghai/ "The statistic was somewhat tongue in cheek as Zemlin pointed out that none of the developers working on Linux Foundation projects actually work for the Linux Foundation." Which is somewhat ironic, because it doesn't really promote unified architectures that could improve delivery to new markets.

https://youtu.be/1ToJAikOEZU?t=6419 I briefly mention Linux in my new video on wireless platform design.

"The truth of the matter is, to say that Linux is bloated is like saying a LEGO set that comes with a million LEGOs is bloated. Just because it has all the pieces doesn’t mean they’ll be used to create a single, monolithic creation. Make what you want. Take those LEGOs and make a bunch of really cool toys. You are free to do with those individual pieces what you want. Of course, some of those pieces will be used more than others (like the Luke Skywalker and Darth Vader figures). Same thing with Linux."

So the issue now isn't the lack of options. Modern linux has many more modular options. I am not misunderstanding one instance of a kernel as the only one, as I have identified by projects such as TLDP and the linux tinification projects: https://tldp.org/HOWTO/Module-HOWTO/x73.html#AEN90 . I understand smaller kernels can and are compiled. My criticism is that few, if anyone with clout is able to make the connection between sponsoring linux projects that explicitly see power consumption as a design feature when developing a low-power kernel for the developing world. That is yet to be addressed specifically. The difference between 2008 and 2023 is 2500 millwatts. And by addressing this issue in the software community, one can spread awareness. If one looks at Busybox, it is a consolidation of an already complex kernel: The authors dubbed it "The Swiss Army knife of Embedded Linux",[10] as the single executable replaces basic functions of more than 300 common commands. https://en.wikipedia.org/wiki/BusyBox What energy autarkic kernels need, is essentially a utility that is not running any background processes- no daemons- no heavy swiss army set of tools on standby in RAM. What it needs is a serial module, like a series of modules, for each application. A "single file line," unlike the three stooges. In a memory constrained microcontroller, 2MB of RAM is the difference between allowing one stooge through or NO stooges through. Hypothetically, if 1MB of RAM uses 1mA and 3MB of RAM uses 3mA, the kernel could be shaved dynamically to use 1MB RAM.
![5c24b3ef-5b28-43e9-9d4a-8c87dca11756_743x526](https://user-images.githubusercontent.com/76194453/212416785-9b0bfd40-59ef-4f1e-9e77-daa8e111fccc.png)

Obviously encrypted data is going to need more power due to hashing, but that is something that can be worked on by anyone who wants to contribute. The goal of this project is to establish the concept and proof of energy autarky first. holistically, the system views display and i/o equally, and sees the importance of providing visual data as important as having a low power cpu. thus it is not 3D or graphical favoritism. 2D text is just as important, if not more important than animations. Additionally, powerfirst design views power consumption in absolutist terms. like the power of a display is absolutely more positive than 0. Obvious facts asidde, this isn't a pessmistic focus. It's not trying lament the impossible. It's not trying to say, "why isn't this display consumption 0 or free?" It's merely acknowledging what products exist in the world, what is commercially avaiable or capable of being deveoped and bringing them together, like some Frankenstein experiment. :) That was a joke. No organic material was harmed in the production of this paragraph. Thus, it is somewhat a rational approach to just finding what can fit under the TDP, and not lament about what isn't possible. In that sense, it's not just the memory that is a limit- the Three stooges analogy is both for frame buffer of display, of application data, and of power consumption. That applies to wireless data too. I.e. pick a module that transmits at no more than what the lithium ion capacitor can power- i.e some are 0.1A max. Some antennas output at 5mA. Literallly too, imagine a crawlspace or a narrow crevice that a handyman could barely fit through. Would they take their entire toolbox/toolbelt with them, or just the tool(s) they need for the job?

Since some RAM can't be "turned off," it is best to design a kernel+app for a known amount of RAM- e.g. 1, 2 or 4, and also, to acknowledge, that certain applications could become, in essence, an appliance for the life of the product. It can be swapped out with other apps/base kernel pairs, but upgrading it to use more RAM is one of the few limitations of this approach. Unused cycles of ram and instruction are considered wasted. https://en.wikipedia.org/wiki/Out-of-order_execution whether this approach is useful for an OS/kernel supporting multiple applications depends more on the supported code bases and the interest in this project. That is, some instruction sets may work better, such as RISCOS, but may lack other software support. https://en.wikipedia.org/wiki/RISC_OS I think stress testing https://en.wikipedia.org/wiki/Stress_testing_(software) is a good way to develop applications for low memory microcontrollers- something like GNU Nano https://www.nano-editor.org/ to run in 1MB if even possible. Perhaps garabage collection or some other offloading mechanism to store data while retaining an amount on screen, shuold be more than enough to view and edit a certain amount of data at a time. For example, a 536 word, 3361 character file only takes up 1.7KB of data, or 4KB if the minimum block size is 4KB. Microcontrollers with 1MB of RAM, can certainly display of page of dense information, for your eyes only. :)

![image](https://user-images.githubusercontent.com/76194453/212424717-ad4a37ce-0026-44e2-ac11-a2f4437fd792.png)


If the the unused kernel is stored in nonvolatile memory, it can be unpowered and retrieved when needed. Thus power consumption is an integral design feature of the kernel. A pillar, if you would like to call it. Three pillars perhaps- power, displayability, and serialness. thus all pipelines of instructions address one application at a time, and the only kernel modules needed to run that app are present in ram at any given time. Thus I am using occam's razor to implicitly state the kernel is not always using something in memory for a given app, but is holding a hefty toolbelt, even if it is not using more 90% of the tools at a given time. 

So after describing such a kernel, what types of existing kernels could support such an OS- a microkernel, am exokernel, unikernel, or a larger, monolithic kernel?
Perhaps, out of efficiency, an exokernel may suffice. But then again, a bootloader would be needed to load different apps and OSes. Something like https://tow-boot.org/ supports external booting, which can be handy in cases where internal drives are not able or designed to support a bootloader, due to lack of space or other reason. After exhausting some of the possibilities in conceptual framework, as this deliberative can be exhausting in more than one sense of the word, I feel it is easier now to define what can be included in a kernel. I still like the idea of a rotary kernel, using loadable kernel modules. That said, the modules may appear to have a size larger than what microcontrollers can support, but I am referring to a base kernel having its own set of modules. https://en.wikipedia.org/wiki/Loadable_kernel_module

https://bbenchoff.github.io/pages/dumb.html
http://www.paperterm.org/notes.html

Why is this important? Computers are just a means of accessing and interacting with information. Today, foundries can produce 5 nanometer chips that use extremely low computations per joule of energy dissipated: https://en.wikipedia.org/wiki/Koomey%27s_law

There's at least two things one can do with lower nodes (such as 5nm)

1. You can pack more transistors, to do more computations. (The Atom N270 processor used 2.5 watts)
https://www.intel.com/content/www/us/en/products/sku/36331/intel-atom-processor-n270-512k-cache-1-60-ghz-533-mhz-fsb/specifications.html
If you look at one of the most modern Atom spiritual sucessors today, I could only find the 2021 Tremont, Atom x6200FE, which is a dual core, 4.5Watt BGA:
https://en.wikipedia.org/wiki/List_of_Intel_Atom_processors#%22Elkhart_Lake%22_(10_nm)
https://ark.intel.com/content/www/us/en/ark/products/207904/intel-atom-x6200fe-processor-1-5m-cache-1-00-ghz.html How many transistors in the x6200Fe? probably far more than needed to look up wikipedia.
https://en.wikipedia.org/wiki/Gracemont_(microarchitecture) is the successor, and the lowest power chip is 6 Watts. It's safe to say, the industry trend is, pack more for the same since the mentality is, "6 watt is good enough for anybody") (yes, i am reversing the meaning to imply that 6 watt is too much, and actually 640K would actually be more useful in some cases)

2. You can do the same number of computations as you were in 2010- you can still access the internet, use word processor, etc. https://rhombus-tech.net/whitepapers/ecocomputing_07sep2015/ But what do you get in exchange for your heroic act of relativistic anemia? a 1-5mW TDP, something that could be powered by a credit card sized solar panel. Deliberately setting a clock rate at no more than 100mhz could allow it to use no more than the amount of power that the solar panel can generate, while simplifying the interface to informational resources, that uses little power (potentially less than a millwatt to retrieve and modify. With time, more computational complex modification can be supported.

The question is, even if you want "more, more, more", have you really ever thought about someone else who just wants "something"? In a region with no electricity? 

Thus, while many environmentally conscious users prefer not to buy new pcs to save on the environment (and they are correct), another aspect of computing is that technology today allows for computing to be autarkic, but due to lack of awareness or interest, leading chip designers can willingly leave out 4 billion users by continuing to develop power hungry devices. To learn programming, one can read a book. But even if a book is available, one cannot interact with a command line interface. Thus the technology today is available to integrate leading edge components (low power Japan Display memory in pixels), Ambiq Apollo4 microcontrollers, to develop autarkic command line interfaces, that give access to the maximum amount of information (whether stored in gigabytes off line on a microSD) or via an online hardware- if the system on a chip has a wireless or ethernet capability. That said, the lowest power mechanism for transferring data -whether it is LPWAN or a usb/cat 5 cable would need to be considered. Thus there is no concerted effort hitherto anywhere to develop this. I seek to be the first to explicitly call for this, since no one else wants to , or believes it is possible.

I think of that fable, by Aesop:
https://en.wikipedia.org/wiki/The_Tortoise_and_the_Hare

In elementary school, our school occasionally had guest speakers, some were motivational speakers in our auditorium. One of them was an acting couple, that told us the story of the the tortoise and the hare. They turned the gym into a racetrack, and one played a bipedal tortoise, and the other one a bipedal hare. The hare ran around the gym, and in his hubris, took a nap at about 75% near the finish line. The tortoise ran, diligently, around the gym, and the hare, sleeping, woke up just as he noticed the hare about the reach the finish line, and started sprinting but lost the race.

Why am I sharing this story? Because it is one of the most inspiring stories in my life. A person without internet access may not seem as cool to you. But they could be studying or reading even without a book or internet access, if only they had a computer that could power itself. So when they connect to the internet, they could upload a magnificent software or story (if they are a writer), which may appear out of nowhere, as the have wake up from their slumber. That is my dream. (It's more like an anecdote worth mentioning at least once)

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

![image](https://user-images.githubusercontent.com/76194453/213939362-9f3e6d94-9289-45e4-addb-9cf5de2fd070.png)


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

In a review of Alexander Galloway's Uncomputable: Play and Politics, Jacob Gaboury writes:

"Instead, uncomputability is a frame for thinking through the presumed inevitability of computation by foregrounding those various moments in the history of what would become our computational culture, in which computing fails to emerge, networks fray, and the digital atrophies." https://muse.jhu.edu/article/904021/summary

According to MIT Press, "In Image Objects, Jacob Gaboury offers a prehistory of computer graphics through an examination of five technical objects—an algorithm, an interface, an object standard, a programming paradigm, and a hardware platform—arguing that computer graphics transformed the computer from a calculating machine into an interactive medium...

...The development of computer graphics, Gaboury argues, signals a change not only in the way we make images but also in the way we mediate our world through the computer—and how we have come to reimagine that world as computational." from https://mitpress.mit.edu/9780262045032/

"Gaboury’s Image Objects is a remarkable and rigorously researched book. Through narrating a history of computer graphics, the author demonstrates that “The computer is not a visual medium. And yet computation as we know it today has been fundamentally shaped by computer graphics” (200). The author’s history traces a professional network of computer scientists with a hub in the University of Utah’s Computer Science Department founded in 1966 by Salt Lake City native David C. Evans with initial funding from Ivan Sutherland, then a program director at the Department of Defense’s Advanced Research Projects Agency (ARPA). Sutherland later joined Evans in Utah to co-found the computer graphics company Evans & Sutherland (E&S). The network, rooted at the University of Utah and E&S, is illustrated by examining work accomplished by faculty and graduate students in the department from, roughly, 1966 to 1980 and by following graduates and former faculty out of the department as they founded and/or shaped Pixar, Adobe, Silicon Graphics, Netscape, Atari, WordPerfect, Xerox PARC, NASA’s Jet Propulsion Laboratory, the New York Institute of Technology, and Industrial Light & Magic." 

"All of these and Gaboury’s image objects are further developments of what philosopher Jean Baudrillard, in the nineteen eighties, referred to as the “precession of simulacra,” the notion that representation precedes and determines the real or, in Baudrillard’s words, “[h]enceforth, it is the map that precedes the territory … it is the map that engenders the territory.”9"

from http://computationalculture.net/object-lessons/ 

Compared to non-computational art, photographs, as in Don Delillo's White Noise serve a similar territorial mapping:

https://czasopisma.uni.lodz.pl/textmatters/article/view/3752

" It is as if the visitors to the barn are “prisoners” in a Platonic cave, fixated on, and even driven into a kind of rapture by, the endless stream of information and images cast on the cave wall. The term “aura” in this context appears to refer to the aura of the commodity, or what Baudrillard terms the “power and pomp of fascination” (4) of the simulacrum. In the silences when Murray isn’t speaking, the only sounds are “the incessant clicking of shutter release buttons, the rustling crank of levers that advanced the film” (DeLillo 13). It seems the photographers are themselves part of a “machine” for producing images, to reinforce the “aura”; all they can do is keep clicking. Mark Schuster suggests that “they exist primarily to service the barn, to maintain, as Murray insists, its image. Just as the barn serves no other purpose than to be photographed, the tourists serve no other purpose than to photograph it” (16–17)" 

Tourism becomes performatism: https://en.wikipedia.org/wiki/Performativity

Furthermore, "...The simulacrum, in Plato’s definition, is a distorted copy—for  example,  a  statue  which  uses  illusory  effects  such  as  false perspective: outwardly, it simulates the real thing, but this is only an effect of resemblance. Any link to the divine Form has been lost; but there is a danger that the spectator may nevertheless mistake the copy for the Idea or Form.3Plato’s  famous  parable  of  the  prisoners  in  a  cave,  mesmerized by shadows cast on the cave wall, has frequently been conflated with Baudrillard’s notion of hyperreality. Carl Plantinga, for example, observes: 

Having never left the cave, and having no experience of that larger, extra-cavern universe, the cave-dwellers naïvely experience shadows on the wall as actuality, appearances as the real thing, these mere semblances as the “really real.” Could this be our condition in today’s world of media images? Have the misleading images on the cave wall been replaced by the relentless flickering lights of television and movie screens? (307)"

p.5 (369)"From Plotinus, then, we may infer a very different definition of the simulacrum from the Platonic model. In Plotinus, the “false” image is deliberately detached from the real. The simulacrum in this sense does not refer to the real, but to the ideal; it seeks to participate in the Platonic “Idea.” It changes the viewer’s way of seeing, redirecting their gaze from the material to the immaterial, and affording them an insight into a “transcendental beauty” which “has all the hallmarks of the sublime” (Porter 609)"

from "David AllenM idland Actors Theatre, UK Agata Handley University of Łódź 'The Most Photographed Barn in America”: Simulacra of the Sublime in American Art and Photograph'y, Text  Matters, Number 8, 2018" 

I had a theater teacher at a community college once, who compared the original Sweeney Todd play to the film version ( (Sweeney Todd: The Demon Barber of Fleet Street, 2007)) (after a student asked about the movie -then new at the time). He said that the film version leaves nothing to the imagination.

Likewise, 3D graphics and user-generated video, from social media, often leave little to the imagination today, and at times frame the discussion and perception of the story, creating often times, the appearance of certainty, when it still it a much futher departure from a primitive terminal or 2D forum, where human, rather than machine inference, and analysis had to be used more. To go even further back, the spacing of letters in Latin was another evolution of pre-masticated text: https://en.wikipedia.org/wiki/Scriptio_continua

"By saving the reader the taxing process of interpreting pauses and breaks, the inclusion of spaces enables the brain to comprehend written text more rapidly. Furthermore, the brain has a greater capacity to profoundly synthesize text and commit a greater portion of information to memory.[7]: 16–17 "

[7] https://www.google.com/books/edition/Space_Between_Words/w3vZaFoaa3EC?hl=en&gbpv=1&bsq=%22short-term+memory+of+word+order%22&pg=PA17&printsec=frontcover

Reading without interpretation, and likewise, accelerated graphics, becomes wholesale transactional performatism. 

----

![image](https://user-images.githubusercontent.com/76194453/213939045-32f61a9d-9218-44e0-a896-494bda38e157.png)

The more I think about this project, it is more an exploration of an economics issue. It seeks to address a gap in access to not just basic ownership of a phone, but a device that can accomplish simple communication and digital processing tasks without needing to devote a sizeable percentage of one's income to a phone plan. In some parts of the world, where one's salary is only a few dollars a month, owning a phone is a larger percentage of one's income than in higher GDP countries (where the cost of rent is also a very high proportion of one's income). consider the discontinuation of 2G and 3G cell phone towers in the U.S. It may not have affected many people that they needed to upgrade to a new phone as many already had a 4G or 5G device, but what happens when upgrading a device causes a significant hardship? Sometimes it is possible to do without a phone in urban environments, but in some places, a phone is a lifeline both for both one's ability to stay employed as well-as one's well being. I know I've veered into using the phrase phone quite frequently in the past paragraph. And that may be the most frequently used movile device. But phones are chosen because they are often convenient to carry, as they fit in a pocket, not because laptops are unaffordable to many. That said, what if our next superstar programmer is in a rural village with no internet or power? He or she wouldn't be able to learn/practice coding, even if someone donated them an i9 laptop, without a solar panel or wind turbine. Designing and  Manufacturing laptops with integrated solar panels is a one time transplant of solar to remote regions and creates a decentralized grid of computer access to the last 14% of people in the world without a phone/or electricity. To get there, software needs to be designed to match the low power of microprocessors, using already low power microprocesors.
https://whossavingtheplanet.com/read/innovation/green-coding-sustainability-in-software/2020-10-04 Datacenters have done this for years:
https://www.computerweekly.com/blog/Green-Tech/Green-coding-A-sustainability-practice-all-software-engineers-should-adhere-to
A solar powered laptop/phone would be a proof of concept that green coding can be applied to the microeconomic level, from kernel to the display monitor) to transform our dependency on lithium ion batteries, as well as the need to plug in to outlets at Starbucks.

You could call this the Free Energy Foundation, modeled after the Free Software Foundation. Energy Independence is Energy Security. Energy Security is a precondition to computing access. If you believe they put a man on the moon, then you can believe they can put a solar panel on a computer, and make it run. https://www.youtube.com/watch?v=eNCDL7wIuEo

Free as in gratis. You can count on the sun more than the grid, in some places of the world. Unless you're in the arctic winter for months where it's perpetually nighttime due to the tilt of the earth during its orbit around the sun. https://www.pmel.noaa.gov/arctic-zone/gallery_np_seasons.html  For as long as the earth is around it will have sunlight. Unless you're Mr. Burns and want to tax and block sunlight. Obviously, humanity is susceptible to tampering with abundance. https://www.youtube.com/watch?v=L3LbxDZRgA4 

----------------
Update 7/7/2023: Some thoughts:

A key issue in computer design is selecting the applications for the hardware. General purpose hardware typically uses more computation to accommodate a suite of apps.  https://www.darpa.mil/program/software-defined-hardware  
https://www.sei.cmu.edu/publications/annual-reviews/2020-year-in-review/year_in_review_article.cfm?customel_datapageid_315013=315530
A lower power thermal envelope allows alternative energy sources in a portable design, potentially requiring far less computation per application.

What if energy design were a formula that would change the world? In the 2002 made-for TV film Copenhagen,
https://www.youtube.com/watch?v=jx1Q5lhkff8
https://en.wikipedia.org/wiki/Copenhagen_(2002_film) 
Physicists Niels Bohr and Werner Heisenberg meet in Copenhagen (just about the only plot detail that was based on a real meeting in 1941). The play is about what they spoke about, or could have spoken about.

Not in the above clip, but during the movie, a topic on factors of ten is brought up. The film portrays Heisenberg as plausibly fishing for clues to support Germany's nuclear program as much as meeting Bohr to devise a plausible excuse to stall the program. A detail that I have not been able to locate in a video clip, regards that Heisenberg was describing a quantity that was off by a factor of 10 or 100, and seeking a hint from Bohr, suggests that Heisenberg had the right concept in mind (for the net production/exothermic reaction of energy), but had not grasped the magnitude of the quantities involved. This, perhaps is the most direct clue that Bohr was willing to yield, and tantalizing for some, set in motion a new mode of thinking, not just for nuclear development, but in shortly after 1945, setting new, practical reasons for deterrence and avoiding mutual assured destruction (MAD). The first concern was, whether the chain reaction would never end, and, once that was determined, how to avoid MAD as it would eventually result in a similar predicament. Thus, WWII was the last Great War because the power from the offensive munitions became so great that there was a permanent shift to deterrence. As has been said about using all of the coal and oil fuels, the destruction would limit humanity's growth far sooner than it would destroy the planet. https://www.newyorker.com/news/daily-comment/if-we-burned-all-the-fossil-fuel-in-the-world

To that end, what would happen if semiconductor manufacturing continued at such a pace that it allocated an even greater quantity of the world's freshwater than 99% of the world's population? Would semiconductors continue to be that useful? Hyperbole is sometimes more useful rhetorically.

Accomplishing more with less is only a mitigating factor, but it is not an insignificant one. Certainly demand in new products continues unabatedly. Demand for general information does not increase exponentially, nor linearly. It plateaus. This allows solar energy to power the simplest systems first- 2D, text based command lines and basic I/O phones. What changes with Koomey's Law is that basic informational queries and communications can use less power on more advanced nodes (5nm, 3nm, 1nm, picometer, and so on), allowing energy harvesting devices from the ambient environment to power completely software defined hardware. This approach does not replace omnibus operating systems such as linux, android, windows and apple, but allows potentially for hybrid, micro and hardware decentralized kernels to run in parallel that rely on isolated energy storage systems, (rather than large 3,000 MAh battery banks, e.g. for one Android OS to power multiple apps), selected for their efficient harvesting, storage, and delivery mechanisms that use less materials. Similar to hyperscaling processors (such as near threshold voltage), "hyper harvesters" or "hyperstoragers" (a cactus stores  very efficiently but evaporates very little) could be the next best complement to efficient processors. Capacitors and Hybrid Lithium Ion capacitors can reduce the densities needed to provide long-term power solutions when singular and software defined hardware profiles provide the most efficient computation per joule: https://en.wikipedia.org/wiki/Performance_per_watt#Definition   

https://beneinstein.medium.com/stop-saying-hardware-is-hard-62fdd3052a2 "Stop Saying “Hardware is Hard”

Ironically, semantic satiation can dissolve the impression, if need be:

https://en.wikipedia.org/wiki/Semantic_satiation

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard

Hardware is Hard


A formula for energy efficiency can sound oversimplistic, but it is actually more a framework or a compass that leads to a new product category- autarkic systems. The other, human-centric question one can ask is, "What is something I don't I know about but need? (Or want)

To that, I present Six Characters in Search of An Author, by Luigi Pirandello. 

Autarkic computers are for many, a solution looking for a problem.  But because they are general purpose, they would appear to become the next general purpose technology, which could connect billions of more people who have never been online, or can stay online:

https://www.thediff.co/archive/a-solution-in-search-of-a-problem/
“One interesting trait of toys-turned-tools is that they seem more likely than average to become such general-purpose technologies. General-purpose technologies are fairly rare, and very important—many comprehensive lists of them will start with things like fire, writing, and the use of tools to improve other tools. A toy that finds another use case is more likely to be a general-purpose technology, in part because of the "Pirahã Are Off By One " phenomenon: most inventions are useless, some have an extremely specific use case, but if you discover that they have more than one use case, it's likely that this generalization will continue. And this is especially true from the standpoint of someone who hears about a new tool: it's going to be more viral if a) it spreads by being useful, and b) it spreads in as many different groups as possible, i.e. it has lots of use cases.”

https://byrnehobart.medium.com/the-pirah%C3%A3-are-off-by-one-9c77eb66a6d9

The general purposeness of a toy actually signifies the ability for a product to be used as a tool, rather than a divertimento.

https://en.wikipedia.org/wiki/Land_of_Toys "To its unsuspecting visitors (like Pinocchio and Candlewick), the Land of Toys appears to be a fantastic haven for wayward children to do whatever they want with no consequences or law; to act as they please without recrimination. However, the truer and more sinister purpose of the Land of Toys is eventually revealed: by means of a disease called "donkey fever" that affects children who never study or work, the children turn physically into donkeys (in Italian culture, the donkey is symbolic of ignorance, stupidity, goofiness and labor). Subsequently, they get sold by The Coachman to different places."

The original representation of the Land of Toys mixes the aspects of a morality tale with those of social critique. What separates Silicon Valley from the Land of Toys? Maturity and a Super-ego.

---
11th Dimensional Chess
---
https://scifi.stackexchange.com/questions/230776/where-did-eleven-dimensional-chess-originate#:~:text=%2211th%20dimensional%20chess%22%20is%20a,than%20they%20appear%20at%20first.

"11th dimensional chess" is a term used to describe someone whose planning and actions are deeper than they appear at first. The derivation of the term comes from the fact that while chess is a complicated game, variants of it in higher dimensions would take such a fine strategic mind that their actions would appear random, confusing or even foolish to the uninitiated. The term has some variants, with the number of dimensions varying, or somethings just "nth dimensional chess", but the idea is that the strategies and subterfuges involved are so complicated as to be opaque to an observer."

http://www.talkleft.com/story/2009/2/10/8179/36722/media/-11-Dimensional-Chess-Goes-Viral

"position seems to be that everything has been  exquisitely planned, leaving no room for synchronism.  Course corrections as well as external influences, ranging from hostile criticisms to the well-meaning 'dutch uncles', were superfluous to the grand plan.  As I read Herbert's column my mind when back to the dark old days of Rummy, when "stuff happens" was the non-explanation for events; now the non-explanation is faith in unseen and foreboding political powers--the wisdom of the eternal chess player."

Software source code can be an open book, but the documentation and politics around it can be anything but. 

I'm a little paranoid that I will be forced to wear the Scarlet Letters "TESCREAL" on my shirt one day https://www.truthdig.com/articles/the-acronym-behind-our-wildest-ai-dreams-and-nightmares/ for hoping to pass my espresso maker down to a future generation and be labeled a longtermist, simply for refusing to get my coffee at a drive through Starbucks that wastes recycled cardboard on cups that I can wash at home using ceramic mugs.

My objective is now clear. I must write and speak with words and opinions that fall just below the threshold of virtue-signalling, as well as just below the threshold of vice-signalling. The No-man's land where neither side regognizes. 

When you have opponents labelling you both terms, you know that at least one of the sides' eyesights is worse than your own.

https://www.adamsmith.org/blog/stop-saying-virtue-signalling (may be old news to some, and not a brand new term to me either)

A refreshing analysis of AI

https://adamsinger.substack.com/p/the-rise-of-ai-nihilism 

"According to Ronald Hingley, it is Dostoevsky's "greatest onslaught on Nihilism", and "one of humanity's most impressive achievements—perhaps even its supreme achievement—in the art of prose fiction."[2]" 
https://en.wikipedia.org/wiki/Demons_(Dostoevsky_novel)#Demons_as_satire

Thus to combat nihilistic AI, one might want to read Dostoevsky.

https://en.wikipedia.org/wiki/Polyphony_(literature)#The_voice-idea

"In contrast to this model of truth, Bakhtin postulates a truth that requires a multiplicity of consciousnesses, something that cannot be contained within a single consciousness; rather it comes into existence at the point of contact between diverse consciousnesses, and is intrinsically "full of event potential."[6] Bakhtin's criticism of the monologic conception of truth is that it abstracts and effaces the "eventness" of the event – everything about it that makes it unique, unfinalizable and full of unrealized potential. In his conception, unknown and unforeseen possibilities arise out of the interaction of autonomous, unfinalized consciousnesses, and this is the true, lived nature of human existence.[7] The "open-ended dialogue" is the verbal manifestation of this truth, and polyphony is its artistic representation in literary form."

"In polyphonic writing, the author must relinquish monologic control over the work. If they do not, there is no possibility of realizing a dialogic sense of the world, where autonomous and unfinalized personalities interact on their own terms. It is only possible if the character is truly an other consciousness, with equal rights to signify, and not merely a 'created' character in the author's imposed reality. The author of the polyphonic novel confronts his characters as equals. He does not withdraw his own ideological position for the sake of an illusory objectivity: rather he places it directly among the equally signifying voice-ideas that are at variance with it, and provokes their confrontation with it and with the other voice-ideas. As his own voice has no more or less existential significance than any other voice, the author himself does not know in advance what the outcome of these confrontations will be. The interactions thus provoked are ripe with "event potential": conclusions are not foreordained, nothing truly comes to an end, and no character can be ultimately finalized from without. Thus the author's role in the polyphonic novel is twofold: "he creates a world where many disparate points of view enter into dialogue, and, in a quite distinct role, he himself participates in that dialogue. He is one of the interlocutors in the "great dialogue" that he himself has created."[16]" 

For someone who has been aware of AI and technology as a way of life, it is interesting to see how some research fields ebb and flow. In the early 2000's, there was a lot of debate that genetic therapies would be like playing God. Later on, it was Nanotechnology (https://web.archive.org/web/20101223170126/http://www.hplusmagazine.com/articles/nano/singularity-nanotech-or-ai) It's not clear why so much emphasis was placed on nanofactories, but today the product design seems to have identified IoT and HPC for AI instead of the more ambiguous "factory" and other nondescript chips that augment AI. Technically any pcb with transistors could pass as one, but perhaps due to fears that nanotechnology could cause cancer and lodge itself into cellular membranes, the focus has been on larger chips perhaps.


https://pmarca.substack.com/p/why-ai-will-save-the-world
"The Baptists And Bootleggers Of AI

Economists have observed a longstanding pattern in reform movements of this kind. The actors within movements like these fall into two categories – “Baptists” and “Bootleggers” – drawing on the historical example of the prohibition of alcohol in the United States in the 1920’s:

“Baptists” are the true believer social reformers who legitimately feel – deeply and emotionally, if not rationally – that new restrictions, regulations, and laws are required to prevent societal disaster.

For alcohol prohibition, these actors were often literally devout Christians who felt that alcohol was destroying the moral fabric of society.

For AI risk, these actors are true believers that AI presents one or another existential risks – strap them to a polygraph, they really mean it.

“Bootleggers” are the self-interested opportunists who stand to financially profit by the imposition of new restrictions, regulations, and laws that insulate them from competitors.

For alcohol prohibition, these were the literal bootleggers who made a fortune selling illicit alcohol to Americans when legitimate alcohol sales were banned.

For AI risk, these are CEOs who stand to make more money if regulatory barriers are erected that form a cartel of government-blessed AI vendors protected from new startup and open source competition – the software version of “too big to fail” banks.

A cynic would suggest that some of the apparent Baptists are also Bootleggers – specifically the ones paid to attack AI by their universities, think tanks, activist groups, and media outlets. If you are paid a salary or receive grants to foster AI panic…you are probably a Bootlegger.

The problem with the Bootleggers is that they win. The Baptists are naive ideologues, the Bootleggers are cynical operators, and so the result of reform movements like these is often that the Bootleggers get what they want – regulatory capture, insulation from competition, the formation of a cartel – and the Baptists are left wondering where their drive for social improvement went so wrong.

We just lived through a stunning example of this – banking reform after the 2008 global financial crisis. The Baptists told us that we needed new laws and regulations to break up the “too big to fail” banks to prevent such a crisis from ever happening again. So Congress passed the Dodd-Frank Act of 2010, which was marketed as satisfying the Baptists’ goal, but in reality was coopted by the Bootleggers – the big banks. The result is that the same banks that were “too big to fail” in 2008 are much, much larger now.

So in practice, even when the Baptists are genuine – and even when the Baptists are right – they are used as cover by manipulative and venal Bootleggers to benefit themselves. 

And this is what is happening in the drive for AI regulation right now.

However, it isn’t sufficient to simply identify the actors and impugn their motives. We should consider the arguments of both the Baptists and the Bootleggers on their merits."

This reasoning seems to miss that the Dodd-Frank bill wasn't as strong as it could have been, and some of the regulations on derivatives and CDOs, which some say have been rebranded as "bespoke tranche opportunities", have been loosened again: https://money.usnews.com/investing/stock-market-news/articles/what-is-a-bespoke-tranche-opportunity
Banks aren't bigger because of regulation, but because there weren't many other players that survived, and the ones that did just happened to grow with more customers (population). Also, the criticism towards "Too Big to Fail" was more because it penalized the taxpayer for risky lending practices that were knowingly carried out by the bank (even if the borrower shared some of that risk knowingly), than allowing banks to become large without fault.

In terms of LLM, open-sourcing the code is only one way that the analogy of bootleggers and authorized alchohol manufacturers doesn't make sense. In distributed computing, Chat-GPT uses multiple clusters of CPU cores to run the LLM. https://en.wikipedia.org/wiki/Distributed_computing#Models 

""ChatGPT is already a model of Large neural networks based on a distributed computing platform. ChatGPT was built in collaboration with Microsoft. The model is trained using Azure supercomputing infrastructure with Nvidia GPUs. ChatGPT’s hardware comprises over 285,000 CPU cores, 10,000 GPUs, and network connectivity of 400 GBs per second per GPU server. Information taken from here and here"" https://ai.stackexchange.com/questions/39740/is-it-possible-for-a-gpt-model-to-run-in-a-distributed-way https://news.microsoft.com/source/features/ai/how-microsofts-bet-on-azure-unlocked-an-ai-revolution/ https://www.mlyearning.org/does-chatgpt-use-nvidia/

However, this distributed design most likely requires the servers with multi-core chips to be localized to a single data center- unless a handful of intercity fiber optic lines are being run for a handful of separate large computational loads. The other model, is distributed computing across the internet (e.g. Folding@ home). https://en.wikipedia.org/wiki/Folding@home 

"Folding@home is one of the world's fastest computing systems. With heightened interest in the project as a result of the COVID-19 pandemic,[8] the system achieved a speed of approximately 1.22 exaflops by late March 2020 and reached 2.43 exaflops by April 12, 2020,[9] making it the world's first exaflop computing system. This level of performance from its large-scale computing network has allowed researchers to run computationally costly atomic-level simulations of protein folding thousands of times longer than formerly achieved. Since its launch on October 1, 2000, Folding@home was involved in the production of 226 scientific research papers.[10] Results from the project's simulations agree well with experiments.[11][12][13]"

Since the tasks do not require a single server setup, they can be designed for a variable number of interested users, and the hardware can be repurposed- based on individual users interests. While it may not be as efficient as an ASIC, the ASIC chip runs the risk of becoming obsolete once the energy costs to run the software are more than newer platforms able to run it on a lower transistor node. In addition, cryptojacking uses a similar concept, without authorization: https://learn.g2.com/cryptojacking except that the mining operations are of a simple hashing algorithm, rather than a unique instruction to run LLM analysis. 

Open source LLMs could be as large as billions of CPUs running for 12 hours at a pre-announced time, or an asynchronous project to allow a number of cpus to run for a period of 30 days. This could be useful in cases where there are many known language/dataset instructions that need to be run and are known, but depend on a large number of CPU cycles that can process just part of the puzzle in smaller clusters or "brigades" Thus distributed computing can still be hiearchical and multi-level, and not permanently tied to a single organization.

Thus, the claimed dichotomy of small AI players and big AI players, by both parties, in the future, could very well be a moot point. Projects to use AI for "special operations," (e.g. to query a single question) could save on costs since there is a lower non-recoverable engineering cost (NRE) involved in designing the LLM on a general purpose, independent architecture, than a specific architecture that is vendor dependent, perhaps ones that can be partially re-used for running other queries. 

---


![image](https://github.com/hatonthecat/Soap-Kernel/assets/76194453/4b913146-2720-4d93-be27-ccbe165622b8)

Tough Actin SI-actin

If AI "news" could be stopped across the entire internet, I would hear a printing press somewhere, exclaim, "Stop the AI!"

https://en.wikipedia.org/wiki/Stop_press 

https://archive.nytimes.com/www.nytimes.com/times-insider/2014/05/27/stop-the-presses/

For more references, see my October 2022 post: https://github.com/EI2030/Low-power-E-Paper-OS/blob/master/82800869.remaking-the-nokia-6110-and-psion.html
(download RAW)

"It is difficult to get a man to understand something when his salary depends on his not understanding it." Upton Sinclair

