# SPDX-License-Identifier: GPL-2.0-only
#
# Copyright (C) 2006-2011 OpenWrt.org

include $(TOPDIR)/rules.mk

ARCH:=i386
BOARD:=x86
BOARDNAME:=x86
FEATURES:=squashfs vdi vmdk vhdx pcmcia fpu boot-part rootfs-part
SUBTARGETS:=64 generic legacy geode 

KERNEL_PATCHVER:=6.6
KERNEL_TESTING_PATCHVER:=6.1

KERNELNAME:=bzImage

include $(INCLUDE_DIR)/target.mk

DEFAULT_PACKAGES += partx-utils mkf2fs e2fsprogs kmod-button-hotplug kmod-usb-hid kmod-mmc kmod-sdhci kmod-fs-f2fs amd64-microcode intel-microcode cfdisk usbutils pciutils \
kmod-alx kmod-e1000e kmod-igb kmod-igc kmod-igbvf kmod-iavf kmod-bnx2x kmod-pcnet32 kmod-tulip kmod-via-velocity kmod-vmxnet3 kmod-i40e kmod-i40evf \
kmod-sound-hda-core kmod-sound-hda-codec-realtek kmod-sound-hda-codec-via kmod-sound-via82xx kmod-sound-hda-intel kmod-sound-hda-codec-hdmi kmod-sound-i8x0 \
kmod-usb-net kmod-usb-net-asix-ax88179 kmod-usb-net-rtl8150 kmod-usb-net-aqc111 kmod-mlx4-core kmod-mlx5-core kmod-drm-i915 kmod-drm-amdgpu kmod-usb-audio \
kmod-usb-net-rtl8152-vendor kmod-r8125 kmod-r8126 kmod-r8168 kmod-8139cp kmod-8139too kmod-tg3 htop lm-sensors autocore-x86 automount autosamba ca-bundle \
ddns-scripts_aliyun ddns-scripts_dnspod ca-certificates \
homelede-autoconfig \
dockerd docker open-vm-tools \
bind-dig unrar unzip dmesg p7zip \
luci-theme-infinityfreedom luci-theme-argon-dark-mod luci-theme-netgear luci-theme-opentomato luci-theme-opentomcat \
ipv6helper \
luci-app-accesscontrol luci-app-control-timewol luci-app-control-webrestriction luci-app-control-weburl \
luci-app-samba luci-app-cifs-mount  \
luci-app-dockerman luci-app-hd-idle \
luci-app-homeconnect luci-app-homeredirect \
luci-app-mwan3 luci-app-syncdial \
luci-app-ttyd luci-app-upnp luci-app-vlmcsd luci-app-vsftpd luci-app-watchcat luci-app-wol luci-app-ramfree \
ppp-mod-pppoa ppp-mod-pppoe ppp-mod-pppol2tp ppp-mod-pptp pppossh xl2tpd 

$(eval $(call BuildTarget))

$(eval $(call $(if $(CONFIG_ISO_IMAGES),SetupHostCommand,Ignore),mkisofs, \
	Please install mkisofs. , \
	mkisofs -v 2>&1 , \
	genisoimage -v 2>&1 | grep genisoimage, \
	xorrisofs -v 2>&1 | grep xorriso \
))
