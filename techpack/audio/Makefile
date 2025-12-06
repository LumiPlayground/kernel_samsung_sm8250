# auto-detect subdirs
ifeq ($(CONFIG_ARCH_SDXPOORWILLS), y)
include $(srctree)/techpack/audio/config/sdxpoorwillsauto.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdxpoorwillsauto.conf)
endif
ifeq ($(CONFIG_ARCH_SM8150), y)
include $(srctree)/techpack/audio/config/sm8150auto.conf
ifeq ($(filter y,$(CONFIG_SEC_BEYOND0QLTE_PROJECT) $(CONFIG_SEC_BEYOND1QLTE_PROJECT) $(CONFIG_SEC_BEYOND2QLTE_PROJECT) $(CONFIG_SEC_BEYOND2Q5G_PROJECT) $(CONFIG_SEC_BEYONDXQ_PROJECT)),y)
include $(srctree)/techpack/audio/config/sm8150_beyondq.conf
else ifeq ($(CONFIG_SEC_WINNERLTE_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_winner.conf
else ifeq ($(filter y,$(CONFIG_SEC_WINNERX_PROJECT) $(CONFIG_SEC_ZODIAC_PROJECT)),y)
include $(srctree)/techpack/audio/config/sm8150_winner.conf
else ifeq ($(CONFIG_SEC_BLOOMQ_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_bloom.conf
else ifeq ($(CONFIG_SEC_BOLTQ5G_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_boltq5g.conf
else ifeq ($(filter y,$(CONFIG_SEC_D1Q_PROJECT) $(CONFIG_SEC_D2Q_PROJECT) $(CONFIG_SEC_D2XQ_PROJECT) $(CONFIG_SEC_D2XQ2_PROJECT)),y)
include $(srctree)/techpack/audio/config/sm8150_davinciq.conf
else ifeq ($(filter y,$(CONFIG_SEC_GTS6L_PROJECT) $(CONFIG_SEC_GTS6LWIFI_PROJECT) $(CONFIG_SEC_GTS6X_PROJECT)),y)
include $(srctree)/techpack/audio/config/sm8150_gts6l.conf
else ifeq ($(CONFIG_SEC_R3Q_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_r3.conf
else ifeq ($(CONFIG_SEC_R5Q_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_r5.conf
else ifeq ($(CONFIG_SEC_A82XQ_PROJECT), y)
include $(srctree)/techpack/audio/config/sm8150_a82.conf
else
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sm8150auto.conf)
endif
endif
ifeq ($(CONFIG_ARCH_SDMSHRIKE), y)
include $(srctree)/techpack/audio/config/sm8150auto.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sm8150auto.conf)
endif
ifeq ($(CONFIG_ARCH_KONA), y)
ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),x1q y2q z3q))
include $(srctree)/techpack/audio/config/kona_picassoq.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),c1q c2q))
include $(srctree)/techpack/audio/config/kona_canvasq.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),f2q win2q))
include $(srctree)/techpack/audio/config/kona_f2.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),gts7l gts7lwifi gts7xl gts7xlwifi))
include $(srctree)/techpack/audio/config/kona_gts7xl.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),bloomxq))
include $(srctree)/techpack/audio/config/kona_bloomx.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),r8q))
include $(srctree)/techpack/audio/config/kona_r8.conf
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),victory))
include $(srctree)/techpack/audio/config/kona_victory.conf
else
include $(srctree)/techpack/audio/config/konaauto.conf
endif
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/konaauto.conf)
endif
ifeq ($(CONFIG_ARCH_SDM660), y)
include $(srctree)/techpack/audio/config/sdm660auto.conf
export $(shell sed 's/=.*//' $(srctree)/techpack/audio/config/sdm660auto.conf)
endif

# Use USERINCLUDE when you must reference the UAPI directories only.
USERINCLUDE     += \
                -I$(srctree)/techpack/audio/include/uapi \
                -I$(srctree)/techpack/audio/include

# Use LINUXINCLUDE when you must reference the include/ directory.
# Needed to be compatible with the O= option
LINUXINCLUDE    += \
                -I$(srctree)/techpack/audio/include/uapi \
                -I$(srctree)/techpack/audio/include

ifeq ($(CONFIG_ARCH_SDXPOORWILLS), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdxpoorwillsautoconf.h
endif
ifeq ($(CONFIG_ARCH_SM8150), y)
ifeq ($(filter y,$(CONFIG_SEC_BEYOND0QLTE_PROJECT) $(CONFIG_SEC_BEYOND1QLTE_PROJECT) $(CONFIG_SEC_BEYOND2QLTE_PROJECT) $(CONFIG_SEC_BEYOND2Q5G_PROJECT) $(CONFIG_SEC_BEYONDXQ_PROJECT)),y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150_beyondq.h
else ifeq ($(CONFIG_SEC_WINNERLTE_PROJECT), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150_winner.h
else ifeq ($(filter y,$(CONFIG_SEC_WINNERX_PROJECT) $(CONFIG_SEC_ZODIAC_PROJECT)),y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150_winner.h
else ifeq ($(CONFIG_SEC_BLOOMQ_PROJECT) ,y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150_bloom.h
else ifeq ($(CONFIG_SEC_BOLTQ5G_PROJECT), y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_boltq5g.h
else ifeq ($(filter y,$(CONFIG_SEC_D1Q_PROJECT) $(CONFIG_SEC_D2Q_PROJECT) $(CONFIG_SEC_D2XQ_PROJECT) $(CONFIG_SEC_D2XQ2_PROJECT)),y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_davinciq.h
else ifeq ($(filter y,$(CONFIG_SEC_GTS6L_PROJECT) $(CONFIG_SEC_GTS6LWIFI_PROJECT) $(CONFIG_SEC_GTS6X_PROJECT)),y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_gts6l.h
else ifeq ($(CONFIG_SEC_R3Q_PROJECT), y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_r3.h
else ifeq ($(CONFIG_SEC_R5Q_PROJECT), y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_r5.h
else ifeq ($(CONFIG_SEC_A82XQ_PROJECT), y)
LINUXINCLUDE	+= \
                -include $(srctree)/techpack/audio/config/sm8150_a82.h
else
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150autoconf.h
endif
endif
ifeq ($(CONFIG_ARCH_SDMSHRIKE), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sm8150autoconf.h
endif
ifeq ($(CONFIG_ARCH_KONA), y)
ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),x1q y2q z3q))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_picassoq.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),c1q c2q))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_canvasq.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),f2q win2q))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_f2.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),gts7l gts7lwifi gts7xl gts7xlwifi))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_gts7xl.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),bloomxq))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_bloomx.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),r8q))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_r8.h
else ifeq ($(PROJECT_NAME),$(filter $(PROJECT_NAME),victory))
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/kona_victory.h
else
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/konaautoconf.h
endif
endif
ifeq ($(CONFIG_ARCH_SDM660), y)
LINUXINCLUDE    += \
                -include $(srctree)/techpack/audio/config/sdm660autoconf.h
endif
obj-y += soc/
obj-y += dsp/
obj-y += ipc/
obj-y += asoc/
