# Sync-Manager

## Panoramica del Prodotto

**Sync-Manager** è uno strumento di automazione pensato per sviluppatori, agenzie digitali e team operativi che gestiscono più applicazioni web in produzione. Permette di aggiornare e allineare i progetti software dall'ambiente di lavoro locale al server di produzione **in pochi secondi e con un solo comando**, eliminando definitivamente gli errori manuali di caricamento.

È la soluzione ideale per chi gestisce un portafoglio di progetti (SaaS, dashboard, connettori) e ha bisogno di un flusso di rilascio rapido, ripetibile e a prova di errore umano.

## Il Problema Risolto

Nel lavoro quotidiano di uno sviluppatore o di un'agenzia, il deploy manuale di un progetto è una delle attività più lente e rischiose:

- **Perdita di tempo:** copiare file a mano, aprire client FTP, ripetere le stesse operazioni per ogni progetto.
- **Errori manuali:** caricare file incompleti, dimenticare cartelle di configurazione, sovrascrivere risorse sbagliate.
- **Colli di bottiglia operativi:** ogni rilascio richiede attenzione costante e intervento umano, anche per una modifica di una singola riga.
- **Downtime prolungato:** se il servizio non viene riavviato correttamente dopo l'aggiornamento, gli utenti subiscono interruzioni evitabili.
- **Tracciabilità assente:** senza versionamento coerente, è difficile sapere cosa è stato pubblicato, quando e perché.

Sync-Manager azzera questi rischi: un'unica procedura guidata gestisce sincronizzazione, riavvio dei servizi e registrazione delle modifiche, in modo tollerante ai guasti (se una fase fallisce, la pipeline si blocca in sicurezza senza lasciare il sistema in uno stato incoerente).

## Come Funziona (Flusso Operativo Utente)

L'utilizzo è pensato per essere immediato, senza configurazioni ripetitive:

1. **Avvio dello strumento:** l'operatore lancia lo script dal proprio ambiente locale e si presenta un menu di selezione chiaro.
2. **Scelta del progetto:** dall'elenco dei progetti gestiti si seleziona quello su cui operare (è possibile uscire in qualsiasi momento).
3. **Scelta dell'operazione:** si sceglie tra:
   - **Pull:** scaricare la versione attuale dal server di produzione verso l'ambiente locale, per lavorare sui dati e sui file più recenti.
   - **Push:** inviare la versione locale aggiornata verso il server di produzione.
4. **Sincronizzazione intelligente:** durante il trasferimento vengono automaticamente escluse le cartelle non necessarie (dipendenze, repository di versione, file temporanei e upload degli utenti), garantendo trasferimenti rapidi e puliti.
5. **Riavvio automatico dei servizi:** al termine del push, i servizi applicativi in produzione vengono riavviati automaticamente per rendere subito operative le modifiche, riducendo il downtime al minimo.
6. **Versioning locale guidato:** viene chiesta una breve descrizione delle modifiche; se non viene inserita entro pochi secondi, viene applicato un auto-commit con descrizione standard, così la cronologia delle versioni non si interrompe mai.
7. **Risultato finale:** il progetto in produzione è allineato, il servizio è operativo e le modifiche sono tracciate localmente. Tutto in un unico flusso, senza passaggi manuali intermedi.

## Funzionalità Principali & Vantaggi Operativi (ROI)

- **Deploy con un solo comando:** da minuti di operazioni manuali a pochi secondi di tempo effettivo.
- **Gestione multi-progetto:** un unico punto di controllo per tutti i progetti e sottodomini gestiti, con mappatura centralizzata facilmente scalabile.
- **Zero errori di caricamento:** esclusioni automatiche e controlli pre-deploy evitano sovrascritture e trasferimenti incompleti.
- **Tolleranza ai guasti:** ogni fase verifica il proprio esito; in caso di errore critico la pipeline si interrompe in modo sicuro, senza riavvii a metà o commit orfani.
- **Riavvio servizi automatico:** hook post-deploy che riporta l'applicazione online immediatamente dopo l'aggiornamento.
- **Versioning integrato:** inizializzazione automatica del repository locale dove assente, con commit guidati o automatici: cronologia sempre completa.
- **Operabilità asincrona:** progettato per ridurre l'interazione umana al minimo indispensabile, liberando tempo per attività a maggior valore.

**ROI concreto:** per un team che effettua anche solo 5-10 rilasci al giorno, il risparmio di tempo e l'eliminazione degli errori di deploy si traducono in ore recuperate ogni settimana e in una drastica riduzione degli incidenti in produzione.

## Tecnologie Utilizzate (Ad Alto Livello)

- **Shell Scripting Bash:** scelta strategica per massima affidabilità, portabilità e zero dipendenze superflue: gira nativamente su qualsiasi ambiente Linux.
- **Rsync:** standard industriale per la sincronizzazione file, con trasferimenti incrementali veloci e verificati.
- **Git:** versionamento locale robusto e universale, per una tracciabilità completa delle modifiche.
- **PM2:** gestione dei processi applicativi in produzione, per riavvii controllati e downtime minimo.
- **SSH:** connessioni sicure verso l'infrastruttura remota per tutte le operazioni di deploy.

Uno stack maturo e consolidato che garantisce stabilità nel tempo, prestazioni elevate e manutenibilità con sforzo minimo: esattamente ciò che serve a un operatore singolo che gestisce più sistemi in produzione.

---

🔒 **Asset Software Proprietario:** Questo repository ha finalità di presentazione funzionale per il Portfolio Professionale (antoniangeloflore.com). Per ragioni di sicurezza operativa e accordi di riservatezza (NDA), il codice sorgente e le specifiche infrastrutturali non sono esposti pubblicamente.
