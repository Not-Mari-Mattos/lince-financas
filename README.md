# LINCE — MVP 0.1

MVP Android em React Native + Expo, com visual preto minimalista e banco SQLite local.

## Incluído
- Dashboard com saldo calculado a partir dos lançamentos cadastrados.
- Cadastro manual de receitas e despesas.
- Categorias e formas de pagamento.
- Escolha individual de contabilização para compras no crédito: mês da compra ou mês de vencimento da fatura.
- Persistência local em SQLite.

## Ainda não incluído
- Importação de PDF, CSV, XLSX ou OFX.
- Seleção de cartão, data de vencimento ou parcelas.
- Conciliação e detecção de duplicidades.
- Backup automático. Como os dados são locais, não desinstale o app sem exportar/guardar seus dados quando esse recurso for implementado.

## Gerar APK
Este projeto está preparado para Expo EAS Build. Para gerar o APK, é necessário enviar a pasta a um repositório Git e executar em um terminal com Node.js:

```bash
npm install
npx eas-cli login
npx eas-cli build:configure
npx eas-cli build --platform android --profile preview
```

O perfil `preview` em `eas.json` gera APK instalável. A criação da conta Expo, por si só, não inicia a compilação; é necessário conectar/autorizar o projeto e executar o build.

## Alternativa para iniciar o build pelo celular via GitHub Actions
Há um workflow em `.github/workflows/build-apk.yml`.
1. Crie um repositório no GitHub e envie o conteúdo desta pasta.
2. No Expo, crie um Access Token em Account Settings > Access Tokens.
3. No GitHub, abra Settings > Secrets and variables > Actions e crie `EXPO_TOKEN` com esse token.
4. Abra Actions > Build LINCE APK > Run workflow.
5. Acompanhe o build em expo.dev e baixe o APK quando terminar.
Nunca compartilhe seu token ou senha no chat.
