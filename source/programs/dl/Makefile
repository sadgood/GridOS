#Must use ABICALLS by setting NORMAL_APP, the ld.sys will call the dynamic entry with t9 as base on MIPS
NORMAL_APP=yes

include $(MY_BUILD_BASE)/config.mk

OBJS					= main.o libs.o lazy.o
TARGET					= dl.sys
LDFLAGS					+= --entry=dl_dynamic_linker  -Ttext-segment=0x200000
DEPENDS =				$(SYSTEM_BUILD_TMP)/libs/elf2/$(ARCH_DIR)/elf.o
PARTS = 
ADD_INCLUDE				+= -I$(MY_BUILD_BASE)/source/libs/grid/include	
all: subs_parts $(OBJS)
	$(LD) $(LDFLAGS) -o $(TARGET) $(ADD_LDFLAGS) $(DEPENDS) *.o $(ADD_LIBS) $(ARCH_LD_FLAGS)
	$(CP) $(TARGET) $(SYSTEM_DIR)

include $(MY_BUILD_BASE)/cc.mk

 
