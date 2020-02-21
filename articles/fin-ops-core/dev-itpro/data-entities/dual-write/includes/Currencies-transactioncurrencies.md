## <a name="currencies-to-transactioncurrencies"></a>Moedas para transactioncurrencies

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Common Data Service.

Filtro de origem: ((CURRENCYCODE! = "999"))

Campo do Finance and Operations | Tipo de mapa | Outro campo Dynamics 365 | Valor padrão
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NAME | = | currencyname | 
SYMBOL | = | currencysymbol | 
none | >> | exchangerate | 1
