## **What is Tuned-adm?**

`tuned-adm` is a command-line tool that manages **system performance profiles** on [[02. Introduction to Red Hat|RHEL]]. It applies pre-built tuning settings (CPU, disk, network behavior) based on what your system is doing.

For example, `throughput-performance` profile is common on servers — it disables power saving and pushes for raw speed.

----
## **Setup**

We download its package called `tuned`:

```bash
dnf install tuned -y
```

Then we should enable and start its service:

```bash
systemctl enable --now tuned.service
```

We can look at all existing profiles using:

```bash
tuned-adm profile
```

We look at the recommended profile using:

```bash
tuned-adm recommend
```

We can switch to another profile (like recommended one):

```bash
tuned-adm profile <PROFILE_NAME>
```

We can look at the active (current) profile:

```bash
tuned-adm active
```

We should restart its service:

```bash
systemctl restart tuned
```