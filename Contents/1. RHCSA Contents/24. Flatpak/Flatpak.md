#package-managers #packages 

## **What is Flatpak?**

Flatpak is a universal package format for Linux that runs apps in a **sandbox**, isolated from the rest of the system. The big idea is that one Flatpak package works on any Linux distro, regardless of whether it's RHEL, Ubuntu, or Fedora. It's mostly relevant for **desktop apps**, not servers. 

---
## **Installation and Setup**

First, we need to download `flatpak` package using `dnf`:

```bash
dnf install flatpak -y
flatpak --version #Look at the version
```

Afterward we need to add flatpak repo to our system:

```bash
flatpak remote-add --if-not-exists <REPO_NAME> <REPO_LINK>
```

- `<REPO_NAME>` - We can give any name to it. However, if it is mentioned in the task, we need to put just this name.
- `<REPO_LINK>` - It is the most important part, because flatpak takes packages from here. It should be given to us. It might be an external link or internal directory path:
	- **External Link** - https://flathub.org/repo/flathub.flatpakrepo
	- **Internal Path** - `/root/repo/local.flatpakrepo`

We can use this command to see all existing flatpak repos in the system:

```bash
flatpak remotes
```


> [!Info] System Info
> System Directory of Flatpak is `/var/lib/flatpak/`. We can view it with `ls -l`.


We can delete existing flatpak repo:

```bash
flatpak remote-remove <REPO_NAME>
```

---
## **Package Management**

After seting repo up we can download the packages:

```bash
flatpak install <REPO_NAME> <PACKAGE_NAME> -y
```

We can search any package using:

```bash
flatpak search <PATTERN>
```

We can look at all installed packages via flatpak:

```bash
flatpak list
```

We can run the installed package:

```bash
flatpak run <PACKAGE_NAME>
```

We can remove flatpak package:

```bash
flatpak uninstall <PACKAGE_NAME>
```

---
## **Specific User**

If we want to add repo for specific user, we use `--user`:

```bash
flatpak remote-add --user --if-not-exists <REPO_NAME> <REPO_LINK>
```

If we want to download the specific package for this user:

```bash
flatpak install --user <PACKAGE_NAME>
```
