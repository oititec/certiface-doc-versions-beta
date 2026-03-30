<p align="center">
 <img src="Images/CertifaceHeader.png"/>
</p>

# Changelog

### [Versão 1.0.0](https://github.com/oititec/certiface-doc-versions/releases/tag/1.0.0)

Data: 30/03/2026

### Visão geral

- Substitui o SDK legado **Liveness 2D**: codebase **novo**, sem migração automática nem paridade de API com o legado.
- UI do fluxo em **Jetpack Compose** (Material 3).

---

### Integração (API pública)

| Etapa | Detalhe |
|--------|---------|
| Inicialização | `CertifaceDocSDK.initialize(context, config)` |
| Execução do fluxo | `CertifaceDocManager.start(config, callback)` |
| Config | `createSDKConfig(...)` → `CertifaceDocConfig` |

**`CertifaceDocConfig`**

| Campo | Descrição |
|--------|-----------|
| `appKey` | Credencial para inicio da sessão |
| `environment` | `HML` ou `PRD` (Ambientes). |
| `theme` | Opcional; `null` usa o tema padrão do SDK. |
| `enableCnhDigital` | Habilita o fluxo de CNH digital. |
| `enablePdfUpload` | Habilita envio de documento em PDF. |

---

### Customização

- **`CertifaceDocTheme.build { }`** — DSL para tema: instruções, permissão, captura, loading, QR, uploads (documento / CNH digital), resultado, instruções complementares, fontes por papel de texto.
- **Granular** — ajuste de cores, textos e recursos por etapa.
- **`setCustomScreens`** — substituição **completa** de telas por Composables próprios, quando a UI precisa ser 100% sob controle do integrador.

---

### Requisitos

- Android **minSdk 26** · **compileSdk 36** · **Kotlin 2.0.x** · **Java 17**

---

### Dependência Gradle

- Dependência: artefato **`manager`** (`br.com.certiface:manager:1.0.0`). 
