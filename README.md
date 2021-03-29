   # NPM Kullanarak Ionic Modülün Yayınlanması
   
**NPM Nedir?**

 Node Package Manager, açık kaynaklı  Node.js için paket yöneticisidir  ve komut satırı üzerinden çalışır. Front-end web uygulamaları, mobil uygulamalar, robotlar, yönlendiriciler ve JavaScript kod paketleri için genel bir depodur . Bağımlılıkları yönetir ve bu bağımlılıklar package.json’da tanımlanır. Kendi modülünüzü paylaşmak istiyorsanız npm’in kendi sitesinde oturum açmanız yeterlidir.
 
 ---
**Npm nasıl kurulur?**

 Npm yükleyebilmek için  [https://nodejs.org/en/](https://nodejs.org/en/) sitesinden node.js kurulumunu gerçekleştirdiğinizde npm de otomatik olarak yüklenmiş olur.
 
 
Nodejs yüklendiğini kontrol etmek için komut satırına `$node -v`  yazabilirsiniz.

Npm kurulumunu kontrol etmek için komut satırına `$npm -v` yazabilirsiniz.




## Başlarken

Modülümüzü oluşturmak için öncelikle masaüstünde bir klasör oluşturuyoruz.
Klasör oluşturmak için öncelikle bir terminal açıyoruz ve ardından;
Windows kullanıyorsanız eğer cmd ile MAC/Linux kullanıyorsanız sudo kullanarak çalıştırın.

   `$cd desktop`
   
   `$mkdir diginova`
   
   
 
 ### 2-VsCode Kullanarak Modülün Oluşturulması
Oluşturduğumuz diginova klasörünü Visual Studio Code yardımıyla açıyoruz. Proje klasöründe paketleri kullanmak için bir tane package.json dosyası oluşturuyoruz.Package json içeriği aşağıdaki gibidir. 

###### 1.Adım

Bu metaveriler üzerinden projeyi tanımlamış oluyoruz.
Windows kulanalar `"build": "del -rf dist && npm run ngc",` bu şekilde build yapmalı.
MAC/Linux kullananlar  `"build": "rm -rf dist && npm run ngc"` bu şekilde build yapmalı.

###### Package.json

```{
  "name": "my_portalium-package",
  "version": "1.0.3",
  "description": "Bu benim ilk test modulum",
  "main": "./dist/index.js",
  "typings": "./dist/index.d.ts",
  "files": [
    "dist"
  ],
  "scripts": {
    "ngc": "ngc",
    "build": "del -rf dist && npm run ngc",
    "publishPackage": "npm run build && npm publish"
  },
  "repository": {
    "type": "git",
    "url": "git+"
  },
  "keywords": [],
  "author": "",
  "license": "MIT",
  "homepage": "",
  "bugs": {
    "url": ""
  },
  "devDependencies": {
    "@angular/common": "^5.0.3",
    "@angular/compiler": "^5.0.3",
    "@angular/compiler-cli": "^5.0.3",
    "@angular/core": "^5.2.11",
    "@angular/forms": "^5.2.11",
    "@angular/platform-browser": "^5.0.3",
    "@angular/platform-browser-dynamic": "^5.0.3",
    "ionic-angular": "^3.9.2",
    "rxjs": "^5.5.2",
    "typescript": "^2.4.2",
    "zone.js": "^0.8.18"
  }
}
```
###### 2.Adım

TypeScript derleyicimize projemiz hakkında bilgi vermek için bir tsconfig.json dosyası oluşturuyoruz.

###### tsconfig.json

```
{
    "compilerOptions": {
        "module": "es2015",
        "target": "es5",
        "moduleResolution": "node",
        "sourceMap": true,
        "inlineSources": true,
        "declaration": true,
        "noImplicitAny": false,
        "experimentalDecorators": true,
        "lib": ["dom", "es2015"],
        "outDir": "dist"
    },
    "exclude": [
        "node_modules",
        "dist",
        "scripts"
    ],
    "angularCompilerOptions": {
        "skipTemplateCodegen": true
    }
    }
```

VsCode terminalde `npm install ` ile projemize modülü yüklüyoruz.

Ardından..
VsCode editörümüzde bir src klasörü oluşturuyoruz.
