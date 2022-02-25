# Introduction
:label:`chap_introduction`

Fino a poco tempo fa, quasi ogni programma per computer 
con il quale si sarebbe potuto interagire in un giorno qualsiasi
era codificato come un rigido insieme di regole 
che specificava precisamente come doveva comportarsi.
Supponiamo volessimo scrivere un'applicazione 
per gestire una piattaforma di e-commerce.
Dopo esserci riuniti intorno ad una lavagna
per qualche ora a riflettere sul problema,
potremmo trovare, a grandi linee,
una soluzione funzionante, per esempio:
(i) gli utenti interagiscono con l'applicazione attraverso un'interfaccia
che gira in un browser web o in un'applicazione mobile;
(ii) la nostra applicazione interagisce con un database commerciale
per tenere traccia dello stato di ogni utente e mantenere le registrazioni
delle transazioni storiche; 
e (iii) nel cuore della nostra applicazione,
la *logica di business* (si potrebbe dire, il *cervello*) 
definisce in maniera metodica un insieme di regole che mappano ogni 
circostanza concepibile all'azione corrispondente
che il nostro programma dovrebbe intraprendere.

Per costruire il cervello della nostra applicazione,
potremmo enumerare tutti gli eventi comuni
che il nostro programma dovrebbe gestire.
Per esempio, ogni volta che un cliente clicca 
per aggiungere un articolo al suo carrello,
il nostro programma dovrebbe aggiungere una voce 
alla tabella del database del carrello della spesa,
associando l'ID dell'utente 
con l'ID del prodotto richiesto.
Potremmo poi tentare di passare attraverso 
ogni possibile caso limite,
testando l'adeguatezza delle nostre regole
e apportando le modifiche necessarie.
Cosa succede se un utente 
inizia un acquisto con un carrello vuoto? 
Anche se qualche sviluppatore ci riesce
completamente bene la prima volta
(potrebbero essere necessari alcuni test per risolvere i problemi),
in generale, possiamo scrivere tali programmi 
e lanciarli con fiducia 
*prima* di vedere un vero cliente.
La nostra capacità di progettare manualmente sistemi automatizzati
che guidano prodotti e sistemi funzionanti, 
spesso in situazioni nuove,
è un'impresa cognitiva notevole.
E quando si è in grado di concepire soluzioni 
che funzionano il 100 % delle volte,
in genere non ci si dovrebbe 
preoccuparsi del machine learning.

Fortunatamente per la crescente comunità 
di scienziati dell'apprendimento automatico,
molti compiti che vorremmo automatizzare
non si piegano così facilmente all'**ingegnosità umana**.
Immaginate di riunirvi intorno alla lavagna 
con le menti più intelligenti che conoscete,
ma questa volta state affrontando 
uno dei seguenti problemi:

* Scrivere un programma che preveda il meteo di domani, date informazioni geografiche, immagini satellitari e una finestra di tempo passata.
* Scrivere un programma che prenda una domanda semplice, espressa in testo libero, e risponda correttamente.
* Scrivere un programma che, data un'immagine, identifichi tutte le persone in essa raffigurate e ne disegni i contorni.
* Scrivete un programma che presenti agli utenti dei prodotti che probabilmente gli piaceranno ma che difficilmente incontreranno nel corso naturale della navigazione.

Per questi problemi,
anche i programmatori d'élite farebbero fatica
a scrivere da zero delle soluzioni.
Le ragioni possono variare. 
A volte il programma che stiamo cercando 
segue un modello che cambia nel tempo,
quindi non c'è sempre una risposta giusta! 
In questi casi, qualsiasi soluzione di successo 
deve adattarsi graziosamente ad un mondo che cambia. 
Altre volte, la relazione (ad esempio tra pixel,
e categorie astratte) può essere troppo complicata,
richiedendo migliaia o milioni di calcoli
e seguendo principi sconosciuti. 
Come nel riconoscimento delle immagini, 
i passi per eseguire un compito
spesso si trovano al di là della nostra comprensione coscente,
anche quando i nostri processi cognitivi subconsci 
possono eseguire il compito con facilità. 


*L'apprendimento automatico* (Machine Learning) è lo studio degli algoritmi
che possono imparare dall'esperienza.
Quanto più un algoritmo di apprendimento automatico accumula esperienza,
tipicamente sotto forma di dati di osservazione 
o interazioni con un ambiente, 
tanto più le sue prestazioni migliorano.
Questo è in contrasto con la nostra piattaforma deterministica di e-commerce
che segue la stessa logica di business, 
indipendentemente da quanta esperienza maturi, 
finché gli sviluppatori stessi non decidono
che è il momento di aggiornare il software.
In questo libro vi insegneremo 
i fondamenti dell'apprendimento automatico,
concentrandosi in particolare sul *apprendimento profondo* (deep learning) , 
un potente insieme di tecniche
che guida le innovazioni in aree diverse come la visione artificiale (computer vision),
l'elaborazione del linguaggio naturale (natural language processing), la sanità (healthcare) e la genomica (genomics).

## Un esempio stimolante

Prima di iniziare a scrivere, gli autori di questo libro,
come gran parte della forza lavoro, dovevano diventare caffeinomani.
Siamo saliti in macchina e abbiamo iniziato a guidare.
Usando un iPhone, Alex ha chiamato "Hey Siri",
risvegliando il sistema di riconoscimento vocale del telefono.
Poi Mu ha detto "indicazioni per la caffetteria Blue Bottle".
Il telefono ha mostrato rapidamente la trascrizione del suo comando.
Ha anche riconosciuto che stavamo chiedendo indicazioni
e ha lanciato l'applicazione Maps
per soddisfare la nostra richiesta.
Una volta lanciata, l'applicazione Mappe ha identificato una serie di percorsi.
Accanto ad ogni percorso, il telefono ha visualizzato un tempo di percorrenza previsto.
Anche se abbiamo inventato questa storia per comodità pedagogica,
ciò dimostra che nell'arco di pochi secondi,
le nostre interazioni quotidiane con uno smartphone
possono coinvolgere diversi modelli di apprendimento automatico.


Immaginate di scrivere un programma che risponda ad una *parola chiave*
come "Alexa", "OK Google" e "Hey Siri".
Provate a programmarlo in una stanza da soli
con nient'altro che un computer e un editor di codice,
come illustrato in :numref:`fig_wake_word`.
Come fareste a scrivere un programma del genere partendo dai zero?
Pensateci... il problema è difficile.
Ogni secondo, il microfono raccoglierà circa 
44000 campioni.
Ogni campione è una misura dell'ampiezza dell'onda sonora.
Quale regola potrebbe mappare in modo affidabile un frammento di audio grezzo in previsioni sicure 
$\{\text{yes}, \text{no}\}$
sul fatto che il frammento contenga o meno la "parola chiave"?
Se siete bloccati, non preoccupatevi.
Neanche noi sappiamo come scrivere un programma del genere da zero.
Ecco perché usiamo il machine learning.

![Identify a wake word.](../img/wake-word.svg)
:label:`fig_wake_word`


Ecco il trucco.
Spesso, anche quando non sappiamo come dire ad un computer
esplicitamente come mappare dagli input in output,
siamo comunque in grado di eseguire noi stessi l'impresa cognitiva.
In altre parole, anche se non si sa
come programmare un computer per riconoscere la parola "Alexa",
voi stessi siete in grado di riconoscerla.
Armati di questa capacità, possiamo raccogliere un enorme *dataset*
contenente esempi di audio 
ed etichettare quelli che contengono
e che non contengono la "parola chiave".
Nell'approccio di apprendimento automatico, 
non cerchiamo di progettare un sistema
*in modo esplicito* per riconoscere le parole di veglia.
Piuttosto, definiamo un programma flessibile
il cui comportamento è determinato da una serie di *parametri*.
Poi usiamo il set di dati per determinare il miglior set di parametri possibile, 
cioè quelli che migliorano le prestazioni del nostro programma
rispetto a qualche misura di performance sul compito di interesse.

Potete pensare ai parametri come a delle manopole che possiamo girare,
manipolando il comportamento del programma.
Fissando i parametri, chiamiamo il programma un *modello*.
L'insieme di tutti i programmi distinti (mappature input-output)
che possiamo produrre solo manipolando i parametri
si chiama una *famiglia* di modelli.
E il metaprogramma che usa il nostro set di dati
per scegliere i parametri si chiama *algoritmo di apprendimento*.

Prima di andare avanti e impegnare l'algoritmo di apprendimento,
dobbiamo definire il problema con precisione,
stabilendo l'esatta natura degli input e degli output,
e scegliere una famiglia di modelli appropriata.
In questo caso, 
il nostro modello riceve un frammento di audio come *input*,
e il modello 
genera una selezione tra 
come *output*.
Se tutto va secondo i piani 
le ipotesi del modello saranno
tipicamente corrette per quanto riguarda 
se il frammento contiene la parola di scia.

Se scegliamo la giusta famiglia di modelli,
dovrebbe esistere un'impostazione delle manopole
tale che il modello spari "sì" ogni volta che sente la parola "Alexa".
Poiché la scelta esatta della parola di sveglia è arbitraria,
avremo probabilmente bisogno di una famiglia di modelli sufficientemente ricca che,
attraverso un'altra impostazione delle manopole, potrebbe sparare "sì"
solo dopo aver sentito la parola "Apricot".
Ci aspettiamo che la stessa famiglia di modelli sia adatta
per il riconoscimento "Alexa" e il riconoscimento "Apricot
perché sembrano, intuitivamente, essere compiti simili.
Tuttavia, potremmo aver bisogno di una famiglia di modelli completamente diversa
se vogliamo trattare con input o output fondamentalmente diversi,
ad esempio se volessimo mappare da immagini a didascalie,
o da frasi inglesi a frasi cinesi.

Come si può intuire, se impostiamo tutte le manopole in modo casuale,
è improbabile che il nostro modello riconosca "Alexa",
"Apricot", o qualsiasi altra parola inglese.
Nell'apprendimento automatico, 
l'*apprendimento* è il processo
con cui scopriamo la giusta impostazione delle manopole
costringendo il comportamento desiderato dal nostro modello.
In altre parole,
noi *addestriamo* il nostro modello con i dati.
Come mostrato in :numref:`fig_ml_loop`, il processo di allenamento di solito assomiglia al seguente:

1. Iniziare con un modello inizializzato a caso che non può fare nulla di utile.
2. Prendete alcuni dei vostri dati (ad esempio, frammenti audio e le corrispondenti etichette ${testo{sì}, \testo{no}}$).
3. Modificate le manopole in modo che il modello faccia meno schifo rispetto a quegli esempi.
4. Ripetere i passi 2 e 3 fino a quando il modello è fantastico.

![A typical training process.](../img/ml-loop.svg)
:label:`fig_ml_loop`

Per riassumere, piuttosto che codificare un riconoscitore di parole di scia,
mettiamo in codice un programma che può *imparare* a riconoscere le parole di veglia,
se gli presentiamo un grande set di dati etichettati.
Si può pensare a questo atto di determinare il comportamento di un programma
presentandogli un set di dati come *programmazione con i dati*.
Vale a dire,
possiamo "programmare" un rilevatore di gatti fornendo al nostro sistema di apprendimento automatico
con molti esempi di cani e gatti.
In questo modo il rilevatore alla fine imparerà ad emettere un numero positivo molto grande se si tratta di un gatto, un numero negativo molto grande se si tratta di un cane,
e qualcosa di più vicino allo zero se non è sicuro,
e questo graffia appena la superficie di ciò che l'apprendimento automatico può fare.
Apprendimento profondo,
che spiegheremo in dettaglio più avanti,
è solo uno dei molti metodi popolari
per risolvere problemi di apprendimento automatico.

## Componenti chiave

