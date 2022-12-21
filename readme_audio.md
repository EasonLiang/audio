##=============================(01/02) audio-specific================================
to run, just execute them one by one in this way :
	cd elf_x86_linux ;
	./elf_2.TwoTones

Because I use archlinux thoroughly, all the depedent library is in latest , so when running in obsolete version-specific linux distribution,
such as ubuntu20.04, it might complaint that version "GLBCXX_3.4.29" and "GLIBC_2.34" inside libstdc++.so.6 and libc.so.6 not found.

firstly try to use LD_PRELOAD environment variable to load them locally :
	(a) LD_PRELOAD="$(pwd)/../libc_libstdc++/libc.so.6  $(pwd)/../libc_libstdc++/libstdc++.so.6" ./elf_2.TwoTones

if it still complaint that _dl_printf or dl_fatal_printf issues , there are 4 ways :
	(b) : download libstdc++.so.6 and libc.so.6 from https://pkgs.org and extract them into ../libc_libstdc++ and try step (a) again;
	(c) : update your system to latest one.
		If you don't want to be bothered frequently by OS itself in superfluous way.
		I suggest that just discard Ubuntu for free from version-specific issues, use archlinux or manjaro instead;
	(d) : download libstdc++.so.6 and libc.so.6 from site https://pkgs.org , and replace original one.
		**** Caution please **** , because libc.so is a heavy infrastructure in linux , mismatch in version will lead
		a system collapse , and what's more , it can't be recovered from a reboot . So before try this way , 
		I suggest backup your original libc.so.6.xxx and prepare a linux livecd to rescue your system ;
	(e) : try patchelf (ignore here , turn to your system administrator for help);
##=============================(02/02) FFT-explore================================
for purpose of FFT test, follow the steps , and so on :
	cd FFT-Test ;
	./elf_FFT-Test ;
