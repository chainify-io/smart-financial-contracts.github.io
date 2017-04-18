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
This manual describes how to invest into the Smart Financial Contract "Germany 30 Daily Knock-Out Future". Purpose of this Smart Financial Contract is to demonstrate the mechanism of financial derivatives on the blockchain "Ethereum".
The prototype is considered as a **TEST** version and not for productive usage. Provision only for private use, for scientific purposes, and to be used at your own risk! By using Ethereum, you should also consider general risks associated with it: see <a href="https://www.ethereum.org/agreement" target="_blank">https://www.ethereum.org/agreement</a>.


## Properties of the "Germany 30 Daly Knock-Out Future"

- Traders and investors can place LONG and SHORT trades on the Germany 30 index. This index is derived from the DAX index.
- Trades are valid for the Dax's result on the following day. If next day, the Dax closes higher, LONG traders win, of lower, SHORT traders win.
> - Example:
>	- It's Monday 6pm. Dax (Germany 30 index) closes at 11,800.12 points.
>	- I assume the Dax will close higher (above 11,800.12 points) tomorrow, on Tuesday.
>	- I go LONG with the Smart Financial Contract, I initiate the GoLong function Monday evening.
>	- The Dax closes 11,900.45 points on Tuesday which is higher than on Monday, thus LONG. My trade was successful.
>	- I can withdraw my profit and invest the following day, Wednesday.
- This prototype Smart Financial Contract is a simple knock out product for **demonstration purposes**. If the forecast (long or short) was right, the investor gets the invest plus a premium back. If the forecast was wrong, the investor loses her invest - this is the "knock out" characteristic.
- The sum of all losing trades will be shared with winning trades based on share of total invest. Potential profits depend on the long/short quota.	


## Instructions
---

