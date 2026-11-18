# Termux

O Termux não é um ambiente oficial/garantido para compilar APK Android com Gradle e Android SDK. Você pode testar o build web:
```bash
termux-setup-storage
pkg update && pkg upgrade -y
pkg install nodejs-lts unzip -y
cd ~/storage/downloads/MedFocus2027-FULL
npm install
npm run build
```
Isso cria `dist/`, não um APK. Para gerar APK com confiabilidade, copie a pasta do projeto para Windows/Linux com Android Studio + SDK e rode os comandos Capacitor/Gradle do README. Não instale scripts de compilação desconhecidos.
