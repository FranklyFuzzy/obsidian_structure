---
type:
  - resource
status:
  - reference
tags:
  - cheatsheet
created: 2025-11-30
updated: 2025-11-30
---
Nala is a command-line APT frontend that aims to provide a tidier alternative to the standard **`apt`** [user interface](https://phoenixnap.com/glossary/what-is-ui-user-interface). Similar to Synaptic, Aptitude, and other APT frontends, Nala adapts the APT interface to a specific use case.

Apt get
Nala
Neofetch
btop

## How to Use Nala?

Once Nala is installed, use it to install and manage packages on the system. The sections below provide a guide on using Nala to perform standard package management operations.

### Install Packages

Use the following command to install a package with Nala:

```
sudo nala install [package-name]
```

The installer shows a formatted list of packages that will be installed. Type **`Y`** and press **Enter** to start the process.

![Installing Neofetch with Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-install-neofetch.png)

The installer has two separate sections for downloading and installing packages, each with a progress bar. Once the installation finishes, Nala displays the confirmation message.

![The download and install interface in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-install-neofetch-finished-successfully.png)

### Remove Packages

Uninstall packages with the **`remove`** command.

```
sudo nala remove [package-name]
```

Nala displays the progress bar and confirmation message.

![Package removal in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-remove-package.png)

### Purge Packages

Use the **`purge`** command to uninstall an application and remove all the associated configuration options.

```
sudo nala purge [package-name]
```

### Update Packages

Refresh the package listings for the repositories on your system with the **`update`** command.

```
sudo nala update
```

Like **`apt`**, Nala updates the package list and displays a message if there are packages to upgrade.

![Updating packages with Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-update.png)

### List Packages

View the list of all available packages by typing:

```
nala list
```

Use options to filter the list. For example, add **`--upgradeable`** to see the packages you can upgrade.

```
nala list --upgradeable
```

![Viewing the list of upgradeable packages in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-nala-list-upgradeable.png)

Below is the list of other Nala flags useful for listing packages.

- **`--installed`** (**`-i`**) shows only the packages installed on the system.
- **`--nala-installed`** (**`-N`**) displays the packages installed using Nala.
- **`--all-versions`** (**`-a`**) **`[package-name]`** lists all the versions of the given package.

### Upgrade Packages

Use the following command to upgrade the installed packages:

```
sudo nala upgrade
```

When you execute the **`upgrade`** command, Nala first performs the package list update, then shows a table with the upgradeable packages. 

Type **`Y`** and press **Enter** to start the process. 

![Upgrading packages in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-upgrade.png)

Nala downloads and upgrades the packages and then prints the confirmation message.

![Package upgrade in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-upgrade-finished-successfully.png)

### Fetch Fast Mirrors

As mentioned in the section on Nala's advantages over **`apt`**, Nala can generate a list of download mirrors sorted by speed and let the user choose the fastest ones. 

1. View the list of mirrors by using the **`fetch`** command.

```
sudo nala fetch
```

Nala performs the latency measurements and displays the list.

2. Choose the mirrors to use by typing their index numbers separated by spaces and pressing **Enter**.

![Choosing the fast mirrors in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-fetch.png)

To confirm the selection, type **Y** and press **Enter**.

![Confirming the mirror selection in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-sudo-nala-fetch-confirm-mirrors.png)

Nala writes the new list of mirrors to the **`/etc/apt/sources.list.d/nala-sources.list`** file.

### Show Package Details

Use the **`nala show`** command to see details about a package.

```
nala show [package-name]
```

The output includes the essential package information like the name, architecture, size, repository section, maintainer info, and package description.

![Viewing the package details in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-nala-show-neofetch.png)

### Show Transaction History

See the history of transactions on the system with the **`history`** command. 

```
nala history
```

Nala creates a list in which each previously executed transaction has a unique ID.

![Viewing package transaction history in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-from-nala-history.png)

To undo changes made by a transaction, type:

```
sudo nala history undo [transaction-id]
```

Revert the changes using the **`redo`** subcommand.

```
sudo nala history redo [transaction-id]
```

Remove an entry with the **`clear`** subcommand.

```
sudo nala history clear [transaction-id]
```

Clear the entire transaction list by typing:

```
sudo nala history clear --all
```

### Clear out the Local Repository

Delete the local cache files with the **`clean`** command.

```
sudo nala clean
```

The output confirms the operation was successful.

![Clearing out the local repository in Nala.](https://phoenixnap.com/kb/wp-content/uploads/2022/12/output-sudo-nala-clean.png)

### Optional Nala Arguments

The following is the list of flags you can add to the **`nala`** commands to enable additional options.

- **`--assume-yes`** (**`-y`**) provides the **`yes`** answer to all prompts and allows the command to run non-interactively.
- **`--debug`** and **`--verbose`** (**`-v`**) provide additional debugging related information.
- **`--download-only`** (**`-d`**) tells Nala to download packages but not to unpack or install them.
- **`--help`** (**`-h`**) shows the help section.
- **`--no-autoremove`** disables package auto removal.
- **`--no-update`** instructs Nala to skip updating the packages.
- **`--raw-dpkg`** disables formatting and shows raw [dpkg](https://phoenixnap.com/kb/dpkg-command) output. 
- **`--remove-essential`** allows the removal of all packages, including the essential ones.
- **`--update`** tells Nala to perform package update.
- **`--version`** shows Nala's version number.