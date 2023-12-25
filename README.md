
# 说明

https://www.electronjs.org/zh/docs/latest/tutorial/quick-start

# 安装 node  npm

# 更换镜像

```
vi ~/.npmrc

registry=https://mirrors.huaweicloud.com/repository/npm/
electron_mirror=https://npm.taobao.org/mirrors/electron/

```

## step1 

mkdir my-electron-app && cd my-electron-app
npm init

package.json
```
{
  "name": "datamake-yarn",
  "version": "1.0.0",
  "description": "datamake-windos",
  "main": "main.js",
  "repository": "",
  "author": "service@datamake.cn",
  "license": "MIT",
  "scripts": {
    "start": "electron ."
  },
  "devDependencies": {
    "electron": "^28.0.0"
  }
}
```

main.js

```
const { app, BrowserWindow } = require('electron/main')
const path = require('node:path')

function createWindow () {
  const win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      preload: path.join(__dirname, 'preload.js')
    }
  })

  win.loadFile('index.html')
}

app.whenReady().then(() => {
  createWindow()

  app.on('activate', () => {
    if (BrowserWindow.getAllWindows().length === 0) {
      createWindow()
    }
  })
})

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit()
  }
})
```
## step2 

npm install --save-dev electron

## step3 test 

npm start



# 指定平台和架构 - 修改package.json scripts脚本
    # windows 64bit
    electron-builder --win --x64
    # windows and mac 32bit
    electron-builder --win --mac --ia32
    
