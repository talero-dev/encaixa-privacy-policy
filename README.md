# Privacy Policy — Encaixa: Offline Block Puzzle

> The **Brazilian Portuguese** version of this policy is the primary one. This English version is
> provided for convenience; if the two disagree, the Portuguese text prevails.

**App:** Encaixa: Offline Block Puzzle
**Package name:** `com.talero.encaixa`
**Data controller:** Talero
**Contact:** talero.dev@gmail.com
**Last updated:** November 10, 2026
**Document version:** 1.0

---

## 1. In one sentence

Encaixa is an offline game. It has **no sign-up, no login and no in-app purchases**. Everything you
play is saved on your own device. The only things that leave your device are what is needed to show
the ads that pay for the game and, when enabled, to tell us that the app crashed — never your name,
your email, your calendar, your photos or your precise location.

## 2. Who is responsible

The controller of the personal data processed by this application, under Brazil's Lei Geral de
Proteção de Dados (Law 13.709/2018, "LGPD") and under the EU General Data Protection Regulation
("GDPR"), is **Talero**, reachable at **talero.dev@gmail.com**.

That address is also the channel for the rights described in §15 and serves as the contact for the
data protection officer / *encarregado* (LGPD art. 41).

## 3. What stays on your device

Encaixa writes the data below **only to the app's private storage** on your phone. None of it is
sent to a server of ours — we do not operate one.

| What | Where | Why |
|---|---|---|
| Best score, games played, total lines, max combo, last-20 average | Local database (Room) | Show your statistics |
| Saved game (board, tray, score, streak, generator state) | Local database (Room) | Let you resume |
| Daily Challenge calendar and streak | Local database (Room) | Mark completed days |
| Adventure stars and progress, achievements, unlocked themes, power-up inventory | Local database (Room) | Your progress |
| Settings: sound, haptics, light/dark mode, block glyphs, tap-to-place, language, board theme | Preferences file `encaixa_settings` | Keep your choices |
| Ad frequency counters (when the last ad was shown, how many videos you watched today) | Preferences file `encaixa_ad_policy` | Respect the ad frequency caps |

**None of this identifies you.** There is no name, nickname, email, phone number, photo or free
text: the app has no field anywhere in which you could type something.