If you already know how to use Ethereum and own some Ethers, you can continue with [Capter B](#kapb).

This video is a quick introduction into Ethereum: <a href="https://youtu.be/j23HnORQXvs" target="_blank">https://youtu.be/j23HnORQXvs</a>

Introdution documents and links with more background information can be found here: 
<a href="http://bit.ly/2mURyWZ" target="_blank">http://bit.ly/2mURyWZ</a>

## Chapter A: Onboarding to Ethereum with "Parity", a Ethereum Browser


| Step        | Screenshot (click to enlarge)|
|:-------------|:------------------|
|Download an Ethereum browser. This prototype is tested with the Ethereum browser "Parity". Go to  <a href="https://parity.io/parity.html" target="_blank">https://parity.io/parity.html</a> and click "Get Parity".| <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getParity.png" width="50%" height="50%">|
|Install Parity (execute InstallParity.exe)|
|Run Parity. You should find Parity in the Windows Start menu.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityStartMenu.png" width="100%" height="100%">|
|Once started, Parity should appear as a tray icon in the info area of your taskbar.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityIcon.png" width="100%" height="100%">|
|Parity's graphical user interface (GUI) should start automatically. If that is not the case: Parity's GUI can be accessed via you standard browser. Just open the URL http://127.0.0.1:8180 to get to Parity's user interface.| <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityHome.png" width="100%" height="100%">|
|**Important: on first startup right after installation, Parity has to perform a full synchronisation with the Ethereum blockchain. This is necessary in order to ensure reliable and secure execution of you Ethereum transactions. The synchroisation process takes a while. You can check the synchronisation status in the Parity screen bottom right.**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/paritySyncStatus.png" width="100%" height="100%">|
|If you want to ensure a proper synchronisation, just compare you local synchronisation status with the public blockchain. The synchronisation is displayed in "blocks". On http://www.etherscan.io you can find the current blockchain's latest block. Your Parity instance should display the same number.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/etherscan.png" width="100%" height="100%"> In the screenshot, the local Parity instancen synchronized 3,402,297 blocks, while http://etherscan.io  shows 3,468,505 blocks. In this example, the synchronisation is not finished yet.|
|**Create your Ethererum Wallet:** <br> On first start, Parity will ask you to create an Ethereum wallet. Just follow the steps through.||
|**Buying ETHER, Ethereums crypto currency**: If you already own Bitcoin, you can exchange them with Ether directly in Parity: Select on of you accounts and click „SHAPESHIFT“ klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/shapeshift.png" width="100%" height="100%">|
|You can also buy Ether with credit card, GiroPay, SOFORT, etc. There are several providers out there like „Anycoin Direct“, Coinbase, Poloniex, Cex.io, Coinhouse and many more. Important: pay a heed to really buy ETHER and no other crypto currency. In any step of purchasing Ether, you will eventually enter your Ethereum address. You can find it in Parity and need to copy&paste it to the Ether market place.|


[back to contents](#sfc)

## <a name="kapb"></a>Chapter B: First steps with our Daily Knock-Out Future

**Important: Please only perform the following steps if your local Parity instance is fully synchronized with the Ethereum blockchain. **

### Step 1: Include the Smart Financial Contract into your Wallet

| Step        | Screenshot (click to enlarge)|
|:-------------|:------------------|
|First you need to unlock the "Contract" button in Parity. Go to "Settings" (top right) and activate the checkbox "Contracts".|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/activatecontracts.png" width="100%" height="100%">|
|Now you need to include the Smart Financial Contract "Dax Daily Knock-Out Future" into your wallet. Click the menu item "Contracts" on the main menu (on the top). Next, click "+ WATCH".|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractswatch.png" width="100%" height="100%">|
|In the next screen, select "Custom Contract" and click "Next".|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/customcontract.png" width="100%" height="100%">|
|The next screen has several input fields. We go through each one by one.||
|**network address**: in this field, you have to copy&paste the Smart Financial Contract's address on the Ethereum blockchain. It is: ```0x78D8AeAE03C12164189272Abd3934c98c87Ff6A4```|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/networkaddress.png" width="100%" height="100%">|
|Enter a name of your choice in  the field **"Contract Name"**(e.g. "Dax Daily Knock-Out Future").|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractname.png" width="100%" height="100%">|
|The field **"contract description"** is optional.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractdescription.png" width="100%" height="100%">|
|The field **"contract abi"** has to be filled out by copy&paste. Copy the following code snippet into that field (imporant: ensure to have selected the whole snippet text from the box below before copy&pasting ist).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractabi.png" width="100%" height="100%">|
```
[{"constant":true,"inputs":[],"name":"LastTradingDay","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"WithdrawMyProfits","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"AccountAddress","type":"address"}],"name":"ShowMyProfits","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"GoLong","outputs":[{"name":"","type":"uint256"}],"payable":true,"type":"function"},{"constant":true,"inputs":[],"name":"NextExpirationDay","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"}],"name":"ShowLongsVsShorts","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"ImportantInfo","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":false,"inputs":[],"name":"GoShort","outputs":[{"name":"","type":"uint256"}],"payable":true,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"},{"name":"AccountAddress","type":"address"}],"name":"getMyLongs","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"}],"name":"getGER30CloseAsOf","outputs":[{"name":"","type":"string"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"Date","type":"uint256"},{"name":"AccountAddress","type":"address"}],"name":"getMyShorts","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"inputs":[],"payable":true,"type":"constructor"},{"anonymous":false,"inputs":[{"indexed":false,"name":"","type":"string"}],"name":"ErrorMessage","type":"event"}]
```

|Finally, click **"+ ADD CONTRACT"**.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/addcontract.png" width="100%" height="100%">|
|:-------------|:------------------|

[back to contents](#sfc)

### Step 2: Execute trades

| Step        | Screenshot (click to enlarge)|
|:-------------|:------------------|
|Make forecast for the German stock market index||
|In Parity, click  „Contracts“ and select the Smart Financial Contract that you just included (step 1).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contracts.png" width="100%" height="100%">|
|Click „Execute“|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractsexecute.png" width="100%" height="100%">|
|In the field "function to execute", select **„GoLong“** (if you expect a bullish German stock market index) oder **„GoShort“** (if you expect the German stock market index to decline).|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/functiontoexecute.png" width="100%" height="100%">|
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




---

> ** Bei Fragen oder Problemen bitte einen "Issue" eröffnen (siehe ganz oben, auf den Reiter "Issue" klicken, dann "New Issue". Ein github-Account ist dafür notwendig, kann aber schnell angelegt werden).**

---