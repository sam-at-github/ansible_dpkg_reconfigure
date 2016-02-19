# Overview
Ansible module to reconfigure a Debian package using dpkg-reconfigure. Uses dpkg "editor" input mode to noninteractively input selections. Why is this necessary? Because (AFAIK), short of purge and reinstall there is no other way to properly reconfigure a package.

# Usage
Only two options `pkg` and `answers_file`.

    - hosts: "{{ hosts }}"
      tasks:
        - name: dpkg reconfigure
          dpkg_reconfigure:
            pkg: tzdata
            answers_file: tzdata.dat

answers_file like:

    tzdata/Zones/Australia: Perth

# Notes
Only tested on Debian.
