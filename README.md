# Software


## Adobe
* Adobe Acrobat DC			
* Adobe Creative Cloud
* Adobe Illustrator CC 2018	
* Adobe InDesign 2020	
* Adobe Lightroom Classic CC
* Adobe Photoshop 2020	


## Microsoft
* Microsoft Word.app
* Microsoft Excel.app
* Microsoft PowerPoint.app
* Microsoft Remote Desktop.localized


## Music & Video / Creative
* MainStage 3.app
* Logic Pro X.app	
* Final Cut Pro.app	
* OBS.app
* KeyCastr.app
* Loopback.app		
* MPEG Streamclip.app			


## Players
* VLC.app

### Todo / Del
* IINA.app


## Games
* Minecraft.jar (TLauncher)
* Roblox.app



## DYI
* Notion.app
* Autodesk Autocad + Fusion 360

## Design
* Axure RP 8.app			
* Sketch.app + CraftManager.app
* MAXON Cinema 4D + RLM
* Exposure X5.app

### Del
* Principle.app


## Development
* PhpStorm.app
* Android Studio.app	
* Atom.app
* PhoneGap.app
* Sourcetree.app
* VirtualBox.app
* Visual Studio Code.app
* Xcode.app

### Todo / Del
* Sequel Pro.app
* Docker.app

## Communication
* Skype.app
* WhatsApp.app
* Telegram.app
* Upwork.app

### Todo / Del
* Discord.app	


## Tools
* Paste.app
* Android File Transfer.app
* ColorSnapper2.app
* DaisyDisk.app	
* PuntoSwitcher.app
* Electrum.app	
* iStat Menus.app
* Grammarly.app				
* Intel Power Gadget	
* Kaleidoscope.app
* Karabiner-Elements.app	
* Keka.app	
* LastPass.app	
* XLD.app
* coconutBattery.app
* DriveDx

### Rare
* freeshuttercounter.app
* gSwitch.app
* MAYA22 Panel.app	

### Todo / Del
* ImageOptim.app	
* Gifox.app			
* Alfred 3.app			
* NarodmonApp.app (?)
* Commander One.app
* DiskMaker X 9 for macOS Catalina.app
* Dropzone 3.app
* SnippetsLab.app
* Magnet.app	

## Clouds
* Dropbox.app


## Browsers & Internet & Network
* Firefox.app	
* TorBrowser.app
* Transmission.app
* TunnelBear.app
* Tunnelblick.app	
* FileZilla.app
* Gas Mask.app	
* LuLu.app	
		
		
		
# Try It
## Best
* Bubble Translate
* Numi
	
## Maybe
* Soda Player (torrents-player)
* Yoink (as a Dropzone)
* iA Writer

* Adguard
* 1Blocker

# Scripts

## TODO


# Notes

## Read
https://medium.com/mactools/%D1%87%D1%82%D0%BE-%D0%B2-%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B5-%D0%BC%D0%B5%D0%BD%D1%8E-%D0%B2%D0%B0%D1%88%D0%B5%D0%B3%D0%BE-%D0%BC%D0%B0%D0%BA%D0%B0-5268cb1cb3cd


## Ruby / gem / cocoapods
Error on:
```
sudo gem install cocoapods
```

Try to switch ruby to homebrew version.
```
brew install ruby
brew link --overwrite ruby
```
If you need to have ruby first in your PATH run:
```
echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile
```

For compilers to find ruby you may need to set:
```
export LDFLAGS="-L/usr/local/opt/ruby/lib"
export CPPFLAGS="-I/usr/local/opt/ruby/include"
```

For pkg-config to find ruby you may need to set:
```
export PKG_CONFIG_PATH="/usr/local/opt/ruby/lib/pkgconfig"
```

If not helped:

For Xcode 11 on macOS 10.14, this can happen even after installing Xcode and installing command-line tools and accepting the license with
```
sudo xcode-select --install
sudo xcodebuild -license accept
```
The issue is that Xcode 11 ships the macOS 10.15 SDK which includes headers for ruby2.6, but not for macOS 10.14's ruby2.3. You can verify that this is your problem by running
```
ruby -rrbconfig -e 'puts RbConfig::CONFIG["rubyhdrdir"]'
```
which on macOS 10.14 with Xcode 11 prints the non-existent path
```
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.15.sdk/System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/include/ruby-2.3.0
```
However, Xcode 11 installs a macOS 10.14 SDK within /Library/Developer/CommandLineTools/SDKs/MacOS10.14.sdk. It isn't necessary to pollute the system directories by installing the old header files as suggested in other answers. Instead, by selecting that SDK, the appropriate ruby2.3 headers will be found:
```
sudo xcode-select --switch /Library/Developer/CommandLineTools
ruby -rrbconfig -e 'puts RbConfig::CONFIG["rubyhdrdir"]'
```
This should now correctly print
```
/Library/Developer/CommandLineTools/SDKs/MacOSX10.14.sdk/System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/include/ruby-2.3.0
```
Likewise, ```gem install``` should work while that SDK is selected.

To switch back to using the current Xcode 11 SDK, use
```
sudo xcode-select --switch /Applications/Xcode.app
```		

	
	

		

		
			
		

			

