

Below are the requirements:
- every normal user can run common Linux commands; every rbash user (symlink commands to /rbash-bin) can run nothing except login, GUI terminal, logout, and RealVNC vncviewer;
- upon start it enters a GUI greeter login screen (with a given wallpaper image, and date/time, hiding user list);
- after login, launch message-of-the-day popup (specified by the multi-line text in `/etc/motd`)  followed by vncviewer;
- do show the taskbar with the 2 app buttons (X terminal and vncviewer), buttons for lock-screen and logout, and date/time (with day-of-week in fullname and time up to seconds);
- VNCviewer can connect to multiple servers simultaneously and switching views;
- idle screen lock is enforced (after 15 minutes inactivity) and secured (cannot bypass by Ctrl+Alt+FN, session locking must work correctly regardless of whether VNCviewer is in fullscreen or not, and for whatever value of VNC GrabKeyboard);
- do not disable Ctrl+Alt+Fn, reserve the 1st 4 seats for TTY, i.e., Ctrl+Alt+F1-4
- switching user must be supported; locked sessions by different users must be preserved;
- in the lock screen, display the current username and add a button to switch user (clicking it will switch to the main login screen); after 1 hour of not unlocking it, auto switch to the main login screen;
- at the main login screen, login to a logged-in user (with a locked session) will instead switch to and unlock the session rather than creating a new session;
- do not install kernal and Linux drivers, the root folder will be NFS-mounted by many clients booted via PXE; thus, you must disable all possible ways of sleep/suspend and change all possible ways of reboot/poweroff to "sync followed by sending direct magic SysRq" (because the default shutdown process will disconnect network -> lose root directory -> system hang);
- in production, the root folder ./rootfs will be mounted by many clients on the local network: home and var will be mounted as read/write; the rest will be mounted as read-only;
- do not create a global kiosk user, each user should be able login/logout and have their own set of accessible servers in the VNC main window;
- pre-create 2 test users: user01 (fullname: "User01 Normal") and user02 (fullname: "User02 Restricted") both with the password abcd1234, also set root password to be the same.

