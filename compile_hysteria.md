准备环境

```
curl -sLo go.tar.gz https://go.dev/dl/go1.21.0.linux-amd64.tar.gz
rm -rf /usr/local/go
tar -C /usr/local -xzf go.tar.gz
rm go.tar.gz
echo -e "export PATH=$PATH:/usr/local/go/bin" > /etc/profile.d/go.sh
source /etc/profile.d/go.sh
go version
```

```
apt install -y git python3
```

```
echo -e 'export HY_APP_PLATFORMS="windows/amd64,linux/amd64"' >> /etc/environment
export HY_APP_PLATFORMS="windows/amd64,linux/amd64"
echo $HY_APP_PLATFORMS
```

首次编译

```
git clone -b wip-hy2 --single-branch https://github.com/apernet/hysteria.git hy2
cd hy2
python3 ./hyperbole.py build
cd ..
```

再次编译

```
cd hy2
git pull
python3 ./hyperbole.py build
cd ..
```

复制文件

**linux-amd64**

```
cp -f /root/hy2/build/hysteria-linux-amd64 /usr/local/bin/hysteria && chmod +x /usr/local/bin/hysteria
```

**windows-amd64**

```
cp -f /root/hy2/build/hysteria-windows-amd64.exe /root/hysteria.exe
```
