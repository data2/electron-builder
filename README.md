# electron-builder

# package.json  demo

    {
      "name": "electron-builder-real",
      "version": "1.0.0",
      "description": "#",
      "main": "main.js",
      "scripts": {
        "start": "electron .",
        "test": "echo \"Error: no test specified\" && exit 1",
        "postinstall": "electron-builder install-app-deps",
        "pack": "electron-builder --dir",
        "dist": "electron-builder"
      },
      "build": {
        "appId": "your.id",
        "mac": {
          "category": "your.app.category.type"
        }
      },
      "devDependencies":{
        "electron": "^1.7.9",
        "electron-builder": "^19.37.2"
      },
      "keywords": [],
      "author": "",
      "license": "ISC"
    }

# 打包 
    生成一个 exe 或者 dmg 文件
    npm run dist

# 指定平台和架构 - 修改package.json scripts脚本
    # windows 64bit
    electron-builder --win --x64
    # windows and mac 32bit
    electron-builder --win --mac --ia32
    