Nel nostro esempio di parole della scia, abbiamo descritto un set di dati
composto da frammenti audio ed etichette binarie, 
e abbiamo
abbiamo dato un'idea di come potremmo addestrare
un modello per approssimare una mappatura dagli snippet alle classificazioni.
Questo tipo di problema, 
in cui cerchiamo di predire un'etichetta sconosciuta designata
sulla base di input noti
dato un set di dati composto da esempi
per i quali le etichette sono note, 
è chiamato *apprendimento supervisionato*.
Questo è solo uno dei tanti tipi di problemi di apprendimento automatico.
Più avanti faremo un'immersione profonda in diversi problemi di apprendimento automatico.
Prima, vorremmo fare più luce su alcuni componenti fondamentali
che ci seguiranno, indipendentemente dal tipo di problema di apprendimento automatico che affrontiamo:

1. I *dati* da cui possiamo imparare.
1. Un *modello* di come trasformare i dati.
1. Una *funzione oggettiva* che quantifica quanto bene (o male) sta facendo il modello.
1. Un *algoritmo* per regolare i parametri del modello per ottimizzare la funzione obiettivo.

### Dati

Non c'è bisogno di dire che non si può fare scienza dei dati senza dati.
Potremmo perdere centinaia di pagine a riflettere su ciò che costituisce precisamente i dati,
ma per ora, sbaglieremo sul lato pratico
e ci concentreremo sulle proprietà chiave di cui preoccuparsi.
In generale, ci preoccupiamo di una collezione di esempi.
Per lavorare utilmente con i dati, 
tipicamente
bisogno di trovare una rappresentazione numerica adatta.
Ogni *esempio* (o *punto dati*, *istanza dati*, *campione*) consiste tipicamente in un insieme
di attributi chiamati *caratteristiche* (o *covariate*),
da cui il modello deve fare le sue previsioni.
Nei problemi di apprendimento supervisionato di cui sopra,
la cosa da predire
è un attributo speciale 
che è designato come
la *etichetta* (o *obiettivo*).


Se stessimo lavorando con dati di immagini,
ogni singola fotografia potrebbe costituire un esempio,
ciascuna rappresentata da una lista ordinata di valori numerici
corrispondenti alla luminosità di ogni pixel.
Una fotografia a colori da 200$ per 200$ consisterebbe in 200$ per 200$ per 3$ per 120000$
valori numerici, corrispondenti alla luminosità
dei canali rosso, verde e blu per ogni posizione spaziale.
In un altro compito tradizionale, potremmo cercare di prevedere
se un paziente sopravviverà o meno,
dato un insieme standard di caratteristiche come
età, segni vitali e diagnosi.

Quando ogni esempio è caratterizzato dallo stesso numero di valori numerici,
diciamo che i dati consistono in vettori di lunghezza fissa
e descriviamo la lunghezza costante dei vettori
come la *dimensionalità* dei dati.
Come potete immaginare, la lunghezza fissa può essere una proprietà conveniente.
Se volessimo addestrare un modello per riconoscere il cancro nelle immagini di microscopia,
gli input a lunghezza fissa significano che abbiamo una cosa in meno di cui preoccuparci.

Tuttavia, non tutti i dati possono essere facilmente rappresentati come 
*vettori di lunghezza fissa*.
Mentre potremmo aspettarci che le immagini del microscopio provengano da apparecchiature standard,
non possiamo aspettarci che le immagini estratte da Internet
si presentino tutte con la stessa risoluzione o forma.
Per le immagini, potremmo considerare di ritagliarle tutte ad una dimensione standard,
ma questa strategia ci porta solo fino a un certo punto.
Rischiamo di perdere informazioni nelle porzioni ritagliate.
Inoltre, i dati di testo resistono ancora più ostinatamente alle rappresentazioni a lunghezza fissa.
Consideriamo le recensioni dei clienti lasciate sui siti di e-commerce
come Amazon, IMDB e TripAdvisor.
Alcune sono brevi: "fa schifo! 
Altre divagano per pagine.
Uno dei principali vantaggi dell'apprendimento profondo rispetto ai metodi tradizionali
è la grazia comparativa con cui i modelli moderni
possono gestire dati di lunghezza variabile.

In generale, più dati abbiamo, più facile diventa il nostro lavoro.
Quando abbiamo più dati, possiamo addestrare modelli più potenti
e fare meno affidamento su ipotesi preconcette.
Il cambio di regime dai (relativamente) piccoli ai grandi dati
è uno dei principali fattori che contribuiscono al successo del moderno deep learning.
Per portare a casa il punto, molti dei modelli più eccitanti nell'apprendimento profondo non funzionano senza grandi set di dati.
Alcuni altri funzionano nel regime dei piccoli dati,
ma non sono migliori degli approcci tradizionali.

Infine, non è sufficiente avere molti dati ed elaborarli in modo intelligente.
Abbiamo bisogno dei dati *giusti*. 
Se i dati sono pieni di errori,
o se le caratteristiche scelte non sono predittive
della quantità target di interesse, 
l'apprendimento fallirà.
La situazione è catturata bene dal cliché:
*garbage in, garbage out*.
Inoltre, la scarsa performance predittiva non è l'unica conseguenza potenziale.
In applicazioni sensibili di apprendimento automatico,
come la polizia predittiva, lo screening dei curriculum, e i modelli di rischio usati per i prestiti,
dobbiamo essere particolarmente attenti alle conseguenze dei dati spazzatura.
Una modalità comune di fallimento si verifica in serie di dati in cui alcuni gruppi di persone
non sono rappresentati nei dati di formazione.
Immaginate di applicare un sistema di riconoscimento del cancro della pelle in natura
che non ha mai visto pelle nera prima.
Il fallimento può verificarsi anche quando i dati
non si limitano a sottorappresentare alcuni gruppi
ma riflettono i pregiudizi della società.
Per esempio, 
se le decisioni di assunzione passate vengono utilizzate per addestrare un modello predittivo
che sarà usato per vagliare i curriculum,
allora i modelli di apprendimento automatico potrebbero inavvertitamente
catturare e automatizzare le ingiustizie storiche.
Si noti che tutto questo può accadere senza che lo scienziato dei dati
senza che lo scienziato dei dati cospiri attivamente o sia consapevole.


Modelli ###

La maggior parte del machine learning implica la trasformazione dei dati in un certo senso.
Potremmo voler costruire un sistema che ingerisce le foto e predice il sorriso.
In alternativa,
potremmo voler ingerire una serie di letture di sensori
e prevedere quanto siano normali o anomale le letture.
Con *modello*, indichiamo il macchinario computazionale per ingerire dati
di un tipo, 
e sputare fuori previsioni di un tipo possibilmente diverso.
In particolare, siamo interessati a modelli statistici
che possono essere stimati dai dati.
Mentre i modelli semplici sono perfettamente in grado di affrontare
problemi adeguatamente semplici,
i problemi
su cui ci concentriamo in questo libro estendono i limiti dei metodi classici.
L'apprendimento profondo si differenzia dagli approcci classici
principalmente dall'insieme di potenti modelli su cui si concentra.
Questi modelli consistono in molte trasformazioni successive dei dati
che sono concatenate da cima a fondo, da cui il nome *apprendimento profondo*.
Nel nostro modo di discutere i modelli profondi,
discuteremo anche alcuni metodi più tradizionali.

Funzioni obiettivo ###

Prima abbiamo introdotto l'apprendimento automatico come apprendimento dall'esperienza.
Con *apprendimento* qui,
intendiamo migliorare in qualche compito nel tempo.
Ma chi può dire cosa costituisce un miglioramento?
Potreste immaginare che potremmo proporre di aggiornare il nostro modello,
e alcune persone potrebbero essere in disaccordo sul fatto che l'aggiornamento proposto
costituisca un miglioramento o un declino.

Per sviluppare un sistema matematico formale di apprendimento delle macchine,
dobbiamo avere misure formali di quanto siano buoni (o cattivi) i nostri modelli.
Nell'apprendimento automatico, e nell'ottimizzazione più in generale,
chiamiamo queste *funzioni obiettivo*.
Per convenzione, di solito definiamo le funzioni obiettivo
in modo che più basso è meglio.
Questa è semplicemente una convenzione. 
Si può prendere qualsiasi funzione
per la quale il più alto è migliore, e trasformarla in una nuova funzione
che è qualitativamente identica, ma per la quale è migliore quella inferiore
invertendo il segno.
Poiché minore è migliore, queste funzioni sono talvolta chiamate
*funzioni di perdita*.

