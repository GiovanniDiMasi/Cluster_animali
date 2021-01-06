# Animals Cluster

Fasi di esecuzione del progetto:
0	Premises.
1	Exploring Data.
2	Data Visualization.
3	Data Quality Assessment and Missing Values.
4	Preprocessing and Clustering
5	Results Visialization.
6	Benchmark and Evaluation.


0.	Premises.  
Dopo avere riportato due premesse generali (una pessimistica e una ottimistica) ci lasciamo ispirare dallo Zen di Python. Si sottolinea quindi che la esortazione ivi contenuta era già presente nel rasoio di Occam, una delle basi della scienza moderna.

1.	 Exploring data.  
Procediamo ad una preliminare esplorazione dei dati. Occorre verificare se vi siano dati anomali o mancanti e procedere ad una eventuale ripulitura degli stessi.  Abbiamo un data set di animali e un data set di classi che chiamiamo datazoo e dataclass. Si tratta di 7 classi fondamentali, per 101 animali, distribuite in modo non uniforme. Gli animali del nostro data set sono contraddistinti da 16 caratteristiche distintive diverse e il progetto consta di raggruppare, in modo non supervisionato, gli animali sulla base di queste caratteristiche a prescindere quindi dalla loro appartenenza alle classi predefinite.
I valori di queste caratteristiche sono espressi in modalità booleana ad eccezione dell'attributo "legs"che è numerico. Ci siamo anzitutto chiesti se fatto che legs abbia valori non booleani ma numerici, compresi tra 0 e 8, possa costituire un problema, ma lo vedremo tra poco. 
Dobbiamo anzitutto esploriamo i dati con varie modalità e in particolare appurare, con più di un metodo, se il data set contenga o meno valori nulli.

2.	Data Visualization.  
Operiamo una successiva visualizzazione dei dati, anzitutto attraverso la importazione di matplotlib.pyplot. 
Utilizziamo lo strumento describe che ci fornisce una indicazione dei valori statistici di base come media, deviazione standard, minimo e massimo).

3.	Data quality assessment and missing values.    
Operando la valutazione della qualità dei dati riscontriamo che non ci sono missing values e la qualità dei dati sembra buona. 
Restituiamo la lista degli oggetti presenti nel data set in formato più leggibile con unique. Controlliamo se il type della classe ha valori corretti. 
Ad un certo punto ci accorgiamo che un dato curioso attira la nostra attenzione e temiamo ad un errore nei dati (un animale con 5 legs?) Verifichiamo di cosa si tratta, constatiamo che non è un errore ma una lettura particolare di un dato. Utilizziamo anche rappresentazioni grafiche, tra cui un boxplot relativo alla presenza di gambe nelle varie classi (la classe 5 è fish e contiene la stella marina).
Facciamo un join tra la tabella degli animali (datazoo) e la tabella delle classi e mostriamo una nuova e più completa classe. 
Importiamo seaborn per fare l'istogramma delle classi.
Mostriamo le correlazioni con una Correlation Heatmap ed evidenziamo le correlazioni significative con valore superiore al 75%, sia positive che negative
Usiamo grupby e, tra l’altro, vediamo che ci sono dei mammiferi, seppure in misura irrisoria (0,048), che depongono le uova (rispondendo al quesito posto nel titolo).

4.	Preprocessing and Clustering.  
Eliminiamo anzitutto dal dataframe le variabili categoriche (animal_name e class_type)
Dalla libreria sklearn importiamo strumenti per scalare i dati MinMaxScaler (questo è necessario anzitutto in relazione al problema delle “legs”, dato non boolenano il cui valore numerico è diverso da tutti gli altri valori degli altri attributi).
Si importa anche la Principal Component Analysis per comprimere i dati in due dimensioni e poterli visualizzare.  
A questo punto possiamo applicare gli algoritmi di clustering. Si applicano nell'ordine kMeans, Agglomerarive Clustering, Spectral Clustering, DBSCAN e Birch. 

5.	Results Visualization.    
Si utilizza matplotlib.pyplot per la visualizzazione dei risultati. 
Si disegnano 6 grafici bidimensionali per visualizzare i risultati rispettivamente ottenuti dai 5 diversi algoritmi e per la classificazione reale.
Si realizza anche un dendrogramma per la visualizzazione gerarchica.

6.	Benchmark and Evaluation.    
Utilizziamo due metriche diverse per verificare quanto il risultato ottenuto con gli algoritmi di clustering sia accurato rispetto alla ground truth.
La prima metrica (completeness_score) misura la completezza del risultato data una ground truth, un risultato sarà cioè 'completo' e avrà un punteggio massimo uguale a 1 se tutti i dati appartenti alla stessa classe sono inseriti nello stesso cluster.
La seconda metrica (adjusted_rand_score) invece misura la similiarità considerando tutte le coppie di punti e contando quante di queste coppie sono assegnate nello stesso gruppo o in gruppi diversi per entrambi il clustering reale e quello predetto.
I risultati più vicini alla ground truth si rivelano nel nostro caso prodotti dall'algoritmo Spectral Clustering.



