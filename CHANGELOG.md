##2014-07-21 - Release 3.3.0
###Summary

Add extra option that allows to download duply using a proxy server ([#11](https://github.com/tohuwabohu/puppet-duplicity/pull/11)).

##2014-07-11 - Release 3.2.0
###Summary

The duply executable is no longer referenced directly but sourced from the `PATH` environment variable instead (#10). As
a result of this change, the `duply_executable` parameter has been deprecated and was replaced with the more specific
`exec_path` and `duply_archive_executable` parameters.

####Further changes
* Improved compatibility with Puppet 4 ([logrotate #46](https://github.com/rodjek/puppet-logrotate/issues/46)).

##2014-04-15 - Release 3.1.1
###Summary

Fix up too restrictive permission on files contained in the tarball that was published to the forge during the last
release (see [#8](https://github.com/tohuwabohu/puppet-duplicity/issues/8)).

##2014-04-12 - Release 3.1.0
###Summary

By default, all backups are encrypted via GPG. With the new boolean `gpg_encryption` parameter, this behaviour can be
turned off in case encryption is not necessary. It can be configured on a per-profile level (see
[#3](https://github.com/tohuwabohu/puppet-duplicity/issues/3)).

##2014-03-31 - Release 3.0.1
###Summary

Just a bugfix release that fixes the wrong `duply_executable` being used.

##2014-03-31 - Release 3.0.0
###Summary

This release adds a better separation of the configuration parameters when using the package vs. archive resource type.

Furthermore, it adds support for RHEL/CentOS 6.

####Changes to default behavior
* Package provider archive: the duply archive is now downloaded directly from sourceforge instead some dude's dropbox
  account; using HTTP by default to facilitate the usage of a HTTP proxy
* Package provider archive: the ambigious usage of the `duply_package_ensure` parameter to transport the default version
  and the packate state has been replaced with the `duply_archive_version` parameter
* On RedHat-based systems, the `yum` package is preferred over the sourceforge one

####Further changes
* Documentation of the `duplicity` class has been reviewed
* Using the archive no longer requires to specify `duply_package_name` or `duply_archive_url`; setting
  `duply_archive_version` and `duply_archive_md5sum` is enough
* Add support for Ubuntu 12.04 and 14.04
* Add system tests

##2014-12-25 - Release 2.0.0
###Summary

* Add default package name/version/handler for Debian based distributions
* Replace gini/archive with camptocamp/archive
* Fix broken example in README
