# Nightsky, my personal Arch Linux setup
![Nightsky!](https://github.com/kerichdev/nightfiles/blob/main/banner.nightsky?raw=true "Nightsky Banner")

## What is it based on?
Nightsky includes various resources from other brojects, like:
- [Catppuccin (catppuccin org)](https://github.com/catppuccin/catppuccin)

## Installation and setup
Clone the repo locally. Since it includes submodules from my own forks to preserve licenses, make sure to clone recursively:
```
git clone --recursive https://github.com/kerichdev/nightfiles
```
Firstly, you should install the packages. Open a terminal of choice (Will be replaced with alacritty), and install your favorite AUR helper. Mine is `yay`, so i will go by it.

To install the packages needed for the setup, go to the directory where you cloned the repo, and do:
```
yay -S - < deplist.nightsky
```
Then follow the steps your AUR helper gives you.

**(The deplist may be incomplete! If you notice something not working, feel free to add any packages into the list, and I will see if I did, in fact, miss them.)**

Then, move the contents of the repo `.config` folder, to your `.config` folder in `$HOME` (`/home/YOUR_USERNAME/.config/`)

### Betterlockscreen
Betterlockscreen requires some additonal setup. First of all, once you copy the config and the wallpaper to their respective folders, generate a lockscreen pre-render:
```
betterlockscreen -u ~/Wallpapers/tropic_island_night.jpg
```
Then, enable the systemd service for automatic lock-on-suspend:
```
systemctl enable betterlockscreen@$USER
```