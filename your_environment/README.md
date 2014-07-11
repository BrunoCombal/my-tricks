# Your environment

The tips I am discussing in this book are mostly based on scripting languages.
Linux based environments are maybe the best suited for scientists needing some intensive or versatile data processing. The type of linux system does not really matter.

Mac OS X is a close cousin of Linux, as OS X is nothing but a version of UNIX.
This does not mean that Microsoft Windows should be discarded. In first place, many scripting languages, such as perl or python, are available for MS-Windows. In addition, it is oftern possible to either install a bash emulating system (such as Cygwin) or simply to install a virtual machine.

Virtual machines offer an excellent way of testing in a safe environment. I would recommend using 'Virtual Box' for the virtual machine, as it is free. Why using virtual machines? You can install as many virtual computers you whish on your physical computer, and have different operating systems running at the same time. A virtual machine goes wrong, you messed-up something in the system? You can roll-back to a formerly saved version. Your virtual MS-Windows box caught a nasty virus? Simply delete the defective virtual machine, roll-back to a former version, re-install it.

My daily job requires me to have an MS-Windows machine, maintained by the IT-support. I simply installed virtual box, and created different VM, with different version of Linux. I can even run my own web server, limited to the company infrastructure and test my developement with my colleague, without conflicting with the company security policy.

I think a good practice is to have a clean, well maintained system on the physical PC, and host the data and processing scripts on this PC. Then, install a virtualisation software (I recommend virtual box, for a start at no cost), and share data folder from your physical PC. By doing so, destroying a virtual machine would not affect your data and processing scripts.

## Sharing directories

## Learning Linux and bash
Don't fear the beast!


