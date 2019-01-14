# Out-of-tree Mali driver

After building the mainline Linux tree, run (where `~/linux` is the location of
the kernel source code; more flags needed for cross-compiling?):

	$ make KDIR=~/linux -j4

When this completes, there will be a file located at:

	driver/product/kernel/drivers/gpu/arm/midgard/mali_kbase.ko

Copy that file to the target running the mainline tree, and run (as root on the target):

	# insmod mali_kbase.ko
	# chmod 666 /dev/mali0
