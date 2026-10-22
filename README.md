# ATLAS — spazio personale

PWA personale local-first progettata per iPhone. ATLAS mette in un unico hub Home, Fitness, Wealth, Properties, Nutrition, Travel e Garage. L’archivio applicativo usa IndexedDB sul dispositivo; backup e ripristino avvengono tramite file JSON scelti dall’utente.

## Avvio

Pubblica il contenuto di questa cartella su un host HTTPS statico (per esempio GitHub Pages). Apri l’indirizzo con Safari su iPhone, quindi **Condividi → Aggiungi alla schermata Home**. Al primo accesso online il service worker memorizza i file essenziali; poi la shell e i dati ATLAS funzionano offline.

## Moduli presenti

- **Home:** attività giornaliere e riepilogo dei moduli.
- **Fitness:** incorpora Lift Log da `https://matteus1985.github.io/myWorkout/`. myWorkout è indipendente; i suoi file e i dati non vengono copiati o modificati. Se il browser o il sito non consentono l’incorporamento, il link apre myWorkout in una scheda separata.
- **Wealth:** voci manuali in CHF, senza accesso a conti o API finanziarie.
- **Properties:** schede personali per proprietà.
- **Nutrition:** pasti, macro inserite manualmente e conteggio acqua.
- **Travel:** destinazioni e date.
- **Garage:** veicoli e prossima manutenzione.

## Dati e privacy

Le voci ATLAS sono salvate nell’IndexedDB del browser. Non sono cifrate dall’app e possono andare perse se si cancellano i dati di Safari: esporta regolarmente un backup da Impostazioni e custodiscilo in un luogo sicuro. Il backup contiene tutte le voci inserite nell’app; chiunque possa leggere il file potrà leggerne i contenuti. L’URL fitness e le preferenze sono salvate in localStorage. Il collegamento a myWorkout carica contenuti dal sito GitHub Pages e il browser contatta quel dominio; per i dati fitness fanno fede le funzionalità di backup di myWorkout.

## Note tecniche

Nessun framework, server applicativo, login o sincronizzazione cloud. IndexedDB è la fonte dei dati; localStorage contiene soltanto preferenze non critiche. La sincronizzazione tra dispositivi e le integrazioni API sono intenzionalmente escluse dalla prima base, per evitare di introdurre un backend e di caricare dati personali su terzi.
