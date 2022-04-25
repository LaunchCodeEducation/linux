## Installation

To read the installation instructions provided by NGINX look over the [NGINX Ubuntu Installation Article](https://nginx.org/en/linux_packages.html#Ubuntu).

### Install Tools Used in Installation

```bash
sudo apt install curl gnupg2 ca-certificates lsb-release ubuntu-keyring
```

### Download and Add the nginx_signing.key:

```bash
curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor | sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg > /dev/null
```

### Check the Contents of the nginx_signing.key:

```bash
gpg --dry-run --quiet --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg
```

Desired Output of the nginx_signing.key:

```bash
pub   rsa2048 2011-08-19 [SC] [expires: 2024-06-14]
      573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
uid                      nginx signing key <signing-key@nginx.com>
```

### Add NGINX Package Repository:

```bash
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" | sudo tee /etc/apt/sources.list.d/nginx.list
```

### Configure Package Repository

Set up repository pinning to prefer our packages over distribution-provided ones:

```bash
echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" | sudo tee /etc/apt/preferences.d/99nginx
```

### Update Package Repository List and Install `nginx` Package:

```bash
sudo apt update
sudo apt install nginx
```

## Validation

```bash
which nginx
```

```bash
nginx -version
```

Output:

![which nginx && nginx -version output](pictures/nginx-validation.png?classes=border)

Upon a successful installation you should see the location of the `nginx` binary and the version of the installed `nginx` package with the preceding commands.

## Managing the `nginx.service`

NGINX automatically creates a service upon installation. The `nginx.service` can be controlled with the `systemctl` package.

For now we will be turning off and disabling the `nginx.service`. We will learn more about this in a later lesson.

### Stop Service

```bash
sudo systemctl stop nginx
```

### Disable Service

```bash
sudo systemctl disable nginx
```