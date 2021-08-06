ifeq ($(CONFIG_OF),y)

dtb-$(CONFIG_BOARD_SLTEEUR) += exynos5430-slte_eur_open_03.dtb \
	exynos5430-slte_eur_open_04.dtb \
	exynos5430-slte_eur_open_06.dtb \
	exynos5430-slte_eur_open_09.dtb
	
dtb-$(CONFIG_BOARD_SLTEKOR) += exynos5430-slte_kor_open_06.dtb

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(DTB_LIST)
endif

# *.dtb used to be generated in the directory above. Clean out the
# old build results so people don't accidentally use them.
dtbs: $(addprefix $(obj)/, $(DTB_LIST))
	$(Q)rm -f $(obj)/../*.dtb

clean-files := *.dtb
