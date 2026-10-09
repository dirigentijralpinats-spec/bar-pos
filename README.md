# ⚾ Bar Alpina Baseball — POS Web Application (Multi-Sede)

Applicazione Web Cassa POS multi-sede, mobile-first e ad alte prestazioni, progettata per la gestione rapida delle vendite, del magazzino e degli operatori dei punti vendita del **Bar Alpina Baseball**.

---

## 🚀 Architettura e Caratteristiche Principali

* **Multi-Sede Dinamico**: Gestione di più punti vendita (*es. Bar Opicina Alpina, Bar Prosecco Alpina*) tramite configurazione accentrata in `sedi.json`.
* **Backend Serverless**: Utilizza Google Apps Script e Fogli Google come database cloud gratuito e a manutenzione zero.
* **Isolamento dei Dati**: Ogni sede dispone del proprio Foglio Google dedicato per il listino utenti, la giacenza di magazzino e il registro vendite.
* **Interfaccia Touch & Mobile-First**:
  * **Incremento rapido (+1)**: Tap singolo sulla scheda del prodotto.
  * **Decremento rapido (-1)**: Pressione prolungata (*long-press*) sulla scheda del prodotto.
  * **Feedback tattile (Vibrazione)** integrato per conferme rapide su dispositivi mobili.
* **Gestione Pagamenti**: Tracciamento distinto tra **Contanti** e **Pagamento Elettronico** (POS / Carte / Satispay).
* **Autenticazione Sicura**: Google OAuth 2.0 con controllo dei ruoli lato server (`ADMIN` / `OPERATORE`).
* **Hosting**: Deploy continuo su **Cloudflare Pages** ad ogni push sul ramo `main`.

---

## 🛠️ Configurazione Multi-Sede (`sedi.json`)

Tutti i punti vendita sono definiti nel file `sedi.json` posizionato nella radice del repository:

```json
{
  "sedi": [
    {
      "id": "opicina",
      "nome": "Bar Opicina Alpina",
      "webAppUrl": "[https://script.google.com/macros/s/.....U/exec)"
    },
    {
      "id": "prosecco",
      "nome": "Bar Prosecco Alpina",
      "webAppUrl": "[https://script.google.com/macros/s.SECONDA_SEDE.../exec)"
    }
  ]
}