Quando si cerca di prevedere valori numerici,
la funzione di perdita più comune è *l'errore quadratico*,
cioè il quadrato della differenza tra la predizione e la verità.
Per la classificazione, l'obiettivo più comune è quello di minimizzare il tasso di errore,
cioè la frazione di esempi su cui le nostre
le nostre previsioni sono in disaccordo con la verità di base.
Alcuni obiettivi (ad esempio, l'errore al quadrato) sono facili da ottimizzare.
Altri (ad esempio, il tasso di errore) sono difficili da ottimizzare direttamente,
a causa della non differenziabilità o altre complicazioni.
In questi casi, è comune ottimizzare un *obiettivo surrogato*.

Tipicamente, la funzione di perdita è definita
rispetto ai parametri del modello
e dipende dal set di dati.
Impariamo
i migliori valori dei parametri del nostro modello
minimizzando la perdita subita su un set
costituito da un certo numero di esempi raccolti per l'addestramento.
Tuttavia, fare bene sui dati di addestramento
non garantisce che faremo bene anche sui dati non visti.
Quindi tipicamente vogliamo dividere i dati disponibili in due partizioni:
il *set di dati di addestramento* (o *set di addestramento*, per l'adattamento dei parametri del modello)
e l'*insieme di dati di prova* (o *insieme di prova*, che è tenuto fuori per la valutazione),
riportando come il modello si comporta su entrambi.
Si potrebbe pensare alla performance di allenamento come a
i punteggi di uno studente agli esami di pratica
usati per preparare un vero esame finale.
Anche se i risultati sono incoraggianti,
questo non garantisce il successo nell'esame finale.
In altre parole,
la performance del test può deviare significativamente dalla performance dell'allenamento. 
Quando un modello si comporta bene sul set di allenamento
ma non riesce a generalizzare ai dati non visti,
diciamo che è *overfitting*.
In termini di vita reale, questo è come essere bocciati all'esame reale
nonostante sia andato bene negli esami di pratica.


### Algoritmi di ottimizzazione

Una volta che abbiamo una fonte di dati e una rappresentazione,
un modello e una funzione obiettivo ben definita,
abbiamo bisogno di un algoritmo capace di cercare
i migliori parametri possibili per minimizzare la funzione di perdita.
Gli algoritmi di ottimizzazione popolari per l'apprendimento profondo
si basano su un approccio chiamato *gradient descent*.
In breve, ad ogni passo, questo metodo 
controlla per vedere, per ogni parametro,
da che parte si muoverebbe la perdita del set di allenamento
se si perturba quel parametro solo di poco.
Quindi aggiorna
il parametro nella direzione che potrebbe ridurre la perdita.

## Tipi di problemi di apprendimento automatico

Il problema della parola scia nel nostro esempio motivante
è solo uno dei tanti problemi
problemi che l'apprendimento automatico può affrontare.
Per motivare ulteriormente il lettore
e fornirci un linguaggio comune quando parleremo di altri problemi nel corso del libro,
di seguito noi 
elenchiamo un campione di problemi di apprendimento automatico.
Faremo costantemente riferimento a
ai nostri concetti sopra menzionati 
come dati, modelli e tecniche di addestramento.

### Apprendimento supervisionato

L'apprendimento supervisionato affronta il compito di
predire le etichette date le caratteristiche di input.
Ogni coppia caratteristica-etichetta è chiamata esempio.
A volte, quando il contesto è chiaro, possiamo usare il termine *esempi*
per riferirsi ad una collezione di input,
anche quando le etichette corrispondenti sono sconosciute.
Il nostro obiettivo è produrre un modello
che mappi qualsiasi input a una predizione di etichetta.


Per radicare questa descrizione in un esempio concreto,
se stessimo lavorando nel settore sanitario,
potremmo voler predire se un paziente
un paziente avrebbe un attacco di cuore.
Questa osservazione, "attacco di cuore" o "nessun attacco di cuore",
sarebbe la nostra etichetta.
Le caratteristiche di input potrebbero essere i segni vitali
come la frequenza cardiaca, la pressione sanguigna diastolica 
e la pressione sanguigna sistolica.

La supervisione entra in gioco perché per scegliere i parametri, noi (i supervisori) forniamo al modello un dataset
composto da esempi etichettati,
dove ogni esempio è abbinato all'etichetta di verità.
In termini probabilistici, siamo tipicamente interessati a stimare
la probabilità condizionata di un'etichetta date le caratteristiche di input.
Sebbene sia solo uno dei tanti paradigmi dell'apprendimento automatico,
l'apprendimento supervisionato rappresenta la maggior parte delle applicazioni
applicazioni di successo dell'apprendimento automatico nell'industria.
In parte, questo è dovuto al fatto che molti compiti importanti
possono essere descritti in modo chiaro come la stima della probabilità
di qualcosa di sconosciuto dato un particolare insieme di dati disponibili:

* Predire il cancro vs. non cancro, data un'immagine di tomografia computerizzata.
* Prevedere la traduzione corretta in francese, data una frase in inglese.
* Prevedere il prezzo di un'azione il mese prossimo sulla base dei dati finanziari di questo mese.

Anche con la semplice descrizione
"predire le etichette date le caratteristiche di input"
l'apprendimento supervisionato può assumere molte forme
e richiedere un gran numero di decisioni di modellazione,
a seconda (tra le altre considerazioni) del tipo, della dimensione,
e il numero di input e output.
Per esempio, usiamo diversi modelli per elaborare sequenze di lunghezza arbitraria
e per elaborare rappresentazioni vettoriali di lunghezza fissa.
Visiteremo molti di questi problemi in profondità
nel corso di questo libro.

Informalmente, il processo di apprendimento assomiglia a quanto segue.
Per prima cosa, prendiamo una grande collezione di esempi per i quali le caratteristiche sono note
e selezioniamo da essi un sottoinsieme casuale,
acquisendo le etichette di verità per ognuno di essi.
A volte queste etichette potrebbero essere dati disponibili che sono già stati raccolti
(ad esempio, un paziente è morto entro l'anno successivo?)
e altre volte potremmo aver bisogno di impiegare annotatori umani per etichettare i dati,
(ad esempio, assegnando le immagini alle categorie).
Insieme, questi input e le etichette corrispondenti costituiscono il set di allenamento.
Alimentiamo il set di dati di allenamento in un algoritmo di apprendimento supervisionato,
una funzione che prende come input un set di dati
e produce un'altra funzione: il modello appreso.
Infine, possiamo dare in pasto al modello appreso degli input non visti in precedenza,
usando i suoi output come previsioni dell'etichetta corrispondente.
Il processo completo è disegnato in :numref:`fig_supervised_learning`.

apprendimento supervisionato](../img/supervised-learning.svg)
:label:`fig_supervised_learning`

#### Regressione

Forse il compito di apprendimento supervisionato più semplice
da comprendere è la *regressione*.
Consideriamo, per esempio, un insieme di dati raccolti
da un database di vendite di case.
Potremmo costruire una tabella, 
dove ogni riga corrisponde ad una casa diversa,
e ogni colonna corrisponde a qualche attributo rilevante,
come la metratura di una casa, 
il numero di camere da letto, il numero di bagni e il numero di minuti (a piedi) dal centro della città.
In questo set di dati, ogni esempio sarebbe una casa specifica,
e il corrispondente vettore di caratteristiche sarebbe una riga della tabella.
Se vivi a New York o San Francisco,
e non sei l'amministratore delegato di Amazon, Google, Microsoft o Facebook,
il (metri quadri, numero di camere da letto, numero di bagni, distanza a piedi)
per la vostra casa potrebbe apparire qualcosa come: $[600, 1, 1, 60]$.
Tuttavia, se vivete a Pittsburgh, potrebbe essere più simile a $[3000, 4, 3, 10]$.
Vettori di caratteristiche come questo sono essenziali
per la maggior parte degli algoritmi classici di apprendimento automatico.

Ciò che rende un problema una regressione è in realtà l'output.
Diciamo che siete sul mercato per una nuova casa.
Potreste voler stimare il valore di mercato di una casa,
date alcune caratteristiche come sopra.
L'etichetta, il prezzo di vendita, è un valore numerico.
Quando le etichette assumono valori numerici arbitrari,
lo chiamiamo un problema di *regressione*.
Il nostro obiettivo è produrre un modello le cui previsioni
si avvicinano molto ai valori reali dell'etichetta.


Molti problemi pratici sono problemi di regressione ben descritti.
Prevedere la valutazione che un utente assegnerà ad un film
può essere pensato come un problema di regressione
e se avete progettato un grande algoritmo per compiere questa impresa nel 2009,
avreste potuto vincere il [premio Netflix da 1 milione di dollari](https://en.wikipedia.org/wiki/Netflix_Prize).
Prevedere la durata della permanenza dei pazienti in ospedale
è anche un problema di regressione.
Una buona regola pratica è che qualsiasi problema *quanto?* o *quanto?*
dovrebbe suggerire la regressione,
come ad esempio:

* Quante ore ci vorranno per questo intervento?
* Quanta pioggia ci sarà in questa città nelle prossime sei ore?


Anche se non avete mai lavorato prima con il machine learning,
probabilmente avete lavorato in modo informale su un problema di regressione.
Immaginate, per esempio, che abbiate fatto riparare i vostri scarichi
e che il vostro appaltatore abbia passato 3 ore
a rimuovere la sporcizia dai vostri tubi di scarico.
Poi ti ha mandato una fattura di 350 dollari.
Ora immaginate che il vostro amico abbia assunto lo stesso appaltatore per 2 ore
e che abbia ricevuto una fattura di 250 dollari.
Se qualcuno vi chiedesse poi quanto aspettarsi
sulla sua prossima fattura per la rimozione del gasolio
potreste fare alcune ipotesi ragionevoli,
come ad esempio che più ore lavorate costano più dollari.
Si potrebbe anche supporre che ci sia un costo di base
e che l'appaltatore si faccia pagare all'ora.
Se queste ipotesi fossero vere, allora, dati questi due esempi di dati,
si potrebbe già identificare la struttura dei prezzi dell'appaltatore:
100 dollari all'ora più 50 dollari per presentarsi a casa vostra.
Se avete seguito tutto ciò, allora avete già capito
l'idea di alto livello dietro la regressione lineare.

In questo caso, potremmo produrre i parametri
che corrispondono esattamente ai prezzi dell'appaltatore.
A volte questo non è possibile, 
per esempio, se una parte della
della varianza è dovuta a qualche fattore 
oltre alle due caratteristiche.
In questi casi, cercheremo di imparare modelli
che minimizzano la distanza tra le nostre previsioni e i valori osservati.
Nella maggior parte dei nostri capitoli, ci concentreremo su 
minimizzare la funzione di perdita dell'errore quadratico.
Come vedremo più avanti, questa perdita corrisponde all'ipotesi
che i nostri dati siano corrotti da rumore gaussiano.

#### Classificazione

Mentre i modelli di regressione sono ottimi per affrontare le domande *quante?*,
molti problemi non si piegano comodamente a questo modello.
Per esempio,
una banca vuole aggiungere la scansione degli assegni alla sua applicazione mobile.
Questo comporterebbe che il cliente scatti una foto di un assegno
con la fotocamera del loro smartphone
e l'app dovrebbe essere in grado di
capire automaticamente il testo visto nell'immagine.
In particolare,
dovrebbe anche capire il testo scritto a mano per essere ancora più robusto,
come la mappatura di un carattere scritto a mano
a uno dei caratteri noti.
Questo tipo di problema *quale?* è chiamato *classificazione*.
Viene trattato con un diverso insieme di algoritmi
rispetto a quelli usati per la regressione, anche se molte tecniche si ripeteranno.

Nella *classificazione*, vogliamo che il nostro modello guardi le caratteristiche,
ad esempio, i valori dei pixel in un'immagine,
e poi predica quale *categoria* (formalmente chiamata *classe*),
tra un insieme discreto di opzioni, un esempio appartiene.
Per le cifre scritte a mano, potremmo avere dieci classi,
corrispondenti alle cifre da 0 a 9.
La forma più semplice di classificazione è quando ci sono solo due classi,
un problema che chiamiamo *classificazione binaria*.
Per esempio, il nostro set di dati potrebbe consistere in immagini di animali
e le nostre etichette potrebbero essere le classi $\mathrm{cat, dog\}}$.
Mentre nella regressione, cerchiamo un regressore che produca un valore numerico,
nella classificazione, cerchiamo un classificatore, il cui output è l'assegnazione della classe prevista.

Per ragioni che approfondiremo man mano che il libro diventa più tecnico,
può essere difficile ottimizzare un modello che può produrre solo
un'assegnazione categorica rigida, 
per esempio, o "gatto" o "cane".
In questi casi, di solito è molto più facile esprimere invece
il nostro modello nel linguaggio delle probabilità.
Date le caratteristiche di un esempio, 
il nostro modello assegna una probabilità
ad ogni possibile classe. 
Tornando al nostro esempio di classificazione degli animali
dove le classi sono $mathrm{ gatto, cane}},
un classificatore potrebbe vedere un'immagine e produrre la probabilità
che l'immagine sia un gatto come 0,9.
Possiamo interpretare questo numero dicendo che il classificatore
è sicuro al 90 % che l'immagine raffiguri un gatto.
La grandezza della probabilità per la classe predetta
trasmette una nozione di incertezza.
Non è l'unica nozione di incertezza
e ne discuteremo altre in capitoli più avanzati.

Quando abbiamo più di due classi possibili,
chiamiamo il problema *classificazione a più classi*.
Esempi comuni includono il riconoscimento dei caratteri scritti a mano
0, 1, 2, ... 9, a, b, c, ...\}}$.
Mentre abbiamo attaccato i problemi di regressione cercando
di minimizzare la funzione di perdita dell'errore quadratico,
la funzione di perdita comune per i problemi di classificazione si chiama *entropia incrociata*,
il cui nome può essere demistificato 
attraverso un'introduzione alla teoria dell'informazione nei capitoli successivi. 

Notate che la classe più probabile non è necessariamente
quello che userete per la vostra decisione.
Supponiamo che troviate un bel fungo nel vostro giardino
come mostrato in :numref:`fig_death_cap`.

![Death cap--non mangiare!](../img/death-cap.jpg)
:width:`200px`
:label:`fig_death_cap`

Ora, supponiamo che tu abbia costruito un classificatore e l'abbia addestrato
per prevedere se un fungo è velenoso sulla base di una fotografia.
Diciamo che il nostro classificatore di rilevamento del veleno produca
che la probabilità che
:numref:`fig_death_cap` contiene un tappo mortale è 0,2.
In altre parole, il classificatore è sicuro all'80
che il nostro fungo non è un tappo mortale.
Tuttavia, dovreste essere pazzi a mangiarlo.
Questo perché il beneficio certo di una cena deliziosa
non vale il rischio del 20% di morirne.
In altre parole, l'effetto del rischio incerto
supera di gran lunga il beneficio.
Quindi, abbiamo bisogno di calcolare il rischio atteso in cui incorriamo come funzione di perdita,
cioè, dobbiamo moltiplicare la probabilità del risultato
con il beneficio (o danno) associato ad esso.
In questo caso,
la perdita subita mangiando il fungo
può essere pari a 0,2 volte \infty + 0,8 volte 0 = \infty$,
mentre la perdita di scartarlo è
0,2 $ per 0 + 0,8 $ per 1 = 0,8$.
La nostra cautela era giustificata:
come ci direbbe qualsiasi micologo,
il fungo in :numref:`fig_death_cap` in realtà
è un tappo mortale.

