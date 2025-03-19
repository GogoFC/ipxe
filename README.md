iPXE README File

Quick start guide:

   cd src
   make

For any more detailed instructions, see http://ipxe.org

---

```
sudo apt install git build-essential tftpd-hpa liblzma-dev
```

### Tags

From original repo get tags and push to fork.

```
git remote add upstream https://github.com/ipxe/ipxe.git
git fetch upstream --tags
git push origin master --tags
git ls-remote --tags origin
```
### Build

```
make -j8 bin-x86_64-efi/ipxe.efi EMBED=menu.ipxe
make -j8 bin/undionly.kpxe EMBED=menu.ipxe 


sudo cp bin-x86_64-efi/ipxe.efi /srv/tftp/ipxe.efi
sudo cp bin/undionly.kpxe /srv/tftp/undionly.kpxe

```

```
make bin-x86_64-efi/ipxe.efi EMBED=menu.ipxe && sudo cp bin-x86_64-efi/ipxe.efi /srv/tftp/ipxe.efi
make bin/undionly.kpxe EMBED=menu.ipxe && sudo cp bin/undionly.kpxe /srv/tftp/undionly.kpxe
```
