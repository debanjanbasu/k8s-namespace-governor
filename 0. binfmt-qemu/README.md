# This is to allow kubernetes to run containers from any arch possible

```bash
sudo apt install -y qemu-user-static binfmt-support
sudo update-binfmts --enable
```
