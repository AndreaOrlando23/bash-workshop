## Comandi base
___

`ls` 
- ti elenca i file visibili nella directory dove si è posizionati

`ls -la`
- non solo ti fa vedere i file visibili della directory, ma anche i file nascosti

`rm <nome_file>`
- ti cancella il file che gli viene passato come argomento

`wget <url>`
- ti scarica il contenuto dell'url passato salvandolo nella directory dove si è posizionati (è possibile anche indicare una destinazione diversa)

`find . -name "<nome_file>"`
- ti trova dove è posizionato il file passato. Il punto `.` indica che lo stiamo cercando nella directory dove si è posizionati.
- se non si è sicuri del nome del file (per esempio se sia upper case o meno) si può utilizzare il comando: `find . -iname "<nome_file>"`
- nel caso in cui non si è sicuri del nome in generale si può utilizzare il comando: `find . -iname "<nom*.*">`. Il programma troverà tutti i file che iniziano per il parametro passato, in questo caso `<nom>`

`cat <nome_file>`
- per aprire il contenuto dei file
- se si aprono file molto grandi il comando va esteso così: `cat <nome_file> | more`. `|` sta per pipe. Questo permettarà di visualizzare il documento fino alla fine del terminale, per proseguire con la visualizzazione di preme invio e il documento scorrerà fino alla fine.

`cat <nome_file> | grep '^blabla'`
- `grep` significa: prendi tutto quanto il contenuto del file `cat <nome_file>` pipe `|` cioè il risultato `grep` cioè filtra tutto quello che inizia per `^blabla`

`cat <nome_file> | grep '^blabla' | wc -l`
- con l'aggiunta di `| wc -l` ti verrà restituito in output il totale degli elementi presenti nel `cat <nome_file>` filtrato per `| grep '^blabla'`

`cat <nome_file> | grep '^blabla' | head -n 3`
- mi restituisce in output per il `<nome_file>`, filtrati per `^blabla`, solo i primi 3 risultati

`cat <nome_file> | grep '^blabla' | tail -n 3`
- mi restituisce in output per il `<nome_file>`, filtrati per `^blabla`, solo gli ultimi 3 risultati

`cat <nome_file> | grep '^blabla' | head -n 3 | tail -n 1`
- mi restituisce in output per il `<nome_file>`, filtrati per `^blabla`, solo l'ultimo dei primi 3 risultati

`cat <nome_file> | awk {'print $1'}`
- con il comando `awk` riusciamo a fare il print solo dei valori di una colonna. In questo caso l'output sarà la prima colonna

`cat <nome_file> | awk {'print $1'} | grep <vaolere_ricercato>`
- ti stampa i valori della colonna 1 filtrati per il valore ricercato

`less <nome_file>`
- nel caso della ricerca, ti apre il file in `vi` e, premendo `:` e `/<valore_ricercato>` ti permette di ritrovare tutti i valori ricercati e premendo `n` (che starebbe per next) ti scorre i risultati.
- la cosa interessante è che per esempio facendo una ricerca di tipo `cat <nome_file> | grep '^blabla' | less`, il risultato ti va su `less` ed effettuando i passaggi del primo punto potrai ricercare i valori in determinati valori e non su tutto il file


