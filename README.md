# <a name="what-is-testssl"></a>Supported tags and respective `Dockerfile` links

-	[`2.6`, `latest` (*2.6/Dockerfile*)](https://github.com/MatthewVance/testssl-docker)

## <a name="what-is-testssl"></a>What is testssl.sh?

 testssl.sh is a free command line tool which checks a server's service on any port for the support of TLS/SSL ciphers, protocols as well as recent cryptographic flaws and more.

> [testssl.sh](https://testssl.sh/)

## <a name="how-to-use-this-image"></a>How to use this image

### Standard usage

Run your testssl container with the following command to run testssl.sh, replacing `<options>` with supported testssl.sh flags:

```console
$ docker run -t --rm matthewvance/testssl:2.6 <options>
```

For example, running `$ docker run -t --rm matthewvance/testssl:2.6 --protocols 127.0.0.1` would check TLS/SSL protocols against localhost, assuming an https service is running on localhost.

### Interactive shell

Run your testssl container with the following command to obtain an interactive bash shell.

```console
$ docker run -i --entrypoint /bin/bash -t --rm matthewvance/testssl:2.6
```

Within the container's shell, you can then run testssl.sh as if it was any other program installed in your `$PATH`.

### View help

Run your testssl container with the following command to access the help file for testssl.sh.

```console
$ docker run -t --rm matthewvance/testssl:2.6
```

For more information on using testssl.sh, visit [https://testssl.sh/](https://testssl.sh/).

# <a name="known-issues"></a>Known issues

**DNS resolution** currently fails. As such, running something like `$ docker run -t --rm matthewvance/testssl:2.6 example.com` results in the following error:

```console
Fatal error: No IPv4 address for "example.com" available
```
As a workaround, always use the IP address when specifying the `URI` parameter of testssl.sh.

If you know how to resolve this issue, please initiate a pull request. Interestingly, running `ping -c 3 example.com` from within the container performs DNS resolution correctly so I am unsure as to why the testssl.sh script is unable to do so.

# <a name="supported-docker-versions"></a>Supported Docker versions

This image is tested on Docker version 1.8.2.

Use on older versions (down to 1.0) at your own risk.

# <a name="user-feedback"></a>User feedback

## <a name="documentation"></a>Documentation

Documentation for this image is stored right here in the [`README.md`](https://github.com/MatthewVance/testssl-docker/blob/master/README.md).

Documentation for testssl.sh is available on the [project's website](https://testssl.sh/).

## <a name="issues"></a>Issues

If you have any problems with or questions about this image, please contact me through a [GitHub issue](https://github.com/MatthewVance/testssl-docker/issues).

## <a name="contributing"></a>Contributing

You are invited to contribute new features, fixes, or updates, large or small. I imagine the upstream projects would be equally pleased to receive your contributions.

Please familiarize yourself with the [repository's `README.md` file](https://github.com/MatthewVance/testssl-docker/blob/master/README.md) before attempting a pull request.

Before you start to code, I recommend discussing your plans through a [GitHub issue](https://github.com/MatthewVance/testssl-docker/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.

## <a name="acknowledgments"></a>Acknowledgments

- [Peter Mosmans OpenSSL fork](https://github.com/PeterMosmans/openssl/)
- [testssl.sh](https://github.com/drwetter/testssl.sh)

## <a name="licenses"></a>Licenses
### <a name="license"></a>License

Unless otherwise specified, all code is released under the MIT License (MIT). See the [repository's `LICENSE` file](LICENSE) for details.

### <a name="licenses-for-other-components"></a>Licenses for other components

- Peter Mosmans OpenSSL fork: [OpenSSL License](https://github.com/PeterMosmans/openssl/blob/1.0.2-chacha/LICENSE) and [Original SSLeay License](https://github.com/PeterMosmans/openssl/blob/1.0.2-chacha/LICENSE)
- testssl.sh: [GPLv2](https://github.com/drwetter/testssl.sh/blob/master/LICENSE)