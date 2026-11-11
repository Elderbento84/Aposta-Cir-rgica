# APOSTA CIRÚRGICA — Android v1.0

Projeto Android (Kotlin + WebView local) para análise de apostas esportivas.

## O que já funciona nesta versão
- Interface Android em português, com abas Radar, Calculadora, Histórico e Dados/API.
- Calculadora de odd justa, probabilidade implícita, edge e EV.
- Histórico local de análises.
- Integração inicial com The Odds API para listar eventos/odds NBA e ligas de futebol disponíveis na conta.
- Horários apresentados em America/Sao_Paulo.
- Não inventa odds, escalações, lesões ou suspensões.

## Requisitos de dados
1. Criar conta/chave em https://the-odds-api.com/.
2. Abrir o app > Dados & API > colar e salvar a chave.
3. Voltar ao Radar e tocar em Atualizar.

A cobertura depende do plano do provedor. Esta versão não integra ainda fontes de lesões, escalações e suspensões, não tem modelo estatístico independente nem atualização em segundo plano. Não confundir consenso de odds com probabilidade própria.

## Gerar APK no GitHub Actions
O ambiente de criação original não inclui Android SDK/Gradle, então não é possível compilar o APK diretamente aqui. O projeto inclui `.github/workflows/android.yml` para compilar automaticamente:
1. Crie um repositório GitHub e envie todos os arquivos desta pasta.
2. Abra a aba Actions e execute **Build Android APK** (ou faça push na branch `main`).
3. Baixe o artefato `Aposta-Cirurgica-debug-apk`; dentro estará `app-debug.apk`.

Também é possível abrir a pasta no Android Studio e executar `assembleDebug`.

## Segurança
A chave da API é armazenada no armazenamento local do app e usada pelo WebView. Para uma versão distribuída publicamente, substituir por backend/proxy seguro e política de privacidade. Não publique APK contendo sua chave pessoal.
