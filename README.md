# My First Book with Markdown
## Some Collection of Pointers
- [How to Create a Book ](/s/how-to-create-book)
- [How to Save Versions](/s/how-to-save)
- [Xilinx Vitis Discussion](https://www.eevblog.com/forum/fpga/xilinx-announces-vitis/?PHPSESSID=o7e7u7ieeshb8lo6jc8hjisf75)
- [FPGA Learning Video](https://www.youtube.com/user/LBEbooks/playlists)
- [FPGA Starter Discussion](https://www.eevblog.com/forum/fpga/exercise-focused-fpga-learning-resource/?PHPSESSID=o7e7u7ieeshb8lo6jc8hjisf75)
- [ARM CM4 Instruction Set Manual](https://developer.arm.com/docs/dui0553/a/the-cortex-m4-instruction-set/memory-access-instructions/ldrex-and-strex)

## Some Log of Random Thoughts
- **Algorithm** Want to design a fast algorithm, given an array of key strings, and one input string, find the first matching key for the input string.
- **To-Study** When learning the totoally new topic, the time spent is most fruteful. New topic should be worthwhile though, like FPGA & RISC-V.
- **Cool-Do** Want to use a MD document to create an mind-map for all the knowledge and notes for the topics that I am required to master.

## Notes for ARM Processor and Assembly
[ARM CM4 Instruction Set Manual](https://developer.arm.com/docs/dui0553/a/the-cortex-m4-instruction-set/memory-access-instructions/ldrex-and-strex)

## Notes on Linux Kernel development and debugging
**Printk calls** - [dev_dbg()/pr_info()/dev_info()](   https://elinux.org/Debugging_by_printing)
The pr_* macros (with exception of pr_debug) are simple shorthand definitions in include/linux/printk.h for their respective printk call and should probably be used in newer drivers.

pr_devel and pr_debug are replaced with printk(KERN_DEBUG ... if the kernel was compiled with DEBUG, otherwise replaced with an empty statement.

For drivers the pr_debug should not be used anymore (use dev_dbg instead). 

**Kernal module entry macro - module_init()**
* It is in include/linux/init.h. 
* The module_init() macro defines which function is to be called at module insertion time (if the file is compiled as a module), or at boot time: if the file is not compiled as a module the module_init() macro becomes equivalent to __initcall(), which through linker magic ensures that the function is called on boot.

**devm_kzalloc()**
[A Good Note on StackOverflow](https://stackoverflow.com/questions/12256986/what-is-the-difference-between-devm-kzalloc-and-kzalloc-in-linux-driver-prog)
* kzalloc() allocates kernel memory like kmalloc(), but it also zero-initializes the allocated memory. devm_kzalloc() is managed kzalloc(). The memory allocated with managed functions is associated with the device.
* The memory allocated with kzalloc() should be freed with kfree(). The memory allocated with devm_kzalloc() is freed automatically.

**PCI configuration space** [Notes from Wikipedia](https://en.wikipedia.org/wiki/PCI_configuration_space)
* PCI devices have a set of registers referred to as configuration space and PCI Express introduces extended configuration space for devices. Configuration space registers are mapped to memory locations. Device drivers and diagnostic software must have access to the configuration space, and operating systems typically use APIs to allow access to device configuration space.
* **Bus Enumeration -** The system's firmware, device drivers or the operating system program the **Base Address Registers** (commonly called **BAR**s) to inform the device of its address mapping by writing configuration commands to the PCI controller. After *PCI Bus Enumeration*, the BIOS or operating system will program the memory-mapped and I/O port addresses into the device's BAR configuration register. These addresses stay valid as long as the system remains turned on. Upon power-off, all these settings are lost and the procedure is repeated next time the system is powered back on.
* **void __iomem * pci_iomap(struct pci_dev * dev, int bar, unsigned long maxlen)** Using this function you will get a __iomem address to your device BAR. You can access it using ioread*() and iowrite*(). These functions hide the details if this is a MMIO or PIO address space and will just do what you expect from them in the correct way.

## Notes for my Black Friday Shopping
### Digital camera
Some models that are 2-3 years old pack good performance while can see great price offers during BF or Prime-Day. 

**Sony alpha a7 II -** full frame, 2019 deal about $990 for the kit

**Fujifilm -**

**Canon -**

## Notes for Car Shopping
[US News 3-Row SUV Ranking page](https://cars.usnews.com/cars-trucks/rankings/suvs-with-3-rows)

- **Mazda CX-9** MPG: 26-28 Hwy, HP 227. **Turing** trim base price  $35,330. 


## Text Playground for Experimenting with *Markdown*
Experiment for Latex support: \(E=mc^2\)
> Latex is a great document formatting language that was invented by reknowned computer scientist *Don Knuth*. It is very strong in describing in plain text of formatting mathmatical formulae.

Now I have text that is outside of the example of definition with *Markdown* language. Simple equations can be formatted with subscripts and superscripts: *E*~0~=*mc*^2^.

Currently I found this [online editor](https://upmath.me) which supports *Markdown* and *Latex* integration. I can write a block of *Latex* text in it, making sure it is correct and then copy-paste it here, as this site supports saving into my *GitHub* account. Here is one example of inclusion of matrix.

$$T^{\mu\nu}=\begin{pmatrix}
\varepsilon&0&0&0\\
0&\varepsilon/3&0&0\\
0&0&\varepsilon/3&0\\
0&0&0&\varepsilon/3
\end{pmatrix}.$$

And here is another try:
![ChaoLatexImage1](//tex.s2cms.ru/svg/%24%24T%5E%7B%5Cmu%5Cnu%7D%3D%5Cbegin%7Bpmatrix%7D%0A%5Cvarepsilon%260%260%260%5C%5C%0A0%26%5Cvarepsilon%2F3%260%260%5C%5C%0A0%260%26%5Cvarepsilon%2F3%260%5C%5C%0A0%260%260%26%5Cvarepsilon%2F3%0A%5Cend%7Bpmatrix%7D.%24%24)
This is achieved by just using this pure [*Latex* online editor](https://tex.s2cms.com). **My thought:** I really think this website is very useful toegether with hackmd.io, and here is another example of showning a general matrix:
![ChaoLatexImage2](https://tex.s2cms.ru/svg/A_%7Bm%2Cn%7D%20%3D%20%5Cbegin%7Bpmatrix%7D%0A%20a_%7B1%2C1%7D%20%26%20a_%7B1%2C2%7D%20%26%20%5Ccdots%20%26%20a_%7B1%2Cn%7D%20%5C%5C%0A%20a_%7B2%2C1%7D%20%26%20a_%7B2%2C2%7D%20%26%20%5Ccdots%20%26%20a_%7B2%2Cn%7D%20%5C%5C%0A%20%5Cvdots%20%20%26%20%5Cvdots%20%20%26%20%5Cddots%20%26%20%5Cvdots%20%20%5C%5C%0A%20a_%7Bm%2C1%7D%20%26%20a_%7Bm%2C2%7D%20%26%20%5Ccdots%20%26%20a_%7Bm%2Cn%7D%0A%5Cend%7Bpmatrix%7D).
(Note: For this second example, I add ```https:``` to the image insert's URL part, and when I export the result document, the image of *Latex* rendering shows up.)



