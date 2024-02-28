# Install a WSL2 distro

## Uninstall a distro
> wsl --unregister podman-machine-default

## If no distro
> wsl --install

## If already installed:
 ```
 wsl --list --online    # to see available distros
 wsl -- install - d <DistroName>
```
## Change DwsL Version
> wsl --set-versions