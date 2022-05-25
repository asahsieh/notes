# Set up a OS
## Sync dotfiles and scripts to automatically set up a OS 
- [Move your dotfiles to version control](https://opensource.com/article/19/3/move-your-dotfiles-version-control#*)
    - Try [chezmoi](https://github.com/twpayne/chezmoi)
- My git repo to achieve this goal: [asahsieh / my-os-home-dir](https://github.com/asahsieh/my-os-home-dir.git)
## Mac OS X 
- [[Mac] 打造美觀又潮的終端機：iTerm + Oh My Zsh + Agnoster + Powerline](http://blog.ctrlxctrlv.net/mac-iterm-zsh/)
- [在macOS (OSX)上建立APFS的高性能Ramdisk](https://blog.jhangy.us/post/create-ramdisk-on-macos/) 
	- ~~在macOS Catalina v10.5, 會因此版本OS新增的System security功能，導致在launchAgent執行失敗，可改用[在 Mac 上的 Automator 工作流程中使用 Shell 工序指令](https://support.apple.com/zh-tw/guide/automator/autbbd4cc11c/2.10/mac/10.15)~~ => 只是建立一個workflow檔，非加入power on的procedure中。
	- Debug and fix
		1. Check executed result of `launchctl load *.plist` in `/var/log/system.log` and we found that our .sh file is executed as a Mach-O executable file and is exited:
	  	![](https://i.imgur.com/KXKpPKp.png)
	  	Ref.: https://stackoverflow.com/a/13372744
		2. Continue from 1., it means that we need to tell OS to execute .sh file by `/bin/bash`. There should have two keys be added, the first one, `Program`, is to specify which command to be used; and another one, `ProgramArguments`, invoke the command and the .sh file we want to execute as argument of the program. Referenced code is marked in yellow as follows:
		![](https://i.imgur.com/uEuUO6C.png)
		Ref.: https://stackoverflow.com/a/64020293
- [Disabling and Enabling System Integrity Protection on v10.5 or above](https://developer.apple.com/documentation/security/disabling_and_enabling_system_integrity_protection)
### Shortcuts
- mac bring select app to front
  *CMD-TAB-OPTION-release*

## Linux
### Distro
- [Ubuntu](/JCdoImyGQ32r_entHMzPKw) 
  
## 編輯器
[VIM](/sfjW7NLjR9CGTfjEOCsqrQ)

## Terminal
### 管理多終端機視窗工具
#### Byobu
* **Frequently-used shortcuts**

| Function | Shortcut |
| -------- | -------- |
新增terminal分頁 | `F2` 
switch between terminal	| `F3`,`F4`
刪除terminal | `^D` or `ctrl`+`F6`
新增水平terminal | `shift`+`F2`
新增垂直terminal | `escape character`+`%` or `ctrl`+`F2`
切換panes | `shift`+方向鍵

* **FAQ**
	* [issue of shortcut on MAC OS X, and a method to fix](https://stackoverflow.com/questions/26180096/os-x-byobu-vertical-split/26470118#26470118)
	* [How to use mouse in Byobu](https://codeyarns.com/tech/2016-01-28-how-to-use-mouse-in-byobu.html)
      *To toggle mouse support, press `Alt+F12`*
	* [Detach a remote screen session in byobu](https://stackoverflow.com/a/19032627)
	
### Frequently-used/useful shortcuts
- clear screen: `ctrl+L`

## Applications
### Note taking
- [Use Joplin on terminal](https://github.com/laurent22/joplin/blob/dev/readme/terminal.md)
### Screenshot
- To avoid RTK's VPN
    - `ScreenShotPro` in Microsoft Store
- Open sourced: `Greenshot` 

###### tags: `computer_system`