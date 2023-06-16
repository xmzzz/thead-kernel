img_basedir := drivers/gpu/drm/img-rogue
include $(img_basedir)/config_kernel.mk

obj-$(CONFIG_DRM_POWERVR_ROGUE) += pvrsrvkm.o

ccflags-y += \
 -include config_kernel.h \
 -I$(img_basedir)/include/drm \
 -I$(img_basedir) \
 -I$(img_basedir)/include \
 -I$(img_basedir)/apollo \
 -I$(img_basedir)/km \
 -I$(img_basedir)/system \
 -D__linux__

include $(img_basedir)/pvrsrvkm.mk

obj-$(CONFIG_DRM_POWERVR_PDP) += pdp/

obj-$(CONFIG_DRM_POWERVR_APOLLO) += apollo/

obj-m	+= drm_nulldisp.o
drm_nulldisp-y	+= drm_nulldisp_drv.o drm_nulldisp_netlink.o drm_netlink_gem.o
ifeq ($(LMA),1)
drm_nulldisp-y	+= apollo/drm_pdp_gem.o
else
drm_nulldisp-y	+= drm_nulldisp_gem.o
endif
