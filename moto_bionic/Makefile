KERNEL_BUILD := /Volumes/FreeBASE/kernels/moto_bionic
KERNEL_CROSS_COMPILE := arm-eabi-
EXTRA_CFLAGS := -DOMAP4 -DMAX8952
FILENAME := overclock

obj-m += $(FILENAME).o

all:
	make -C $(KERNEL_BUILD) ARCH=arm CROSS_COMPILE=$(KERNEL_CROSS_COMPILE) M=$(PWD) modules
	$(KERNEL_CROSS_COMPILE)strip --strip-debug $(FILENAME).ko
	mv $(FILENAME).ko $(FILENAME)_moto_bionic.ko

clean:
	make -C $(KERNEL_BUILD) M=$(PWD) clean 2> /dev/null
	rm -f modules.order *~
