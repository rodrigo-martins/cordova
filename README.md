# cordova

Aplicativo baseado em cordova/phonegap   

## Pré Requisitos
Instalar
[NodeJS](https://nodejs.org/en/)

Instalar [Android Studio](https://developer.android.com/studio/install) 

Instalar [SDK tools package](https://developer.android.com/studio/#downloads)

Instalar [Java 1.8.0_xxx](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html)

```
sudo add-apt-repository ppa:webupd8team/java
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C2518248EEA14886
sudo apt update
sudo apt install oracle-java8-installer
```

Instalar Cordova 
```node
$ npm install -g cordova 
```

Instalar Phonegap 
```node
$ npm install -g phonegap
```

## Configurar Variáveis de Ambiente (Linux/Mac)
Android Tools

```export PATH=/Users/<YOUR_USER>/Library/Android/sdk/platform-tools:$PATH```

Android Emulator

```export PATH=/Users/<YOUR_USER>/Library/Android/sdk/emulator:$PATH```

Java Version

(mac)```export JAVA_HOME='/usr/libexec/java_home -v 1.8' ```  
(linux)```export JAVA_HOME=/usr/java/jre1.8.0_xxx```

## Criar Emulador (Android)
Criar um projeto vazio
![](https://i2.wp.com/www.rafaeltoledo.net/wp-content/uploads/2016/12/android-studio-2.png?resize=768%2C424)
![](https://i0.wp.com/www.rafaeltoledo.net/wp-content/uploads/2016/12/avd-button.png?w=302)
![](https://i2.wp.com/www.rafaeltoledo.net/wp-content/uploads/2016/12/avd-manager.png?resize=768%2C337)
![](https://i2.wp.com/www.rafaeltoledo.net/wp-content/uploads/2016/12/image-select.png?resize=768%2C584)
![](https://i1.wp.com/www.rafaeltoledo.net/wp-content/uploads/2016/12/play.png?resize=220%2C91)


## Instalação
Clonar projeto 
```git
$ git clone https://github.com/<PROJECT_NAME> 
```

Baixar dependências do Cordova (path ./)
```node 
$ npm install 
```

Baixar dependências do Projeto (path ./www) 
```node
$ npm install
```

Adicionar Plaforma (path ./) 
```cordova
$ cordova platform add [android | ios] 
```
Iniciar Android Debug Bridge (path ./) 
```cordova
$ adb devices
```

Rodar Projeto no Emulador ou Celular conectado  (path ./) 
```cordova
$ cordova run android device
```

## Publicar Play Store
```
$ cordova build --release
```

Criar Chave Java
```
$ keytool -genkey -v -keystore <android>.keystore -alias 
<android-app-key> -keyalg RSA -keysize 2048 -validity 10000
```

Adicionar Assinatura
```
$ jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore android.keystore app-release-unsigned.apk android-app-key
```

Se Zipalign não instalado
```
# if zipalign is not installed
$ sudo apt install zipalign
```

Criar .apk assinado
```
$ zipalign -v 4 app-release-unsigned.apk app-release.apk
```

## Principais comandos
### Cordova
```cordova
$ cordova plaform [add | rm] [android | ios]
$ cordova plugin  [add | rm] [android | ios]
$ cordova build [android | ios]
$ cordova build [android | ios] --inc-version
$ cordova build --release
$ cordova run [android | ios] device
$ cordova prepare ios

```

### Phonegap
```phonegap
$ phonegap serve
```
### Android Tools
```
$ adb devices
$ emulator @<NOMEDOEMULADOR>
```

## Referências
[NodeJS](https://nodejs.org/en/)

[Android Studio](https://developer.android.com/studio/install)

[SDK tools package](https://developer.android.com/studio/#downloads)

[Java 1.8.0_xxx](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html)

[Cordova](https://cordova.apache.org/)

[Icons/Splashscreen](https://www.resource-generator.com/)

[Paleta de Cores](http://mcg.mbitson.com/#!?mcgpalette0=%233f51b5)
