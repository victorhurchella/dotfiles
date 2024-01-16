## How To Install (Windows):

1. ### Powershell 

   - Download Hack font from Nerd Fonts
   - Change the font on Windows Terminal configuration
   - Activate the acrilic background and set the opacity to 50%
   - Duplicate the One Half Dark theme on PowerShell settings.json (openning via terminal) and change the "background" to `#001B26`.

1.  ### Scope:

	- Install scope

		```powershell
		Set-ExecutionPolicy RemoteSigned -Scope CurrentUser 
		# Optional: Needed to run a remote script the first time
		
		irm get.scoop.sh | iex
		```

1.  ### VIM:

	- Install NeoVIM

		```powershell
		scoop install neovim gcc
		```

1.  ### Open Powershell Profile Config:

	- Create the powershell config file and point it to the file inside .config/powershell:
 
        ```powershell
        nvim $PROFILE.CurrentUserCurrentHost
        ```
        or 
        ```powershell
        notepad $PROFILE.CurrentUserCurrentHost
        ```

	- Inside the file, insert the exactly line (don't miss the dot):

		```
		. $env:USERPROFILE\.config\powershell\user_profile.ps1
		```

	- Close the file and save (:wqa for saving in VIM)
  
1. ### Oh My Posh:

	- Install the Oh My Posh module:

		```powershell
		Install-Module posh-git -Scope CurrentUser -Force
		winget install JanDeDobbeleer.OhMyPosh -s winget
		```

		That's different from the devasalife video but it's the new way to install oh-my-posh, further info on: https://ohmyposh.dev/docs/migrating.

	- Change the theme inside the user_profile.ps1 file or enable a custom theme by adding and removing the # on the correct lines.

1. ### Install Powershell Modules:

	- Terminal Icons: 

		```powershell
		Install-Module -Name Terminal-Icons -Repository PSGallery -Force
		```
	  (This module is imported automatically on user_profile.ps1)

	- Z: 

		```powershell
		Install-Module -Name z -Force -AllowClobber
		```

	- PSReadLine - Autocomplete

		```powershell
		Install-Module -Name PSReadLine -Scope CurrentUser -Force -SkipPublisherCheck
		```

		Probably PSReadLine is already installed on Powershell if you're using a recent version of it.

   - PSFzf:

	 - First, install fzf with scoop:

		```powershell
		scoop install fzf
		```

	 - Then:
     
		```powershell
		Install-Module -Name PSFzf -Scope CurrentUser -Force
		```

- [In case of fire, this is the video where I learned it all from](https://www.youtube.com/watch?v=5-aK2_WwrmM)
