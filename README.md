# ATLAS — spazio personale

PWA personale local-first per iPhone. La Home offre un riepilogo dei moduli Fitness, Wealth, Casa, Nutrition, Travel e Garage. I dati inseriti in ATLAS vengono conservati nell’IndexedDB del browser.

## Avvio

Sito pubblicato su GitHub Pages: <https://matteus1985.github.io/atlas/>. Su iPhone apri il link in Safari e scegli **Condividi → Aggiungi alla schermata Home**. La shell applicativa funziona offline.

## Moduli

- **Fitness:** apre Lift Log da `https://matteus1985.github.io/myWorkout/`. myWorkout rimane indipendente; i suoi file e dati non vengono modificati.
- **Wealth:** voci manuali in CHF, senza accesso a conti o API finanziarie.
- **Casa:** schede personali per proprietà.
- **Nutrition:** pasti e acqua; le stime nutrizionali sono inserite manualmente.
- **Travel:** destinazioni e date.
- **Garage:** veicoli e prossima manutenzione. La connessione Connected Car di Stellantis richiede credenziali dell’app sviluppatore e autorizzazione del veicolo; non è configurata in questa versione statica.

## Dati e privacy

Le voci ATLAS sono salvate nell’IndexedDB del browser e non sono cifrate dall’app. Esporta regolarmente un backup JSON dalle Impostazioni prima di cancellare i dati di Safari o cambiare dispositivo. Le preferenze, incluso l’indirizzo fitness, sono salvate in localStorage.
