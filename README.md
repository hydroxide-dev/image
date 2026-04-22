# image
Manifest of known good images with cloudinit and QEMU GA.

## But why?
In order to interact with VMs, Hydroxide uses the QEMU guest agent via. Proxmox's API. Unfortunately, it doesn't come with every system. You either need to:
 - use an image with Cloudinit and install that way
 - ... or install it manually in the VM

Neither of which are things you should have to do.

Hydroxide solves this by keeping track of a list of known-good OS images from the vendors directly. In a `compute.yaml` file, you designate the OS location as follows:
```yaml
# compute.yaml
# insert resources section here...
runtime:
  os: github/hydroxide/image/ubuntu-24-lts
  # Alternatively, if it's already on GitHub:
  # os: hydroxide/image/ubuntu-24-lts
  # ... or use your own repo's
  # os: spacedouut/hydrox-images/endevouros
```
