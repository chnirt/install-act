# install-act
Run your GitHub Actions locally!

# Chnirt

## Installation through package managers

### [Homebrew](https://brew.sh/) (Linux/macOS)

[![homebrew version](https://img.shields.io/homebrew/v/act)](https://github.com/Homebrew/homebrew-core/blob/master/Formula/act.rb)

```shell
brew install act
```

or if you want to install version based on latest commit, you can run below (it requires compiler to be installed installed but Homebrew will suggest you how to install it, if you don't have it):

```shell
brew install act --HEAD
```

### [MacPorts](https://www.macports.org) (macOS)

[![MacPorts package](https://repology.org/badge/version-for-repo/macports/act-run-github-actions.svg)](https://repology.org/project/act-run-github-actions/versions)
install [MacPorts](https://guide.macports.org/#installing.macports.git) before execute below
check port:
```shell
port --version
```

install act:

```shell
sudo port install act
```

### [Nix](https://nixos.org) (Linux/macOS)

[Nix recipe](https://github.com/NixOS/nixpkgs/blob/master/pkgs/development/tools/misc/act/default.nix)

Install [Nix](https://nixos.org/download.html):
```shell
sh <(curl -L https://nixos.org/nix/install) --daemon
```

Global install:

```sh
nix-env -iA nixpkgs.act
```

or through `nix-shell`:

```sh
nix-shell -p act
```

Using the latest [Nix command](https://nixos.wiki/wiki/Nix_command), you can run directly :

```sh
nix run nixpkgs#act
```

### [Docker](https://www.docker.com/) (macOS)

Install Docker

```shell
brew install --cask docker
```

Check Docker

```shell
docker ps
```

### Quickstart for GitHub Actions
- Create a .github/workflows directory in your repository on GitHub if this directory does not already exist.
- In the .github/workflows directory, create a file named github-actions-demo.yml. For more information, see "Creating new files."
- Copy the following YAML contents into the github-actions-demo.yml file:

```shell
name: GitHub Actions Demo
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v3
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
```

### Run act to execute

```shell
act
```

**Free Software, Hell Yeah!**
