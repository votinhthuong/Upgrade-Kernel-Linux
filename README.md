**Step 1: Check Your Current Kernel Version

*uname -msr*

Step 2: Update CentOS Repositories

*sudo yum -y update*

Step 3: Enable the ELRepo Repository

*sudo rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org*

*sudo rpm -Uvh https://www.elrepo.org/elrepo-release-7.0-3.el7.elrepo.noarch.rpm*

Step 4: List Available Kernels

*yum list available --disablerepo='*' --enablerepo=elrepo-kernel*

Step 5: Install New CentOS Kernel Version

To install the latest mainline kernel:

*sudo yum --enablerepo=elrepo-kernel install kernel-ml*

To install the latest long-term support kernel:

*sudo yum --enablerepo=elrepo-kernel install kernel-lt*

Step 6: Reboot and Select the New Kernel

*reboot*

Step 7: Verify Functionality

*None*

Step 8: Set Default Kernel Version

*sudo vim /etc/default/grub*

*sudo grub2-mkconfig -o /boot/grub2/grub.cfg*

*reboot*
