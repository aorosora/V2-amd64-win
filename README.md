# NOT-CON
This feature is enabled default by officially. https://github.com/v2fly/v2ray-core/releases/tag/v4.32.0

# V2Ray
Load JSON internally.

## Source
See https://github.com/v2fly/v2ray-core

## Gudie
Open ./main/distro/all/all.go with txt editer.<br>
Goto line 62, find `_ "v2ray.com/core/main/json"` and change to  `// _ "v2ray.com/core/main/json"`.<br>
Goto line 64, fine `// _ "v2ray.com/core/main/jsonem"` and change to `_ "v2ray.com/core/main/jsonem"`.

## Compile
Download and install golang in https://golang.org/dl.<br>
Use powershell or cmd to execute commands `go env -w GO111MODULE=on GOPROXY=https://goproxy.cn,https://goproxy.io,direct`.<br>
Download v2ray's source code in https://github.com/v2fly/v2ray-core (or https://codeload.github.com/v2fly/v2ray-core/tar.gz/v4.31.3 ).<br>
Open a command window in source folder.<br>
Execute these commands:<br>
```
$env:CGO_ENABLED=0

go build -o v2ray.exe -trimpath -ldflags "-s -w" ./main
go build -o wv2ray.exe -trimpath -ldflags "-s -w -H windowsgui" ./main
go build -o v2ctl.exe -trimpath -ldflags "-s -w" -tags confonly ./infra/control/main
```
You'll find v2ray and wv2ray in the current source directory. And other files will be found in the ./release/config/.
