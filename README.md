NSS files.d module
==================

This is a NSS module which can read user information from files
in the same format as `/etc/passwd` and `/etc/group` stored in 
the alternate location `/etc/passwd.d` and `/etc/group.d`.

As of version 2.27 the following directories will be searched
by nss_filesd:

- `/etc/group.d`
- `/etc/passwd.d`
- `/etc/shadow.d`

The sources are copied from the nss_files modules from
[glibc2](http://www.gnu.org/software/libc/) and adjusted for
this project.


Usage
-----

List the module the `/etc/nsswitch.conf` configuration file.
For example:

```
    passwd: files filesd
    group:  files filesd

    # Other entries follow...
```

This will try to read files from `/etc` first, and under
`/etc/<database>.d/` (using the `nss_filesd` module).


Version scheme
--------------

Version numbers follow the numbering of the glibc releases from
which the sources are taken.


Licensing
---------

As the sources are taken from glibc, which is distributed under the
terms of the LGPL 2.1, the same applies to the extra bits needed to
make `nss_filesd` work.

See the file COPYING for full text and copying restrictions.
