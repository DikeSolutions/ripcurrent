# Ripcurrent

Ripcurrent is a simple and efficient CLI tool designed for handling deployment tasks across multiple servers. With an easy-to-use command structure and flexible installation, Ripcurrent makes creating your deployment pipeline a breeze.

## Summary

Ripcurrent greatly simplifies the deployment of .NET applications (and soon more) running on Linux servers with Nginx. It automates the deployment of your artifact, restarts the service for your DLL, and can also restart the Nginx service if needed. Additionally, you can use Ripcurrent to restart other services, such as background sync tasks. This functionality makes it easy to integrate into your CI/CD pipelines, streamlining the deployment process.

## Installation

To install Ripcurrent, download the tarball and extract it:

```bash
tar -xzf ripcurrent.tar.gz
cd ripcurrent
./install.sh
```

## Usage

Ripcurrent is easy to use. Below are the available commands and their respective flags:

```bash
Usage: ripcurrent <command> [flags]

Commands:
  help: show this help message
  deploy: deploy an artifact to a destination site
    Flags:
        -a: specify an artifact
        -d: specify a destination
  restart-service: restart a service
    Flags:
        -s: specify a service to restart
  update-config: update the current config
    Flags:
        -k: specify a key to update
        -v: specify a value to update the key with
  validate-config: validate the current config
  current-config: print the current config
```

## configuration

ripcurrent utilizes a `.conf` configuration file to store and manage key settings, ensuring that your deployments are consistent and configurable. This configuration file allows you to define various parameters, making the tool adaptable to different environments and needs.

The `ripcurrent.conf` is placed in /etc/ripcurrent during installation, with some default settings.

```text
[server_config]
framework=dotnet
web_server=nginx
user=www-data
group=www-data

[deployment]
app_structure=/var/www/apps/
static_structure=/var/www/html/

[service_config]
allow_restart=TRUE
service_location=/test/
```


## Contributing

I welcome contributions from the community. If you'd like to propose changes, please fork the repository and submit a pull request with your changes.

## License

Ripcurrent is licensed under the MIT License. Feel free to use, modify, and distribute it as you see fit.

```text
MIT License

Copyright (c) 2025 Jordi van Dijk

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Support

If you encounter any issues or have questions, feel free to open an issue in the repository or reach out to the maintainers.
