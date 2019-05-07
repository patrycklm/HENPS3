PS3HEN v2.0.0

Compatible with 4.84 HFW ONLY


WHAT IS HEN:
HEN stands for Homebrew ENabler. it also consists of much more new functions relatively close to a CFW


File Hash Verify

PS3HEN.BIN 	8bb70295550bb1f92e8c37b39ad23f84
stackframe.bin 	08d6299d3788486cb7596f4a5857c01f


Plugins Support (Online and Offline Methods):

Place boot_plugins.txt on dev_usb000 if using plugins
Place boot_plugins_kernel.txt on dev_usb000 if using kernel plugins






Standard Online/Local Host HEN Setup Instructions
-------------------------------------------------

** HEN status is verified with /html/ps3hen.html, and will display an error if HEN does not load from USB **

1) Copy PS3HEN.BIN and stackframe.bin to /dev_usb000/
2) Run the /html/ps3hen.html




Offline HEN Setup Instructions
------------------------------

** Offline packages do not verify HEN load This should not be a problem and people reported issues with verify on **


** REQUIRED BEFORE STARTING **

Run HAN Installer To Get Package Manager
http://ps3xploit.com/hfw/release/ps3_tools-v3.0-HAN484_HFW_release_PS3XPloit.zip


Run From Hard Drive (Recommended):

1) Run /html/han_flash_mount.html
2) Install HEN_v2_Offline_Installer_HDD_signed.pkg
3) Reboot PS3
4) Launch From New "Enable HEN" XMB Icon, Under Game Column


Run From USB:

* This method requires that the USB drive be plugged in to load PS3HEN
* Some USB drives are not compatible and will not work

* If PS3HEN.BIN is missing, you will get a failed message and need to reboot console
* If stackframe.bin is missing, your console will freeze, and you will need to reboot

1) Run /html/han_flash_mount.html
2) Install HEN_v2_Offline_Installer_USB_signed.pkg
3) Reboot PS3
4) Place PS3HEN.BIN and stackframe.bin on dev_usb000
5) Launch From New "Enable HEN" XMB Icon, Under Game Column




CHANGELOG
----------

v2.0.0

- HOTFIX: Removed HEN Check From Offline Packages

- Fake flash is no longer used, in favor of on-the-fly patching
- Fixed blackscreen crashes
- Fixed random recovery kicks
- ISO support added
- PS3MAPI support can now read/set process mem using webman
- KW stealth extensions added
- Random lv2 panic fixed
- Added check in html for hen success
- Kernel plugins support
- Photo gui opcode support for webman
- Syscall 389/409 product mode check disabled
- Opcode 1339 added, returns HEN version (0x0200)

Notes:

WebmanMOD tested with 1.47.17 and 1.47.19, with fan control and PS3MAPI working



v1.0.0

- Managunz backup manager works best for jb rips(ISO not supported)!
- MULTIMAN works too but compatibility is not the same.
- PSXISO Support is there!!!!
- BD/DVD Region patches
- BDISO support(stutter with xmb, use showtime)
- BOOTPLUGINS WORK location "/dev_usb000/boot_plugins_nocobra.txt"(Use webman original one and not the mod one. also disable - content scan on boot in settings)
- Discless games work with disc icon!
- Syscall 6 added
- Syscall 7 added(address>0x8000000000352230) and disabled overwriting syscall 0->15
- Syscall 15 added
- Syscall 8 opcodes added for detection HEN and for advanced lv2 poke(read DEVELOPER SECTION)
- Whole kernel memory RWX(execute kernel payload like this at high locations or hook syscalls etc)
- PS3MAPI support for modding
- Debug PKG install
- Homebrew resigned for 3.55 and less support!
- Homebrew Root Flags enabled!
- HAN PKG insall support
- PSN Connectivity
- All process executed after HEN have rwx permissions!
- HAN Enabled by default!

CFW PATCHES:
	CFW settings
	Retail/DEBUG pkg installation
	Unlink to Delete
	Remote play with PC
	Download debug pkg on retail
	Remote play ignores SFO check
	Cinavia protection
    videoplayer_plugin
	DVD region check (not cracking RCE)
	REBUG themed RCO & XML
	AIO copy

NOTES:
	if you get error 80010017 launching homebrew that simply means HEN failure, restart console and try again!(restart is important!)
	also try deleting cache, browsing data, cookies and the likes from browser, make the exploit page the home page
	
DEVELOPERS:
	   #define SYSCALL8_OPCODE_IS_HEN						0x1337
	   using this if return 0x1337 its hen
		
	   ADVANCED POKE:syscall8(0x7003, addr, value);
			 this allows poking any location in lv2 memory BUT you have to restore original value before exiting to another application or exiting to xmb.USE WISELY OTHERWISE PS3 SHUTS DOWN

	   BDMIRROR:Managunz FTW!(please use Cobra payload because by default its MULTIMAN) 	
	   NOTE:mounting dev_blind will actually mount dev_flash. change files directly from dev_flash instead or hdd0/plugins/CFW/			
		
	   Kernel Mode returns 0x53434500 on success to user webkit 0x8a000000. its good to measure HEN success. right now hen is already close to or is 100%
	   




