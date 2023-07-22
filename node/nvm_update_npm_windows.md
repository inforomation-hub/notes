```
cd %APPDATA%\nvm\v8.10.0           # or whatever version you're using
mv npm npm-old
mv npm.cmd npm-old.cmd
cd node_modules\
mv npm npm-old
cd npm-old\bin
node npm-cli.js i -g npm@latest

cd %APPDATA%\nvm\v8.10.0 # or whatever version you're using
rm npm-old
rm npm-old.cmd
cd node_modules\
rm -r -force npm-old
```
