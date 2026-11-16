# Sync-Manager — Local-to-Production Multi-App Deployment & Sync Orchestrator

🇬🇧 / 🇺🇸 **ENGLISH** | [🇮🇹 Vai alla versione in Italiano](#-italiano)

[![Portfolio](https://img.shields.io/badge/Portfolio-antoniangeloflore.com-0d6efd?style=flat-square)](https://antoniangeloflore.com)
[![Stack](https://img.shields.io/badge/Stack-Bash%20%7C%20Rsync%20%7C%20Git%20%7C%20PM2%20%7C%20SSH-198754?style=flat-square)](https://github.com/pratico)
[![Architecture](https://img.shields.io/badge/Execution-Local%20Control--Plane%20%E2%86%92%20VPS%20%2F%20Hosting-dc3545?style=flat-square)](https://antoniangeloflore.com)

## Product Overview

**Sync-Manager** is a local-first deployment and synchronization automation tool built for developers, digital agencies, and operations teams managing multiple web applications in production.

Running **exclusively on the operator's local Linux workstation** (with zero agent overhead on remote servers), it aligns and updates software projects across **remote Linux VPS and Hosting environments in seconds with a single command**, permanently eliminating manual upload errors.

It is the ideal control plane for engineers and agencies managing a multi-project portfolio (SaaS platforms, internal dashboards, API connectors) who require a fast, repeatable, and fault-tolerant release workflow.

## The Problem Solved

In the daily operations of a software engineer or web agency, manual deployment is one of the slowest and highest-risk bottlenecks:

- **Wasted engineering time:** Manually copying files, opening FTP/SFTP clients, and repeating identical steps across multiple projects.
- **Human deployment errors:** Uploading incomplete builds, forgetting configuration directories, or overwriting production assets.
- **Operational bottlenecks:** Every release demands constant manual attention, even for a single-line patch.
- **Extended downtime:** Failing to restart background services cleanly after an update causes avoidable service interruptions.
- **Missing audit trail:** Without consistent version control, tracking what was deployed, when, and why becomes impossible.

**Sync-Manager** eliminates these risks: a single guided pipeline handles bidirectional synchronization, service restarts, and local version logging in a strictly fault-tolerant manner—if any stage fails, execution halts safely without leaving production in an inconsistent state.

## Operator Workflow (Local Workstation → Remote VPS / Hosting)

The workflow is designed for immediate execution without repetitive configuration:

1. **Tool Launch:** The operator runs the script from their local Linux environment and is presented with a clean interactive project menu.
2. **Project Selection:** Select the target project from the centralized registry of managed applications (with instant exit available at any step).
3. **Operation Mode:** Choose between two bidirectional actions:
   - **Pull:** Download the current live state from the remote VPS or hosting environment to the local machine to work on up-to-date files and datasets.
   - **Push:** Deploy the updated local codebase to the remote production server.
4. **Smart Incremental Sync:** During transfer, unnecessary directories (`node_modules`, `.git`, temporary caches, and user upload folders) are automatically excluded, ensuring fast, clean, and bandwidth-efficient delta transfers.
5. **Automated Service Restart:** Upon completing a push, remote application processes are automatically reloaded/restarted to apply changes immediately with near-zero downtime.
6. **Guided Local Versioning:** The operator is prompted for a brief changelog message; if none is entered within a few seconds, an automatic timestamped commit is applied so version history never breaks.
7. **Production Ready:** The remote VPS/hosting application is aligned, services are live, and changes are committed locally—all in one atomic workflow with zero intermediate manual steps.

## Key Features & Operational Benefits (ROI)

- **Single-Command Deployment:** Reduces multi-minute manual release routines to a few seconds of wall-clock time.
- **Centralized Multi-App Management:** One local control point for all applications and subdomains hosted across remote VPS and hosting servers.
- **Zero Upload Errors:** Automated exclusion rules and pre-deploy checks prevent accidental overwrites and partial transfers.
- **Fault-Tolerant Pipeline:** Every step validates its exit status; on critical errors, execution aborts safely with no half-restarted services or orphan commits.
- **Automated Service Reloads:** Post-deploy hooks bring updated applications back online immediately.
- **Built-in Local Versioning:** Automatic local Git repository initialization where missing, paired with guided or timed auto-commits for a complete audit trail.
- **Asynchronous Single-Operator Leverage:** Engineered to minimize human intervention and free up engineering capacity for high-value tasks.

**Concrete ROI:** For a developer or agency performing even 5–10 releases per day, time saved and deployment incidents avoided translate into hours recovered every week and dramatically higher production stability.

## Technologies Used (High Level)

- **Linux Bash Scripting:** Strategic choice for native speed, portability, and zero external runtime dependencies across any Linux workstation.
- **Rsync:** Industry-standard incremental file synchronization engine with fast, verified delta transfers.
- **Git:** Universal local version control ensuring complete change traceability.
- **PM2:** Production process manager for controlled zero/low-downtime application reloads on remote VPS environments.
- **SSH:** Encrypted transport layer securing all remote synchronization and command execution operations.

## Confidentiality Notice & B2B Inquiries

🔒 **Proprietary Software Asset (All Rights Reserved):** This repository serves as a functional and architectural showcase within the Professional Portfolio ([https://antoniangeloflore.com](https://antoniangeloflore.com) — *Italian portal & technical video demos; full English B2B communication and delivery*). For operational security and NDA compliance, the source code and server mapping configurations are not publicly exposed.

🤝 **Custom Automation & White-Label Licensing:** Available for custom deployment pipelines, Linux/VPS infrastructure automation, and asynchronous technical consulting (zero-call workflow). Connect via [antoniangeloflore.com](https://antoniangeloflore.com) or [LinkedIn](https://www.linkedin.com/in/antoniangelo-f-30003622/).

---

<a name="-italiano"></a>
## 🇮🇹 ITALIANO

# Sync-Manager — Orchestratore Locale di Deploy e Sincronizzazione Multi-App (VPS & Hosting)

## Panoramica del Prodotto

**Sync-Manager** è uno strumento di automazione pensato per sviluppatori, agenzie digitali e team operativi che gestiscono più applicazioni web in produzione. Operando **esclusivamente in locale** sulla workstation Linux dell'operatore, permette di aggiornare e allineare tutti i progetti software ospitati su **server VPS o piani Hosting remoti in pochi secondi e con un solo comando**, eliminando definitivamente gli errori manuali di caricamento.

È la soluzione ideale per chi gestisce un portafoglio di progetti (SaaS, dashboard, connettori) e ha bisogno di un flusso di rilascio rapido, ripetibile e a prova di errore umano.

## Il Problema Risolto

Nel lavoro quotidiano di uno sviluppatore o di un'agenzia, il deploy manuale di un progetto è una delle attività più lente e rischiose:

- **Perdita di tempo:** copiare file a mano, aprire client FTP, ripetere le stesse operazioni per ogni progetto.
- **Errori manuali:** caricare file incompleti, dimenticare cartelle di configurazione, sovrascrivere risorse sbagliate.
- **Colli di bottiglia operativi:** ogni rilascio richiede attenzione costante e intervento umano, anche per una modifica di una singola riga.
- **Downtime prolungato:** se il servizio non viene riavviato correttamente dopo l'aggiornamento, gli utenti subiscono interruzioni evitabili.
- **Tracciabilità assente:** senza versionamento coerente, è difficile sapere cosa è stato pubblicato, quando e perché.

**Sync-Manager** azzera questi rischi: un'unica procedura guidata gestisce sincronizzazione, riavvio dei servizi e registrazione delle modifiche, in modo tollerante ai guasti (se una fase fallisce, la pipeline si blocca in sicurezza senza lasciare il sistema in uno stato incoerente).

## Come Funziona (Flusso Operativo Utente)

L'utilizzo è pensato per essere immediato, senza configurazioni ripetitive:

1. **Avvio dello strumento:** l'operatore lancia lo script dal proprio ambiente locale e si presenta un menu di selezione chiaro.
2. **Scelta del progetto:** dall'elenco dei progetti gestiti (su VPS o Hosting) si seleziona quello su cui operare (è possibile uscire in qualsiasi momento).
3. **Scelta dell'operazione:** si sceglie tra:
   - **Pull:** scaricare la versione attuale dal server di produzione verso l'ambiente locale, per lavorare sui dati e sui file più recenti.
   - **Push:** inviare la versione locale aggiornata verso il server di produzione.
4. **Sincronizzazione intelligente:** durante il trasferimento vengono automaticamente escluse le cartelle non necessarie (dipendenze, repository di versione, file temporanei e upload degli utenti), garantendo trasferimenti rapidi e puliti.
5. **Riavvio automatico dei servizi:** al termine del push, i servizi applicativi in produzione vengono riavviati automaticamente per rendere subito operative le modifiche, riducendo il downtime al minimo.
6. **Versioning locale guidato:** viene chiesta una breve descrizione delle modifiche; se non viene inserita entro pochi secondi, viene applicato un auto-commit con descrizione standard, così la cronologia delle versioni non si interrompe mai.
7. **Risultato finale:** il progetto in produzione è allineato, il servizio è operativo e le modifiche sono tracciate localmente. Tutto in un unico flusso, senza passaggi manuali intermedi.

## Funzionalità Principali & Vantaggi Operativi (ROI)

- **Deploy con un solo comando:** da minuti di operazioni manuali a pochi secondi di tempo effettivo.
- **Gestione multi-progetto:** un unico punto di controllo locale per tutti i progetti e sottodomini gestiti su VPS e Hosting, con mappatura centralizzata facilmente scalabile.
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

## Nota di Riservatezza & Collaborazioni B2B

🔒 **Asset Software Proprietario (Tutti i diritti riservati):** Questo repository ha finalità di presentazione funzionale per il Portfolio Professionale ([https://antoniangeloflore.com](https://antoniangeloflore.com)). Per ragioni di sicurezza operativa e accordi di riservatezza (NDA), il codice sorgente e le specifiche infrastrutturali non sono esposti pubblicamente.

🤝 **Automazioni Custom & Licensing White-Label:** Disponibile per pipeline di deploy su misura, automazione infrastrutturale Linux/VPS e consulenze tecniche asincrone (zero call). Contatti su [antoniangeloflore.com](https://antoniangeloflore.com) o su [LinkedIn](https://www.linkedin.com/in/antoniangelo-f-30003622/).
