---
title: Fornecedor mestre integrado
description: Este tópico descreve a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2b8d1e872b65f40a63c0771cb95d8d1c0875ca82
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249077"
---
## <a name="integrated-vendor-master"></a>Fornecedor mestre integrado

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

O termo *fornecedor* se refere a uma organização fornecedora ou um único proprietário que faça parte do processo da cadeia de suprimentos, e que forneça mercadorias para a empresa. Embora *fornecedor* seja um conceito estabelecido em aplicativos do Finance and Operations, ele não existe em outros aplicativos do Dynamics 365. No lugar, algumas empresas sobrecarregam a entidade Conta para armazenar as informações do cliente e as informações do fornecedor. Outras empresas usam um conceito personalizado de fornecedor. A integração do Common Data Service oferece suporte a ambos os designs. Portanto, você pode habilitar qualquer design, dependendo de seu cenário empresarial.

A integração de dados do fornecedor entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 permite vários dados mestre. Independentemente de onde os dados do fornecedor são originados, eles são integrados em segundo plano nos limites dos aplicativos e nas diferenças de infraestrutura. 

### <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor

Se você deseja usar outros aplicativos do Dynamics 365 para controlar os fornecedores e quer separar as informações dos fornecedores das informações dos clientes, pode usar o novo design de fornecedor.

![Fluxo de dados do fornecedor](media/dual-write-vendor-data-flow.png)

Se você deseja usar outros aplicativos do Dynamics 365 para controlar os fornecedores e quer continuar usando a entidade Conta para armazenar informações dos fornecedores, pode usar o novo design de fornecedor estendido. Nesse design, informações estendidas de fornecedor, como grupo de fornecedores e o perfil de lançamentos do fornecedor, são armazenadas nos detalhes do fornecedor.

![Fluxo de dados estendidos do fornecedor](media/dual-write-vendor-detail.jpg)

As informações de contato do fornecedor se assemelham às informações de contato do cliente. Em segundo plano, as informações de contato da pessoa são armazenadas e recuperadas das mesmas entidades.

## <a name="templates"></a>Modelos

Os dados do fornecedor incluem todas as informações sobre ele, como o grupo de fornecedores, os endereços, as informações de contato, o perfil do pagamento e o perfil da fatura. Uma coleção de mapas de entidades funcionam juntos durante a interação de dados do fornecedor, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations  | Outros aplicativos do Dynamics 365
------------------------|---------------------------------
Fornecedor V2               | Conta
Fornecedor V2               | Msdyn\_vendors
Contatos do CDS V2         | Contato
Grupos de fornecedores           | Msdyn\_vendorgroups
Método de Pagamento do Fornecedor   | Msdyn\_vendorpaymentmethods
Agenda de Pagamento        | Msdyn\_paymentschedules
Agenda de Pagamento        | Msdyn\_paymentschedulelines
Dia de pagamento CDS         | Msdyn\_paymentdays
Linhas de dia de pagamento CDS   | Msdyn\_paymentdaylines
Condições de Pagamento        | Msdyn\_paymentterms
Afixos de Nome            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Fornecedor V2 e Conta 

As empresas que usam a entidade Conta para armazenar informações do fornecedor podem continuar a usá-la da mesma maneira. Elas também podem aproveitar a funcionalidade explícita de fornecedor que será disponibilizada com a integração de aplicativos do Finance and Operations.

## <a name="vendor-v2-and-msdyn_vendors"></a>Fornecedor V2 e Msdyn\_vendors

As empresas que usam uma solução personalizado para fornecedores podem aproveitar o conceito de fornecedor pronto para uso que está sendo apresentado no Common Data Service com a integração de aplicativos do Finance and Operations. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Contatos

Esse modelo sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores entre os aplicativos do Finance and Operations e outros aplicativos do Dynamics 365. Para obter detalhes do mapa de entidades, consulte [Cliente mestre integrado](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Grupos de Fornecedores

Esse modelo sincroniza as informações do grupo de fornecedores entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
DESCRIÇÃO | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Método de Pagamento do Fornecedor

Esse modelo sincroniza as informações de método de pagamento de fornecedores entre o Finance and Operations e outros aplicativos do Dynamics 365.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
NOME | = | msdyn\_name
DESCRIÇÃO | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

