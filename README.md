ConduentLCS.java
=========

This role is for installing Java via a remote tarball over HTTP(S).

Requirements
------------

None.

Role Variables
--------------
Required
* `java_tarball_url` -- The URL to pull the Java tarball from.

Optional
* `java_install_base`: Defaults to `/usr/local`
* `java_current_link`: Defaults to `{{ java_install_base }}/java`
* `java_tarball_file`: Defaults to `{{ java_tarball_url | basename }}`
* `java_tarball_directory`: Defaults to `{{ java_install_base }}/{{ java_tarball_file | regex_replace('(\\.tar\\.gz|.tgz)', '') }}`
* `java_tarball_tmp`: Defaults to `/tmp/{{ java_tarball_file }}`

Dependencies
------------

None

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - role: ConduentLCS.java
           java_tarball_url: "https://tarball.host.com/mytarball.tar.gz"
```

License
-------

BSD-3-Clause

Author Information
------------------

[@brandisher](https://github.com/brandisher)
