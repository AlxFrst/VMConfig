# VM Setup istallation
You will find here the steps to install best pre-configured VM for development.
If you have any question or suggestion, please contact me in issues section.

Let's start 🚀

### Environment
- OS: Ubuntu 20.04
- Desktop Environment: Gnome
- Shell: Zsh


## Oh My Zsh
Now we will install Oh My Zsh, a framework for managing your Zsh configuration.

```bash
sudo apt update
sudo apt install -y curl imagemagick jq unzip vim zsh tree
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

:warning: Do this only if you want to use the theme powerlevel10k

Add Powerlevel10k theme to Oh My Zsh
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```

reload zsh
```bash
exec zsh
```

Nice! Now we have a beautiful terminal with a lot of features.

## GitHub CLI installation

Let's now install [GitHub official CLI](https://cli.github.com) (Command Line Interface). It's a software used to interact with your GitHub account via the command line.

In your terminal, copy-paste the following commands and type in your password if asked:

```bash
sudo apt update && sudo apt install git
sudo apt remove -y gitsome # gh command can conflict with gitsome if already installed
```

```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update && sudo apt install -y gh
```

To check that `gh` has been successfully installed on your machine, you can run:

```bash
gh --version
```

:heavy_check_mark: If you see `gh version X.Y.Z (YYYY-MM-DD)`, you're good to go :+1:

### GitHub CLI

CLI is the acronym of [Command-line Interface](https://en.wikipedia.org/wiki/Command-line_interface).

In this section, we will use [GitHub CLI](https://cli.github.com/) to interact with GitHub directly from the terminal.

It should already be installed on your computer from the previous commands.

First in order to **login**, copy-paste the following command in your terminal:

:warning: **DO NOT edit the `email`**

```bash
gh auth login -s 'user:email'
```

gh will ask you few questions:

- **What account do you want to log into?** :arrow_right: Select your GitHub account


## Node.js

[Node.js](https://nodejs.org/en/) is a JavaScript runtime to execute JavaScript code in the terminal. Let's install it with [nvm](https://github.com/nvm-sh/nvm), a version manager for Node.js.

In a terminal, execute the following commands:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | zsh
exec zsh
```

Then run the following command:

```bash
nvm -v
```

You should see a version. If not, ask a teacher.

Now let's install node:

```bash
nvm install 16.15.1
```

When the installation is finished, run:

```bash
node -v
```

If you see `v16.15.1`, the installation succeeded :heavy_check_mark: You can then run:

```bash
nvm cache clear
```



### yarn

[`yarn`](https://yarnpkg.com/) is a package manager to install JavaScript libraries. Let's install it:

In a terminal, run the following commands:

```bash
npm install --global yarn
exec zsh
```

Then run the following command:

```bash
yarn -v
```

:heavy_check_mark: If you see a version, you're good :+1:

## Terraform

[Terraform](https://www.terraform.io/) is a tool to provision infrastructure as code. Let's install it:

In a terminal, run the following commands:

```bash
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

⚠️ if you get an error, try:

```bash
sudo snap install terraform --classic
```

Then run the following command:

```bash
terraform -v
```

:heavy_check_mark: If you see a version, you're good :+1:


## Setup completed!

Enjoy :rocket:




