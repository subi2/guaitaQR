# guaitaQR v1.0

[Català](#guaitaqr-v10) · [English](#english)

Descodificador de codis QR local i sense xarxa per a mòbil i tauleta. **Analitza l'adreça o el contingut codificat al QR *abans* que res s'obri.**

Part de [Guaita Apps](https://github.com/subi2/guaitaApps), la col·lecció d'eines HTML autònomes de codi obert (AGPL-3.0) per a fluixos BIM/IFC/AEC.

## Per què guaitaQR

Els QR codes es fan servir per dirigir-te a pàgines web, però no sempre és clar on porto realment:
- Els escurçadors (bit.ly, tinyurl…) amagan la destinació final
- Els dominis falsificats (paypal.com.cobrament.top) semblen legítims
- Els caràcters invisibles o alfabets aliens imiten les lletres reals
- Fins una redirecció pot dur-te a un altre lloc del que veus

**guaitaQR et mostra la URL o el contingut complet, decodificat, amb un semàfor que avisa dels senyals d'estafa més freqüents.**

## Característiques

- 🔒 **Sense xarxa:** res no surt del dispositiu. El fitxer incorpora tot el que necessita.
- 📱 **Per a mòbil i tauleta:** funciona a l'iPhone, iPad i Android amb Safari, Chrome o similar.
- 📷 **Càmera en directe** (si és HTTPS o localhost): escaneja mentre filmes.
- 📸 **Des de foto:** fes la captura o tria una de la galeria.
- 🎨 **Tema Caixetí:** verd àcid sobre negre, tipografia IBM Plex.
- 🔍 **Anàlisi de seguretat:** detecta dominis falsificats, imitacions de marques, escurçadors, paràmetres de redirecció, caràcters invisibles, etc.
- 🛡️ **Política CSP estricta:** el navegador bloqueja qualsevol connexió.
- 📋 **Menús en cascada:** totes les accions des del menú (Fitxer, Edita, Veure, Ajuda).
- 📚 **Finestra d'ajuda detallada:** explica cada tipus de QR, com llegir el semàfor, límits de la detecció.

## Tipus de QR que llegeix

- 🌐 **URL** (`https://…`, `www.…`)
- 📡 **Wi-Fi** (`WIFI:…`)
- ☎️ **Telèfon** (`tel:…`, `sms:…`)
- 📧 **Correu** (`mailto:…`)
- 👤 **Contactes** (vCard, MeCard)
- 📅 **Esdeveniments** (iCal)
- 🗺️ **Ubicació** (`geo:…`)
- 🔐 **2FA** (`otpauth:…`)
- 💰 **Pagaments** (Bitcoin, SEPA, etc.)
- 📝 **Text pla**

I altres esquemes (`ftp:`, `intent:`, etc.). Alguns es marquen en vermell perquè són senyals d'estafa.

## Com usar-lo

### Opció 1: Online (GitHub Pages)
```
https://subi2.github.io/guaitaqr/
```
Obre el navegador del mòbil i visita l'adreça. Funciona sense WiFi (excepte la càmera en directe, que necessita HTTPS).

### Opció 2: Local (descàrrega)
1. Descarrega `guaitaQR_1.0.html`
2. Envia't el fitxer per correu o penja-ho a iCloud Drive
3. Obre el fitxer amb el navegador del mòbil
4. Funciona tot (menys la càmera, que necessita HTTPS)

### Opció 3: Fitxer local (Mac/PC)
1. Descàrrega el fitxer
2. Fes clic dret > Obrir amb > Navegador
3. O arrossega'l al navegador

## Seguretat

**Res no surt del dispositiu.** guaitaQR és autònom:

- ✅ No fa cap petició de xarxa (ni siquiera rastreig)
- ✅ No emmagatzema res (sense cookies, sense localStorage)
- ✅ No carrega recursos externos (les fonts i el lector QR van dins)
- ✅ La càmera es processa en memòria i es descarta
- ✅ El navegador imposa una política de seguretat (`connect-src 'none'`) que bloqueja qualsevol connexió

**Com verificar-ho:**
1. Activa el mode avió del mòbil
2. Obriu guaitaQR: funciona igual
3. O al navegador (F12 > Console) veuràs que no hi ha cap petició de xarxa

## Què detecta, qué no

### Detecta (semàfor groc o vermell)
- Dominis falsificats (paypal.com.x, google.x.top)
- Marques imitades o amb leet-speak (pаypal, paypa1)
- Escurçadors (bit.ly, tinyurl, t.co…): adreça amagada
- Paràmetres de redirecció (`url=`, `redirect=`)
- `@` en l'adreça (navegador va al que sigui després)
- IP pública o amb port estrany
- `http` sense xifrat
- Caràcters invisibles o de control
- Mescla d'alfabets (cirílic que imita llatí)
- TLD sospitosos (.zip, .top, .xyz…)
- Molt subdominis, guions excessius
- Hosts compartits (github.io, web.app…)

### No detecta
- Domini acabat de registrar que sembla normal
- Web legítima que ha sigut compromesa
- Adhesiu de QR enganxat damunt d'un altre
- Llistes parcials: la detecció es basa en patrons, no és exhaustiva

⚠️ **Regla pràctica:** si el semàfor és verd però el domini **no és el que esperaves**, no l'obris.

## Límits

- 📸 **Càmera en directe:** necessita HTTPS (o localhost). Des d'un fitxer local al mòbil, fes servir «Tria foto».
- 🔗 **Escurçadors:** sense xarxa, solo veus l'adreça curta. L'eina avisa que és opaca.
- 📋 **Llistes de referència:** marques, escurçadors i TLD sospitosos són parcials. Sempre usa el criteri personal.

## Instal·lació a GitHub Pages

1. Crea un repo públic a GitHub (o usa `guaitaqr` o el nom que prefereixis)
2. Puja `guaitaQR_1.0.html` amb el nom `index.html` (o qualsevol `.html`)
3. Settings > Pages > Source: `main` / `root` > Save
4. Dins de 1-2 minuts: `https://tunom.github.io/nom-repo/`

Des de qualsevol mòbil, tauleta o ordenador, obre l'adreça i funciona.

## Ús educatiu

Perfecte per a:
- Cursos sobre seguretat digital i suplantació d'identitat
- Tallers sobre phishing i estafes
- Anàlisi de codis QR sospitosos en campanyes reals
- Arquitectura i construcció: validar QR de plànols, licitacions, proveïdors

## Contribucions

Proporciona marques, escurçadors o TLD addicionals que creguis que hauria de detectar. Abre un issue a [subi2/guaitaApps](https://github.com/subi2/guaitaApps).

## Llicència

AGPL-3.0-only. Lliure de usar, modificar i distribuir amb el codi obert.

Inclou:
- **jsQR** 1.4.0 (Apache-2.0, Cozmo)
- **IBM Plex Mono** i **IBM Plex Sans** (SIL OFL 1.1, IBM Corp.)

## Sobre Guaita Apps

guaitaQR és una peça de [Guaita Apps](https://github.com/subi2/guaitaApps), una col·lecció de eines BIM/IFC/AEC de codi obert per a arquitectes, enginyers i gestor de projectes.

Altres tools:
- **guaitaIFCParser:** comparador diagnostic de fitxers IFC
- **guaitaFedera:** visor federat de IFC/DXF/PDF amb alineament
- **GuaitaCDE:** gestor de documents ISO 19650
- **guaitaZip:** compressor de fitxers
- … i més

Tots són fitxers HTML únics, sense dependències externes, AGPL-3.0.

---

## English

# guaitaQR v1.0

Local, offline QR code reader for phones and tablets. **It decodes and analyses the address or content inside a QR *before* anything is opened.**

Part of [Guaita Apps](https://github.com/subi2/guaitaApps), an open-source (AGPL-3.0) collection of self-contained HTML tools for BIM/IFC/AEC workflows.

### Why guaitaQR

A QR code is just text, and you can't tell by looking where it will take you:
- URL shorteners (bit.ly, tinyurl…) hide the final destination
- Look-alike domains (`paypal.com.cobrament.top`) seem legitimate
- Invisible characters and foreign alphabets mimic real letters
- A redirect parameter can send you somewhere other than what you see

**guaitaQR shows the full decoded URL or content, with a traffic light that flags the most common scam signals.**

### Features

- 🔒 **Offline:** nothing leaves the device. The file contains everything it needs.
- 📱 **Built for phones and tablets:** works on iPhone, iPad and Android with Safari, Chrome or similar.
- 📷 **Live camera** (over HTTPS or localhost): scan as you point.
- 📸 **From a photo:** take a picture or pick one from the gallery.
- 🎨 **Caixetí theme:** acid green on black, IBM Plex typography.
- 🔍 **Security analysis:** detects look-alike domains, brand imitations, shorteners, redirect parameters, invisible characters and more.
- 🛡️ **Strict CSP:** the browser blocks any connection.
- 📋 **Classic cascading menus:** every action is in the menu (File, Edit, View, Help).
- 📚 **Detailed help window:** explains how it works from a security point of view, how to read the traffic light, and the limits of detection.

### QR types it reads

- 🌐 **URL** (`https://…`, `www.…`)
- 📡 **Wi-Fi** (`WIFI:…`)
- ☎️ **Phone** (`tel:…`, `sms:…`)
- 📧 **Email** (`mailto:…`)
- 👤 **Contacts** (vCard, MeCard)
- 📅 **Events** (iCal)
- 🗺️ **Location** (`geo:…`)
- 🔐 **2FA** (`otpauth:…`)
- 💰 **Payments** (Bitcoin and other crypto, SEPA)
- 📝 **Plain text**

Other schemes (`ftp:`, `intent:`, `itms-services:`…) are also recognised, and some are flagged red because they are typical scam vectors.

### How to use it

**Option 1: Online (GitHub Pages)**
```
https://subi2.github.io/guaitaqr/
```
Open the address in your phone's browser. The live camera needs HTTPS, which GitHub Pages provides.

**Option 2: Local file**
1. Download `guaitaQR_1.0.html`
2. Open it with the browser
3. Everything works except the live camera. Use "Tria foto" (pick a photo) instead.

### Security

**Nothing leaves the device.** guaitaQR is self-contained:

- ✅ Makes no network requests
- ✅ Stores nothing (no cookies, no localStorage)
- ✅ Loads no external resources (fonts and the QR decoder are inlined)
- ✅ Camera frames and photos are processed in memory and discarded
- ✅ The browser enforces a Content Security Policy (`connect-src 'none'`) that blocks any connection

**How to verify it:**
1. Turn on airplane mode
2. Open guaitaQR: it works the same
3. Or run the isolation test from the Help menu

### What it detects and what it doesn't

**Detects (yellow or red):**
- Look-alike domains (`paypal.com.x`, `google.x.top`)
- Imitated brands, including leetspeak and Cyrillic look-alikes (`pаypal`, `paypa1`)
- URL shorteners (bit.ly, tinyurl, t.co…): the destination is opaque
- Redirect parameters (`url=`, `redirect=`)
- `@` in the address (the browser goes to what follows it)
- IP addresses, including obfuscated forms, and unusual ports
- `http` without encryption
- Invisible or control characters, bidirectional text tricks
- Mixed alphabets inside one name
- Suspicious TLDs (.zip, .top, .xyz…)
- Excess subdomains and hyphens
- Platforms where anyone can host a page (github.io, web.app…)

**Does not detect:**
- A newly registered domain that looks normal and imitates no known brand
- A legitimate site that has been compromised
- A QR sticker placed over another one
- Anything outside its reference lists, which are partial

⚠️ **Rule of thumb:** if the light is green but the domain **is not the one you expected**, don't open it.

### Limits

- 📸 **Live camera:** needs HTTPS (or localhost). From a local file on a phone, use "Tria foto".
- 🔗 **Shorteners:** offline, you only see the short address. The tool warns that the destination is opaque and, for tinyurl and bit.ly, offers a preview link to copy.
- 📋 **Reference lists:** brands, shorteners and TLDs are partial. Always use your own judgement.

### Deploying on GitHub Pages

1. Create a public repository on GitHub (e.g. `guaitaqr`)
2. Upload `guaitaQR_1.0.html` as `index.html`
3. Settings > Pages > Source: `main` / `root` > Save
4. After 1–2 minutes: `https://yourname.github.io/guaitaqr/`

### Educational use

Useful for:
- Digital security and phishing awareness courses
- Workshops on QR-based scams
- Checking suspicious QR codes found in real campaigns
- Architecture and construction: validating QR codes on drawings, tenders or supplier documents

### Contributing

Suggest extra brands, shorteners or TLDs worth detecting by opening an issue at [subi2/guaitaApps](https://github.com/subi2/guaitaApps).

### License

AGPL-3.0-only. Free to use, modify and distribute with the source open.

Includes:
- **jsQR** 1.4.0 (Apache-2.0, Cozmo)
- **IBM Plex Mono** and **IBM Plex Sans** (SIL OFL 1.1, IBM Corp.)

### About Guaita Apps

guaitaQR is part of [Guaita Apps](https://github.com/subi2/guaitaApps), an open-source collection of BIM/IFC/AEC tools for architects, engineers and project managers. Every tool is a single HTML file with no external dependencies, licensed AGPL-3.0.
