<a name="sfc"></a>
<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/ws_logo.png" width="20%" height="20%">

# Prototype: Daily Future Knock-Out
---
## Contents

-	[Properties of the "Germany 30 Daly Knock-Out Future"](#properties-of-the-germany-30-daily-knock-out-future)
-	[Instructions](#instructions)
    - [Chapter A: Onboarding to Ethereum with "Parity", a Ethereum Browser](#chapter-a-onboarding-to-ethereum-with-parity-a-ethereum-browser)
	- [Chapter B: First steps with our Daily Knock-Out Future](#chapter-b-first-steps-with-our-daily-knock-out-future)
		- [Step 1: Include the Smart Financial Contract into your Wallet](#step-1-include-the-smart-financial-contract-into-your-wallet)
		- [Step 2: Execute trades](#step-2-execute-trades)
		- [Step 3: Get Information from the Smart Financial Contract](#step-3-get-information-from-the-smart-financial-contract)
		- [Step 4: Withdraw profits](#step-4-withdraw-profits)
		
		
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
|Download an Ethereum browser. <br> This prototype is tested with the Ethereum browser "Parity". Go to  <a href="https://parity.io/parity.html" target="_blank">https://parity.io/parity.html</a> and click "Get Parity".| <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getParity.png" width="50%" height="50%">|
|Install Parity (execute InstallParity.exe)|
|Run Parity. You should find Parity in the Windows Start menu.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityStartMenu.png" width="100%" height="100%">|
|Once started, Parity should appear as a tray icon in the info area of your taskbar.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityIcon.png" width="100%" height="100%">|
|Parity's graphical user interface (GUI) should start automatically. If that is not the case: Parity's GUI can be accessed via you standard browser. Just open the URL http://127.0.0.1:8180 to get to Parity's user interface.| <img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/parityHome.png" width="100%" height="100%">|
|**Important: on first startup right after installation, Parity has to perform a full synchronisation with the Ethereum blockchain. This is necessary in order to ensure reliable and secure execution of you Ethereum transactions. The synchroisation process takes a while. You can check the synchronisation status in the Parity screen bottom right.**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/paritySyncStatus.png" width="100%" height="100%">|
|If you want to ensure a proper synchronisation, just compare you local synchronisation status with the public blockchain. The synchronisation is displayed in "blocks". On http://www.etherscan.io you can find the current blockchain's latest block. Your Parity instance should display the same number.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/etherscan.png" width="100%" height="100%"> In the screenshot, the local Parity instancen synchronized 3,402,297 blocks, while http://etherscan.io  shows 3,468,505 blocks. In this example, the synchronisation is not finished yet.|
|**Create your Ethererum Wallet:** <br> On first start, Parity will ask you to create an Ethereum wallet. Just follow the steps through.||
|**Buying ETHER, Ethereums crypto currency**: <br> If you already own Bitcoin, you can exchange them with Ether directly in Parity: Select on of you accounts and click „SHAPESHIFT“ klicken.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/shapeshift.png" width="100%" height="100%">|
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
|Choose the investment amount. <br> Enter your investment amount in field **"transaction value"** ein. **A minimum of 0.1 has to be invested. As this is only a demo version of a Smart Financial Contract, the maximum invest is 2 Ether**|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionvalue.png" width="100%" height="100%">|
|**Numbers are entered in American format. Thus:  dot "." is used as decimal mark, not commas(,), e.g. one tenth is 0.1 (NOT 0,1)** ||
|Click "Post Transaction" (bottom right) to confirm your transaction.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/posttransaction.png" width="100%" height="100%">|
|Enter the password of your Ethereum account (that you have given on first start of Parity) and click "CONFIRM REQUEST".|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/confirmrequest.png" width="100%" height="100%">|
|Your transaction is delivered to and confirmed by the Ethereum blockchain. This may take a while.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionposted.png" width="100%" height="100%">|
|You can follow your transaction's status by clicking the transaction number. This opens the blockchain scanner "etherscan.io"|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/transactionposted2.png" width="100%" height="100%">|
|The blockchain scanner shows the current confirmation status of you transaction. Usually, 6 confirmations make a transaction "confirmed".|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/etherscan2.png" width="100%" height="100%">|

[back to contents](#sfc)

### Step 3: Get Information from the Smart Financial Contract

When clicking the Smart Financial Contract in Parity, you get to the main page for that Smart Contract. That page shows some information and queries about the Smart Financial Contract, your investment, the current Long/Short ratio etc. Each information field and query is described below.
Some queries require you to input parameters, e.g. the date. **Dates are entered in format "YYYYMMDD". Thus, April 27, 2017 is 20170427.**


**Screenshot: Main Page of a Smart Financial Contract:**
<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractoverview.png" width="100%" height="100%">



| Step        | Screenshot (click to enlarge)|
|:-------------|:------------------|
|**Get next expiration day:** <br> The field "NextExpirationDay" shows the next expiration day of the daily future. All trades (long or short) that you execute right now will be valid for that day. For example: If you invest short (function "GoShort"), you go short for day that's displayed in "NextExpirationDay". If "NextExpirationDay", the German stock market index closes lower than the day before, your short deal will be successful.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/nextexpirationday.png" width="100%" height="100%">|
|**Get Long Short ratio:** <br> The field **ShowLongsVsShorts** shows all invested Ether (both, long investments and short investments) for one day. The more longs or shorts are invested, the higher is the possible profit for counter positions. In order to get the Long Short Ratio for a specific trading day (Expiration Day), just enter the date and click "query". **Dates are entered in format "YYYYMMDD". E.g. April 27, 2017 is 20170427.** The long short ration can be queried for all dates, also for the past.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/longsvsshorts.png" width="100%" height="100%">|
|**Important Information:** <br> The field "ImportantInfo" shows current important information. Usually it shows the link to www.smart-financial-contracts.de.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/importantinfo.png" width="100%" height="100%">|
|**LastTradingDay**:<br>The **LastTradingDay** is the last day you can invest in the Smart Financial Contract. After that date, the Smart Financial Contract cannot be traded any more. Neverteheless, the Smart Financial Contract will be stored in the blockchain forever, e.g. for information retrieval purposes.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/lasttradingday.png" width="100%" height="100%">|
|**Get closing prices for the underlying asset.**<br> The function **getGER30CloseAsOf** gives you closing prices of the underlying asset on a daily bases. In order to get a closing price, you need to specify the day (date). **Dates are entered in format "YYYYMMDD". E.g. April 27, 2017 is 20170427.** |<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getger30closesasof.png" width="100%" height="100%">|
|**Show my investments.**<br> The queries **getMyLongs** and **getMyShorts** show your long and short investments on a daily basis. You need to enter the day you want to query. **Dates are entered in format "YYYYMMDD". E.g. April 27, 2017 is 20170427.**. You further need to choose your Ethereum **Account**. If you click the field *AccountAddress:address* Parity will open a selection box to select your account (you could also enter an Ethereum address). Click *Query* to get the invested amount in Ether. **By default, the amount will be shown in the Etheruem currency unit "Wei"**, that's why the number looks so large. In order to get the **amount in Ether**, just click the small slide control.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/getmylongs.png" width="100%" height="100%">|
|**Show my accumulated profits:**<br> The function **ShowMyProfit** shows all accumulated profits and invests that have not been withdrawn yet. This is the amount, that the function **WithDrawMyProfit** would withdraw to your Ethereum account. Again, you need to enter your Ethereum address. Click *Query* to get the amount. **By default, the amount will be shown in the Etheruem currency unit "Wei"**, that's why the number looks so large. In order to get the **amount in Ether**, just click the small slide control.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/showmyprofits.png" width="100%" height="100%">|


[back to contents](#sfc)


### Step 4: Withdraw profits

Profits can be withdrawn the day that follows the expiration day.

#### Example:
> - It is Friday (April 7, 2017), the German stock market index closed at 12225.06 points.
> - On Sunday (April 9, 2017), I decide to go "SHORT" and initiate my trade (as described above).
> - The next expiration day (**NextExpirationDay**) is Monday (April 10, 2017).
> - Thus, my trade is valide for Monday (April 10, 2017).
> - On Monday (April 10, 2017), the Germany stock market index closes at  12200.52 points, thus it is bearish and therefore short. My short trade wins.
> - I can withdraw my profit and invest on Tuesday (April 11, 2017).
> 
> |Friday|Sunday|Monday|Tuesday|
> |:-----|:-----|:-----|:-----|
> |German stock market index closes 12225.06|I invest SHORT|German stock market index closes 12200.52|I withdraw my profit|

| Step        | Screenshot (click to enlarge)|
|:-------------|:------------------|
|Click „Execute“|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/contractsexecute.png" width="30%" height="30%">|
|Choose "function to execute" ==> „WithDrawMyProfts“.|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/functiontoexecute.png" width="100%" height="100%">|
|Click "Post Transaction"|<img src="https://raw.githubusercontent.com/smart-financial-contracts/smart-financial-contracts.github.io/master/images/posttransaction.png" width="50%" height="50%">|




---

> ** In case of problems or questions, please open an "Issue" (see on the very top of this page, click the tab "Issue", then "New Issue". You need a github account, but this can be created very quickly).**

---