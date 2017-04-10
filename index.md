<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/ws_logo.png" width="20%" height="20%">

# Prototype: Daily Future Knock-Out
---
**Inhaltsübersicht**

-	[Eigenschaften des „Dax Daily Knock-Out Future“](#eigenschaften-des-dax-daily-knock-out-future)
-	[Anleitung](#anleitung)
    - [Kapitel A: Einstieg in die Ethereum Blockchain mit dem Ethereum-Browser "Parity"](#kapitel-a-einstieg-in-die-ethereum-blockchain-mit-dem-ethereum-browser-parity)
	- [Kapitel B: Erste Schritte mit dem Dax Daily Knock-Out Future](#kapitel-b-erste-schritte-mit-dem-dax-daily-knock-out-future)
		- [Schritt 1: Den Smart Financial Contract in die eigene Wallet einfügen](#schritt-1-den-smart-financial-contract-in-die-eigene-wallet-einf%C3%BCgen)
		- [Schritt 2: Trades duchführen](#schritt-2-trades-duchf%C3%BChren)


Diese Anleitung beschreibt, wie in den Smart Financial Contract „Dax Daily Knock-Out Future“ investiert werden kann.
Das Ziel dieses Smart Financial Contracts ist es, zu zeigen, dass Finanz-Terminkontrakte in der Blockchain „Ethereum“ abgebildet werden können. In diesem Sinn wird dieser Prototyp Interessierten als TEST zur Verfügung gestellt. Die Benutzung der Software geschieht auf eigene Gefahr; jede Haftung für Schäden oder Verluste ist ausgeschlossen. Insbesondere die allgemeinen Risiken bei der Nutzung von Ethereum gelten auch hier, siehe <a href="https://www.ethereum.org/agreement" target="_blank">https://www.ethereum.org/agreement</a>.

## Eigenschaften des „Dax Daily Knock-Out Future“

-	Der Trader setzt auf die Dax-Entwicklung des Folgetages. Man kann „LONG“ oder „SHORT“ gehen. Schließt der Dax am Folgetag über dem Schlusskurs des vorigen Tages, dann ist de „Dax Daily Knock-Out Future“ LONG, ansonsten short.
-	Beispiel:
    - Es ist Montag, 18:00 Uhr. Der Dax schloss um 17:45 Uhr mit 11.800,12 Punkten
    - Meine Prognose für Dienstag (der Folgetage) ist, dass der Dax höher schließt
    - Also gehe ich „LONG“
    - Am Dienstag schließt der Dax bei 11.900,45 Punkten, also höher als am Montag. LONG war somit die richtige Prognose.  - Die Auszahlung meines Gewinns (inkl. Invest natürlich) ist ab dem Folgetag (Mittwoch) möglich
    - Test
- Der Prototyp „Dax Daily Knock-Out Future“ ist ein recht einfaches Knock-Out Produkt. Trifft die Prognose ein, also Dax schließt höher oder tiefer, erhält man einen Gewinn. Trifft die eigene Prognose nicht ein, verliert man den investierten Ether-Betrag. Die Summe aller Verlust-Trades wird auf die Gewinner-Trades aufgeteilt. Der potentielle Gewinn ist somit abhängig von der Long/Short-Quota.

## Anleitung
---
Wer sich bereits mit Ethereum auskennt und eine Wallet mit ein paar Ether besetzt, kann direkt ins [Kapitel B](#kapb). springen.
Als kurze Einführung in Ethereum dient auch dieses Video: 
<a href="https://youtu.be/j23HnORQXvs" target="_blank">https://youtu.be/j23HnORQXvs</a>

Eine Einführung in Ethereum mit vielen Links ist hier zu finden: 
<a href="http://bit.ly/2mURyWZ" target="_blank">http://bit.ly/2mURyWZ</a>

## Kapitel A: Einstieg in die Ethereum Blockchain mit dem Ethereum-Browser "Parity"


| Schritt        | Screenshot|
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




## <a name="kapb"></a>Kapitel B: Erste Schritte mit dem Dax Daily Knock-Out Future

**Die nachfolgenden Schritte bite erst ausführen, wenn Parity vollständig synchron mit der Ethereum-Blockchain ist (siehe oben.**

### Schritt 1: Den Smart Financial Contract in die eigene Wallet einfügen

| Schritt        | Screenshot|
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



### Schritt 2: Trades duchführen

| Schritt        | Screenshot|
|:-------------|:------------------|
|Erstelle deine Prognose (Dax schließt morgen höher oder tiefer)||
|Gehe in Parity auf „Contracts“ und klicke auf den Smart Financial Contract, den du gerade angelegt hast.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/contracts.png" width="100%" height="100%">|
|Klicke auf „Execute“|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/contractsexecute.png" width="100%" height="100%">|
|Wähle im Feld "function to execute" die Funktion „GoLong“ (wenn du einen steigenden Dax erwartest“) oder „GoShort“ (wenn du einen fallenden Dax erwartest).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/functiontoexecute.png" width="100%" height="100%">|
|Wähle den Betrag, den du investieren möchtest und gibt ihn im Feld "transaction value" ein. **Mindestens 0,1 Ether, Maximal 2 Ether**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/transactionavalue.png" width="100%" height="100%">|
|**Wichtig: Zahlen werden in Parity in amerikanischem Format eingegeben. Das heißt: Punkt statt Komma!** ||
|Klicken Sie anschließend auf "Post Transaction" (unten rechts).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/posttransaction.png" width="100%" height="100%">|
|Jetzt noch das Passwort für deinen Account eingeben (welches du beim ersten Start von Parity vergeben hast) und "CONFIRM REQUEST" klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/conformrequest.png" width="100%" height="100%">|
|Deine Transaktion wird an die Blockchain "Ethereum" übergeben. Das kann ein paar Momente dauern.||


| Schritt        | Screnshit          |
|:-------------|:------------------|
| tes tes test | <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/test.jpg" width="12%" height="12%"> |
|Der Smart Financial Contract ist nun vorbereitet, um Transaktionen durchzuführen.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/contraticon.jpg" width="12%" height="12%">|



Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](#header-4).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [](#header-1)Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## [](#header-2)Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### [](#header-3)Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [](#header-4)Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [](#header-5)Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [](#header-6)Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![](https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/test.jpg =200x200)

<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/test.jpg" width="12%" height="12%">



### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
