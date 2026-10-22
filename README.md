# ATLAS — spazio personale

PWA local-first per iPhone. Home e Agenda mostrano gli eventi del calendario principale Google in sola lettura. Fitness, Wealth, Properties, Nutrition, Travel e Garage restano moduli separati. I dati inseriti in ATLAS vengono conservati nell’IndexedDB del browser.

## Avvio

Sito pubblicato su GitHub Pages: <https://matteus1985.github.io/atlas/>. Su iPhone apri il link in Safari e scegli **Condividi → Aggiungi alla schermata Home**. La shell applicativa funziona offline; il calendario richiede rete e collegamento Google.

## Collegare Google Calendar

1. In Google Cloud crea un progetto, abilita **Google Calendar API** e configura la schermata di consenso OAuth.
2. Crea un ID client OAuth di tipo **Applicazione web**. Aggiungi `https://matteus1985.github.io` tra le origini JavaScript autorizzate.
3. Apri ATLAS → Impostazioni e inserisci il Client ID OAuth.
4. Torna ad Agenda e premi **Collega Google Calendar**. Google chiede il consenso per `calendar.events.readonly`, accesso in sola lettura agli eventi.

ATLAS legge gli eventi del calendario principale per il giorno selezionato. Il token rimane solo in memoria, non viene salvato e non passa da un server ATLAS. Gli eventi visualizzati non vengono copiati nell’archivio locale. La connessione va ripetuta dopo aver ricaricato la PWA; il pulsante **Disconnetti** revoca il consenso.

## Moduli presenti

- **Home e Agenda:** eventi della giornata da Google Calendar; navigazione tra date.
- **Fitness:** collega Lift Log da `https://matteus1985.github.io/myWorkout/`. myWorkout rimane indipendente; i suoi file e dati non vengono modificati.
- **Wealth:** voci manuali in CHF, senza accesso a conti o API finanziarie.
- **Properties:** schede personali per proprietà.
- **Nutrition:** pasti, macro inserite manualmente e conteggio acqua.
- **Travel:** destinazioni e date.
- **Garage:** veicoli e prossima manutenzione.

## Dati e privacy

Le voci ATLAS sono salvate nell’IndexedDB del browser e non sono cifrate dall’app. Esporta regolarmente un backup JSON dalle Impostazioni prima di cancellare i dati di Safari o cambiare dispositivo. Il Client ID e l’indirizzo fitness sono preferenze salvate in localStorage. Il collegamento a Google è facoltativo: le richieste API avvengono dal browser dopo il consenso e gli eventi non vengono persistiti da ATLAS.
