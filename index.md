<a name="sfc"></a>
<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/ws_logo.png" width="20%" height="20%">

# Prototype: Daily Future Knock-Out
---
## Inhalt

-	[Eigenschaften des „Dax Daily Knock-Out Future“](#eigenschaften-des-dax-daily-knock-out-future)
-	[Anleitung](#anleitung)
    - [Kapitel A: Einstieg in die Ethereum Blockchain mit dem Ethereum-Browser "Parity"](#kapitel-a-einstieg-in-die-ethereum-blockchain-mit-dem-ethereum-browser-parity)
	- [Kapitel B: Erste Schritte mit dem Dax Daily Knock-Out Future](#kapitel-b-erste-schritte-mit-dem-dax-daily-knock-out-future)
		- [Schritt 1: Den Smart Financial Contract in die eigene Wallet einfügen](#schritt-1-den-smart-financial-contract-in-die-eigene-wallet-einf%C3%BCgen)
		- [Schritt 2: Trades duchführen](#schritt-2-trades-duchf%C3%BChren)
		- [Schritt 3: Informationen abrufen](#schritt-3-informationen-abrufen)
		- [Schritt 4: Gewinne auszahlen lassen](#schritt-4-gewinne-auszahlen-lassen)
		
		
---
Diese Anleitung beschreibt, wie in den Smart Financial Contract „Dax Daily Knock-Out Future“ investiert werden kann.
Das Ziel dieses Smart Financial Contracts ist es, zu zeigen, dass Finanz-Terminkontrakte in der Blockchain „Ethereum“ abgebildet werden können. In diesem Sinn wird dieser Prototyp Interessierten als **TEST** zur Verfügung gestellt. Die Benutzung der Software geschieht auf eigene Gefahr; jede Haftung für Schäden oder Verluste ist ausgeschlossen. Insbesondere die allgemeinen Risiken bei der Nutzung von Ethereum gelten auch hier, siehe <a href="https://www.ethereum.org/agreement" target="_blank">https://www.ethereum.org/agreement</a>.

## Eigenschaften des „Dax Daily Knock-Out Future“

-	Der Trader setzt auf die Dax-Entwicklung des Folgetages. Man kann „LONG“ oder „SHORT“ gehen. Schließt der Dax am Folgetag über dem Schlusskurs des vorigen Tages, dann ist de „Dax Daily Knock-Out Future“ LONG, ansonsten short.
-	Beispiel:
    - Es ist Montag, 18:00 Uhr. Der Dax schloss um 17:45 Uhr mit 11.800,12 Punkten
    - Meine Prognose für Dienstag (der Folgetag) ist, dass der Dax höher schließt
    - Also gehe ich „LONG“, ich initiiere die Transaktion am Montag abend.
    - Am Dienstag schließt der Dax bei 11.900,45 Punkten, also höher als am Montag. LONG war somit die richtige Prognose.  
	- Die Auszahlung meines Gewinns (inkl. Invest natürlich) ist ab dem Folgetag (Mittwoch) möglich
- Der Prototyp „Dax Daily Knock-Out Future“ ist ein recht einfaches Knock-Out Produkt für Demonstrationszwecke. Trifft die Prognose ein, also Dax schließt höher oder tiefer, erhält man einen Gewinn. Trifft die eigene Prognose nicht ein, verliert man den investierten Ether-Betrag. Die Summe aller Verlust-Trades wird auf die Gewinner-Trades aufgeteilt. Der potentielle Gewinn ist somit abhängig von der Long/Short-Quota.

## Anleitung
---
Wer sich bereits mit Ethereum auskennt und eine Wallet mit ein paar Ether besetzt, kann direkt ins [Kapitel B](#kapb). springen.
Als kurze Einführung in Ethereum dient auch dieses Video: 
<a href="https://youtu.be/j23HnORQXvs" target="_blank">https://youtu.be/j23HnORQXvs</a>

Eine Einführung in Ethereum mit vielen Links ist hier zu finden: 
<a href="http://bit.ly/2mURyWZ" target="_blank">http://bit.ly/2mURyWZ</a>

## Kapitel A: Einstieg in die Ethereum Blockchain mit dem Ethereum-Browser "Parity"


| Schritt        | Screenshot (klick zum Vergrößern)|
|:-------------|:------------------|
|Schritt 1: Ethereum Browser herunterladen. Zur Verwendung des Prototypen sollte der Ethereum-Browser "Parity" verwendet werden. Gehe zu <a href="https://parity.io/parity.html" target="_blank">https://parity.io/parity.html</a> und klicke auf "Get Parity"|  <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getParity.png" width="50%" height="50%">|
|Parity installieren (InstallParity.exe ausführen)| 
|Parity starten und synchronisieren. Im Startmenü sollte Parity als Anwendung aufgeführt sein|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityStartMenu.png" width="100%" height="100%">|
|Partiy sollte nun als kleines Icon im Info-Bereich der Taskleiste erscheinen.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityIcon.png" width="100%" height="100%">|
|Die Parity-Benutzeroberfläche sollte nach der Installation automatisch starten. Falls nicht: Parity wird über den Browser bedient. Öffne die URL http://127.0.0.1:8180, um auf die Parity-Oberfläche zu gelangen.| <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityHome.png" width="100%" height="100%">|
|**Wichtig: beim ersten Start von Parity erfolgt eine vollständige Synchronisation mit der Blockchain „Ethereum“. Um Transaktionen sicher durchzuführen, sollte diese Synchronisation vollständig abgeschlossen sein. Das kann eine Weile dauern. Der Status der Synchronisation kann ganz unten in Parity abgelesen werden.**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/paritySyncStatus.png" width="100%" height="100%">|
|Wer auf Nummer sicher gehen möchte, kann die Anzahl synchronisierter Blöcke mit der Anzahl auf http://www.etherscan.io vergleichen.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/etherscan.png" width="100%" height="100%"> In den hier gezeigten Screenshots / Beispielen sind 3.402.297 synchronisiert, während in der Ethereum-Blockchain bereits 3.468.505 Blöcke vorhanden sind. Die Synchronisation ist in diesem Beispiel somit noch nicht abgeschlossen.|
|**Ethererum Wallet anlegen:** Partiy wird dich beim ersten Start auffordern, eine Wallet anzulegen. Folge einfach den angezeigten Schritten.|
|**Ether kaufen**: Falls du bereits Bitcoin besitzt, kannst Du direkt in Parity Bitcoins in Ether umtauschen. Dazu einfach auf einen deiner Accounts klicken und dann oben in der Symbolleiste auf „SHAPESHIFT“ klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/shapeshift.png" width="100%" height="100%">|
|Man kann auch direkt mit Kreditkarte, Giropay, Sofort-Überweisung usw. Ether kaufen, bspw. über „Anycoin Direct“. Weitere Möglichkeiten: Coinbase, Poloniex, Cex.io, Coinhose usw. Achtung: immer darauf achten, auch wirklich ETHER zu kaufen und keine Bitcoins. Du wirst bei jedem Anbieter irgendwann deine Ether-Wallet-Adresse angeben müssen. Diese findest du in Parity (und muss per Copy & Paste übertragen werden).|


[zum Inhaltsverzeichnis](#sfc)

## <a name="kapb"></a>Kapitel B: Erste Schritte mit dem Dax Daily Knock-Out Future

**Die nachfolgenden Schritte bite erst ausführen, wenn Parity vollständig synchron mit der Ethereum-Blockchain ist (siehe oben.**

### Schritt 1: Den Smart Financial Contract in die eigene Wallet einfügen

| Schritt        | Screenshot (klick zum Vergrößern)|
|:-------------|:------------------|
|Als erstes muss in Parity die Möglichkeit aktiviert werden, mit Smart Contracts zu interagieren. Dazu in den Bereich "Settings" (ganz oben rechts) gehen und die Checkbox bei "Contracts" aktivieren.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/activatecontracts.png" width="100%" height="100%">|
|Als nächstes holen wir uns den Smart Financial Contract "Dax Daily Knock-Out Future" in unser Profil. Im Hauptmenü ganz oben erscheint nun der Menüpunkt "Contracts". Bitte darauf klicken, anschließen auf "+ WATCH" klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractswatch.png" width="100%" height="100%">|
|Im nächsten Fenster "Custom Contract" auswählen und "Next" klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/customcontract.png" width="100%" height="100%">|
|Das nächste Fenster hat viele Eingabefelder. Wir gehen jedes einzelne durch.||
|**network address**: hier muss die Adresse des Smart Financial Contracts per copy&paste eingegeben werden. Die Adresse lautet: ```0x78D8AeAE03C12164189272Abd3934c98c87Ff6A4```|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/networkaddress.png" width="100%" height="100%">|
|Bei "Contract Name" kann ein beliebiger Name eingetragen werden (bspw. "Dax Daily Knock-Out Future"). Dieser erscheint dann in der Liste aller Smart Contracts.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractname.png" width="100%" height="100%">|
|Das Feld "contract description" ist optional. Hier können weitere Infos hinterlegt werden (bspw. "Prototype").|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractdescription.png" width="100%" height="100%">|
|Das Feld "contract abi" muss wieder per copy&paste befüllt werden. Dort muss folgender Text eingefügt werden (Hinweis: es muss der gesamte Quelltext in der unten abgebildeten Box kopiert werden).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractabi.png" width="100%" height="100%">|
```
[{"constant":true,"inputs":[],"name":"LastTradingDay","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"WithdrawMyProfits","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"AccountAddress","type":"address"}],"name":"ShowMyProfits","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"GoLong","outputs":[{"name":"","type":"uint256"}],"payable":true,"type":"function"},{"constant":true,"inputs":[],"name":"NextExpirationDay","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"}],"name":"ShowLongsVsShorts","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"ImportantInfo","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"GoShort","outputs":[{"name":"","type":"uint256"}],"payable":true,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"},{"name":"AccountAddress","type":"address"}],"name":"getMyLongs","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"}],"name":"getGER30CloseAsOf","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"},{"name":"AccountAddress","type":"address"}],"name":"getMyShorts","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"inputs":[],"payable":true,"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":false,"name":"","type":"string"}],"name":"ErrorMessage","type":"event"}]
```

|Abschließen auf "+ ADD CONTRACT" klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/addcontract.png" width="100%" height="100%">|
|:-------------|:------------------|

[zum Inhaltsverzeichnis](#sfc)

### Schritt 2: Trades duchführen

| Schritt        | Screenshot (klick zum Vergrößern)|
|:-------------|:------------------|
|Erstelle deine Prognose (Dax schließt morgen höher oder tiefer)||
|Gehe in Parity auf „Contracts“ und klicke auf den Smart Financial Contract, den du gerade angelegt hast.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contracts.png" width="100%" height="100%">|
|Klicke auf „Execute“|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractsexecute.png" width="100%" height="100%">|
|Wähle im Feld "function to execute" die Funktion „GoLong“ (wenn du einen steigenden Dax erwartest“) oder „GoShort“ (wenn du einen fallenden Dax erwartest).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/functiontoexecute.png" width="100%" height="100%">|
|Wähle den Betrag, den du investieren möchtest und gibt ihn im Feld "transaction value" ein. **Mindestens 0,1 Ether, Maximal 2 Ether**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionvalue.png" width="100%" height="100%">|
|**Wichtig: Zahlen werden in Parity in amerikanischem Format eingegeben. Das heißt: Punkt statt Komma!** ||
|Klicken Sie anschließend auf "Post Transaction" (unten rechts).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/posttransaction.png" width="100%" height="100%">|
|Jetzt noch das Passwort für deinen Account eingeben (welches du beim ersten Start von Parity vergeben hast) und "CONFIRM REQUEST" klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/confirmrequest.png" width="100%" height="100%">|
|Deine Transaktion wird an die Blockchain "Ethereum" übergeben. Das kann ein paar Momente dauern.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionposted.png" width="100%" height="100%">|
|Man kann den Status der Transaktion live in der Blockchain verfolgen, indem man auf die Transaktionsnummer klickt.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionposted2.png" width="100%" height="100%">|
|Im Blockchain-Scanner sieht man den aktuellen Stand der Confirmations. Ab 6 Conformations sind Transaktionen in der Regel durchgeführt.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/etherscan2.png" width="100%" height="100%">|

[zum Inhaltsverzeichnis](#sfc)

### Schritt 3: Informationen abrufen

Wenn du den Smart Financial Contract aufrufst, landest Sie auf der Startseite des Smart Contracts. Auf dieser Startseite befinden sich einige Funktionen, mit denen du Informationen zu deinen Investments, zum aktuellen Long/Short-Verhältnis usw. abrufen kannst. Die einzelnen Funktionen werden nachfolgend erklärt. Bei einigen Funktionen muss noch ein Input-Parameter eingegeben werden, bspw. ein Datum (im Format JJJMMTT), und die Abfrage mit einem Klick auf "Query" ausgeführt werden.

**Übersichtsseite eines Smart Financial Contracts:**
<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractoverview.png" width="100%" height="100%">



| Schritt        | Screenshot (klick zum Vergrößern)|
|:-------------|:------------------|
|**Nächsten Verfallstag abrufen:** Im Feld "NextExpirationDay" steht der nächste Verfallstag des Daily Futures. Sämtliche Trades, die du jetzt tätigst, sind für diesen Verfallstag gültig. Das heißt bspw.: Wenn du short gehst (Funktion "GoShort"), dann gehst du für den "NextExpirationDay" short. Wenn am "NextExpirationDay" der Dax tiefer schließt als am Vortag, dann wäre dein Short-Deal erfolgreich.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/nextexpirationday.png" width="100%" height="100%">|
|**Long/Short-Verhältnis abrufen:** Das Long/Short-Verhältnis zeigt an, wie viele Ether an einem Tag Long und Short investiert sind. Dabei handelt es sich um eine Momentaufnahme. Es können noch weitere Longs oder Shorts für den NextExpirationDay hinzukommen, bis keine Trades mehr angenommen werden. Je mehr Longs bzw. Shorts investiert sind, desto höher ist der mögliche Profit für die Gegenpositionen. Um das Long/Short-Verhältnis für einen Handelstag (Expiration Day) abzurufen, muss das Datum des Handelstages eingegeben werden. **Dabei ist das Format JJJMMTT (YYYYMMDD) einzuhalten. Der 10.04.2017 ist in diesem Format beispielsweise 20170410.** Das Long/Short-Verhältnis kann auch für Tage aus der Vergangenheit abgerufen werden.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/longsvsshorts.png" width="100%" height="100%">|
|**Aktuelle Infos:** Im Feld "ImportantInfo" werden aktuelle Informationen dargestellt. Üblicherweise wird hier ein Verweis auf www.smart-financial-contracts.de dargestellt.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/importantinfo.png" width="100%" height="100%">|
|Der **LastTradingDay** bezeichnet den letzten Handelstag, für den noch Trades angenommen werden (sozusagen ein Ablaufdatum). Danach ist der Smart Financial Contract nicht mehr handelbar.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/lasttradingday.png" width="100%" height="100%">|
|**Schlusskurse der Vergangenheit abrufen.** Mit der Funktion **getGER30CloseAsOf** können Schlusskurse aus der Vergangenheit abgerufen werden. Um Schlusskurse abzurufen, muss das Datum des Handelstages eingegeben werden. **Dabei ist das Format JJJMMTT (YYYYMMDD) einzuhalten. Der 10.04.2017 ist in diesem Format beispielsweise 20170410.** |<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getger30closesasof.png" width="100%" height="100%">|
|**Meine Investments abrufen.** Mit den Funktionen **getMyLongs** und **getMyShorts** können Long- bzw. Short-Investments für den jeweiligen Handelstag abgerufen werden. Dazu muss das Datum des Handelstages eingegeben werden. **Dabei ist das Format JJJMMTT (YYYYMMDD) einzuhalten. Der 10.04.2017 ist in diesem Format beispielsweise 20170410.**. Weiterhin muss der **Account** eingegeben werden. Beim Klick in das Feld *AccountAddress:address* wird Parity ein Auswahlfeld öffnen, in dem der Account ausgewählt werden kann. (alternativ kann man hier auch Ethereum-Adressen eingeben). Nach Klick auf *Query* wird der investierte Betrag angezeigt. **Der Betrag wird dabei in der Währungseinheit "Wei" angezeigt** und sieht deshalb so "riesig" aus. Um den **Betrag in Ether anzeigen zu lassen**, einfach auf den kleinen Schieberegler daneben klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getmylongs.png" width="100%" height="100%">|
|Die Funktion **ShowMyProfit** zeigt alle bisher aufgelaufenen und noch nicht ausgezahlten Umsätze an. Das ist der Betrag, der beim Aufruf der Funktion **WithDrawMyProfit** überwiesen würde. Auch hier muss wieder die Adresse des Ethereum-Kontos angegeben werden. Nach Klick auf *Query* wird der  Betrag angezeigt. **Der Betrag wird dabei in der Währungseinheit "Wei" angezeigt** und sieht deshalb so "riesig" aus. Um den **Betrag in Ether anzeigen zu lassen**, einfach auf den kleinen Schieberegler daneben klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/showmyprofits.png" width="100%" height="100%">|


[zum Inhaltsverzeichnis](#sfc)


### Schritt 4: Gewinne auszahlen lassen

Gewinne können am Folgetag des Verfallstages abgerufen werden. 
#### Beispiel:
> - Der DAX schloss am Freitag, 07.04.2017, bei 12225,06 Punkten.
> - Ich entschließe mich am Sonntag, 09.04.2017, "SHORT" zu gehen und stelle meinen Trade wie oben beschrieben ein.
> - Der nächste Verfallstag (**NextExpirationDay**) ist Montag (10.07.2017).
> - Daher ist mein Trade gültig für Montag, 10.07.2017.
> - Der Dax schließt am Montag, 10.07.2017, bei 12200,52 Punkten und ist damit gesunken. Mein Short-Trade geht auf.
> - Ich kann meinen Gewinn ab Dienstag, 11.07.2017, abrufen.
> 
> |Freitag|Sonntag|Montag|Dienstag|
> |:-----|:-----|:-----|:-----|
> |Dax schließt bei 12225,06|Ich gehe short|Dax schließt bei 12200,52|Ich lasse meinen Gewinnn auszahlen|

| Schritt        | Screenshot (klick zum Vergrößern)|
|:-------------|:------------------|
|Klicke auf „Execute“|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractsexecute.png" width="30%" height="30%">|
|Wähle im Feld "function to execute" die Funktion „WithDrawMyProfts“.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/functiontoexecute.png" width="100%" height="100%">|
|Klick auf "Post Transaction"|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/posttransaction.png" width="50%" height="50%">|






> ** Bei Fragen oder Problemen bitte einen "Issue" eröffnen (siehe ganz oben, auf den Reiter "Issue" klicken, dann "New Issue". Ein github-Account ist dafür notwendig, kann aber schnell angelegt werden).