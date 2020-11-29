# Windbg-Windows-API-Call-logging

Step by step guide to generate Windows API call logging for PE files through windbg and logger.exe , windbg(x64) and Windows 10

1- Copy the manifest file LogManifest.lgm and Logexts.ini from C:\Program Files (x86)\Windows Kits\10\Debuggers\x64\winext
   to \x64\

2- Tweak the ini file for InitialStateON=1 and other settings as desired.

3- Command to get help for logexts and further commands to initialize and generate logging through windbg
	!logexts.loghelp

	!logexts.logi
	!logexts.loge
	!logexts.logc e *
	!logexts.logo e t
	g
	!logexts.logir

5- Following are the refrences
	https://github.com/evandowning/windbg-trace
	https://social.msdn.microsoft.com/Forums/en-US/57ae2e28-eb2d-4bcd-8c22-0dcb04a8703f/windbgs-logger-logextsdll-wont-work-in-winsdk-17763?forum=windbg

6- Command to use the logger util to generate the call logging
	logger.exe notepad.exe


7- On your Desktop folder you'll see a new folder "ApiLogs".

In this folder you'll see files ending in *.lgx

The LGX file can be opened with the logviewer application (in the same directory as windbg.exe). This is a detailed view of the program's API sequence.

