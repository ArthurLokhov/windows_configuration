# Shell configuration(Windows terminal)

## Powershell
1. Download `Powershell`. `WARNING`: Microsoft Powershell != Powershell
2. Create in `~\Documents\Powershell` folder `powershell.config.json` file:
```json
{
    "Microsoft.PowerShell:ExecutionPolicy": "RemoteSigned"
}
```

## Scoop
```ps1
irm get.scoop.sh | iex # Install it
scoop bucket add extras
scoop install mpv
```

## Git
```ps1
scoop install git
git config --global user.email "<email>" # (1)
git config --global user.name "<name>" # (2)
```

1. Put your email desired `<email>`.
2. Put your name desired `<name>`.

## Oh-my-posh
```ps1
# Oh-my-posh
scoop install https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/oh-my-posh.json # Install it
scoop update oh-my-posh # Update it

# Posh-git
PowerShellGet\Install-Module posh-git -Scope CurrentUser -Force # Install it
PowerShellGet\Update-Module posh-git # Update it

# Terminal icons
Install-Module -Name Terminal-Icons -Repository PSGallery # Install it
Update-Module -Name Terminal-Icons # Update it

# PSReadline
Install-Module -Name PowerShellGet -Force # Install PowerShellGet 
Install-Module PSReadLine # Install it
Update-Module PSReadLine # Update it
```

## Starship
```ps1
scoop install starship # Install it
scoop update starship # Update it
```

Create configuration `starship.toml`
```toml
# ~/.config/starship.toml

add_newline = true
format = """\
[╭╴](238)$env_var\
$all[╰─](238)$character"""

[character]
success_symbol = "[](238)"
error_symbol = "[](238)"

[env_var.STARSHIP_DISTRO]
format = '[$env_value](bold white)'
variable = "STARSHIP_DISTRO"
disabled = false

[username]
style_user = "white bold"
style_root = "black bold"
format = "[$user]($style) "
disabled = true
show_always = false

[directory]
truncation_length = 3
truncation_symbol = "…/"
home_symbol = " ~"
read_only_style = "197"
read_only = "  "
format = "at [$path]($style)[$read_only]($read_only_style) "

[git_branch]
symbol = " "
format = "on [$symbol$branch]($style) "
truncation_length = 4
truncation_symbol = "…/"
style = "bold green"

[git_status]
format = '[\($all_status$ahead_behind\)]($style) '
style = "bold green"
conflicted = "🏳"
up_to_date = " "
untracked = " "
ahead = "⇡${count}"
diverged = "⇕⇡${ahead_count}⇣${behind_count}"
behind = "⇣${count}"
stashed = " "
modified = " "
staged = '[++\($count\)](green)'
renamed = "襁 "
deleted = " "

[docker_context]
format = "via [ $context](bold blue) "

[nodejs]
format = "via [ $version](bold green) "
disabled = true

[dotnet]
format = "via [$symbol($version )(🎯 $tfm )]($style)"
version_format = "v${raw}"
symbol = ".NET "
detect_extensions = ["csproj", "fsproj", "xproj", "sln"]
detect_files = ["global.json", "project.json", "Directory.Build.props", "Directory.Build.targets", "Packages.props"]
style = "bold blue"
```

## Poweshell configuration
1. Create in `~\Documents\Powershell` folder `Microsoft.PowerShell_profile.ps1` file:
```ps1
# set PowerShell to UTF-8
[console]::InputEncoding = [console]::OutputEncoding = New-Object System.Text.UTF8Encoding

# Import Modules
Import-Module posh-git
Import-Module -Name Terminal-Icons
Import-Module PSReadLine

# PSReadLine
Set-PSReadLineOption -EditMode Emacs
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -BellStyle None
Set-PSReadLineOption -PredictionViewStyle ListView

# Env
$ENV:GIT_SSH = "C:\Windows\system32\OpenSSH\ssh.exe"
$ENV:STARSHIP_CONFIG = "C:/Users/<User>/Documents/Powershell/starship.toml"
$ENV:STARSHIP_DISTRO = "者  $env:username"

# Alias
Set-Alias d dotnet
Set-Alias g git
Set-Alias ll ls
Set-Alias grep findstr
Set-Alias tig 'C:\Users\<User>\Dev\Git\usr\bin\tig.exe'
Set-Alias less 'C:\Users\<User>\Dev\Git\usr\bin\less.exe'

# Utility
function which ($command) {
  Get-Command -Name $command -ErrorAction SilentlyContinue |
    Select-Object -ExpandProperty Path -ErrorAction SilentlyContinue
}

function goto {
    param (
        $location
    )

    Switch ($location) {
        "ps1" {
            Set-Location -Path "C:/Users/<User>/Documents/Powershell"
        }
        "dev" {
            Set-Location -Path "C:/Users/<User>/Documents/dev"
        }
        default {
            echo "Invalid location"
        }
    }
}

# InvokeExpression
Invoke-Expression (&starship init powershell)
```
2. Reboot the `Windows Terminal`.