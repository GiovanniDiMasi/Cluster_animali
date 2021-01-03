# Cluster_animali

# Fasi di esecuzione del progetto:

1. Premesse (Premises)  
Dopo avere riportato due premesse generali (una pessimistica e una ottimistica) ci lasciamo ispirare dallo Zen di Python. Si sottolinea quindi che la esortazione ivi contenuta era già presente nel rasoio di Occam, una delle basi della scienza moderna.

2. Esplorazione dei dati (Exploring data)
Procediamo ad una preliminare esplorazione dei dati. Occorre verificare se vi siano dati anomali o mancanti e procedere ad una eventuale ripulitura degli stessi.  Abbiamo un data set di animali e un data set di classi che chiamiamo datazoo e dataclass. Si tratta di 7 classi fondamentali, per 101 animali, distribuite in modo non uniforme. Gli animali del nostro data set sono contraddistinti da 16 caratteristiche distintive diverse e il progetto consta di raggruppare, in modo non supervisionato, gli animali sulla base di queste caratteristiche a prescindere quindi dalla loro appartenenza alle classi predefinite.
I valori di queste caratteristiche sono espressi in modalità booleana ad eccezione dell'attributo "legs"che è numerico. Esploriamo i dati con varie modalità e in particolare riveliamo, con più di un metodo, che il data set non contiene valori nulli.

3. Valutazione della qualità dei dati e valori mancanti (Data quality assessment and missing values)
Non ci sono missing values e la qualità dei dati sembra buona. Restituiamo la lista degli oggetti presenti nel data set in formato più leggibile con unique. Controlliamo se il type della classe ha valori corretti. 
Ad un certo punto ci accorgiamo che un dato curioso attira la nostra attenzione e temiamo ad un errore nei dati (un animale con 5 legs?) Verifichiamo di cosa si tratta, constatiamo che non è un errore ma una lettura particolare di un dato. Utilizziamo anche rappresentazioni grafiche, tra cui un boxplot relativo alla presenza di gambe nelle varie classi (la classe 5 è fish e contiene la stella marina).
Facciamo un join tra la tabella degli animali (datazoo) e la tabella delle classi e mostriamo una nuova e più completa classe. Importiamo seaborn per fare l'istogramma delle classi.
Mostriamo le correlazioni con una Correlation Heatmap ed evidenziamo le correlazioni significative con valore superiore al 75%, sia positive che negative
Usiamo grupby e, tra l’altro, vediamo che ci sono dei mammiferi, seppure in misura irrisoria (0,048), che depongono le uova (rispondendo al quesito posto nel titolo).

4. Preprocessing