**Google backup.** If Android's automatic backup is on for your Google account, the progress and
settings above are copied to your account's Google Drive, encrypted and subject to
[Google's Privacy Policy](https://policies.google.com/privacy). The ad counters and the consent
state are deliberately **excluded** from backup. You control this backup in your Android settings,
not inside the game.

## 4. What leaves your device

Encaixa uses Google components (SDKs). Each collects data on its own, under Google's policies. Here
is what each one does, with the official links.

### 4.1 Google AdMob — ads

- Component: **Google Mobile Ads SDK (Next-Gen)**, `com.google.android.libraries.ads.mobile.sdk:ads-mobile-sdk:1.5.0`
- Why it is there: it is what pays for the game. There are no in-app purchases.

To select and measure ads, Google may collect and process:

- the **Android advertising ID** and device identifiers;
- device and app information (model, OS, app version, language, time zone);
- **approximate location derived from your IP address** (typically city or region — never GPS: the
  app neither requests nor uses any location permission);
- ad interactions (impression, tap, video watch time) and diagnostic data.

Official links: [How Google uses data from apps that use its services](https://policies.google.com/technologies/partner-sites)
· [Google Privacy Policy](https://policies.google.com/privacy)
· [Google Ads Data Processing Terms](https://business.safety.google/adsprocessing/)
· [AdMob and privacy](https://developers.google.com/admob/android/privacy)

### 4.2 Google UMP — consent

- Component: **User Messaging Platform**, `com.google.android.ump:user-messaging-platform:4.0.0`

On every app start, UMP checks whether your region requires a consent form for ads and, where it
does, shows that form (its wording is Google's, not ours). Your answer is stored on the device and
decides whether ads may be personalised. When UMP reports that the privacy option is required in
your region, the game shows a **"Privacy options"** entry in Settings so you can change your mind at
any time.

Official link: [Privacy and messaging](https://support.google.com/admob/answer/10113207)

### 4.3 Firebase — analytics and crash reporting *(may not be present)*

**This is important and unusual, so it is spelled out:** Encaixa is built to work **with or
without** Firebase. If the Firebase configuration file is absent at build time, the Firebase
libraries **are not included in the application** and the app uses empty implementations that
collect and send nothing at all. In that case only sections 4.1, 4.2 and 4.4 apply.

When Firebase **is** enabled (Firebase BoM 34.19.0), these services are used:

**Google Analytics for Firebase** — records gameplay events so we can understand what people play
and where they get stuck. The events are a closed list defined in code (`AnalyticsEvent.kt`), and
every string value is reduced to a token from the set `[a-z0-9_]` before it leaves the app — by
construction, **no free text and no personal data can enter an event**. Recorded events include:
level start and end, a run's score, game over (score, lines, max combo, placements, duration),
achievement unlocked, theme selected, settings changed, screen viewed, and the ad funnel (request,
loaded, failed, shown, reward earned). Four user properties are set: app theme, font-scale bucket,
app language and consent state. The Analytics SDK additionally collects, on its own, the **Firebase
installation ID**, the advertising ID (where permitted) and device and session information.
[Data collected by Google Analytics](https://firebase.google.com/docs/analytics/user-data-collection)

**Firebase Crashlytics** — sends a report when the app crashes or records a handled error. The
report contains the stack trace, device model, OS version, app version, an installation identifier,
and a closed set of our own keys (current screen, app language, board theme). Log messages are
written by us in source code; none of them interpolates anything you typed, because there is nothing
for you to type. [Crashlytics and privacy](https://firebase.google.com/support/privacy#crashlytics)

**Firebase Remote Config** — fetches game configuration parameters (for example ad frequency caps).
To do so the SDK sends the Firebase installation ID and basic app and device data. It does not send
your progress or your scores. Without Firebase, the app uses the default values already built into
it.

**Firebase Cloud Messaging is not used.** The optional Daily Challenge reminder, if you turn it on,
is a **local** notification scheduled on the device itself. No server pushes messages to your phone.

[Privacy and security in Firebase](https://firebase.google.com/support/privacy)

### 4.4 Google Play libraries

- **Play In-App Review** (`com.google.android.play:review-ktx:2.0.2`) — opens the Play Store review
  dialog inside the game. The review you write goes to Google, not to us; we are not even told
  whether you reviewed.
- **Play In-App Update** (`com.google.android.play:app-update-ktx:2.1.0`) — asks the Play Store
  whether a newer version exists and offers the update.

Both run through the Google Play services already installed on your device and follow
[Google's Privacy Policy](https://policies.google.com/privacy).

### 4.5 What does **not** happen

- We do not collect your name, email, phone number, address, ID document or photo.
- We do not use the camera, microphone, contacts, calendar, SMS, call log, files or precise location.
- There is no account, login, registration or profile.
- There are no in-app purchases, subscriptions or paid currency.
- There is no chat, forum, online leaderboard or any way to contact other players.
- We do not sell data. We run no server of our own and receive no database of players.
- We use no third-party tracking beyond the Google SDKs listed above.

## 5. Collection summary

| Category | Collected? | By which component | Purpose |
|---|---|---|---|
| Device or other IDs, advertising ID | Yes | AdMob; Analytics and Crashlytics (if enabled) | Ads, measurement, crash diagnostics |
| App interactions (gameplay and ad events) | Yes | AdMob; Analytics (if enabled) | Ads and improving the game |
| Diagnostics, crash logs, performance | Yes | AdMob; Crashlytics (if enabled) | Fixing crashes |
| Approximate location derived from IP | Yes | AdMob (and Analytics, if enabled) | Ad targeting and regional obligations |
| Precise location (GPS) | **No** | — | — |
| Name, email, phone, government IDs | **No** | — | — |
| Contacts, calendar, photos, files, messages | **No** | — | — |
| Audio, video, camera, microphone | **No** | — | — |
| Financial or health information | **No** | — | — |
| Game progress and settings | Yes, **on your device only** | The app itself | Saving your game and your choices |

## 6. App permissions

Encaixa declares only three permissions, all of them automatic (none of them shows a prompt):

| Permission | Why |
|---|---|
| `android.permission.INTERNET` | Fetch ads and, when Firebase is enabled, send events and crash reports |
| `android.permission.ACCESS_NETWORK_STATE` | Check for connectivity before requesting an ad |
| `com.google.android.gms.permission.AD_ID` | Read the Android advertising ID, required by Google for apps that show ads and target API 33 or higher |

If the installed version includes the optional Daily Challenge reminder, the app also declares
`android.permission.POST_NOTIFICATIONS` and asks for it **at the moment you turn the reminder on** —
never at first launch. Declining affects nothing else in the game.

The game works fully **offline**. The network is used only for ads and, where applicable, telemetry.

## 7. Advertising ID and personalised ads

The Android advertising ID is a resettable number that belongs to you, not to us. You control it in
the system itself:

**Android Settings → Google → All services → Ads** (the exact path varies by manufacturer), where
you can **reset** or **delete** the identifier. If you delete it you still see ads, but they stop
being personalised.

Inside the game, where UMP indicates your region requires it, **Settings → Privacy options** reopens
Google's consent form so you can change your answer.

[More about the advertising ID](https://support.google.com/googleplay/android-developer/answer/6048248)

## 8. Legal bases

### 8.1 LGPD (Brazil) — the primary regime

| Processing | Legal basis (Law 13.709/2018) |
|---|---|
| Saving your progress and settings on the device | Performance of the service you requested (art. 7, V) — and in practice the data never leaves your device |
| Showing non-personalised ads and enforcing frequency caps | Legitimate interests of the controller (art. 7, IX): it is what makes a free game with no purchases possible |
| Showing **personalised** ads | Consent (art. 7, I), collected through Google's form (UMP) where it is required |
| Usage analytics and crash reporting (when Firebase is enabled) | Legitimate interests of the controller (art. 7, IX) in keeping the app stable, limited to data that does not directly identify you |

### 8.2 GDPR / UK GDPR — because the app is downloadable in the EEA

| Processing | Legal basis |
|---|---|
| Personalised ads, usage analytics | Consent, art. 6(1)(a), collected by the UMP form, which also operates the TCF |
| Non-personalised ads, security and fraud prevention, crash reporting | Legitimate interests, art. 6(1)(f) |

Where the GDPR applies, the UMP form is shown before any ad request, and no ad is requested until
the SDK confirms that it may be. Consent can be withdrawn at any time in **Settings → Privacy
options**.

## 9. Who we share with

- **Google LLC and its affiliates**, as a processor and/or ad network, through the AdMob, UMP,
  Firebase and Google Play services described in §4.
- **Ad buyers and Google's mediation partners**, to the extent Google involves them in delivering
  ads, under Google's own policies.

We share with nobody else. We do not sell data. We do no profiling of our own: we have no access to
any individual record — only aggregated reports in the AdMob and, if enabled, Firebase dashboards.

## 10. International transfers

Google's services process data on servers outside Brazil, including in the United States. Those
transfers are made by Google under the safeguards Google itself publishes (standard contractual
clauses and applicable adequacy frameworks), described in the
[Ads Data Processing Terms](https://business.safety.google/adsprocessing/) and at the
[Google Privacy Hub](https://policies.google.com/privacy).

## 11. How long data is kept

- **On your device:** until you uninstall the app or use **Settings → Delete my data**. There is no
  automatic expiry; nothing ages out on its own.
- **Google Analytics (if enabled):** for the period configured in the Firebase console — Google's
  default for new properties is **2 months**, and the maximum is **14 months**.
- **Crashlytics (if enabled):** crash reports are retained for the period Google publishes for the
  service. See the [Crashlytics privacy page](https://firebase.google.com/support/privacy#crashlytics).
- **AdMob:** per Google's retention policies, outside our control.

We keep no copy of anything: we operate no server and no database.

## 12. Security

- All traffic between the app and Google's services uses **HTTPS/TLS** (data encrypted in transit).
- Local data lives in the app's private storage, isolated by Android from other apps, and is
  protected by the device's own encryption.
- The app exposes no component to other applications other than the launcher screen.
- We log no personal data, and debug logging is stripped from the published build.

No system is perfectly secure; we do what we can, but we cannot offer an absolute guarantee.

## 13. Children

Encaixa is **not directed to children**. The target audience declared on Google Play is **13 and
over** (age bands 13–15, 16–17 and 18+). The game is not in the Google Play Families programme, uses
no mascots, characters or child-oriented art, and its description, icon and screenshots are designed
not to appeal primarily to children.

We do not knowingly collect data from children under 13. In Brazil, processing children's data
(under 12, per the Statute of the Child and Adolescent) requires specific and prominent consent from
at least one parent or legal guardian (LGPD art. 14), and this app was not built to obtain it. If
you are a parent or guardian and believe a child has used the app, write to **talero.dev@gmail.com** and
we will explain how to erase the data — which in practice sits on the device itself and is erased
with one tap (§14).

## 14. How to delete your data

### 14.1 Inside the game — immediate, no request to anyone

Open **Settings → Delete my data** and confirm. The action is destructive and cannot be undone. It:

1. discards any queued saved-game write;
2. erases **every** table of the local database — best score, statistics, saved game, Daily
   Challenge calendar and streak, Adventure stars, achievements, unlocked themes and power-ups — in
   a single transaction, including the internal recent-scores counter, so the install really does
   look fresh;
3. clears the settings file (`encaixa_settings`);
4. clears the ad frequency counters (`encaixa_ad_policy`);
5. resets analytics state on the device (Firebase Analytics `resetAnalyticsData()`) when Firebase is
   enabled — without Firebase this step does nothing, because there is nothing to reset;
6. resets your answer to the consent form (UMP), so it will be asked again where it is required.

The app **has no user account**, so there is no "delete account": there is nothing server-side to
delete.

### 14.2 By uninstalling

Uninstalling the app removes all local storage. If Google's automatic backup is on, a copy of your
progress may remain in your account's Google Drive — you remove it in your Google account's backup
settings.

### 14.3 By contacting us

Write to **talero.dev@gmail.com** with the subject "Data subject request". We reply within **15 days**
(LGPD art. 19 §1) or within **30 days** for requests under the GDPR. Since we keep no database of
our own, the reply will normally consist of guiding you through the procedure above and, where
applicable, directing you to Google for the data it controls.

### 14.4 Data held by Google

For data collected by Google's SDKs, the controls sit with Google:

- advertising ID: **Android Settings → Google → Ads** (reset or delete);
- data associated with your Google Account: [My Activity](https://myactivity.google.com) and the
  [Google Privacy Hub](https://myaccount.google.com/privacy).

## 15. Your rights

**Under the LGPD (art. 18)** you may ask, at any time and free of charge, for: confirmation that
processing exists; access to the data; correction of incomplete, inaccurate or outdated data;
anonymisation, blocking or deletion of unnecessary or excessive data or data processed unlawfully;
portability; deletion of data processed on the basis of your consent; information about the entities
we share data with; information about your option not to consent and the consequences; and
withdrawal of consent.

You may also complain to Brazil's data protection authority, the **ANPD**:
[gov.br/anpd](https://www.gov.br/anpd/pt-br).

**Under the GDPR**, if you are in the EEA, the UK or Switzerland, you have the rights of access
(art. 15), rectification (16), erasure (17), restriction (18), portability (20), objection (21) and
withdrawal of consent at any time (7(3)), plus the right to lodge a complaint with your national
supervisory authority.

To exercise any of them: **talero.dev@gmail.com**.

## 16. Changes to this policy

When this policy changes we will update the "Last updated" date at the top and publish the new
version at **https://github.com/talero-dev/encaixa-privacy-policy**. Material changes will also be noted in the Google Play release
notes. Continuing to use the app after an update means you are aware of the new version.

## 17. Contact

**Data controller:** Talero
**Privacy contact:** talero.dev@gmail.com

---

## 18. Annex — third-party components and their links

| Component | Version | Vendor | Policy |
|---|---|---|---|
| Google Mobile Ads SDK (Next-Gen) | 1.5.0 | Google | https://policies.google.com/technologies/partner-sites |
| User Messaging Platform (UMP) | 4.0.0 | Google | https://support.google.com/admob/answer/10113207 |
| Google Analytics for Firebase | BoM 34.19.0 | Google | https://firebase.google.com/docs/analytics/user-data-collection |
| Firebase Crashlytics | BoM 34.19.0 | Google | https://firebase.google.com/support/privacy#crashlytics |
| Firebase Remote Config | BoM 34.19.0 | Google | https://firebase.google.com/support/privacy |
| Play In-App Review | 2.0.2 | Google | https://policies.google.com/privacy |
| Play In-App Update | 2.1.0 | Google | https://policies.google.com/privacy |

The three Firebase components are present only in the configuration described in §4.3.

---

# Política de Privacidade (Português) — Encaixa: Blocos Offline

> Versão primária: **português do Brasil**. A versão em inglês desta política é uma tradução de
> cortesia; em caso de divergência, prevalece este texto.

**Aplicativo:** Encaixa: Blocos Offline
**Identificador do pacote:** `com.talero.encaixa`
**Controlador dos dados:** Talero
**Contato:** talero.dev@gmail.com
**Última atualização:** 10 de novembro de 2026
**Versão do documento:** 1.0

---

## 1. Em uma frase

O Encaixa é um jogo offline. Ele **não pede cadastro, não tem login e não tem compras dentro do
app**. Tudo que você joga fica salvo no seu próprio aparelho. O que sai do aparelho é apenas o
necessário para exibir os anúncios que sustentam o jogo e, quando ativado, para nos dizer se o app
travou — nunca seu nome, seu e-mail, sua agenda, suas fotos ou sua localização precisa.

## 2. Quem é o responsável

O controlador dos dados tratados por este aplicativo, nos termos da Lei nº 13.709/2018 (LGPD), é
**Talero**, que pode ser contatado em **talero.dev@gmail.com**.

Esse mesmo endereço é o canal para exercer os direitos descritos na §15 e funciona como contato do
encarregado pelo tratamento de dados pessoais (LGPD, art. 41). Para o Regulamento Geral de Proteção
de Dados da União Europeia (GDPR), **Talero** atua como *controller*.

## 3. O que fica guardado no seu aparelho

O Encaixa grava os dados abaixo **somente no armazenamento privado do app**, no seu celular. Eles
não são enviados para nenhum servidor nosso — não temos servidor.

| O que | Onde fica | Para quê |
|---|---|---|
| Recorde, partidas jogadas, total de linhas, combo máximo, média das últimas partidas | Banco de dados local (Room) | Mostrar suas estatísticas |
| Partida salva (tabuleiro, bandeja, pontos, sequência, estado do gerador) | Banco de dados local (Room) | Continuar de onde você parou |
| Calendário e sequência do Desafio do Dia | Banco de dados local (Room) | Marcar os dias concluídos |
| Estrelas e progresso da Aventura, conquistas, temas desbloqueados, ajudas disponíveis | Banco de dados local (Room) | Seu progresso |
| Configurações: som, vibração, modo claro/escuro, símbolos nos blocos, tocar para colocar, idioma, tema do tabuleiro | Arquivo de preferências `encaixa_settings` | Manter suas escolhas |
| Contadores de frequência de anúncios (quando o último anúncio apareceu, quantos vídeos você viu hoje) | Arquivo de preferências `encaixa_ad_policy` | Respeitar os limites de exibição de anúncios |

**Nada disso identifica você.** Não há nome, apelido, e-mail, telefone, foto nem texto livre: o app
não tem nenhum campo em que você possa digitar algo.

**Backup do Google.** Se o backup automático do Android estiver ligado na sua conta Google, o
progresso e as configurações acima são copiados para o Google Drive da sua conta, de forma
criptografada e sujeita à [Política de Privacidade do Google](https://policies.google.com/privacy).
Os contadores de anúncios e o estado de consentimento **ficam de fora do backup** de propósito.
Você controla esse backup nas configurações do Android, não dentro do jogo.

## 4. O que sai do aparelho

O Encaixa usa componentes (SDKs) do Google. Cada um coleta dados por conta própria, de acordo com a
política do Google. Abaixo está o que cada um faz, com os links oficiais.

### 4.1 Google AdMob — anúncios

- Componente: **Google Mobile Ads SDK (Next-Gen)**, `com.google.android.libraries.ads.mobile.sdk:ads-mobile-sdk:1.5.0`
- Por que existe: é o que sustenta o jogo. Não há compras dentro do app.

Para escolher e medir anúncios, o Google pode coletar e tratar:

- o **identificador de publicidade do Android (Advertising ID)** e identificadores do dispositivo;
- informações do aparelho e do app (modelo, sistema operacional, versão do app, idioma, fuso horário);
- a **localização aproximada derivada do endereço IP** (tipicamente cidade ou região — nunca GPS:
  o app não pede nem usa permissão de localização);
- interações com o anúncio (exibição, toque, tempo de vídeo) e dados de diagnóstico.

Links oficiais: [Como o Google usa dados de apps que usam seus serviços](https://policies.google.com/technologies/partner-sites)
· [Política de Privacidade do Google](https://policies.google.com/privacy)
· [Termos de Processamento de Dados de Publicidade do Google](https://business.safety.google/adsprocessing/)
· [AdMob e privacidade](https://developers.google.com/admob/android/privacy)

### 4.2 Google UMP — consentimento

- Componente: **User Messaging Platform**, `com.google.android.ump:user-messaging-platform:4.0.0`

O UMP verifica, a cada abertura do app, se a sua região exige um formulário de consentimento para
anúncios e, quando exige, exibe esse formulário (o texto dele é do Google, não nosso). A sua
resposta fica gravada no próprio aparelho e é usada para decidir se os anúncios podem ser
personalizados. Quando o UMP informa que a opção é exigida na sua região, o jogo mostra o item
**"Opções de privacidade"** em Configurações, para você rever a escolha a qualquer momento.

Link oficial: [Mensagens de privacidade e consentimento](https://support.google.com/admob/answer/10113207)

### 4.3 Firebase — análise e relatórios de falha *(pode não estar ativo)*

**Isto é importante e pouco comum, então está escrito com todas as letras:** o Encaixa é construído
para funcionar **com ou sem** o Firebase. Se o arquivo de configuração do Firebase não estiver
presente no momento da compilação, as bibliotecas do Firebase **não são incluídas no aplicativo** e
o app usa implementações vazias, que não coletam nem enviam absolutamente nada. Nesse caso, valem
somente as seções 4.1, 4.2 e 4.4.

Quando o Firebase **está** ativo (Firebase BoM 34.19.0), os seguintes serviços são usados:

**Google Analytics for Firebase** — registra eventos de uso do jogo para entendermos o que as
pessoas jogam e onde travam. Os eventos são uma lista fechada, definida no código
(`AnalyticsEvent.kt`), e todo valor de texto é reduzido a um token do conjunto `[a-z0-9_]` antes de
sair do app — por construção, **nenhum texto livre e nenhum dado pessoal consegue entrar num
evento**. São registrados, por exemplo: início e fim de fase, pontuação de uma partida, fim de
partida (pontos, linhas, combo máximo, número de peças colocadas, duração), conquista desbloqueada,
tema escolhido, mudança de configuração, tela visitada e o funil de anúncios (pedido, carregado,
falhou, exibido, recompensa concedida). Também são definidas quatro propriedades de usuário: tema
do app, faixa de tamanho de fonte, idioma do app e estado do consentimento. O SDK do Analytics
coleta ainda, por conta própria, o **ID de instalação do Firebase**, o identificador de publicidade
(quando permitido) e informações de dispositivo e sessão.
[Dados coletados pelo Google Analytics](https://firebase.google.com/docs/analytics/user-data-collection)

**Firebase Crashlytics** — envia um relatório quando o app trava ou registra um erro tratado. O
relatório contém a pilha de execução, modelo do aparelho, versão do sistema, versão do app, um
identificador de instalação e um conjunto fechado de chaves nossas (tela atual, idioma do app, tema
do tabuleiro). Mensagens de log são escritas por nós no código-fonte; nenhuma delas interpola algo
digitado por você, porque não há nada digitado por você.
[Crashlytics e privacidade](https://firebase.google.com/support/privacy#crashlytics)

**Firebase Remote Config** — busca parâmetros de configuração do jogo (por exemplo, limites de
frequência de anúncios). Para isso o SDK envia o ID de instalação do Firebase e dados básicos do
app e do dispositivo. Não envia seu progresso nem suas pontuações. Sem Firebase, o app usa os
valores padrão que já vêm embutidos nele.

**O Firebase Cloud Messaging não é usado.** O lembrete diário opcional do Desafio do Dia, quando
você o ativa, é uma notificação **local**, agendada no próprio aparelho. Nenhum servidor envia
mensagens para o seu celular.

[Privacidade e segurança no Firebase](https://firebase.google.com/support/privacy)

### 4.4 Bibliotecas do Google Play

- **Play In-App Review** (`com.google.android.play:review-ktx:2.0.2`) — abre a janela de avaliação da
  Play Store dentro do jogo. A avaliação que você escreve vai para o Google, não para nós; nós nem
  ficamos sabendo se você avaliou.
- **Play In-App Update** (`com.google.android.play:app-update-ktx:2.1.0`) — verifica com a Play Store
  se existe uma versão mais nova e oferece a atualização.

Ambas funcionam através dos serviços do Google Play já instalados no seu aparelho e seguem a
[Política de Privacidade do Google](https://policies.google.com/privacy).

### 4.5 O que **não** acontece

- Não coletamos nome, e-mail, telefone, endereço, documento nem foto.
- Não usamos câmera, microfone, contatos, agenda, SMS, chamadas, arquivos nem localização precisa.
- Não há conta, login, cadastro nem perfil.
- Não há compras dentro do app, assinaturas nem moeda paga.
- Não há chat, fórum, placar online nem qualquer forma de contato com outros jogadores.
- Não vendemos dados. Não temos servidor próprio e não recebemos nenhuma base de dados de jogadores.
- Não usamos rastreamento de terceiros além dos SDKs do Google listados acima.

## 5. Resumo do que é coletado

| Categoria | Coletado? | Por qual componente | Finalidade |
|---|---|---|---|
| Identificadores do dispositivo e de publicidade | Sim | AdMob; Analytics e Crashlytics (se ativos) | Anúncios, medição, diagnóstico de falhas |
| Interações com o app (eventos de jogo e de anúncio) | Sim | AdMob; Analytics (se ativo) | Anúncios e melhoria do jogo |
| Diagnóstico, registros de falha e desempenho | Sim | AdMob; Crashlytics (se ativo) | Corrigir travamentos |
| Localização aproximada derivada do IP | Sim | AdMob (e Analytics, se ativo) | Segmentação e obrigações regionais |
| Localização precisa (GPS) | **Não** | — | — |
| Nome, e-mail, telefone, documentos | **Não** | — | — |
| Contatos, agenda, fotos, arquivos, mensagens | **Não** | — | — |
| Áudio, vídeo, câmera, microfone | **Não** | — | — |
| Informações financeiras ou de saúde | **Não** | — | — |
| Progresso e configurações do jogo | Sim, **só no seu aparelho** | O próprio app | Salvar sua partida e suas escolhas |

## 6. Permissões do aplicativo

O Encaixa declara apenas três permissões, todas automáticas (nenhuma delas abre um pedido na tela):

| Permissão | Para quê |
|---|---|
| `android.permission.INTERNET` | Baixar anúncios e, quando o Firebase está ativo, enviar eventos e relatórios de falha |
| `android.permission.ACCESS_NETWORK_STATE` | Saber se há conexão antes de pedir um anúncio |
| `com.google.android.gms.permission.AD_ID` | Ler o identificador de publicidade do Android, exigido pelo Google para apps que mostram anúncios e têm como alvo a API 33 ou superior |

Se a versão instalada incluir o lembrete diário opcional do Desafio do Dia, o app também declara
`android.permission.POST_NOTIFICATIONS` e pede sua autorização **no momento em que você liga o
lembrete** — nunca na primeira abertura. Recusar não afeta nada mais no jogo.

O jogo funciona por completo **sem internet**. A conexão é usada apenas para anúncios e, se
aplicável, telemetria.

## 7. Identificador de publicidade e anúncios personalizados

O identificador de publicidade do Android é um número que pode ser zerado e que pertence a você, não
a nós. Você controla esse identificador diretamente no sistema:

**Configurações do Android → Google → Todos os serviços → Anúncios** (o caminho muda um pouco
conforme o fabricante), onde é possível **redefinir o identificador** ou **excluí-lo**. Excluindo-o,
você continua vendo anúncios, mas eles deixam de ser personalizados.

Dentro do jogo, quando o UMP indica que sua região exige, o item **Configurações → Opções de
privacidade** reabre o formulário de consentimento do Google para você mudar de ideia.

[Mais sobre o identificador de publicidade](https://support.google.com/googleplay/android-developer/answer/6048248)

## 8. Bases legais

### 8.1 LGPD (Brasil) — regime principal

| Tratamento | Base legal (Lei nº 13.709/2018) |
|---|---|
| Salvar seu progresso e suas configurações no aparelho | Execução do próprio serviço que você solicitou (art. 7º, V) — e, na prática, o dado nem sai do seu aparelho |
| Exibir anúncios não personalizados e aplicar limites de frequência | Legítimo interesse do controlador (art. 7º, IX), por ser o que viabiliza um jogo gratuito e sem compras |
| Exibir anúncios **personalizados** | Consentimento (art. 7º, I), coletado pelo formulário do Google (UMP) onde ele for exigido |
| Análise de uso e relatórios de falha (quando o Firebase está ativo) | Legítimo interesse do controlador (art. 7º, IX) em manter o app estável, limitado a dados não identificáveis diretamente |

### 8.2 GDPR / UK GDPR — porque o app pode ser baixado no Espaço Econômico Europeu

| Tratamento | Base legal |
|---|---|
| Anúncios personalizados, análise de uso | Consentimento, art. 6(1)(a), coletado pelo formulário do UMP, que também opera o TCF |
| Anúncios não personalizados, segurança e prevenção a fraude, relatórios de falha | Legítimo interesse, art. 6(1)(f) |

Onde o GDPR se aplica, o formulário do UMP aparece antes de qualquer pedido de anúncio, e nenhum
anúncio é solicitado enquanto o SDK não confirmar que pode solicitá-lo. O consentimento pode ser
revogado a qualquer momento em **Configurações → Opções de privacidade**.

## 9. Com quem os dados são compartilhados

- **Google LLC e suas afiliadas**, na qualidade de operador e/ou de rede de anúncios, através dos
  serviços AdMob, UMP, Firebase e Google Play descritos na §4.
- **Compradores de espaço publicitário e parceiros de mediação do Google**, na medida em que o
  Google os envolve na entrega dos anúncios, conforme as políticas do próprio Google.

Não compartilhamos dados com mais ninguém. Não vendemos dados. Não fazemos perfilamento próprio:
nós não temos acesso a nenhum dado individual — só a relatórios agregados nos painéis do AdMob e,
se ativo, do Firebase.

## 10. Transferência internacional

Os serviços do Google tratam dados em servidores localizados fora do Brasil, inclusive nos Estados
Unidos. Essas transferências são feitas pelo Google com as salvaguardas que o próprio Google
publica (cláusulas contratuais padrão e programas de adequação aplicáveis), descritas nos
[Termos de Processamento de Dados de Publicidade](https://business.safety.google/adsprocessing/) e
na [Central de Privacidade do Google](https://policies.google.com/privacy).

## 11. Por quanto tempo os dados ficam

- **No seu aparelho:** até você desinstalar o app ou usar **Configurações → Excluir meus dados**.
  Não há prazo automático; nada expira sozinho.
- **Google Analytics (se ativo):** pelo prazo configurado no console do Firebase — o padrão do
  Google para novas propriedades é de **2 meses**, e o máximo é de **14 meses**.
- **Crashlytics (se ativo):** relatórios de falha ficam retidos pelo prazo publicado pelo Google
  para o serviço. Consulte a [página de privacidade do Crashlytics](https://firebase.google.com/support/privacy#crashlytics).
- **AdMob:** conforme as políticas de retenção do Google, fora do nosso controle.

Nós, como desenvolvedores, não guardamos cópia de nada: não operamos nenhum servidor nem nenhuma
base de dados.

## 12. Segurança

- Todo o tráfego entre o app e os serviços do Google usa **HTTPS/TLS** (dados criptografados em
  trânsito).
- Os dados locais ficam no armazenamento privado do aplicativo, isolado pelo sistema Android de
  outros apps, e são protegidos pela criptografia do próprio aparelho.
- O app não expõe nenhum componente a outros aplicativos além da tela inicial (o *launcher*).
- Não registramos dados pessoais em logs, e os logs de depuração são removidos da versão publicada.

Nenhum sistema é perfeitamente seguro; fazemos o que está ao nosso alcance, mas não podemos dar
garantia absoluta.

## 13. Crianças e adolescentes

O Encaixa **não é direcionado a crianças**. O público-alvo declarado na Google Play é de **13 anos
ou mais** (faixas 13–15, 16–17 e 18+). O jogo não participa do programa Google Play Famílias, não
usa mascotes, personagens ou arte infantil, e sua descrição, ícone e capturas de tela são feitos
para não atrair primariamente crianças.

Não coletamos conscientemente dados de crianças menores de 13 anos. No Brasil, o tratamento de
dados de crianças (menores de 12 anos, conforme o ECA) exige consentimento específico e destacado
de ao menos um dos pais ou responsável legal (LGPD, art. 14), e este aplicativo não foi construído
para obtê-lo. Se você é pai, mãe ou responsável e acredita que uma criança usou o app, escreva para
**talero.dev@gmail.com** e nós orientaremos como apagar os dados — que, na prática, estão no próprio
aparelho e são apagados com um toque (§14).

## 14. Como excluir seus dados

### 14.1 Dentro do jogo — imediato, sem pedir nada a ninguém

Abra **Configurações → Excluir meus dados** e confirme. A ação é destrutiva e não tem volta. Ela:

1. descarta qualquer gravação de partida que ainda esteja na fila;
2. apaga **todas** as tabelas do banco de dados local — recorde, estatísticas, partida salva,
   calendário e sequência do Desafio do Dia, estrelas da Aventura, conquistas, temas desbloqueados
   e ajudas — numa única transação, incluindo o contador interno de pontuações recentes, de modo que
   a instalação volta a parecer nova;
3. limpa o arquivo de configurações (`encaixa_settings`);
4. limpa os contadores de frequência de anúncios (`encaixa_ad_policy`);
5. zera os dados de análise do aparelho (`resetAnalyticsData()` do Firebase Analytics) quando o
   Firebase está ativo — sem Firebase, este passo não faz nada, porque não há nada a zerar;
6. redefine sua resposta ao formulário de consentimento (UMP), de modo que ele será perguntado de
   novo onde for exigido.

O app **não tem conta de usuário**, então não existe "excluir conta": não há nada no lado do
servidor para excluir.

### 14.2 Desinstalando

Desinstalar o aplicativo remove todo o armazenamento local. Se o backup automático do Google
estiver ligado, uma cópia do progresso pode permanecer no Google Drive da sua conta — você a remove
nas configurações de backup da sua conta Google.

### 14.3 Falando com a gente

Escreva para **talero.dev@gmail.com** com o assunto "LGPD — solicitação de titular". Responderemos
em até **15 dias** (LGPD, art. 19, §1º) ou em até **30 dias** quando o pedido vier sob o GDPR.
Como não mantemos base de dados própria, a resposta normalmente consistirá em orientar o
procedimento acima e, quando cabível, encaminhar você ao Google para os dados que estão sob o
controle dele.

### 14.4 Dados que estão com o Google

Para os dados coletados pelos SDKs do Google, os controles ficam com o Google:

- identificador de publicidade: **Configurações do Android → Google → Anúncios** (redefinir ou
  excluir);
- dados associados à sua Conta Google: [Minha Atividade](https://myactivity.google.com) e a
  [Central de Privacidade do Google](https://myaccount.google.com/privacy).

## 15. Seus direitos

**Pela LGPD (art. 18)**, você pode pedir, a qualquer momento e gratuitamente: confirmação da
existência de tratamento; acesso aos dados; correção de dados incompletos, inexatos ou
desatualizados; anonimização, bloqueio ou eliminação de dados desnecessários, excessivos ou
tratados em desconformidade com a lei; portabilidade; eliminação dos dados tratados com base no seu
consentimento; informação sobre as entidades com quem compartilhamos dados; informação sobre a
possibilidade de não fornecer consentimento e suas consequências; e revogação do consentimento.

Você também pode apresentar reclamação à **Autoridade Nacional de Proteção de Dados (ANPD)**:
[gov.br/anpd](https://www.gov.br/anpd/pt-br).

**Pelo GDPR**, se você estiver no Espaço Econômico Europeu, no Reino Unido ou na Suíça, você tem
direito de acesso (art. 15), retificação (16), apagamento (17), limitação do tratamento (18),
portabilidade (20), oposição (21) e de revogar o consentimento a qualquer momento (7(3)), além do
direito de reclamar à autoridade de proteção de dados do seu país.

Para exercer qualquer um deles: **talero.dev@gmail.com**.

## 16. Alterações nesta política

Quando esta política mudar, atualizaremos a data de "Última atualização" no topo e publicaremos a
nova versão em **https://github.com/talero-dev/encaixa-privacy-policy**. Mudanças relevantes serão comunicadas também
nas notas da versão na Google Play. Continuar usando o app depois da atualização significa que você
tomou conhecimento da nova versão.

## 17. Contato

**Controlador dos dados:** Talero
**Contato de privacidade:** talero.dev@gmail.com

---

## 18. Anexo — componentes de terceiros e seus links

| Componente | Versão | Fornecedor | Política |
|---|---|---|---|
| Google Mobile Ads SDK (Next-Gen) | 1.5.0 | Google | https://policies.google.com/technologies/partner-sites |
| User Messaging Platform (UMP) | 4.0.0 | Google | https://support.google.com/admob/answer/10113207 |
| Google Analytics for Firebase | BoM 34.19.0 | Google | https://firebase.google.com/docs/analytics/user-data-collection |
| Firebase Crashlytics | BoM 34.19.0 | Google | https://firebase.google.com/support/privacy#crashlytics |
| Firebase Remote Config | BoM 34.19.0 | Google | https://firebase.google.com/support/privacy |
| Play In-App Review | 2.0.2 | Google | https://policies.google.com/privacy |
| Play In-App Update | 2.1.0 | Google | https://policies.google.com/privacy |

Os três componentes do Firebase só estão presentes na configuração descrita em §4.3.
