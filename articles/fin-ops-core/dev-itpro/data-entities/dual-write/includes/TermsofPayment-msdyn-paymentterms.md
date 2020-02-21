## <a name="terms-of-payment-to-msdyn_paymentterms"></a>Condições de pagamento para msdyn_paymentterms

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Common Data Service.

Campo do Finance and Operations | Tipo de mapa | Outro campo Dynamics 365 | Valor padrão
---|---|---|---
DESCRIPTION | = | msdyn_description | 
NAME | = | msdyn_name | 
NUMBEROFMONTHS | = | msdyn_numberofmonth | 
CUTOFFDAYOFMONTH | = | msdyn_cutoffdayofmonth | 
ISCASHPAYMENT | >< | msdyn_iscashpayment | 
NUMBEROFDAYS | = | msdyn_days | 
ISCERTIFIEDCOMPANYCHECK | >< | msdyn_iscertifiedcompanycheck | 
ISDEFAULTPAYMENTTERM | >< | msdyn_isdefaultpaymentterm | 
CREDITCARDPAYMENTTYPE | >< | msdyn_creditcardpaymenttype | 
CREDITCARDCREDITCHECKTYPE | >< | msdyn_creditcardcreditchecktype | 
PAYMENTDAYNAME | = | msdyn_paymentdayname.msdyn_name | 
PAYMENTMETHODTYPE | >< | msdyn_paymentmethodtype | 
PAYMENTSCHEDULENAME | = | msdyn_paymentschedulename.msdyn_name | 
