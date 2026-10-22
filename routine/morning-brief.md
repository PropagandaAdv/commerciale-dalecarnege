Genera il brief mattutino di Giovanni Bertoni in italiano. Questa è un'esecuzione automatica (nessuno presente per rispondere a domande), quindi non usare AskUserQuestion: produci direttamente il testo del brief in chat, in italiano.

Fonti da usare (tutte già collegate):
1. Google Calendar — calendario "info@propagandaadv.com" (fuso Europe/Rome). Recupera gli eventi di oggi (00:00-24:00 locali). Per ogni evento con videocall (Google Meet), controlla se l'evento ha allegati o link nella descrizione a trascrizioni/note della riunione (Google Docs generati da Meet/Gemini) e, se presenti/accessibili, leggile per capire cosa è stato discusso.
2. Gmail — account g.bertoni@propagandaadv.com (è la mailbox da cui leggere per il brief). Cerca in:inbox degli ultimi 3-4 giorni e individua le email a cui Giovanni deve ancora rispondere: qualcuno gli ha fatto una domanda diretta o segnalato un problema e non risulta una risposta successiva sua nello stesso thread. Ignora newsletter, notifiche LinkedIn, promozioni, alert automatici non azionabili. Cerca anche eventuali email "Note della riunione" / Gemini notes ricevute di recente per gli stessi contatti/aziende dei meeting di oggi, e usale per arricchire la preparazione (vedi sotto).
3. Calendly (utente registrato come info@giovannibertoni.com, slug info-43026 — è l'account aziendale di Propaganda Adv, l'email di login è solo storica) — appuntamenti commerciali di oggi ("Presentazione per Sito Web", "Discovery call" e simili). Per ogni appuntamento recupera anche invitato, email, eventuali guest, e le risposte alle domande del modulo di prenotazione (sono la fonte principale per il "motivo del contatto"). Se il connettore Calendly risulta disconnesso, salta questa sezione e segnalalo in una riga nel brief, senza bloccare il resto.
4. ClickUp — utente "Giovanni Bertoni" (id 54058090, email info@propagandaadv.com). Recupera tutte le sue task aperte (clickup_filter_tasks, assignees=["54058090"], include_closed=false) e classificale per data di scadenza rispetto a oggi: in ritardo, in scadenza oggi, in scadenza domani, prossimi 7 giorni, senza scadenza. Nota: il campo priority non è quasi mai impostato, quindi l'urgenza va stimata dalla scadenza e dal contenuto (es. "Sollecito telefonico" è tipicamente time-sensitive). Se un task ha un list_id che corrisponde a uno Space cliente (usa clickup_get_workspace_hierarchy per la mappa Space→List se serve), indicalo.
5. GitHub — repository PropagandaAdv/commerciale-dalecarnege (usa il branch predefinito, senza specificare ref). Contiene la skill "prepara-prospect", che è l'UNICA fonte del metodo per preparare i prospect. Leggi con get_file_contents questi file, solo se oggi c'è almeno una prima call con un prospect:
   - agenzia.md (servizi, USP aziendale e personale, casi studio, testimonianze reali dell'agenzia)
   - plugins/prepara-prospect/skills/prepara-prospect/SKILL.md
   - plugins/prepara-prospect/skills/prepara-prospect/references/modalita-brief.md
   - plugins/prepara-prospect/skills/prepara-prospect/references/metodo-carnegie.md
   - plugins/prepara-prospect/skills/prepara-prospect/references/ricerca.md
   - plugins/prepara-prospect/skills/prepara-prospect/references/dossier-template.md
   Se agenzia.md contiene segnaposto [DA COMPILARE]/[INSERIRE CASO REALE] o manca una sezione (es. casi studio), NON inventare casi studio né numeri: segnalalo in una riga nel brief.

Per ogni meeting di oggi con un CLIENTE esistente (ha uno Space dedicato in ClickUp): prepara un breve riassunto di preparazione incrociando lo storico task ClickUp del progetto, le email recenti pertinenti, e — se disponibile — la trascrizione/nota dell'ultima videocall con lo stesso cliente (da Calendar o dalle email "Note della riunione"/Gemini) per ricordare cosa era stato deciso o promesso.

Per ogni meeting di OGGI che è una PRIMA CALL CON UN PROSPECT (es. eventi Calendly "Presentazione per Sito Web", "Discovery call" o simili con un'azienda che NON ha ancora uno Space ClickUp dedicato): applica la skill "prepara-prospect" in MODALITÀ BRIEF, seguendo i file letti da GitHub (SKILL.md, modalita-brief.md e i riferimenti da lì richiamati). Il dossier va scritto direttamente nel brief, in una sezione "Prep prospect: {Nome azienda} — {orario}", una per ogni prima call di oggi. Non creare file e non fare domande.

Regole inderogabili anche se i file della skill non sono raggiungibili:
- Etichetta ogni fatto sul prospect: [VERIFICATO] + URL fonte; [INFERENZA] + ragionamento; [DA VERIFICARE IN CALL] per ipotesi.
- Non inventare mai numeri (fatturato, dipendenti, clienti, risultati): se non lo trovi scrivi "non reperito". Non inventare casi studio dell'agenzia.
- Niente critiche al prospect: i limiti sono opportunità. Apprezzamenti specifici.
- L'apertura della call è una domanda aperta sul mondo del cliente, ancorata a un fatto verificato (affermazione di credibilità).
- Se un sito o una piattaforma non è raggiungibile, dichiaralo invece di riempire il vuoto.
Se i file della skill su GitHub non sono accessibili, dillo in una riga nel brief e prepara comunque una sezione ridotta per ogni prospect: cosa fa l'azienda, sito e settore, fatturato stimato da Partita IVA (ufficiocamerale.it, reportaziende.it, opencorporates), una domanda di apertura e 2-3 miglioramenti concreti per il sito.

Per le prime call con prospect dei PROSSIMI 7 GIORNI (non oggi): non fare il dossier completo, solo una riga-scheda lampo per ciascuna (data/ora, azienda, sito, aderenza ICP provvisoria, motivo del contatto dal modulo Calendly) in una sezione "Radar prossime call", così Giovanni sa cosa gli arriva.

Struttura del brief:
- Calendario di oggi con orari, e per ogni meeting la nota di preparazione (cliente esistente: riassunto breve; prospect: sezione "Prep prospect" completa come sopra), arricchita con eventuali trascrizioni/note di call precedenti quando disponibili.
- Appuntamenti Calendly di oggi (o nota che il connettore è disconnesso), più "Radar prossime call" per i nuovi appuntamenti commerciali dei prossimi 7 giorni.
- Task ClickUp: in ritardo, in scadenza oggi/domani, prossimi 7 giorni, cenno al numero di task senza scadenza.
- Email a cui rispondere: elenco con mittente, oggetto, cosa chiedono, da quanti giorni è aperta.
- Nuove task ClickUp: per ogni email azionabile che richiede un follow-up, CREA direttamente la task (clickup_create_task) nel progetto/lista ClickUp del cliente corrispondente (in Commerciale - Propaganda se non è un cliente con Space dedicato), assegnata a Giovanni Bertoni (id 54058090). REGOLA FISSA E NON NEGOZIABILE: ogni task creata, senza eccezioni, deve avere due_date impostato alla data odierna (la data in cui gira questo task schedulato, formato YYYY-MM-DD) — mai una data futura, mai nessuna data. Nel brief elenca le task appena create con link.

Dopo aver scritto il brief in chat, crea ANCHE una bozza email (tool create_draft sull'account Gmail collegato) indirizzata a g.bertoni@propagandaadv.com, oggetto "Brief mattutino - {data di oggi}", con lo stesso identico contenuto del brief (incluse le sezioni prep cliente/prospect) in formato testo semplice. Nota: create_draft crea solo una bozza, non invia l'email — questo è l'unico comportamento disponibile con il connettore Gmail collegato, quindi non provare a inviarla, si ferma alla bozza.

Non inviare messaggi/email reali, non modificare calendario, non modificare questo task schedulato.
