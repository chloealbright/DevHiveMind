# Linux
wget -q [https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb](https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb) -O packages-microsoft-prod.deb

// downloaded deb

sudo dpkg -i packages-microsoft-prod.deb

sudo add-apt-repository universe

sudo apt-get update

sudo aptitude -y install apt-transport-https

sudo aptitude -y install dotnet-sdk-3.1

[https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-ubuntu-1804](https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-ubuntu-1804)

install c #plugin in visual studio code