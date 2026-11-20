# Budget di casa

Web app per gestire le spese di famiglia da due telefoni: entrate, uscite fisse, spese extra, grafici e fringe welfare.

Servono **due repository** su GitHub:

| Repository | Visibilità | Cosa contiene |
|---|---|---|
| `budget-casa` | Pubblico (serve per GitHub Pages) | L'app: `index.html`, `sw.js`, `manifest.webmanifest`, le icone |
| `budget-dati` | **Privato** | Solo il file `budget.json` con i vostri numeri |

Così il codice dell'app è online, ma i vostri soldi restano in un repository che vedete solo voi.

---

## 1. Pubblicare l'app

1. Su GitHub: **New repository** → nome `budget-casa` → **Public** → Create.
2. **Add file → Upload files** e caricate: `index.html`, `sw.js`, `manifest.webmanifest`, `icon-180.png`, `icon-192.png`, `icon-512.png`, `README.md`.
   ⚠️ **Non** caricate `budget.json` qui.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save.
4. Dopo un minuto l'app è su `https://nikolas8693-star.github.io/budget-casa/`.

## 2. Repository privato per i dati

1. **New repository** → nome `budget-dati` → **Private** → Create.
2. **Add file → Upload files** → caricate `budget.json` (contiene già i dati del vostro file Numbers: il mese 10 ott – 9 nov e la tabella Fringe Welfare 2026).

## 3. Creare il token (una volta sola)

1. GitHub → foto profilo → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Nome: `budget`. Scadenza: quella che preferite (anche 1 anno).
3. **Repository access → Only select repositories** → scegliete solo `budget-dati`.
4. **Permissions → Repository permissions → Contents → Read and write**.
5. **Generate token** e copiatelo (inizia con `github_pat_…`).

Il token può leggere e scrivere **solo** quel repository. Va inserito in ogni telefono che usa l'app e resta salvato solo lì.
Se il token scade, l'app mostra "Non sincronizzato": generatene uno nuovo e inseritelo in Impostazioni → Sincronizzazione → Modifica.

## 4. Sul telefono

1. Aprite l'indirizzo dell'app in **Safari**.
2. **Collega i dati su GitHub** → scrivete `nikolas8693-star`, `budget-dati`, e incollate il token.
3. Condividi → **Aggiungi alla schermata Home**: si apre a tutto schermo, come un'app.
4. In **Impostazioni → Chi usa questo telefono** scegliete Ninni o Lilli.

Fate lo stesso sul telefono di vostra moglie (lo stesso token va bene, oppure createne un secondo).

---

## Come funziona

- **Mese**: il periodo va dal 10 al 9 del mese dopo (si cambia in Impostazioni). In alto c'è l'avanzo; sotto, entrate, uscite fisse e spese extra. Toccate una voce per modificarla.
- **Entrate e uscite fisse**: l'importo a destra si modifica direttamente, basta toccarlo. Il nuovo valore vale per questo mese e per i successivi (i mesi passati non cambiano). Toccando il nome si apre la scheda per rinominare o eliminare la voce.
- **Voci ricorrenti**: entrate e uscite fisse si ricopiano da sole in ogni nuovo mese.
- **+ arancione**: aggiunge una spesa extra. Il mese si sceglie in base alla data.
- **Grafici**: dove vanno i soldi nel mese e l'avanzo mese per mese.
- **Welfare**: benzina e spesa per mese, con quanto resta del tetto annuo (impostato a 1.000 €, si cambia in Impostazioni).
- **Sincronizzazione**: ogni modifica viene salvata su GitHub dopo un secondo. Quando aprite l'app scarica le modifiche dell'altro telefono. Se modificate tutti e due insieme, le modifiche vengono unite.
- **Senza internet** l'app funziona lo stesso e sincronizza appena torna la connessione.
- **Backup**: Impostazioni → Esporta file. In più GitHub conserva la cronologia di ogni modifica in `budget-dati`.
