- Error: Permission denied @ apply2files
sudo chown -R $(whoami):admin /usr/local/* \
&& sudo chmod -R g+rwx /usr/local/*

[Reference](https://stackoverflow.com/questions/61899041/permission-denied-apply2files-usr-local-lib-node-modules-expo-cli-node-modu)
