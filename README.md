# Chest Counter

Programma per Windows che conta le casse aperte in Fortnite leggendo i file di replay delle partite. Mostra totali, medie e andamento nel tempo, con filtri per periodo e modalità.

Non è affiliato né approvato da Epic Games. Fortnite è un marchio di Epic Games.

## Download

Ultima versione: [ChestCounter-Setup.exe](https://github.com/LorenzoLT22/chest-counter-fortnite/releases/latest/download/ChestCounter-Setup.exe) (circa 32 MB).

Serve Windows 10 o 11 a 64 bit. Non servono permessi di amministratore né altri programmi: il .NET è già incluso.

## Installazione

1. Scarica ed esegui `ChestCounter-Setup.exe`.
2. Windows può mostrare la schermata "Windows ha protetto il PC", perché il programma non ha una firma digitale a pagamento. Clicca su "Ulteriori informazioni" e poi su "Esegui comunque".
3. Segui la procedura, che dura pochi secondi. Al termine il programma si apre da solo.

Durante l'installazione puoi scegliere se creare un'icona sul desktop e se eliminare il file di installazione una volta finito.

## Primo utilizzo

Chest Counter non legge il gioco mentre giochi: analizza i replay che Fortnite salva a fine partita. Perché funzioni, la registrazione dei replay deve essere attiva nelle impostazioni di Fortnite. I file si trovano in `%LOCALAPPDATA%\FortniteGame\Saved\Demos`.

Alla prima apertura il programma chiede se contare anche i replay già presenti sul PC. Conviene rispondere di sì, perché Fortnite può eliminare i replay più vecchi. Da quel momento le nuove partite vengono aggiunte da sole, e non serve tenere il programma aperto mentre giochi: le partite non ancora contate vengono analizzate alla prossima apertura.

## Cosa mostra

La finestra riporta il totale delle casse, il numero di partite, le casse aperte a mano e quelle distrutte, la media e la mediana per partita, il record, le casse al minuto e l'andamento giorno per giorno. Ogni partita ha il suo dettaglio, con il minuto e il tipo di ogni cassa. Si può filtrare per periodo, modalità, squadra e durata minima, e i dati si possono esportare in CSV.

## Come vengono contate le casse

Vengono contate le casse aperte dal giocatore che ha registrato il replay, sia a mano sia distrutte di colpo senza aprirle. Non vengono contate le casse di munizioni e di frutta, le casse già aperte e poi distrutte, quelle aperte da altri giocatori e quelle della caccia al tesoro.

Le casse fisse, normali e rare, si possono includere o escludere con un'apposita opzione. Un simbolo di avviso accanto al totale di una partita indica che il conteggio potrebbe non essere affidabile, per esempio zero casse in una partita lunga.

Il conteggio è stato controllato su partite reali con un numero di casse noto, ma dipende dal formato dei replay. Fortnite può cambiarlo con gli aggiornamenti: dopo una nuova stagione i numeri potrebbero risultare sbagliati finché non esce una versione adeguata.

## Aggiornamenti

All'avvio e poi ogni sei ore il programma controlla se in questo repository c'è una versione più recente. In caso positivo mostra un avviso in alto con il pulsante "Aggiorna ora": scarica il nuovo file, ne verifica la firma digitale e si riavvia. Non installa nulla senza il tuo consenso, e la versione precedente resta nella cartella di installazione come `ChestCounter.previous.exe`.

## Dati e disinstallazione

Le partite contate e le impostazioni sono salvate in `%APPDATA%\ChestCounter`.

Per disinstallare apri le impostazioni di Windows, vai su App, poi App installate, e rimuovi Chest Counter. Alla fine la procedura chiede se cancellare anche i dati.

## Privacy e sicurezza

Il programma legge soltanto i file di replay e salva i risultati sul tuo PC. Non legge la memoria del gioco, non modifica file di Fortnite e non invia dati a nessuno. L'unica connessione a internet serve a controllare e scaricare gli aggiornamenti da questo repository.

Epic Games dichiara di non poter dire se un software di terze parti comporti sanzioni all'account. Chest Counter lavora solo su file già salvati e non interagisce con il gioco in esecuzione, ma l'uso resta a tuo rischio.

## Problemi comuni

**Windows mostra un avviso all'avvio del Setup.** Succede perché il file non è firmato con un certificato a pagamento. Vedi il punto 2 dell'installazione.

**L'antivirus segnala il Setup.** Anche questo dipende dalla mancanza della firma. Se il Setup viene bloccato, prova a ripetere l'installazione togliendo la spunta a "Elimina questo file di installazione al termine", che è l'opzione più facile da scambiare per un comportamento sospetto.

**Il programma non trova i replay.** Controlla che la registrazione sia attiva in Fortnite e che esista la cartella indicata sopra. Se i replay sono altrove, avvia il programma da un terminale con `ChestCounter.exe --demos "percorso\della\cartella"`.

**Una partita risulta a zero casse o con il simbolo di avviso.** Apri la partita dall'elenco: il dettaglio indica il motivo e mostra eventuali altri tipi di contenitore presenti nel replay.

## Segnalare un problema

Apri una segnalazione nella sezione Issues indicando la versione del programma (si legge in alto, accanto al titolo), cosa ti aspettavi e cosa è successo. Se esiste, allega il file `errors.log` dalla cartella dei dati. Non pubblicare i file di replay, perché contengono i nomi dei giocatori.

## Crediti

La lettura dei replay usa [FortniteReplayDecompressor](https://github.com/Shiqan/FortniteReplayDecompressor) di Shiqan, distribuito con licenza MIT.
