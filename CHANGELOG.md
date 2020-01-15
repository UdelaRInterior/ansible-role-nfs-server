# Change Log

## [v2.0.0](https://github.com/UdelaRInterior/ansible-role-nfs-server/tree/v2.0.0)

* Added support for multiple networks per directory. Sub-element `network` of the `exports` list, was deprecated by `networks` (now it's a list).

## [v1.0.0](https://github.com/UdelaRInterior/ansible-role-nfs-server/tree/v1.0.0)

* First stable version. Export directories with their corresponding parameters to a given network.