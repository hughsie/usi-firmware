VENDOR=Lenovo
PROJECT_NAME=ThinkPad_TBT3_WS_Dock
VERSION=3166
FIRMWARE_FILE=\
	../../fw/fr2033_app_v0.29_OneClick.hex \
	../../fw/TRDOCK_5000.bin \
	../../fw/Lenovo_Thunderbolt3_B0_Gen2_Patch_04-0E-90_Rev_0090_NVM-.ptc \
	../../fw/Panamera_fw_tbt3_Ver5_04_005.fullrom \
	../../fw/TR_Dock_Tier1_VL820Q7_FW5113.bin \
	../../fw/TR_Dock_Tier2_VL820Q7_FW5113.bin
METAINFO_FILE=\
	audio.metainfo.xml \
	dp_hub.metainfo.xml \
	tbt.metainfo.xml \
	usbhub_tier1.metainfo.xml \
	usbhub_tier2.metainfo.xml

#FIXME: mcu.metainfo.xml is missing as it's not yet installable

all: $(VENDOR)-$(PROJECT_NAME)-v$(VERSION).cab

clean:
	rm -f *.cab

check: $(METAINFO_FILE)
	appstream-util validate-relax $(METAINFO_FILE)

%.cab: $(FIRMWARE_FILE) $(METAINFO_FILE)
	gcab --create --nopath $@ $(FIRMWARE_FILE) $(METAINFO_FILE)
