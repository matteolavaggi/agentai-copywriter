# Framework AI per la gestione del Personal Brand

Questo manuale spiega come costruire un sistema semplice e replicabile per gestire il tuo personal brand e produrre contenuti in modo efficiente usando l'intelligenza artificiale.

Il metodo si basa su tre principi: struttura chiara, istruzioni persistenti e automazione della scrittura. Il risultato è un ecosistema dove l'AI conosce già il tuo posizionamento, il tuo tono di voce e le regole dei tuoi contenuti, e può produrre materiale coerente senza dover rispiegare tutto ogni volta.

Questa soluzione è completamente gratuita e sostituisce abbonamenti mensili a tool di copywriting e content creation come Jasper, Copy.ai o Writesonic. Con il vantaggio che i risultati sono migliori: l'AI lavora con il tuo contesto completo, non con template generici.

➡️ Approfondimento completo: [matteolavaggi.it/agentai-copywriter](https://www.matteolavaggi.it/agentai-copywriter)

## Il problema che risolve

Quando usi ChatGPT, Claude o altri chatbot per creare contenuti, devi fornire ogni volta il contesto: chi sei, come scrivi, a chi parli, che formato vuoi. Questo genera tre problemi concreti:

Il primo è la perdita di tempo. Ogni sessione parte da zero, e devi reinserire le stesse informazioni.

Il secondo è l'incoerenza. Senza istruzioni fisse, i contenuti variano nel tono e nello stile da una sessione all'altra.

Il terzo è la frammentazione. I contenuti restano sparsi tra chat diverse, senza versioning e senza una struttura che li organizzi.

Questo framework elimina tutti e tre i problemi.

## Strumenti necessari

Per applicare il metodo servono tre strumenti, tutti gratuiti o con versione gratuita sufficiente:

**Google Docs** serve per scrivere e mantenere aggiornato il documento madre del tuo personal brand. È comodo perché puoi accedervi ovunque e condividerlo facilmente.

**Visual Studio Code con GitHub Copilot** è l'ambiente dove lavori. Copilot legge le istruzioni che hai impostato e genera contenuti già allineati al tuo brand. L'editor ti permette di modificare solo le parti necessarie, senza riscrivere tutto.

**Git** gestisce il versioning. Ogni modifica viene tracciata, puoi tornare indietro, confrontare versioni e mantenere uno storico completo di tutto ciò che produci.

## Come funziona il sistema

Il flusso operativo è lineare:

Scrivi il tuo personal brand in Google Docs, organizzato in sezioni chiare. Poi esporti ogni sezione in formato Markdown e la salvi come file di istruzioni nella cartella del progetto. Copilot legge questi file automaticamente ogni volta che lavori, quindi l'AI parte già con tutto il contesto necessario. Quando crei un contenuto, lo salvi nella cartella giusta del repository. Git traccia ogni modifica.

In pratica, l'AI diventa un assistente che conosce già tutto di te e del tuo brand.

## Struttura del documento Personal Brand

Il documento madre in Google Docs si compone di sei sezioni, ognuna con una funzione specifica:

**Identità e posizionamento** contiene chi sei, cosa fai, per chi lo fai, qual è la tua promessa implicita e come vuoi essere percepito.

**Tono di voce e stile** definisce come scrivi: frasi lunghe o corte, formale o diretto, tecnico o accessibile. Include esempi concreti di frasi che useresti e frasi che eviteresti.

**Call to action** elenca le CTA standard da usare nei contenuti, già scritte e pronte. Così non devi inventarle ogni volta e mantieni coerenza.

**Hashtag** raggruppa gli hashtag per categoria, pronti da copiare nei post social.

**Linee guida Markdown** spiega le regole di formattazione: un solo H1, niente linee orizzontali, niente emoji nei titoli, niente TAB per indentare.

**Piano Editoriale** descrive i tipi di contenuto che produci, la frequenza, i formati, i canali e la funzione di ogni formato nel tuo funnel.

## Come configurare i file di istruzioni

Una volta scritto il documento in Google Docs, devi trasformarlo in file che Copilot possa leggere.

Crea una cartella `.github/instructions` nella root del tuo progetto. All'interno, salva ogni sezione come file `.instructions.md`. Per esempio:

```
.github/instructions/
├── chi-sono.instructions.md
├── cta.instructions.md
├── hashtag.instructions.md
├── linee-guida-markdown.instructions.md
├── linee-guida-articoli.instructions.md
├── ped.instructions.md
└── personal-brand.instructions.md
```

Ogni file deve iniziare con un frontmatter che indica quando applicarlo:

```yaml
---
applyTo: '**'
---
```

Il valore `'**'` significa che le istruzioni si applicano a tutti i file. Puoi restringere a `'**.md'` se vuoi che valgano solo per i Markdown.

## Come creare un agente specializzato

Copilot permette di creare agenti con competenze specifiche. Per la produzione di contenuti, è utile creare un agente Writer che abbia solo gli strumenti di testo e nessuno strumento di programmazione.

Crea il file `.github/agents/Writer.agent.md` e definisci:

Le capacità: leggere documenti, creare file markdown, modificare testi esistenti, fare ricerche nel workspace.

Le limitazioni: niente script, niente terminal, niente debug, niente git da linea di comando.

Le istruzioni: quali file leggere prima di ogni operazione.

In questo modo, quando attivi l'agente Writer, Copilot lavora esclusivamente come copywriter, seguendo le tue regole.

## Struttura delle cartelle del progetto

Organizza il repository in cartelle per tipo di contenuto:

```
Draft/          → bozze e documenti di lavoro
Guide/          → guide e manuali
Posts/          → post per social
Shorts - Reels/ → script per contenuti brevi
Video/          → script e materiali per video lunghi
```

Questa struttura ti permette di tenere insieme, per ogni contenuto, il file sorgente, lo script, i sottotitoli e le descrizioni. Tutto versionato e tutto in un unico posto.

## Vantaggi concreti del metodo

**Editing preciso.** Copilot modifica solo le parti che servono. Non devi riscrivere tutto il documento come faresti con un chatbot.

**Contesto persistente.** Le istruzioni vengono lette automaticamente. L'AI parte già allineata al tuo brand.

**Formattazione conservata.** Il Markdown si copia e incolla senza perdere la struttura, sia verso Google Docs che verso altri editor.

**Versioning completo.** Git traccia ogni modifica. Puoi vedere cosa hai cambiato, quando e perché.

**Storage unificato.** File sorgente, esportati, script e descrizioni stanno tutti nella stessa directory, organizzati per progetto.

**Zero costi ricorrenti.** A differenza delle app di copywriting che richiedono abbonamenti mensili da 30 a 100 euro, questo sistema usa strumenti gratuiti. L'unico costo eventuale è l'abbonamento a GitHub Copilot, che però usi anche per altre attività.

**Risultati migliori.** Le app di content creation lavorano con prompt generici e template standard. Questo sistema lavora con il tuo contesto completo: posizionamento, tono di voce, CTA, piano editoriale. Il risultato è un contenuto che rispecchia davvero il tuo brand, non un testo generico da adattare.

## Come ottenere il progetto

Puoi ottenere il progetto completo in due modi:

**Clonando il repository da GitHub**

```bash
git clone https://github.com/matteolavaggi/agentai-copywriter
```

**Scaricando il file zip**

Se preferisci non usare Git, puoi scaricare direttamente l'archivio completo da questo link: [Download progetto completo](https://drive.google.com/file/d/10L5PAo1ri9W5bZ4hJ-6BVQEiGzNNfd0s/view?usp=sharing)

Una volta scaricato, estrai il contenuto e aprilo con VS Code.

## Come iniziare

Il primo passo è scrivere il tuo personal brand in Google Docs. Non deve essere perfetto: può evolvere nel tempo. L'importante è che contenga le informazioni essenziali su chi sei, come comunichi e cosa produci.

Il secondo passo è esportare ogni sezione in Markdown e salvarla nella cartella `.github/instructions`.

Il terzo passo è creare la struttura delle cartelle per i tuoi contenuti.

Il quarto passo è inizializzare un repository Git e fare il primo commit.

Da quel momento, ogni volta che apri VS Code e attivi Copilot, l'AI legge le tue istruzioni e può iniziare a produrre contenuti coerenti con il tuo brand.

## Considerazioni finali

Questo sistema non è magia. È un metodo per ridurre il lavoro ripetitivo e mantenere coerenza nella comunicazione.

Funziona perché separa la definizione del brand dalla produzione dei contenuti. Prima definisci le regole una volta sola, poi le applichi automaticamente a tutto ciò che crei.

Il tempo che investi nella configurazione iniziale lo recuperi ogni volta che produci un contenuto senza dover rispiegare chi sei e come scrivi.

È un sistema che scala: più contenuti produci, più il vantaggio diventa evidente.

Se vuoi approfondire il metodo o vedere come applicarlo al tuo caso, trovi tutto su ➡️ [matteolavaggi.it/agentai-copywriter](https://www.matteolavaggi.it/agentai-copywriter)

## Esempi

Nella cartella Shorts - Reeel trovi un esempio di progetto "openai.fm.md" e "openai.fm.mp4". Qusti sono il file video + audio (generato da llm) con sottotitoli e il file che contiene la descrizione del post instagram da pubblicare.