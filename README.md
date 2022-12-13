
# Notes on setting up Honeycomb LX2

## SolidRun documentation

Main documentation is at
https://solidrun.atlassian.net/wiki/spaces/developer/pages/197494288/HoneyComb+LX2+ClearFog+CX+LX2+Quick+Start+Guide#Booting-from-an-SD-card

# my notes

most writeable data, particularly /home and parts of /var (should try for all of var?) are on the nvme drive.

would be interesting to try and come up with a way to run on a read-only root to preserve the eMMC lifetime.

* Build a custom image with options to enable docker, per https://community.solid-run.com/t/building-a-docker-enabled-kernel-for-the-solidrun/379
* Follow instructions from https://solidrun.atlassian.net/wiki/spaces/developer/pages/197494288/HoneyComb+LX2+ClearFog+CX+LX2+Quick+Start+Guide#Booting-from-an-SD-card
* Before resize2fs, mount data volume, move logs to it, symlink logs
* adduser justizin
* add justizin to sudo group
* symlink home
* symlink /var/lib/transmission-daemon to /mnt/data/transmission-daemon
* edit /etc/transmission-daemon/settings.json to add 192.168.*.* to rpc-whitelist
* add /mnt/data to fstab
* edit /etc/hostname to set studiolab
* hostname -F /etc/hostname
* reboot
