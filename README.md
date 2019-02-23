# aratrohcaz.pihole
---
This project is in its infancy. Expect it to break and be missing features through-out it's life.

## Aim
Allow easy redeployment of a pihole system to multiple hosts to maintain settings across the board. Allowing for redundancy, multiple sites, all running the same settings. Later this may be improved upon to support different configurations easier, but currently it's on a per-host basis.

## Background Info
Considering this project is for ansible, some of the nice things that are offered in the script are being dropped, for example interactivity is gone. Some basic network knowledge is assumed if you're running this software (e.g. setting the IP of the pihole in your DHCP lease etc.) and is not going to be mentioned at all.

I had originally attempted to parse the script and work around whiptail, but I ran into some issues with return codes not being quite right, and ending of transmissions causing ansible to break, amongst other issues that I cannot recall. Which has resulted in this monstrosity/atrocity of a role.

## Running
Testing/deploying on Debian, Centos is considered - but not tested against yet. So don't expect it to work (yet).

## TODO
- Start and Finish handling of firewall rules
- Start and Finish handling of lightttpd
  - Install PHP DONE
  - Install Lighttpd DONE
  - Configure vhosts
  - enable and start services (done?)
  - reload of lighttpd when configs change
- Start and Finish handling of pihole-FTL
- Set SELinux to Permissive (or bomb out if it's enforcing?)
- Support password generation if none-specified
- Disable DNSStubListener
- Config cron
- Free Space Check

## Future
- Add detection to check when a new release comes out and see if the script needs updating
- Clone the repo to the host and rsync the files to the hosts (currently it checks the project out on each of them)
- Add support for nginx
- Handle SELinux (make policy for it?)
- Handle Updates
