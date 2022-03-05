Ansible playbook that sets up an GNOME shell tweaks and themes on an Ubuntu desktop system. 

*Tested against Ubuntu 21.10*

## Roles

* [flat remix](roles/flat_remix)
  * install [Flat Remix](https://github.com/daniruiz/flat-remix-gtk) from github
  * also include the flat remix snaps for snap package theming consistency
* [icons](roles/oxygen-cursors)
  * install the oxygen-cursor-theme & oxygen-cursor-theme-extra package for the Ubuntu repo
  * also include the oxygen-cursors snap for theming consistency with snap applications
* [gnome](roles/gnome)
  * keybinds, power, mutter, and other dconf settings
  * set theme 
  * extensions (from apt repo)
* [fonts](roles/fonts)
  * install JetBrains Mono using [nerd-fonts](https://github.com/ryanoasis/nerd-fonts)

## Requirements

* Ansible, which can be installed in a several ways, including:
  * ```apt install ansible```
  * ```python -m pip install ansible```
    
### Run

*Note: the ```-K``` flag will prompt for a sudo password to use on the tasks which require root privileges, such as updating and installing packages.*

```
cd /to/the/playbook/directory

# local
ansible-playbook -K main.yml --connection=local

# remote
ansible-playbook -K main.yml
```

## @TODO

- enable extensions
- better handling of fonts/themes that are already present
- download zips instead of cloning themes
 
## Resources

@carlwgeorge [Gnome Keybindings and Settings](https://gist.github.com/carlwgeorge/c560a532b6929f49d9c0df52f75a68ae)  
@steinwaywhw [One Liner to Download the Latest Release from Github Repo](https://gist.github.com/steinwaywhw/a4cd19cda655b8249d908261a62687f8)