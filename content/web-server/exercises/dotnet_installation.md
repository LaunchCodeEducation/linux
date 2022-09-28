
### Install .NET SDK 6.0 and the `dotnet` CLI

#### Add Package Repository

```bash
wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb 

sudo dpkg -i packages-microsoft-prod.deb
```

#### Update Package Repository List

```bash
sudo apt update
```

#### Install .NET SDK 6.0 and `dotnet` CLI

```bash
sudo apt install dotnet-sdk-6.0
```