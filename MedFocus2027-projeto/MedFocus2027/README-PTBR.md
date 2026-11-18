# MedFocus 2027 — pacote fonte ampliado

Este ZIP contém um projeto React + TypeScript + Vite preparado para integração Android via Capacitor, com interface PT-BR, navegação das 11 áreas planejadas, catálogo inicial de 15 disciplinas, 15 aulas introdutórias (uma por disciplina), 15 questões autorais, cronograma 12x36 básico, registro de sessões, revisões agendadas, editor/histórico de redação, autoavaliação pelas cinco competências, desempenho local, backup/restauração e cache PWA.

## Transparência: o que ainda não é integral
Este pacote é uma base funcional ampliada, mas **não é honesto chamá-lo de produto completo pronto para Medicina/ENEM**. Uma aula e uma questão por disciplina não formam um curso completo. Ainda faltam: cobertura curricular aprofundada e revisada de todas as disciplinas; banco amplo e progressivo de questões; simulados completos no formato ENEM (180 questões em dois dias); temporizador e análise por área completos; algoritmo de revisão mais sofisticado; correção de redação por IA; integração real de IA online com backend seguro; biblioteca offline ampla e gerenciador de downloads; testes de acessibilidade, segurança, desempenho e aparelhos reais. O painel Assistente IA explica a ausência da conexão e não finge enviar perguntas.

As questões incluídas são autorais de demonstração, não questões oficiais do INEP. Não há nota oficial. O app é individual e não possui login/servidor.

## Requisitos para build web
Node.js LTS e internet para baixar dependências:
```bash
npm install
npm run build
```

## Gerar Android
Em Windows/Linux com Android Studio, Android SDK, Build Tools e JDK compatível:
```bash
npm install
npx cap add android
npx cap sync android
cd android
```
Windows: `gradlew.bat assembleDebug`; Linux/macOS: `./gradlew assembleDebug`.
APK debug: `android/app/build/outputs/apk/debug/app-debug.apk`.

Se a pasta android já existir, não repita `npx cap add android`; execute `npx cap sync android`.

## Termux
Termux pode ser usado para editar o projeto e talvez executar `npm run build`, mas a compilação APK nativa no próprio Android/Termux não é garantida. Capacitor Android precisa de Android SDK, Build Tools, plataforma Android e Gradle compatíveis; esse conjunto tem incompatibilidades frequentes no Termux. O caminho confiável é compilar em Windows/Linux com Android Studio/SDK. O build inicial exige internet; o APK instalado pode usar conteúdo empacotado offline.

## Offline e dados
O app registra dados em armazenamento local do WebView/navegador. A limpeza dos dados do app pode apagar progresso; exporte backups regularmente. O Service Worker é para PWA em origem compatível; o APK empacota os arquivos web. IA remota não funciona sem conexão.
