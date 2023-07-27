#
#kernel dump Makefile
#
ccflags-y += -Idrivers/hisi/memory_dump/
subdir-ccflags-y              += -DTEXT_OFFSET=$(TEXT_OFFSET)
obj-$(CONFIG_HISI_KERNELDUMP) += kernel_dump.o
EXTRA_CFLAGS += -Idrivers/hisi/tzdriver/libhwsecurec
