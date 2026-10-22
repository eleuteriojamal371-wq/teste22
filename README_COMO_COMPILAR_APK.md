# 📱 LATIMO STORE - Aplicação Android Oficial (Projeto Completo)

Este diretório contém o projeto de código-fonte Android nativo completo para compilar o arquivo `.apk` instalável da **LATIMO STORE**.

---

## 🚀 Funcionalidades Integradas na Aplicação

- **Splash Screen de Luxo**: Abertura com fundo escuro minimalista (`#0C0C0C`) e o logótipo oficial branco da Latimo Store.
- **Suporte Completo a Upload de Fotos & Comprovativos**:
  - Permite aos clientes anexar comprovativos de pagamento **M-Pesa** e **e-Mola**.
  - Permite tirar fotografias diretamente com a câmara ou escolher da galeria.
- **Suporte a WhatsApp e Chamadas**: Links de apoio ao cliente (`wa.me`) abrem diretamente na aplicação oficial do WhatsApp instalada no telemóvel.
- **Gesto de Puxar para Atualizar (Pull to Refresh)**: Atualização suave e nativa puxando o topo do ecrã para baixo.
- **Download de Recibos em PDF**: Guarda automaticamente faturas e recibos de compras na pasta *Transferências / Downloads* do Android.
- **Ecrã Offline Inteligente**: Caso o cliente perca a ligação aos dados móveis ou Wi-Fi, é apresentado um ecrã moderno com o logótipo e botão *"Tentar Novamente"*.
- **Controlo de Retrocesso**: O botão "Voltar" do telemóvel navega pelo histórico da loja sem fechar a aplicação acidentalmente.

---

## 🛠️ Como Gerar o Ficheiro `.apk` Instalável

Você pode gerar o seu `.apk` de **3 formas diferentes**:

### 🌟 Opção 1: Compilação Automática na Nuvem (Mais fácil, 100% grátis e sem instalar nada no PC)

O projeto já inclui o arquivo de automação do **GitHub Actions** em `.github/workflows/build_apk.yml`.

1. Crie um repositório no seu GitHub (pode ser Público ou Privado).
2. Suba os ficheiros desta pasta `android_app` para o repositório.
3. No GitHub, clique na aba **"Actions"**.
4. O GitHub compilará o ficheiro `.apk` automaticamente em cerca de 2 minutos nos servidores da Google/Microsoft.
5. Quando terminar, clique no fluxo de trabalho e descarregue o ficheiro **`LatimoStore-APK`**.
6. Transfira o ficheiro `.apk` para o seu telemóvel Android e instale!

---

### 💻 Opção 2: Gerar no Android Studio (Se já tiver ou quiser instalar no PC)

1. Transfira e instale o [Android Studio](https://developer.android.com/studio) (gratuito).
2. Abra o Android Studio e escolha **Open** (Abrir Projeto).
3. Selecione a pasta: `C:\xampp\htdocs\latimo_store\android_app`.
4. Aguarde alguns instantes enquanto o Gradle sincroniza as dependências.
5. No menu superior, clique em:
   👉 **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**.
6. Quando a compilação terminar, surgirá uma notificação no canto inferior direito:
   Clique em **"locate"** para abrir a pasta com o seu ficheiro `app-debug.apk` pronto a instalar!

---

### ⌨️ Opção 3: Gerar por Linha de Comando (Gradle)

Se tiver o Java JDK 17 configurado no seu sistema:

```powershell
cd C:\xampp\htdocs\latimo_store\android_app
.\gradlew.bat assembleDebug
```

O ficheiro APK final será gerado em:
`app\build\outputs\apk\debug\app-debug.apk`

---

## ⚙️ Como Alterar o URL da Loja

Para apontar a aplicação para o seu domínio final ou testar localmente:

Abra o ficheiro:
📄 [`app/src/main/java/com/latimostore/app/AppConfig.java`](file:///C:/xampp/htdocs/latimo_store/android_app/app/src/main/java/com/latimostore/app/AppConfig.java)

- **Para o site online (Produção)**:
  ```java
  public static final String STORE_URL = "https://latimostore.com/";
  ```
- **Para testar no emulador Android do PC**:
  ```java
  public static final String STORE_URL = "http://10.0.2.2/latimo_store/";
  ```
- **Para testar no telemóvel físico via Wi-Fi**:
  Substitua pelo IP da sua máquina na rede local (ex: `http://192.168.1.150/latimo_store/`).

---

## 📦 Estrutura dos Ícones e Logótipos

Todos os ícones para todos os tamanhos de ecrã Android já foram processados e inseridos nas pastas de densidade:
- `mipmap-mdpi` (ecrãs normais)
- `mipmap-hdpi` (ecrãs de alta densidade)
- `mipmap-xhdpi` (ecrãs retina)
- `mipmap-xxhdpi` (ecrãs full HD)
- `mipmap-xxxhdpi` (ecrãs quad HD / 4K)
- Logótipos oficiais vetorizados em `drawable/logo_latimo_white.png` e `drawable/logo_latimo_black.png`.
