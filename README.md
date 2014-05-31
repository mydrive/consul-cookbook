# consul-cookbook

Installs and configures [Consul][1].

## Supported Platforms

CentOS 5.10, 6.5
Ubuntu 12.04, 14.04

## Attributes

<table>
  <tr>
    <th>Key</th>
    <th>Type</th>
    <th>Description</th>
    <th>Default</th>
  </tr>
  <tr>
    <td><tt>['consul']['version']</tt></td>
    <td>String</td>
    <td>Version to install</td>
    <td><tt>0.2.0</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['base_url']</tt></td>
    <td>String</td>
    <td>Base URL for binary downloads</td>
    <td><tt>https://dl.bintray.com/mitchellh/consul/</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['install_method']</tt></td>
    <td>String</td>
    <td>Method to install consul with when using default recipe: binary or source</td>
    <td><tt>binary</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['install_dir']</tt></td>
    <td>String</td>
    <td>Directory to install binary to.</td>
    <td><tt>/usr/local/bin</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['service_mode']</tt></td>
    <td>String</td>
    <td>Mode to run consul as: bootstrap, server, or client</td>
    <td><tt>bootstrap</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['data_dir']</tt></td>
    <td>String</td>
    <td>Location to store consul's data in</td>
    <td><tt>/var/lib/consul</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['config_dir']</tt></td>
    <td>String</td>
    <td>Location to read service definitions from (directoy will be created)</td>
    <td><tt>/etc/consul.d</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['servers']</tt></td>
    <td>Array Strings</td>
    <td>Consul servers to join</td>
    <td><tt>[]</tt></td>
  </tr>
</table>

### Consul UI Attributes

<table>
  <tr>
    <th>Key</th>
    <th>Type</th>
    <th>Description</th>
    <th>Default</th>
  </tr>
  <tr>
    <td><tt>['consul']['client_address']</tt></td>
    <td>String</td>
    <td>Address to bind to</td>
    <td><tt>0.0.0.0</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['ui_dir']</tt></td>
    <td>String</td>
    <td>Location to download the UI to</td>
    <td><tt>/var/lib/consul/ui</tt></td>
  </tr>
  <tr>
    <td><tt>['consul']['serve_ui']</tt></td>
    <td>Boolean</td>
    <td>Determines whether the consul service also serve's the UI</td>
    <td><tt>false</tt></td>
  </tr>
</table>

## Usage

### consul::default

This uses the binary installation recipe by default. It also starts consul at boot time.

### consul::binary_install

Include `consul::binary_install` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[consul::binary_install]"
  ]
}
```

### consul::source_install

Include `consul::source_install` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[consul::source_install]"
  ]
}
```

### consul::ui

This installs the UI into a specified directory.

Include `consul::ui` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[consul::ui]"
  ]
}
```

## Authors

Author:: [John Bellone][3] [@johnbellone][2] (<jbellone@bloomberg.net>)

[1]: http://consul.io
[2]: https://twitter.com/johnbellone
[3]: https://github.com/johnbellone
