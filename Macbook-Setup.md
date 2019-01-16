## Macbook Development Environment Setup


1. Create SSH keys

```shell
C02XR1UVJGH5:~ i313873$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/i313873/.ssh/id_rsa): 
Created directory '/Users/i313873/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/i313873/.ssh/id_rsa.
Your public key has been saved in /Users/i313873/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:r8oFsX1AgzHWsmLU+txHsklyyVRERIAjbqC4N0RHzXs i313873@C02XR1UVJGH5
The key's randomart image is:
+---[RSA 2048]----+
|   ..++=+B*      |
|  o +.Ooo.       |
|.o = o.B..       |
|o . * ++E..      |
| o o +o*S=.      |
|. o   o.+o.      |
| . .    ...      |
|     . . .       |
|      o..        |
+----[SHA256]-----+

```
Keys get saved to `~/.ssh`.

2. Add SSH public key `~/.ssh/id_rsa.pub` to Github