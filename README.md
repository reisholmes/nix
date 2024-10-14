Nix repo experimenting with flakes.

Modified from someone smarter than me: https://github.com/pusherofbrooms/ops-tool-belt/tree/main

The main idea is to easily install all packages required into our profile with one profile command.

1. Install nix package manager as per the instructions at https://nixos.org/download.html

2. Enable nix flakes and experimental tooling.
  - [Flakes](https://nixos.wiki/wiki/Flakes) allow for highly configurable environments,
    - See this [youtube video](https://www.youtube.com/watch?v=cw4wJjjQYMU) for more info.
  - Set nix to allow flakes to be used, add "experimental-features = nix-command flakes" to /etc/nix/nix.conf

3. Run `nix profile install .#stdPkgs` to install the packages.

4. Run `nix profile upgrade stdPkgs` to update the profile when you add new packages.

5. Don't forget that some tools may require you to reload the shell
