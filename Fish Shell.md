# Fish Shell

Fish Shell 开箱即用，速度快，自带补全功能。

website: https://fishshell.com/

## 1. install

### 1.1 macOS

```shell
brew install fish
```

### 1.2 CentOS

For **CentOS 8** run the following as **root**:

```shell
cd /etc/yum.repos.d/
wget https://download.opensuse.org/repositories/shells:fish:release:3/CentOS_8/shells:fish:release:3.repo
yum install -y fish
```

For **CentOS 7** run the following as **root**:

```shell
cd /etc/yum.repos.d/
wget https://download.opensuse.org/repositories/shells:fish:release:3/CentOS_7/shells:fish:release:3.repo
yum install -y fish
```

## 2. Starting and Exiting

Once fish has been installed, open a terminal. If fish is not the default shell:

- Type **fish** to start a shell:

  ```shell
  fish
  ```
  
- Type **exit** to end the session:

  ```shell
  exit
  ```

## 3. Change Default Shell

To change your login shell to fish:

1. Add the shell to `/etc/shells` with:

   ```shell
   echo /usr/local/bin/fish | sudo tee -a /etc/shells
   ```

2. Change your default shell with:

   ```shell
   chsh -s $(which fish)
   ```

Again, substitute the path to fish for `/usr/local/bin/fish` - see `command -s fish` inside fish. To change it back to another shell, just substitute `/usr/local/bin/fish` with `/bin/bash`, `/bin/tcsh` or `/bin/zsh` as appropriate in the steps above.

## 4. Uninstalling fish

If you want to uninstall fish, first make sure fish is not set as your shell. Run `chsh -s /bin/bash` if you are not sure.

If you installed it with a package manager, just use that package manager’s uninstall function. If you built fish yourself, assuming you installed it to /usr/local, do this:

```
rm -Rf /usr/local/etc/fish /usr/local/share/fish ~/.config/fish
rm /usr/local/share/man/man1/fish*.1
cd /usr/local/bin
rm -f fish fish_indent
```

## 6. Configuration

To store configuration write it to a file called `~/.config/fish/config.fish`.

`.fish` scripts in `~/.config/fish/conf.d/` are also automatically executed before `config.fish`.

These files are read on the startup of every shell, whether interactive and/or if they’re login shells. Use `status --is-interactive` and `status --is-login` to do things only in interactive/login shells, respectively.

This is the short version; for a full explanation, like for sysadmins or integration for developers of other software, see [Configuration files](https://fishshell.com/docs/current/language.html#configuration).

### 6.1 fish_config - start the web-based configuration interface

`fish_config` is used to configure fish.

## 5. fisher: A plugin manager for [Fish](https://fishshell.com/)

Website: https://github.com/jorgebucaran/fisher

### 5.1 Installation

```shell
curl -sL https://git.io/fisher | source && fisher install jorgebucaran/fisher
```

### 5.2 Install Dracula theme

Website: https://draculatheme.com/fish

```shell
fisher install dracula/fish
```



