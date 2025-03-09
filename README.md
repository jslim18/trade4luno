# trade4luno - Luno Engine API

Source API LUNO: https://www.luno.com/en/developers/api
Source API SINEGY: https://exchange.sinegy.com/exchange-documentation/api
Source API TOKENIZE: https://tokenizemalaysia.com/tokenize-api-introduction
Source API MX: https://openapi.mx.exchange/index.html
Source API HATA: https://support.hata.io/support/solutions/articles/150000150817-how-to-create-api-keys-on-hata


[First Milestone]
All commands capable to check syntax error. No rubbish intake will have to check and filter off or display error in command appropriately. Eg. Integer quantity and rate must be positive. All these commands are yet to find tune. Commands should be capable to carry -flag parameters like DOS old days so to extract useful information and locate further narrow down result then execute orders

All connections to Luno, Sinegy, Tokenize, MX and HATA must be clearly documented and tidy up code in separate function written in app scripts

I will provide you a Google spreadsheet and a template in app scripts. The app scripts is connected to Telegram bot, the Spreadsheet and various Exchanges. You have to provide me the code made to the Exchange API connections above and able to perform the tricks below 

Apps script connected to Spreadsheet are already well written in template with demo Gsheet
Apps script connected to Telegram are already well written in template with demo Telegram bot

You have to work out code in Apps script to various Exchanges using API for my trade purpose below. Operator controls from Telegram bot, issues command to various Exchanges to complete orders manually or to execute auto-assisted orders accurately in volatile market without the needs to login each and individual portal. Operator should be able to check $status (inclusive set default channel and set default pair), $balance, execute order either $LMT (Limit Order) mode or $INS (Instant Order) mode and able to use $showq (market queue), $showd (market last done price), $showo (MyOrder) and $showtx (MyTransactionHistory). All my preference data can be collected and kept in spreadsheet logs later to determine the average buy/sell rate and display accordingly to operator on demand basis to make better informed decisions 

[Last Milestone]
The other AI portion is the ability of the bot to queue order between the spread at a preset interval. Only in a specific circumstances trigger where the criterion is the exchange has wide market spread and low liquidity. Tight market spread may not work so effectively, not my interest. That means bot will auto queue to the first position of buy queue or sell queue without human interaction. If position isn't favourable bot will cancel queue order and place it again with another rate say every 5 minutes. Once trade matches successfully then deliver a message to Telegram 

$status
API Connection LIVE/FAIL
Which channel 
Which pair

$switch: LUNO -ON
$switch: LUNO -OFF
$switch: TOKENIZE

set$channel: #LUNO
set$pair: #BTCMYR

$balance: FIAT
LUNO: You have RM200 (Free) and RM0 (Lock) #240308
MX: You have RM350 (Free) #240308
$balance: BTC, SOL
$balance: #MX
Present current balance amount in account 

Order type: LMT/INS

$showq: BTC #LUNO -3
Best Buy Q vs Best Sell Q
.. Qty1Rate ..:.. Rate4Qty ..
.. Qty2Rate ..:.. Rate5Qty ..
.. Qty3Rate ..:.. Rate6Qty ..

$showd: ETH #SINEGY -2
Last done price and quantity date/time2
Last done price and quantity date/time1

$showo: BTC
$showo: BTC #LUNO -B
$showo: BTC #LUNO -S
r$trade: ALL #LUNO
r$trade: 3
Remove and cancel trade order number 3

Quick command
set$LMT<< 0.005@375000
set$LMT<< 0.005@=1875
set$LMT: WTB 0.005 BTC Rate 375000 #LUNO
set$LMT: WTS 0.005 BTC Rate 375000 #LUNO
Quick command 
$INS<< 0.005
$INS: WTB 0.005 BTC #SINEGY
$INS: WTS 0.005 BTC #MX

Bought 0.002 BTC @ RM280000 by LUNO
=-RM560
Sold 0.001 BTC @ RM300000 by LUNO
=+RM300

$showtx: 240308 -5
$showtx: 240303~240308
Average rate, Qty, Sum
$showtx: 2403
