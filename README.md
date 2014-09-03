bashShot
=================================
Replicates the Solaris sun-auto-snap functionality as shell script with help of cron. Tested on Debian and Ubuntu GNU/Linux with ZFSonLinux (zfsonlinux.org).


LICENSE
=================================
    bashShot - sun-auto-snap-like implementation for ZFSonLinux using cron
    Copyright (C) 2014  Hans-Filip Elo

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

REQUIREMENTS
=================================
Should run on any *NIX system that has crontab and ZFS (zfsonlinux.org) installed, but only tested on Debian and Ubuntu. If you are interested in running bashShot on another distro or OS, please confirm it's functioning status.

INSTALLATION
=================================
These scripts needs crontab/anacron, which are installed by default on Debian and Ubuntu. You also need ZFSonLinux (zfsonlinux.org). Note that the author recommends reading and understanding any script before running it as root.

Clone project, cd to folder:

	git clone git://github.com/hansfilipelo/bashshot.git
	cd bashshot

Run install.bash:

	sudo ./install.bash

Edit /etc/bashshot/bashshot.conf. Set FILESYSTEMS to snapshot and wanted periods on snapshots. Example below:

	FILESYSTEMS=$(array 'pool/filesystem' 'pool/filesystem')
	frequently="no"
	hourly="no"
	daily="yes"
	weekly="yes"
	monthly="yes"


UNINSTALL
=================================
Run uninstall.sh

	sudo ./uninstall.sh
	# To also remove config
	sudo ./uninstall.sh purge
