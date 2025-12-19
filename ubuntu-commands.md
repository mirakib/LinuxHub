### Overall system summary (quick view)

```bash
sudo lshw -short
```

If **lshw** isn’t installed:

```bash
sudo apt update && sudo apt install -y lshw
```

**Kernel Info**

```bash
lsb_release -a
```

### CPU information

```bash
lscpu
```

**Quick one-liner:**

```
nproc
```

## RAM

```bash
free -h
```