La classificazione può diventare molto più complicata di una semplice
classificazione binaria, multiclasse o anche multietichetta.
Per esempio, ci sono alcune varianti di classificazione
per affrontare le gerarchie.
Le gerarchie presuppongono che esistano alcune relazioni tra le varie classi.
Quindi non tutti gli errori sono uguali - se dobbiamo sbagliare, preferiamo
sbagliare la classificazione in una classe correlata piuttosto che in una classe lontana.
Di solito, ci si riferisce a questo come *classificazione gerarchica*.
Un primo esempio è dovuto a [Linneo](https://en.wikipedia.org/wiki/Carl_Linnaeus), che ha organizzato gli animali in una gerarchia.

Nel caso della classificazione degli animali,
potrebbe non essere così male confondere un barboncino (una razza di cane) con uno schnauzer (un'altra razza di cane),
ma il nostro modello pagherebbe una penalità enorme
se confondesse un barboncino per un dinosauro.
Quale gerarchia è rilevante potrebbe dipendere
da come pensate di usare il modello.
Per esempio, i serpenti a sonagli e i serpenti giarrettiera
potrebbero essere vicini sull'albero filogenetico,
ma scambiare un serpente a sonagli per una giarrettiera potrebbe essere mortale.

#### Tagging

Alcuni problemi di classificazione rientrano perfettamente
nei setup di classificazione binaria o multiclasse.
Per esempio, potremmo addestrare un normale classificatore binario
per distinguere i gatti dai cani.
Dato lo stato attuale della computer vision,
possiamo farlo facilmente, con strumenti standard.
Tuttavia, non importa quanto sia accurato il nostro modello,
potremmo trovarci nei guai quando il classificatore
incontra un'immagine dei *Musicisti della città di Brema*,
una popolare fiaba tedesca con quattro animali
in :numref:`fig_stackedanimals`.

Un asino, un cane, un gatto e un gallo.](../img/stackedanimals.png)
:width:`300px`
:label:`fig_stackedanimals`

Come puoi vedere, c'è un gatto in :numref:`fig_stackedanimals`,
e un gallo, un cane e un asino,
con alcuni alberi sullo sfondo.
A seconda di cosa vogliamo fare con il nostro modello
alla fine, trattare questo come un problema di classificazione binaria
potrebbe non avere molto senso.
Invece, potremmo voler dare al modello la possibilità di
dire che l'immagine rappresenta un gatto, un cane, un asino,
*e* un gallo.

Il problema di imparare a predire classi che non si
non si escludono a vicenda è chiamato *classificazione multietichetta*.
I problemi di auto-tagging sono tipicamente descritti
come problemi di classificazione multietichetta.
Pensate ai tag che la gente potrebbe applicare ai post su un blog tecnico,
ad esempio, "apprendimento automatico", "tecnologia", "gadget",
"linguaggi di programmazione", "Linux", "cloud computing", "AWS".
Un tipico articolo potrebbe avere 5-10 tag applicati
perché questi concetti sono correlati.
I post sul "cloud computing" è probabile che menzionino "AWS"
e i post su "apprendimento automatico" potrebbero anche trattare
con "linguaggi di programmazione".

Abbiamo anche a che fare con questo tipo di problema quando si tratta
con la letteratura biomedica, dove è importante etichettare correttamente gli articoli
perché permette ai ricercatori di fare revisioni esaustive della letteratura.
Alla National Library of Medicine, un certo numero di annotatori professionisti
esaminano ogni articolo che viene indicizzato in PubMed
per associarlo ai termini rilevanti di MeSH,
una collezione di circa 28000 tag.
Questo è un processo che richiede tempo e gli
annotatori in genere hanno un ritardo di un anno tra l'archiviazione e l'assegnazione dei tag.
L'apprendimento automatico può essere usato qui per fornire tag provvisori
fino a quando ogni articolo può avere un'adeguata revisione manuale.
Infatti, per diversi anni, l'organizzazione BioASQ
ha [ospitato concorsi](http://bioasq.org/) per fare proprio questo.

#### Ricerca 

A volte non vogliamo semplicemente assegnare ogni esempio ad un secchio
o ad un valore reale. Nel campo dell'information retrieval,
vogliamo imporre una classifica su un insieme di elementi.
Prendiamo ad esempio la ricerca sul web. 
L'obiettivo non è tanto determinare se
una particolare pagina è rilevante per una query, ma piuttosto,
quale tra la pletora di risultati di ricerca è
più rilevante
per un particolare utente.
Ci interessa davvero l'ordine dei risultati di ricerca rilevanti
e il nostro algoritmo di apprendimento deve produrre sottoinsiemi ordinati
di elementi da un insieme più ampio.
In altre parole, se ci viene chiesto di produrre le prime 5 lettere dell'alfabeto, c'è una differenza
tra restituire "A B C D E" e "C A B E D".
Anche se l'insieme dei risultati è lo stesso,
l'ordine all'interno dell'insieme conta.

Una possibile soluzione a questo problema è di assegnare prima
ad ogni elemento dell'insieme un punteggio di rilevanza corrispondente
e poi recuperare gli elementi con il punteggio più alto.
[PageRank](https://en.wikipedia.org/wiki/PageRank),
la salsa segreta originale dietro il motore di ricerca Google
era un primo esempio di un tale sistema di punteggio, ma era
peculiare in quanto non dipendeva dalla query effettiva.
Qui si basava su un semplice filtro di rilevanza
per identificare l'insieme di elementi rilevanti
e poi su PageRank per ordinare i risultati
che contenevano il termine della query.
Oggi, i motori di ricerca usano l'apprendimento automatico e modelli comportamentali
per ottenere punteggi di rilevanza dipendenti dalla query.
Ci sono intere conferenze accademiche dedicate a questo argomento.

#### Recommender Systems
:label:`subsec_recommender_systems`

I sistemi di raccomandazione sono un'altra impostazione del problema
che è collegato alla ricerca e al ranking.
I problemi sono simili nella misura in cui l'obiettivo
è quello di visualizzare un insieme di elementi rilevanti per l'utente.
La differenza principale è l'enfasi su
*personalizzazione*
a specifici utenti nel contesto dei sistemi di raccomandazione.
Per esempio, per le raccomandazioni di film,
la pagina dei risultati per un fan della fantascienza
e la pagina dei risultati
per un conoscitore di commedie di Peter Sellers potrebbero differire significativamente.
Problemi simili si presentano in altre impostazioni di raccomandazione,
ad esempio, per i prodotti al dettaglio, la musica e la raccomandazione di notizie.

In alcuni casi, i clienti forniscono un feedback esplicito che comunica
quanto gli è piaciuto un particolare prodotto
(ad esempio, le valutazioni e le recensioni dei prodotti su Amazon, IMDb e Goodreads).
In altri casi, forniscono un feedback implicito,
per esempio, saltando i titoli di una playlist,
il che potrebbe indicare insoddisfazione, ma potrebbe semplicemente indicare
che la canzone era inappropriata nel contesto.
Nelle formulazioni più semplici, questi sistemi sono addestrati
per stimare un certo punteggio,
come una valutazione stimata
o la probabilità di acquisto,
dato un utente e un oggetto.

Dato un tale modello, 
per ogni dato utente,
potremmo recuperare l'insieme di oggetti con i maggiori punteggi,
che potrebbero poi essere raccomandati all'utente.
I sistemi di produzione sono considerevolmente più avanzati e prendono
l'attività dettagliata dell'utente e le caratteristiche degli oggetti
quando si calcolano tali punteggi. :numref:`fig_deeplearning_amazon` è un esempio
di apprendimento profondo dei libri raccomandati da Amazon sulla base di algoritmi di personalizzazione messi a punto per catturare le preferenze di una persona.

Libri di apprendimento profondo raccomandati da Amazon](../img/deeplearning-amazon.jpg)
:label:`fig_deeplearning_amazon`

Nonostante il loro enorme valore economico,
sistemi di raccomandazione
ingenuamente costruiti sulla base di modelli predittivi
soffrono di alcuni gravi difetti concettuali.
Per cominciare, osserviamo solo il feedback *censurato*:
gli utenti valutano preferenzialmente i film che sentono fortemente.
Per esempio, 
su una scala a cinque punti,
si potrebbe notare che gli articoli ricevono molti voti a cinque e una stella
ma che ci sono cospicuamente poche valutazioni a tre stelle.
Inoltre, le attuali abitudini di acquisto sono spesso un risultato
dell'algoritmo di raccomandazione attualmente in uso,
ma gli algoritmi di apprendimento non sempre tengono conto di questo dettaglio.
Così è possibile che si formino dei cicli di feedback
dove un sistema di raccomandazione spinge preferenzialmente un articolo
che viene poi considerato migliore (a causa dei maggiori acquisti)
e a sua volta viene raccomandato ancora più frequentemente.
Molti di questi problemi su come affrontare la censura,
incentivi e cicli di feedback, sono importanti domande di ricerca aperte.

#### Apprendimento delle sequenze

Finora abbiamo esaminato problemi in cui abbiamo
un certo numero fisso di input e produciamo un numero fisso di output.
Per esempio,
abbiamo considerato la previsione dei prezzi delle case da un insieme fisso di caratteristiche: metratura, numero di camere da letto,
numero di bagni, tempo di percorrenza a piedi fino al centro città.
Abbiamo anche discusso la mappatura da un'immagine (di dimensione fissa)
alle probabilità previste che appartenga a ciascuna
di un numero fisso di classi, o prendendo un ID utente e un ID prodotto,
e prevedendo una valutazione a stelle. In questi casi,
una volta che alimentiamo il nostro input a lunghezza fissa
nel modello per generare un output,
il modello dimentica immediatamente ciò che ha appena visto.

Questo potrebbe andare bene se i nostri input avessero veramente tutti le stesse dimensioni
e se gli input successivi non hanno veramente nulla a che fare l'uno con l'altro.
Ma come faremmo con i frammenti di video?
In questo caso, ogni frammento potrebbe consistere in un numero diverso di fotogrammi.
E la nostra ipotesi di cosa sta succedendo in ogni fotogramma potrebbe essere molto più forte
se teniamo conto dei fotogrammi precedenti o successivi.
Lo stesso vale per il linguaggio. Un popolare problema di deep learning
è la traduzione automatica: il compito di ingerire frasi
in una lingua di partenza e prevedere la loro traduzione in un'altra lingua.

Questi problemi si verificano anche in medicina.
Potremmo volere un modello per monitorare i pazienti nel reparto di terapia intensiva
e che emetta avvisi se il loro rischio di morte
nelle prossime 24 ore supera una certa soglia.
Sicuramente non vogliamo che questo modello butti via
tutto ciò che sa sulla storia del paziente ogni ora
e faccia le sue previsioni solo sulla base delle misurazioni più recenti.

Questi problemi sono tra le applicazioni più eccitanti dell'apprendimento automatico
e sono istanze di *apprendimento delle sequenze*.
Richiedono un modello per ingerire sequenze di input
o di emettere sequenze di output (o entrambi).
In particolare,
*l'apprendimento da sequenza a sequenza* considera problemi
in cui l'input e l'output sono entrambi sequenze di lunghezza variabile,
come la traduzione automatica e la trascrizione di testo dal parlato.
Mentre è impossibile considerare tutti i tipi di trasformazioni di sequenza,
vale la pena menzionare i seguenti casi speciali.

**Tagging e Parsing**. Si tratta di annotare una sequenza di testo con attributi.
In altre parole, il numero di ingressi e uscite è essenzialmente lo stesso.
Per esempio, potremmo voler sapere dove sono i verbi e i soggetti.
In alternativa, potremmo voler sapere quali parole sono le entità nominate.
In generale, l'obiettivo è quello di decomporre e annotare il testo sulla base di presupposti strutturali
e grammaticali per ottenere qualche annotazione.
Questo sembra più complesso di quanto sia in realtà.
Di seguito è riportato un esempio molto semplice di annotazione di una frase
con tag che indicano quali parole si riferiscono a entità nominate (etichettate come "Ent").

``testo
Tom cena a Washington con Sally
Ent - - - Ent - Ent
```


**Riconoscimento vocale automatico**. Con il riconoscimento vocale, la sequenza di input
è una registrazione audio di un oratore (mostrata in :numref:`fig_speech`), e l'output 
è la trascrizione testuale di ciò che l'oratore ha detto.
La sfida è che ci sono molti più frame audio
(il suono è tipicamente campionato a 8kHz o 16kHz)
rispetto al testo, cioè non c'è una corrispondenza 1:1 tra audio e testo,
poiché migliaia di campioni possono
corrispondere a una singola parola parlata.
Questi sono problemi di apprendimento da sequenza a sequenza in cui l'output è molto più breve dell'input.

![`-D-e-e-p- L-ea-r-ni-ng-` in una registrazione audio.](../img/speech.png)
:width:`700px`
:label:`fig_speech`.

**Text to Speech**. Questo è l'inverso del riconoscimento vocale automatico.
In altre parole, l'input è il testo
e l'output è un file audio.
In questo caso, l'output è molto più lungo dell'input.
Mentre è facile per gli umani riconoscere un cattivo file audio,
questo non è così banale per i computer.

**Traduzione automatica**. A differenza del caso del riconoscimento vocale, dove gli
input e output si presentano nello stesso ordine (dopo l'allineamento),
nella traduzione automatica, l'inversione dell'ordine può essere vitale.
In altre parole, mentre stiamo ancora convertendo una sequenza in un'altra,
né il numero di input e output né l'ordine
degli esempi di dati corrispondenti si presume che siano gli stessi.
Si consideri il seguente esempio illustrativo
della peculiare tendenza dei tedeschi
a mettere i verbi alla fine delle frasi.

``testo
Tedesco: Haben Sie sich schon dieses grossartige Lehrwerk angeschaut?
Inglese:          Hai già dato un'occhiata a questo eccellente tutorial?
Allineamento sbagliato:  Did you yourself already this excellent tutorial looked-at?
```


Molti problemi correlati si presentano in altri compiti di apprendimento.
Per esempio, determinare l'ordine in cui un utente
legge una pagina web è un problema di analisi del layout bidimensionale.
I problemi di dialogo presentano tutti i tipi di complicazioni aggiuntive,
dove determinare cosa dire dopo richiede di prendere in considerazione
la conoscenza del mondo reale e lo stato precedente della conversazione
attraverso lunghe distanze temporali.
Queste sono aree attive di ricerca.

### Apprendimento non supervisionato e auto-supervisionato

Tutti gli esempi finora erano relativi all'apprendimento supervisionato,
cioè situazioni in cui forniamo al modello un gigantesco set di dati
contenente sia le caratteristiche che i corrispondenti valori di etichetta.
Si potrebbe pensare all'apprendista supervisionato come se avesse
un lavoro estremamente specializzato e un capo estremamente banale.
Il capo sta sopra le tue spalle e ti dice esattamente cosa fare
in ogni situazione finché non imparate a mappare dalle situazioni alle azioni.
Lavorare per un tale capo sembra piuttosto noioso.
D'altra parte, è facile compiacere questo capo.
Basta riconoscere il modello il più rapidamente possibile
e imitare le sue azioni.

In modo completamente opposto, potrebbe essere frustrante
lavorare per un capo che non ha idea di cosa vuole che tu faccia.
Tuttavia, se hai intenzione di essere uno scienziato dei dati, è meglio che ti ci abitui.
Il capo potrebbe semplicemente passarvi un'enorme discarica di dati e dirvi di *farci un po' di scienza dei dati!*. 
Questo suona vago perché lo è.
Chiamiamo questa classe di problemi *apprendimento non supervisionato*,
e il tipo e il numero di domande che potremmo porre
è limitato solo dalla nostra creatività.
Ci occuperemo delle tecniche di apprendimento non supervisionato
nei capitoli successivi. 
Per stuzzicare l'appetito per ora,
descriviamo alcune delle seguenti domande che potreste fare.

* Possiamo trovare un piccolo numero di prototipi
che riassumono accuratamente i dati?
Dato un insieme di foto, possiamo raggrupparle in foto di paesaggi,
foto di cani, bambini, gatti e cime di montagna?
Allo stesso modo, dato un insieme di attività di navigazione degli utenti,
possiamo raggrupparli in utenti con comportamenti simili?
Questo problema è tipicamente noto come *clustering*.
* Possiamo trovare un piccolo numero di parametri
che catturino accuratamente le proprietà rilevanti dei dati?
Le traiettorie di una palla sono abbastanza ben descritte
dalla velocità, dal diametro e dalla massa della palla.
I sarti hanno sviluppato un piccolo numero di parametri
che descrivono abbastanza accuratamente la forma del corpo umano
allo scopo di adattare i vestiti.
Questi problemi sono chiamati *sottospazio di stima*.
Se la dipendenza è lineare, si parla di *analisi delle componenti principali*.
* Esiste una rappresentazione di oggetti (arbitrariamente strutturati)
nello spazio euclideo 
tale che le proprietà simboliche possano essere ben abbinate?
Questo può essere usato per descrivere entità e le loro relazioni,
come "Roma" $-$ "Italia" $+$ "Francia" $=$ "Parigi".
* Esiste una descrizione delle cause alla radice
di molti dei dati che osserviamo?
Per esempio, se abbiamo dati demografici
sui prezzi delle case, l'inquinamento, la criminalità, la posizione,
istruzione, e salari, possiamo scoprire
come sono correlati semplicemente basandoci sui dati empirici?
I campi che si occupano di *causalità* e *modelli grafici probabilistici* affrontano questo problema.
* Un altro importante ed eccitante sviluppo recente nell'apprendimento non supervisionato
è l'avvento delle *reti generative avversarie*.
Queste ci danno un modo procedurale per sintetizzare i dati,
anche complicati dati non strutturati come immagini e audio.
I meccanismi statistici sottostanti sono test
per verificare se i dati reali e quelli falsi sono gli stessi.

Come forma di apprendimento non supervisionato,
*apprendimento auto-supervisionato*
sfrutta i dati non etichettati 
per fornire una supervisione nell'addestramento,
come ad esempio
prevedendo una parte dei dati non etichettati
utilizzando altre parti.
Per il testo,
possiamo addestrare modelli 
a "riempire gli spazi vuoti"
prevedendo parole mascherate a caso
usando le parole circostanti (contesti)
in grandi corpora senza alcuno sforzo di etichettatura :cite:`Devlin.Chang.Lee.ea.2018`!
Per le immagini,
possiamo addestrare modelli
per dire la posizione relativa
tra due regioni ritagliate
della stessa immagine :cite:`Doersch.Gupta.Efros.2015`.
In questi due esempi di apprendimento auto-supervisionato,
l'addestramento di modelli per prevedere
le possibili parole e le posizioni relative
sono entrambi compiti di classificazione
(dall'apprendimento supervisionato).



### Interagire con un ambiente

Finora, non abbiamo discusso da dove i dati effettivamente
provengono,
o cosa succede effettivamente quando un modello di apprendimento automatico genera un output.
Questo perché l'apprendimento supervisionato e l'apprendimento non supervisionato
non affrontano queste questioni in modo molto sofisticato.
In entrambi i casi, prendiamo una grande quantità di dati in anticipo,
poi mettiamo in moto le nostre macchine di riconoscimento dei modelli
senza mai più interagire con l'ambiente.
Poiché tutto l'apprendimento avviene
dopo che l'algoritmo è disconnesso dall'ambiente,
questo è talvolta chiamato *apprendimento offline*.
Per l'apprendimento supervisionato,
il processo considerando la raccolta di dati da un ambiente assomiglia a :numref:`fig_data_collection`.

Raccolta di dati per l'apprendimento supervisionato da un ambiente](../img/data-collection.svg)
:label:`fig_data_collection`

Questa semplicità dell'apprendimento offline ha il suo fascino.
Il lato positivo è che
possiamo preoccuparci del riconoscimento dei modelli
in isolamento, senza alcuna distrazione da questi altri problemi.
Ma il lato negativo è che la formulazione del problema è piuttosto limitante.
Se siete più ambiziosi, o se siete cresciuti leggendo la serie dei Robot di Asimov,
allora potreste immaginare bot artificialmente intelligenti capaci
non solo di fare previsioni, ma anche 
di compiere azioni nel mondo.
Vogliamo pensare ad *agenti* intelligenti, non solo a modelli predittivi.
Questo significa che
dobbiamo pensare a scegliere *azioni*,
non solo a fare previsioni.
Inoltre, a differenza delle previsioni,
le azioni hanno un impatto effettivo sull'ambiente.
Se vogliamo addestrare un agente intelligente,
dobbiamo tenere conto del modo in cui le sue azioni potrebbero
avere un impatto sulle future osservazioni dell'agente.

Considerare l'interazione con un ambiente
apre tutta una serie di nuove domande di modellazione.
I seguenti sono solo alcuni esempi.

* L'ambiente ricorda cosa abbiamo fatto in precedenza?
* L'ambiente vuole aiutarci, per esempio un utente che legge un testo in un riconoscitore vocale?
* L'ambiente vuole batterci, ad esempio in un contesto conflittuale come il filtraggio dello spam (contro gli spammer) o un gioco (contro un avversario)?
* All'ambiente non interessa?
* L'ambiente ha dinamiche mutevoli? Per esempio, i dati futuri assomigliano sempre al passato o i modelli cambiano nel tempo, naturalmente o in risposta ai nostri strumenti automatici?

Quest'ultima domanda solleva il problema dello *spostamento della distribuzione*,
quando i dati di allenamento e quelli di test sono diversi.
È un problema che la maggior parte di noi ha sperimentato
quando si fanno esami scritti da un docente,
mentre i compiti erano stati composti dai suoi assistenti.
In seguito, descriveremo brevemente l'apprendimento per rinforzo,
un'impostazione che considera esplicitamente le interazioni con un ambiente.

### Apprendimento per rinforzo

Se siete interessati ad usare l'apprendimento automatico
per sviluppare un agente che interagisce con un ambiente
e compie azioni, allora probabilmente finirete per
concentrarsi sull'*apprendimento per rinforzo*.
Questo potrebbe includere applicazioni alla robotica,
ai sistemi di dialogo, 
e persino allo sviluppo di intelligenza artificiale (AI)
per i videogiochi.
*Apprendimento per rinforzo profondo*, che applica
l'apprendimento profondo ai problemi di apprendimento per rinforzo,
è cresciuto in popolarità.
La rivoluzionaria rete Q profonda che ha battuto gli umani ai giochi Atari usando solo l'input visivo,
e il programma AlphaGo che ha detronizzato il campione del mondo del gioco da tavolo Go sono due esempi importanti.

L'apprendimento per rinforzo fornisce una dichiarazione molto generale di un problema,
in cui un agente interagisce con un ambiente in una serie di passi temporali.
Ad ogni passo temporale, 
l'agente riceve qualche *osservazione* 
dall'ambiente e deve scegliere un'azione
che viene successivamente trasmessa all'ambiente
attraverso qualche meccanismo (a volte chiamato attuatore).
Infine, l'agente riceve una ricompensa dall'ambiente.
Questo processo è illustrato in :numref:`fig_rl-ambiente`.
L'agente riceve poi un'osservazione successiva,
e sceglie un'azione successiva, e così via.
Il comportamento di un agente di apprendimento per rinforzo è governato da una politica.
In breve, una *politica* è solo una funzione che mappa
dalle osservazioni dell'ambiente alle azioni.
L'obiettivo dell'apprendimento per rinforzo è di produrre una buona politica.

L'interazione tra l'apprendimento per rinforzo e un ambiente.](../img/rl-environment.svg)
:label:`fig_rl-ambiente`

E' difficile sopravvalutare la generalità della struttura dell'apprendimento per rinforzo.
Per esempio, possiamo presentare qualsiasi problema di apprendimento supervisionato come un problema di apprendimento con rinforzo.
Diciamo che abbiamo un problema di classificazione.
Potremmo creare un agente di apprendimento per rinforzo con un'azione corrispondente ad ogni classe.
Potremmo quindi creare un ambiente che dia una ricompensa
che era esattamente uguale alla funzione di perdita
del problema originale di apprendimento supervisionato.

Detto questo, l'apprendimento per rinforzo può anche affrontare molti problemi
che l'apprendimento supervisionato non può affrontare.
Per esempio, nell'apprendimento supervisionato ci aspettiamo sempre
che l'input di addestramento venga associato all'etichetta corretta.
Ma nell'apprendimento per rinforzo, non assumiamo che per ogni osservazione 
l'ambiente ci dica l'azione ottimale.
In generale, otteniamo solo una ricompensa.
Inoltre, l'ambiente può anche non dirci quali azioni hanno portato alla ricompensa.

Consideriamo per esempio il gioco degli scacchi.
L'unico vero segnale di ricompensa arriva alla fine del gioco
quando vinciamo, a cui potremmo assegnare una ricompensa di 1,
o quando perdiamo, a cui potremmo assegnare una ricompensa di -1.
Quindi chi impara il rinforzo deve affrontare il problema dell'*assegnazione dei crediti*:
determinare quali azioni accreditare o incolpare per un risultato.
Lo stesso vale per un impiegato che ottiene una promozione l'11 ottobre.
Quella promozione riflette probabilmente un gran numero
di azioni ben scelte nel corso dell'anno precedente.
Ottenere più promozioni in futuro richiede di capire
quali azioni lungo il percorso hanno portato alla promozione.

Chi impara con il rinforzo può anche avere a che fare
con il problema dell'osservabilità parziale.
Cioè, l'osservazione corrente potrebbe non
dire tutto sul suo stato attuale.
Supponiamo che un robot pulitore si trovi intrappolato
in uno dei tanti armadi identici di una casa.
Dedurre la posizione precisa (e quindi lo stato) del robot
potrebbe richiedere di considerare le sue precedenti osservazioni prima di entrare nell'armadio.

Infine, in ogni dato punto, gli apprendisti di rinforzo
potrebbero conoscere una buona politica,
ma potrebbero esserci molte altre politiche migliori
che l'agente non ha mai provato.
L'apprendista di rinforzo deve costantemente scegliere
se *sfruttare* la migliore strategia attualmente conosciuta come politica,
o *esplorare* lo spazio delle strategie,
potenzialmente rinunciando a qualche ricompensa a breve termine in cambio della conoscenza.

Il problema generale di apprendimento per rinforzo
è un'impostazione molto generale.
Le azioni influenzano le osservazioni successive.
Si osservano solo le ricompense corrispondenti alle azioni scelte.
L'ambiente può essere completamente o parzialmente osservato.
Tenere conto di tutta questa complessità in una volta sola può chiedere troppo ai ricercatori.
Inoltre, non tutti i problemi pratici presentano tutta questa complessità.
Di conseguenza, i ricercatori hanno studiato una serie di
casi speciali di problemi di apprendimento per rinforzo.

Quando l'ambiente è completamente osservato,
chiamiamo il problema di apprendimento per rinforzo un *processo decisionale di Markov*.
Quando lo stato non dipende dalle azioni precedenti,
chiamiamo il problema un *problema del bandito contestuale*.
Quando non c'è uno stato, ma solo un insieme di azioni disponibili
con ricompense inizialmente sconosciute, questo problema
è il classico *problema del bandito a più braccia*.

## Radici

Abbiamo appena esaminato
un piccolo sottoinsieme di problemi che il machine learning 
può affrontare.
Per una serie diversificata di problemi di apprendimento automatico,
l'apprendimento profondo fornisce potenti strumenti per risolverli.
Anche se molti metodi di apprendimento profondo
siano invenzioni recenti,
l'idea di base della programmazione con dati e reti neurali (nomi di molti modelli di apprendimento profondo)
è stata studiata per secoli.
Infatti,
gli esseri umani hanno avuto il desiderio di analizzare i dati
e di prevedere i risultati futuri per molto tempo
e gran parte delle scienze naturali ha le sue radici in questo.
Per esempio, la distribuzione di Bernoulli prende il nome da
[Jacob Bernoulli (1655--1705)](https://en.wikipedia.org/wiki/Jacob_Bernoulli), e la distribuzione Gaussiana fu scoperta
da [Carl Friedrich Gauss (1777--1855)](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss).
Egli inventò, per esempio, l'algoritmo dei minimi quadrati,
che è usato ancora oggi per innumerevoli problemi
dai calcoli assicurativi alla diagnostica medica.
Questi strumenti hanno dato origine a un approccio sperimentale
nelle scienze naturali--per esempio, la legge di Ohm
che mette in relazione corrente e tensione in un resistore
è perfettamente descritta da un modello lineare.

Anche nel Medioevo, i matematici avevano un'intuizione acuta delle stime.
Per esempio, il libro di geometria di [Jacob Köbel (1460--1533)](https://www.maa.org/press/periodicals/convergence/mathematical-treasures-jacob-kobels-geometry) illustra
la media della lunghezza di 16 piedi di uomini adulti per ottenere la lunghezza media del piede.

Stimare la lunghezza di un piede](../img/koebel.jpg)
:width:`500px`
:label:`fig_koebel`

:numref:`fig_koebel` illustra come funziona questo stimatore.
Ai 16 uomini adulti è stato chiesto di mettersi in fila all'uscita dalla chiesa.
La loro lunghezza complessiva è stata poi divisa per 16
per ottenere una stima di ciò che ora ammonta a 1 piede.
Questo "algoritmo" è stato successivamente migliorato per trattare con i piedi deformi - i
I 2 uomini con i piedi più corti e più lunghi rispettivamente furono mandati via,
facendo una media solo sul resto.
Questo è uno dei primi esempi di stima della media tagliata.

La statistica è veramente decollata con la raccolta e la disponibilità di dati.
Uno dei suoi titani, [Ronald Fisher (1890--1962)](https://en.wikipedia.org/wiki/Ronald_Fisher),
ha contribuito significativamente alla sua teoria
e anche alle sue applicazioni nella genetica.
Molti dei suoi algoritmi (come l'analisi discriminante lineare)
e formula (come la matrice di informazione di Fisher)
sono ancora oggi di uso frequente. 
Infatti,
anche il set di dati Iris
che Fisher rilasciò nel 1936 è ancora usato a volte
per illustrare gli algoritmi di apprendimento automatico.
Era anche un sostenitore dell'eugenetica,
il che dovrebbe ricordarci che l'uso moralmente dubbio della scienza dei dati
ha una storia lunga e duratura quanto il suo uso produttivo
nell'industria e nelle scienze naturali.

Una seconda influenza per l'apprendimento automatico venne dalla teoria dell'informazione di
[Claude Shannon (1916--2001)](https://en.wikipedia.org/wiki/Claude_Shannon) e dalla teoria della computazione di [Alan Turing (1912--1954)](https://en.wikipedia.org/wiki/Alan_Turing).
Turing pose la domanda "le macchine possono pensare?
nel suo famoso documento *Computing Machinery and Intelligence* :cite:`Turing.1950`.
In quello che ha descritto come il test di Turing, una macchina
può essere considerata *intelligente* se è difficile
per un valutatore umano distinguere tra le risposte
di una macchina e di un umano sulla base di interazioni testuali.

Un'altra influenza può essere trovata nelle neuroscienze e nella psicologia.
Dopo tutto, gli esseri umani mostrano chiaramente un comportamento intelligente.
È quindi ragionevole chiedersi se si possa spiegare
e possibilmente invertire questa capacità.
Uno dei più vecchi algoritmi ispirati in questo modo
è stato formulato da [Donald Hebb (1904--1985)](https://en.wikipedia.org/wiki/Donald_O._Hebb).
Nel suo libro rivoluzionario *The Organization of Behavior* :cite:`Hebb.Hebb.1949`,
ha postulato che i neuroni imparano tramite rinforzo positivo.
Questo è diventato noto come la regola di apprendimento di Hebbian.
È il prototipo dell'algoritmo di apprendimento del perceptron di Rosenblatt
e ha gettato le basi di molti algoritmi di discesa del gradiente stocastico
che oggi sono alla base dell'apprendimento profondo: rinforzare il comportamento desiderabile
e diminuire il comportamento indesiderabile per ottenere buone impostazioni
dei parametri in una rete neurale.

L'ispirazione biologica è ciò che ha dato il nome alle *reti neurali*.
Per oltre un secolo (risalente ai modelli di Alexander Bain, 1873
e James Sherrington, 1890), i ricercatori hanno cercato di assemblare
circuiti computazionali che assomigliano a reti di neuroni interagenti.
Nel corso del tempo, l'interpretazione della biologia è diventata meno letterale
ma il nome è rimasto. Al suo cuore, ci sono alcuni principi chiave
che si possono trovare nella maggior parte delle reti oggi:

* L'alternanza di unità di elaborazione lineari e non lineari, spesso indicate come *strati*.
* L'uso della regola della catena (conosciuta anche come *backpropagation*) per regolare i parametri dell'intera rete in una sola volta.

Dopo un rapido progresso iniziale, la ricerca sulle reti neurali
ha languito dal 1995 circa fino al 2005.
Ciò era dovuto principalmente a due ragioni.
Primo, l'addestramento di una rete è computazionalmente molto costoso.
Mentre la memoria ad accesso casuale era abbondante alla fine del secolo scorso,
la potenza di calcolo era scarsa.
In secondo luogo, i set di dati erano relativamente piccoli.
Infatti, il set di dati Iris di Fisher del 1932
era uno strumento popolare per testare l'efficacia degli algoritmi.
Il dataset MNIST con le sue 60000 cifre scritte a mano era considerato enorme.

Data la scarsità di dati e di calcolo,
strumenti statistici forti come i metodi kernel,
alberi decisionali e modelli grafici si sono dimostrati empiricamente superiori.
A differenza delle reti neurali, non hanno richiesto settimane di addestramento
e fornivano risultati prevedibili con forti garanzie teoriche.


## La strada verso l'apprendimento profondo

Molto di tutto questo è cambiato con 
la pronta disponibilità di grandi quantità di dati,
grazie al World Wide Web, 
l'avvento delle aziende che servono
centinaia di milioni di utenti online, 
la diffusione di sensori economici e di alta qualità, 
all'immagazzinamento di dati a basso costo (legge di Kryder),
e calcolo a basso costo (legge di Moore), in particolare sotto forma di GPU, originariamente progettate per il gioco al computer.
Improvvisamente gli algoritmi e i modelli che sembravano computazionalmente inapplicabili
sono diventati rilevanti (e viceversa).
Questo è meglio illustrato in :numref:`tab_intro_decade`.

:Dataset vs. memoria del computer e potenza di calcolo

|Decennio|Dataset|Memoria|Calcoli in virgola mobile al secondo
|:--|:-|:-|:-|
|1970|100 (Iris)|1 KB|100 KF (Intel 8080)|
|1980|1 K (prezzi delle case a Boston)|100 KB|1 MF (Intel 80186)|
|1990|10 K (riconoscimento ottico dei caratteri)|10 MB|10 MF (Intel 80486)|
|2000|10 M (pagine web)|100 MB|1 GF (Intel Core)|
|2010|10 G (pubblicità)|1 GB|1 TF (Nvidia C2050)|
|2020|1 T (social network)|100 GB|1 PF (Nvidia DGX-2)|
:label:`tab_intro_decade`

È evidente che la memoria ad accesso casuale non ha tenuto il passo con la crescita dei dati.
Allo stesso tempo, l'aumento della potenza di calcolo
ha superato quello dei dati disponibili.
Questo significa che i modelli statistici devono diventare più efficienti dal punto di vista della memoria
(questo si ottiene tipicamente aggiungendo delle non linearità)
e contemporaneamente essere in grado di spendere più tempo
sull'ottimizzazione di questi parametri, a causa di un maggiore budget computazionale.
Di conseguenza, lo sweet spot nell'apprendimento automatico e nelle statistiche
si è spostato dai modelli lineari (generalizzati) e dai metodi kernel alle reti neurali profonde.
Questo è anche uno dei motivi per cui molti dei pilastri
dell'apprendimento profondo, come i percettori multistrato
:cite:`McCulloch.Pitts.1943`, le reti neurali convoluzionali
:cite:`LeCun.Bottou.Bengio.ea.1998`, memoria a lungo termine
:cite:`Hochreiter.Schmidhuber.1997`,
e Q-Learning :cite:`Watkins.Dayan.1992`,
sono stati essenzialmente "riscoperti" nell'ultimo decennio,
dopo essere rimasti relativamente dormienti per molto tempo.

Il recente progresso nei modelli statistici, nelle applicazioni e negli algoritmi
è stato talvolta paragonato all'esplosione cambriana:
un momento di rapido progresso nell'evoluzione delle specie.
Infatti, lo stato dell'arte non è solo una mera conseguenza
delle risorse disponibili, applicate ad algoritmi vecchi di decenni.
Si noti che l'elenco che segue graffia appena la superficie
delle idee che hanno aiutato i ricercatori a raggiungere progressi enormi
nell'ultimo decennio.


* Nuovi metodi per il controllo della capacità, come il *dropout*.
  :cite:`Srivastava.Hinton.Krizhevsky.ea.2014`,
  hanno contribuito a mitigare il pericolo di overfitting.
  Questo è stato ottenuto applicando l'iniezione di rumore :cite:`Bishop.1995`
  in tutta la rete neurale, sostituendo i pesi con variabili casuali
  ai fini dell'addestramento.
* I meccanismi di attenzione hanno risolto un secondo problema
  che aveva afflitto la statistica per oltre un secolo:
  come aumentare la memoria e la complessità di un sistema senza
  aumentare il numero di parametri apprendibili.
  I ricercatori hanno trovato una soluzione elegante
  utilizzando ciò che può essere visto solo come una struttura di puntatori imparabile :cite:`Bahdanau.Cho.Bengio.2014`.
  Piuttosto che dover ricordare un'intera sequenza di testo, ad es,
  per la traduzione automatica in una rappresentazione a dimensione fissa,
  tutto ciò che doveva essere memorizzato era un puntatore allo stato intermedio
  del processo di traduzione. Questo ha permesso di aumentare significativamente
  una maggiore accuratezza per le sequenze lunghe, poiché il modello
  non aveva più bisogno di ricordare l'intera sequenza prima di
  iniziare la generazione di una nuova sequenza.
* Disegni a più stadi, per esempio, attraverso le reti di memoria 
  :cite:`Sukhbaatar.Weston.Fergus.ea.2015` e il programmatore-interprete neurale :cite:`Reed.De-Freitas.2015`
  hanno permesso ai modellatori statistici di descrivere approcci iterativi al ragionamento. Questi strumenti permettono che uno stato interno della rete neurale profonda
  essere modificato ripetutamente, eseguendo così i passi successivi
  in una catena di ragionamento, simile a come un processore
  può modificare la memoria per una computazione.
* Un altro sviluppo chiave è stata l'invenzione delle reti avversarie generative
  :cite:`Goodfellow.Pouget-Abadie.Mirza.ea.2014`.
  Tradizionalmente, i metodi statistici per la stima della densità
  e i modelli generativi si concentravano sulla ricerca di adeguate distribuzioni di probabilità
  e su algoritmi (spesso approssimativi) per il campionamento da esse.
  Di conseguenza, questi algoritmi erano in gran parte limitati dalla mancanza di
  flessibilità inerente ai modelli statistici.
  L'innovazione cruciale nelle reti avversarie generative è stata quella di sostituire il campionatore
  da un algoritmo arbitrario con parametri differenziabili.
  Questi sono poi regolati in modo tale che il discriminatore
  (effettivamente un test a due campioni) non può distinguere i dati falsi da quelli reali.
  Attraverso la capacità di utilizzare algoritmi arbitrari per generare dati,
  ha aperto la stima della densità a un'ampia varietà di tecniche.
  Esempi di zebre al galoppo :cite:`Zhu.Park.Isola.ea.2017`
  e di falsi volti di celebrità :cite:`Karras.Aila.Laine.ea.2017`.
  sono entrambi testimonianza di questo progresso.
  Anche gli scarabocchiatori dilettanti possono produrre
  immagini fotorealistiche basate solo su schizzi che descrivono
  come appare il layout di una scena :cite:`Park.Liu.Wang.ea.2019`.
* In molti casi, una singola GPU è insufficiente per elaborare
  le grandi quantità di dati disponibili per la formazione.
  Nell'ultimo decennio la capacità di costruire algoritmi paralleli e
  algoritmi di addestramento distribuiti è migliorata notevolmente.
  Una delle sfide chiave nella progettazione di algoritmi scalabili
  è che il cavallo di battaglia dell'ottimizzazione dell'apprendimento profondo,
  la discesa del gradiente stocastico, si basa su relativamente
  piccoli minibatch di dati da elaborare.
  Allo stesso tempo, i piccoli lotti limitano l'efficienza delle GPU.
  Quindi, l'addestramento su 1024 GPU con una dimensione minibatch di,
  diciamo 32 immagini per batch ammonta a un minibatch aggregato
  di circa 32000 immagini. Lavori recenti, prima da :cite:`Li.2017`,
  e successivamente da :cite:`You.Gitman.Ginsburg.2017`
  e :cite:`Jia.Song.He.ea.2018` hanno spinto la dimensione fino a 64000 osservazioni,
  riducendo il tempo di addestramento del modello ResNet-50 sul set di dati ImageNet a meno di 7 minuti.
  Per confronto - inizialmente i tempi di addestramento erano misurati nell'ordine dei giorni.
* La capacità di parallelizzare i calcoli ha anche contribuito in modo cruciale
  al progresso nell'apprendimento per rinforzo, almeno quando la simulazione è un'opzione
  un'opzione. Questo ha portato a progressi significativi nei computer che raggiungono
  prestazioni sovrumane nel Go, nei giochi Atari, in Starcraft, e nelle simulazioni fisiche
  simulazioni fisiche (ad esempio, usando MuJoCo). Vedi ad esempio,
  :cite:`Silver.Huang.Maddison.ea.2016` per una descrizione
  di come raggiungere questo obiettivo in AlphaGo. In poche parole,
  l'apprendimento per rinforzo funziona meglio se sono disponibili molte triple (stato, azione, ricompensa), cioè quando è possibile provare molte cose per imparare come si relazionano
  l'una con l'altra. La simulazione fornisce una tale strada.
* I quadri di apprendimento profondo hanno giocato un ruolo cruciale
  nella diffusione delle idee. La prima generazione di framework
  che permette una facile modellazione comprendeva
  [Caffe](https://github.com/BVLC/caffe),
  [Torch](https://github.com/torch), e
  [Theano](https://github.com/Theano/Theano).
  Molti articoli seminali sono stati scritti usando questi strumenti.
  Ora, sono stati sostituiti da
  [TensorFlow](https://github.com/tensorflow/tensorflow) (spesso usato tramite la sua API di alto livello [Keras](https://github.com/keras-team/keras)), [CNTK](https://github.com/Microsoft/CNTK), [Caffe 2](https://github.com/caffe2/caffe2), e [Apache MXNet](https://github.com/apache/incubator-mxnet). La terza generazione di strumenti, cioè strumenti imperativi per l'apprendimento profondo,
  è stato probabilmente guidato da [Chainer](https://github.com/chainer/chainer),
  che ha usato una sintassi simile a Python NumPy per descrivere i modelli.
  Questa idea è stata adottata sia da [PyTorch](https://github.com/pytorch/pytorch),
  la [Gluon API](https://github.com/apache/incubator-mxnet) di MXNet, e [Jax](https://github.com/google/jax).


La divisione del lavoro tra i ricercatori di sistema che costruiscono strumenti migliori
e i modellatori statistici che costruiscono reti neurali migliori
ha notevolmente semplificato le cose. Per esempio,
addestrare un modello di regressione logistica lineare
era un problema di compiti non banale,
degno di essere dato ai nuovi studenti di
studenti di dottorato alla Carnegie Mellon University nel 2014.
Ora, questo compito può essere realizzato con meno di 10 righe di codice,
mettendolo saldamente alla portata dei programmatori.

## Storie di successo

L'IA ha una lunga storia di risultati
che sarebbero difficili da ottenere altrimenti.
Per esempio, 
i sistemi di smistamento della posta
che utilizzano il riconoscimento ottico dei caratteri
sono stati impiegati fin dagli anni '90.
Questa è, dopo tutto, la fonte del famoso dataset MNIST di cifre scritte a mano.
Lo stesso vale per la lettura degli assegni per i depositi bancari e il punteggio
la solvibilità dei richiedenti.
Le transazioni finanziarie sono controllate automaticamente per le frodi.
Questo costituisce la spina dorsale di molti sistemi di pagamento e-commerce,
come PayPal, Stripe, AliPay, WeChat, Apple, Visa e MasterCard.
I programmi informatici per gli scacchi sono stati competitivi per decenni.
L'apprendimento automatico alimenta la ricerca, la raccomandazione, la personalizzazione,
e il ranking su Internet.
In altre parole, il machine learning è pervasivo, anche se spesso nascosto alla vista.

È solo di recente che l'AI
è stata alla ribalta, soprattutto a causa di
soluzioni a problemi
che prima erano considerati intrattabili
e che sono direttamente collegati ai consumatori.
Molti di questi progressi sono attribuiti al deep learning.

* Gli assistenti intelligenti, come Siri di Apple, Alexa di Amazon e l'assistente di Google
  Google, sono in grado di rispondere a domande parlate con un ragionevole grado di
  accuratezza. Questo include compiti meniali come accendere gli interruttori della luce (una manna per i disabili) fino a prendere appuntamenti dal barbiere e offrire dialoghi di supporto telefonico. Questo è probabilmente il segno più evidente che l'IA sta influenzando le nostre vite.
* Un ingrediente chiave negli assistenti digitali è la capacità di riconoscere il discorso
  accuratamente. Gradualmente la precisione di tali sistemi è aumentata fino al punto
  in cui raggiungono la parità umana per certe
  applicazioni :cite:`Xiong.Wu.Alleva.ea.2018`.
* Anche il riconoscimento degli oggetti ha fatto molta strada. Stimare l'oggetto in una
  immagine era un compito abbastanza impegnativo nel 2010. Sul benchmark ImageNet i ricercatori di NEC Labs e dell'Università dell'Illinois a Urbana-Champaign hanno raggiunto un tasso di errore top-5 del 28% :cite:`Lin.Lv.Zhu.ea.2010`. Entro il 2017,
  questo tasso di errore è stato ridotto al 2,25% :cite:`Hu.Shen.Sun.2018`. Allo stesso modo, risultati sorprendenti
  risultati sono stati raggiunti per identificare gli uccelli o diagnosticare il cancro alla pelle.
* I giochi erano un tempo un bastione dell'intelligenza umana.
  A partire da TD-Gammon, un programma per giocare a backgammon utilizzando l'apprendimento di rinforzo della differenza temporale, il progresso algoritmico e computazionale ha portato ad algoritmi
  per una vasta gamma di applicazioni. A differenza del backgammon,
  gli scacchi hanno uno spazio di stato molto più complesso e un insieme di azioni.
  DeepBlue ha battuto Garry Kasparov usando un parallelismo massiccio,
  hardware speciale e una ricerca efficiente attraverso l'albero del gioco :cite:`Campbell.Hoane-Jr.Hsu.2002`.
  Go è ancora più difficile, a causa del suo enorme spazio di stato.
  AlphaGo ha raggiunto la parità umana nel 2015, utilizzando l'apprendimento profondo combinato con il campionamento dell'albero di Monte Carlo :cite:`Silver.Huang.Maddison.ea.2016`.
  La sfida nel poker era che lo spazio di stato è
  grande e non è completamente osservato (non conosciamo le carte degli
  carte). Libratus ha superato le prestazioni umane nel poker usando efficientemente
  strategie strutturate in modo efficiente :cite:`Brown.Sandholm.2017`.
  Questo illustra l'impressionante progresso nei giochi
  e il fatto che gli algoritmi avanzati hanno giocato un ruolo cruciale in essi.
 * Un'altra indicazione del progresso dell'IA è l'avvento delle auto a guida autonoma
  e camion. Mentre la piena autonomia non è ancora a portata di mano,
  sono stati fatti ottimi progressi in questa direzione,
  con aziende come Tesla, NVIDIA,
  e Waymo che spediscono prodotti che permettono un'autonomia almeno parziale.
  Ciò che rende la piena autonomia così impegnativa è che la guida corretta
  richiede la capacità di percepire, ragionare e incorporare regole
  in un sistema. Attualmente, l'apprendimento profondo è usato principalmente
  nell'aspetto della visione artificiale di questi problemi.
  Il resto è pesantemente messo a punto dagli ingegneri.



Di nuovo, l'elenco di cui sopra graffia appena la superficie di dove l'apprendimento automatico ha avuto un impatto sulle applicazioni pratiche. Per esempio, la robotica, la logistica, la biologia computazionale, la fisica delle particelle e l'astronomia devono alcuni dei loro più impressionanti progressi recenti almeno in parte al machine learning. L'apprendimento automatico sta quindi diventando uno strumento onnipresente per ingegneri e scienziati.

Spesso, la questione dell'apocalisse dell'IA, o la singolarità dell'IA
è stata sollevata in articoli non tecnici sull'IA.
La paura è che in qualche modo i sistemi di apprendimento automatico
diventino senzienti e decidano indipendentemente dai loro programmatori
(e padroni) su cose che riguardano direttamente il sostentamento degli umani.
In una certa misura, l'IA influenza già il sostentamento degli esseri umani
in modo immediato:
l'affidabilità creditizia viene valutata automaticamente,
i piloti automatici per lo più navigano i veicoli, le decisioni
se concedere la cauzione utilizzano dati statistici come input.
Più frivolamente, possiamo chiedere ad Alexa di accendere la macchina del caffè.

Fortunatamente, siamo lontani da un sistema di IA senziente
che sia pronto a manipolare i suoi creatori umani (o a bruciare il loro caffè).
In primo luogo, i sistemi di IA sono progettati, addestrati e distribuiti in modo specifico,
orientati all'obiettivo. Mentre il loro comportamento potrebbe dare l'illusione
di intelligenza generale, è una combinazione di regole, euristiche
e modelli statistici che sono alla base del design.
In secondo luogo, attualmente non esistono strumenti di *intelligenza generale artificiale*
semplicemente non esistono che siano in grado di migliorare se stessi,
ragionare su se stessi, e che siano in grado di modificare,
estendere e migliorare la propria architettura
mentre cercano di risolvere compiti generali.

Una preoccupazione molto più pressante è come l'IA viene utilizzata nella nostra vita quotidiana.
È probabile che molti compiti umili svolti da autisti di camion
e dai commessi dei negozi possono essere e saranno automatizzati.
I robot agricoli probabilmente ridurranno il costo dell'agricoltura biologica
ma automatizzeranno anche le operazioni di raccolta.
Questa fase della rivoluzione industriale
potrebbe avere profonde conseguenze su ampie fasce della società,
dato che gli autisti di camion e i commessi sono alcuni
dei lavori più comuni in molti paesi.
Inoltre, i modelli statistici, se applicati senza cura
possono portare a pregiudizi razziali, di genere o di età e sollevare
ragionevoli preoccupazioni sull'equità procedurale
se automatizzati per guidare decisioni consequenziali.
È importante assicurare che questi algoritmi siano usati con cura.
Con quello che sappiamo oggi, questa ci sembra una preoccupazione molto più pressante
del potenziale di una superintelligenza malevola di distruggere l'umanità.


## Caratteristiche

Finora abbiamo parlato dell'apprendimento automatico in senso lato, che è sia una branca dell'IA che un approccio all'IA.
Anche se l'apprendimento profondo è un sottoinsieme dell'apprendimento automatico,
l'insieme vertiginoso di algoritmi e applicazioni rende difficile valutare quali siano specificamente gli ingredienti dell'apprendimento profondo. 
Questo è difficile come cercare di individuare gli ingredienti necessari per la pizza, dato che quasi ogni componente è sostituibile.

Come abbiamo descritto, l'apprendimento automatico può
usare i dati per imparare trasformazioni tra gli input e gli output,
come la trasformazione dell'audio in testo nel riconoscimento vocale.
Nel fare ciò, è spesso necessario rappresentare i dati in un modo adatto agli algoritmi per trasformare tali rappresentazioni in output.
Il *Deep learning* è *profondo* proprio nel senso
che i suoi modelli
imparano molti *strati* di trasformazioni,
dove ogni strato offre la rappresentazione
ad un livello.
Per esempio,
gli strati vicini all'input possono rappresentare 
dettagli di basso livello dei dati,
mentre gli strati più vicini all'output di classificazione
possono rappresentare concetti più astratti utilizzati per la discriminazione.
Poiché l'apprendimento delle rappresentazioni mira a
trovare la rappresentazione stessa,
l'apprendimento profondo può essere definito come apprendimento
di rappresentazione.

I problemi che abbiamo discusso finora, come l'apprendimento
dal segnale audio grezzo, 
i valori grezzi dei pixel delle immagini,
o la mappatura tra frasi di lunghezza arbitraria e
le loro controparti in lingue straniere,
sono quelli
dove il deep learning eccelle e dove il tradizionale 
apprendimento automatico
metodi tradizionali di apprendimento automatico vacillano.
Si scopre che questi modelli a più livelli
sono in grado di affrontare i dati percettivi di basso livello
in un modo che gli strumenti precedenti non potevano.
Probabilmente l'elemento comune più significativo nei metodi di apprendimento profondo è l'uso dell'addestramento *end-to-end*. 
Cioè, piuttosto che assemblare un sistema basato su componenti che sono sintonizzati individualmente, si costruisce il sistema e poi si sintonizzano le loro prestazioni insieme.
Per esempio, nella computer vision gli scienziati erano soliti separare il processo di *ingegneria delle caratteristiche* dal processo di costruzione dei modelli di apprendimento automatico. Il rilevatore di bordi Canny :cite:`Canny.1987` e l'estrattore di caratteristiche SIFT di Lowe :cite:`Lowe.2004` hanno regnato per oltre un decennio come algoritmi per la mappatura delle immagini in vettori di caratteristiche.
In passato, la parte cruciale dell'applicazione dell'apprendimento automatico a questi problemi
consisteva nel trovare modi ingegnerizzati manualmente
di trasformare i dati in qualche forma adatta a modelli poco profondi.
Sfortunatamente, c'è solo così poco che gli umani possono realizzare con l'ingegno in confronto ad una valutazione coerente su milioni di scelte effettuate automaticamente da un algoritmo.
Quando l'apprendimento profondo ha preso il sopravvento,
questi estrattori di caratteristiche sono stati sostituiti da filtri sintonizzati automaticamente, ottenendo una precisione superiore.

Quindi,
un vantaggio chiave dell'apprendimento profondo è che sostituisce non
solo i modelli superficiali alla fine delle tradizionali pipeline di apprendimento,
ma anche l'impegnativo processo di 
dell'ingegneria delle caratteristiche.
Inoltre, sostituendo gran parte della pre-elaborazione specifica del dominio,
l'apprendimento profondo ha eliminato molti dei confini
che prima separavano la visione artificiale, il riconoscimento vocale,
l'elaborazione del linguaggio naturale, l'informatica medica e altre aree di applicazione,
offrendo un insieme unificato di strumenti per affrontare problemi diversi.

Al di là della formazione end-to-end, 
stiamo vivendo una transizione dalle descrizioni statistiche parametriche a modelli completamente non parametrici. Quando i dati sono scarsi, si deve fare affidamento su ipotesi semplificative sulla realtà per ottenere modelli utili. Quando i dati sono abbondanti, questo può essere sostituito da modelli non parametrici che si adattano alla realtà in modo più accurato. In una certa misura, questo rispecchia il progresso che la fisica ha sperimentato nella metà del secolo scorso con la disponibilità dei computer. Piuttosto che risolvere a mano le approssimazioni parametriche del comportamento degli elettroni, si può ora ricorrere a simulazioni numeriche delle equazioni differenziali parziali associate. Questo ha portato a modelli molto più accurati, anche se spesso a spese della spiegabilità.

Un'altra differenza rispetto al lavoro precedente è l'accettazione di soluzioni subottimali, la gestione di problemi di ottimizzazione non lineari non convessi e la volontà di provare le cose prima di provarle. Questo ritrovato empirismo nell'affrontare i problemi statistici, combinato con un rapido afflusso di talenti ha portato ad un rapido progresso degli algoritmi pratici, anche se in molti casi a spese della modifica e reinvenzione di strumenti che esistevano da decenni.

Alla fine, la comunità del deep learning è orgogliosa di condividere strumenti oltre i confini accademici e aziendali, rilasciando molte librerie eccellenti, modelli statistici e reti addestrate come open source.
È in questo spirito che i quaderni che formano questo libro sono liberamente disponibili per la distribuzione e l'uso. Abbiamo lavorato duramente per abbassare le barriere di accesso a tutti per imparare il deep learning e speriamo che i nostri lettori ne traggano beneficio.



## Riassunto

* L'apprendimento automatico studia come i sistemi informatici possono sfruttare l'esperienza (spesso i dati) per migliorare le prestazioni in compiti specifici. Combina idee dalla statistica, dal data mining e dall'ottimizzazione. Spesso, è usato come un mezzo per implementare soluzioni AI.
* Come classe di apprendimento automatico, l'apprendimento rappresentazionale si concentra su come trovare automaticamente il modo appropriato per rappresentare i dati. L'apprendimento profondo è un apprendimento di rappresentazione a più livelli attraverso l'apprendimento di molti strati di trasformazioni.
* L'apprendimento profondo sostituisce non solo i modelli superficiali alla fine delle tradizionali pipeline di apprendimento automatico, ma anche il processo ad alta intensità di lavoro dell'ingegneria delle caratteristiche. 
* Gran parte dei recenti progressi nell'apprendimento profondo sono stati innescati da un'abbondanza di dati derivanti da sensori economici e applicazioni su scala Internet, e da progressi significativi nel calcolo, per lo più attraverso le GPU.
* L'ottimizzazione dell'intero sistema è una componente chiave per ottenere alte prestazioni. La disponibilità di efficienti framework di deep learning ha reso la progettazione e l'implementazione di questo significativamente più facile.
 Tradotto con www.DeepL.com/translator (versione gratuita)
 
## Esercizi

1. Quali parti di codice che state attualmente scrivendo potrebbero essere "apprese", cioè migliorate imparando e determinando automaticamente le scelte di design che vengono fatte nel vostro codice? Il vostro codice include scelte di design euristiche?
1. Quali problemi che incontrate hanno molti esempi su come risolverli, ma nessun modo specifico per automatizzarli? Questi potrebbero essere i candidati principali per l'uso del deep learning.
1. Considerando lo sviluppo dell'IA come una nuova rivoluzione industriale, qual è la relazione tra algoritmi e dati? È simile alle macchine a vapore e al carbone? Qual è la differenza fondamentale?
1. Dove altro si può applicare l'approccio di formazione end-to-end, come in :numref:`fig_ml_loop`, fisica, ingegneria ed econometria?

[Discussions](https://discuss.d2l.ai/t/22)
