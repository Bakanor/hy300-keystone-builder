# HY300 Pro - Android 16 Keystone Builder (TrebleDroid a64)

Questo repository contiene il workflow automatico di GitHub Actions per compilare **SurfaceFlinger** e **librenderengine** con la patch di correzione del trapezio (Keystone) a 4 angoli per il proiettore Magcubic HY300 Pro (Allwinner H713).

Target compilato: `treble_a64_bvS-userdebug` (ARM 32-bit con Binder a 64-bit).

---

## Come Avviare la Compilazione Gratuita

### 1. Crea un repository su GitHub
1. Vai su [github.com/new](https://github.com/new).
2. Nome repository: `hy300-keystone-builder` (puoi impostarlo sia **Pubblico** che **Privato**).
3. Non selezionare "Add a README file" o "Add .gitignore". Clicca **Create repository**.

### 2. Carica questi file dal tuo PC Windows
Dalla cartella `diagnostics/hy300-keystone-builder`, esegui in PowerShell:
```powershell
cd V:\Documents\ChatGPT\Cast\work\hy300-pro\diagnostics\hy300-keystone-builder
git init
git add .
git commit -m "Add Android 16 Keystone build workflow"
git branch -M main
git remote add origin https://github.com/TUO_USERNAME/hy300-keystone-builder.git
git push -u origin main
```
*(In alternativa, puoi anche trascinare la cartella `.github` e `patches` direttamente dall'interfaccia web di GitHub).*

### 3. Avvia la build e scarica i file
1. Nel tuo repository su GitHub, vai nella scheda **Actions**.
2. Clicca sul workflow **Build SurfaceFlinger with Keystone for HY300 Pro (ARM32/Binder64)**.
3. Clicca su **Run workflow** $\to$ **Run workflow**.
4. Al termine dell'esecuzione (icona verde di successo), troverai nella sezione **Artifacts** il pacchetto scaricabile:
   `hy300pro-android16-keystone-a64`
   Contiene:
   - `surfaceflinger` (eseguibile ARM32)
   - `libsurfaceflinger.so`
   - `librenderengine.so`
   - `architecture_report.txt` (verifica dell'architettura ELF ARM32)
   - `sha256_checksums.txt` (hash di integrità di ogni file)
   - `build.log` (log completo di compilazione)
