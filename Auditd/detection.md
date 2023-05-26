- Persistence
## .ssh directory tampering // authorized_keys
## add users/manipulate current users with sshd config
## webshells(execve with www-data)
## Service&Timer persistence(.service,.timer)
-w /etc/systemd/ -p wa -k systemd
-w /usr/lib/systemd/ -p wa -k systemd
-w /lib/systemd/ -p wa -k systemd

# Directories may not exist
-w /usr/local/lib/systemd/ -p wa -k systemd
-w /usr/local/share/systemd/user -p wa -k systemd_user
-w /usr/share/systemd/user  -p wa -k systemd_user 

## Cron jobs T1053.003
-w /etc/cron.allow -p wa -k cron
-w /etc/cron.deny -p wa -k cron
-w /etc/cron.d/ -p wa -k cron
-w /etc/cron.daily/ -p wa -k cron
-w /etc/cron.hourly/ -p wa -k cron
-w /etc/cron.monthly/ -p wa -k cron
-w /etc/cron.weekly/ -p wa -k cron
-w /etc/crontab -p wa -k cron
-w /var/spool/cron/ -k cron

## Init script
-w /etc/rc.local -p wa -k rclocal
-w /etc/init.d/ -p wa -k init
-w /etc/update-motd.d/ -p wa -k motd

# Shell profiles
-w /etc/bash.bashrc -p wa -k shell_profiles
-w /etc/bash.bash_logout -p wa -k shell_profiles

# Shell profiles - known users
-w /root/.profile -p wa -k shell_profiles
-w /root/.bashrc -p wa -k shell_profiles
-w /root/.bash_logout -p wa -k shell_profiles
-w /root/.bash_profile -p wa -k shell_profiles
-w /root/.bash_login -p wa -k shell_profiles

# System generators
-w /etc/systemd/system-generators/ -p wa -k systemd_generator
-w /usr/local/lib/systemd/system-generators/ -p wa -k systemd_generator
-w /lib/systemd/system-generators/ -p wa -k systemd_generator
-w /usr/lib/systemd/system-generators -p wa -k systemd_generator
-w /etc/systemd/user-generators/ -p wa -k systemd_generator
-w /usr/local/lib/systemd/user-generators/ -p wa -k systemd_generator
-w /usr/lib/systemd/user-generators/ -p wa -k systemd_generator