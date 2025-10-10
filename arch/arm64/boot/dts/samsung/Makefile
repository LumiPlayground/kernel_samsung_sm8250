# SPDX-License-Identifier: GPL-2.0

SAMSUMG_DTB := arch/$(SRCARCH)/boot/dts/samsung
QCOM_DTB := ../vendor/qcom

define __sec_dtbo_build
dtbo-$(2) += $(1)
$(1)-base := $(3)
endef

define sec_dtbo_build
$(foreach dtbo, $(1), $(eval $(call __sec_dtbo_build, $(dtbo),$(2),$(3))))
endef

# KONA BASE DTB
SEC_KONA_BASE_DTB := $(QCOM_DTB)/kona.dtb $(QCOM_DTB)/kona-v2.dtb $(QCOM_DTB)/kona-v2.1.dtb

ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)

SEC_KONA_SPU_DTBO := \
		common/kona-sec-system-update-overlay.dtbo

$(eval $(call sec_dtbo_build, \
		$(SEC_KONA_SPU_DTBO),$(CONFIG_ARCH_KONA),$(SEC_KONA_BASE_DTB)))

endif

ifeq ($(filter y,$(CONFIG_SEC_BEYOND0QLTE_PROJECT) $(CONFIG_SEC_BEYOND1QLTE_PROJECT) $(CONFIG_SEC_BEYOND2QLTE_PROJECT) $(CONFIG_SEC_BEYONDXQ_PROJECT)),y)
dts-dirs += beyond
else ifeq ($(filter y,$(CONFIG_SEC_D1Q_PROJECT) $(CONFIG_SEC_D2Q_PROJECT) $(CONFIG_SEC_D2XQ_PROJECT) $(CONFIG_SEC_D2XQ2_PROJECT)),y)
dts-dirs += davinci
else ifeq ($(filter y,$(CONFIG_SEC_WINNERLTE_PROJECT) $(CONFIG_SEC_WINNERX_PROJECT)),y)
dts-dirs += winner
else ifeq ($(filter y,$(CONFIG_SEC_GTS6L_PROJECT) $(CONFIG_SEC_GTS6LWIFI_PROJECT) $(CONFIG_SEC_GTS6X_PROJECT)),y)
dts-dirs += gts
else ifeq ($(filter y,$(CONFIG_SEC_BLOOMQ_PROJECT)),y)
dts-dirs += bloom
else ifeq ($(filter y,$(CONFIG_SEC_BOLTQ5G_PROJECT)),y)
dts-dirs += bolt
else ifeq ($(filter y,$(CONFIG_SEC_R5Q_PROJECT) $(CONFIG_SEC_R3Q_PROJECT)),y)
dts-dirs += renovation
else ifeq ($(filter y,$(CONFIG_SEC_ZODIAC_PROJECT)),y)
dts-dirs += zodiac
else ifeq ($(filter y,$(CONFIG_SEC_A82XQ_PROJECT)),y)
dts-dirs += a82
endif

dts-dirs += x1q
dts-dirs += y2q
dts-dirs += z3q

always          := $(dtb-y)
subdir-y        := $(dts-dirs)

clean-files := *.dtb *.reverse.dts *.dtbo
