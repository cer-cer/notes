
## set
### run in console
```
git config --global http.proxy 'socks5://127.0.0.1:1086'
git config --global https.proxy 'socks5://127.0.0.1:1086'
```

### config in bash_profile
```
export PATH=/Users/allen.chen/prj/depot_tools:$PATH


function proxy_off(){
        unset http_proxy
        unset https_proxy
        unset ftp_proxy
        unset rsync_proxy
        echo -e "已关闭代理"
}
 
function proxy_on() {
        export no_proxy="localhost,127.0.0.1,localaddress,.localdomain.com"
        export http_proxy="socks5://127.0.0.1:1086"#注意，根据自己的配置设置有可能会是1080或1086
        export https_proxy=$http_proxy
        export ftp_proxy=$http_proxy
        export rsync_proxy=$http_proxy
        export HTTP_PROXY=$http_proxy
        export HTTPS_PROXY=$http_proxy
        export FTP_PROXY=$http_proxy
        export RSYNC_PROXY=$http_proxy
        echo -e "已开启代理"
}

source .bash_profile
```

## recover

```
git config --global --unset http.proxy 
git config --global --unset https.proxy

proxy_off
```
