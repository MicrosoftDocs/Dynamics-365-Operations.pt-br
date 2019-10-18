---
title: Sites e depósitos integrados
description: Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service.
author: benebotg
manager: AnnBe
ms.date: 15/8/2019
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
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 38c0b9add014867eb203aeeb02217cbc4c4d0b00
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249123"
---
# <a name="integrated-sites-and-warehouses"></a>Sites e depósitos integrados

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service. Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management. Eles são usados para modelar a cadeia de fornecedores da sua empresa.

## <a name="templates"></a>Modelos

A integração com o Common Data Service disponibiliza esses conceitos e todas as informações relacionadas no Common Data Service por meio das entidades de dados de site e depósito na tabela a seguir.

Aplicativos do Finance and Operations | Outros aplicativos do Dynamics 365
--------------------------|---------------------------------
Sites                     | msdyn_operationalsites
Depósitos                | depósitos

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="operational-sites"></a>Sites operacionais

Os sites operacionais estão disponíveis no Common Data Service usando os seguintes mapeamentos.

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
SITENAME | >< | msdyn_name
DEFAULTFINANCIALDIMENSIONVALUE | >< | msdyn_defaultfinancialdimensionvalue
DEFAULTINVENTORYSTATUSID | >< | msdyn_defaultinventorystatusid
ISRECEIVINGWAREHOUSEOVERRIDEALLOWED | >< | msdyn_isreceivingwarehouseoverrideallowed
SITEID | >< | msdyn_siteid
SITENAME | >< | msdyn_sitename
TAXBRANCHCODE | >< | msdyn_taxbranchcode
FISCALESTABLISHMENTID | >< | msdyn_fiscalestablishmentid
ISPRIMARYADDRESSASSIGNED | >< | msdyn_isprimaryaddressassigned
PRIMARYADDRESSCITY | >< | msdyn_primaryaddresscity
PRIMARYADDRESSCOUNTRYREGIONID | >< | msdyn_primaryaddresscountryregionid
PRIMARYADDRESSCOUNTYID | >< | msdyn_primaryaddresscountyid
PRIMARYADDRESSDISTRICTNAME | >< | msdyn_primaryaddressdistrictname
PRIMARYADDRESSLATITUDE | >< | msdyn_primaryaddresslatitude
PRIMARYADDRESSLOCATIONROLES | >< | msdyn_primaryaddresslocationrole
PRIMARYADDRESSLOCATIONSALESTAXGROUPCODE | >< | msdyn_primaryaddresslocationsalestaxgroupcode
PRIMARYADDRESSLONGITUDE | >< | msdyn_primaryaddresslongitude
PRIMARYADDRESSSTATEID | >< | msdyn_primaryaddressstateid
PRIMARYADDRESSSTREET | >< | msdyn_primaryaddressstreet
PRIMARYADDRESSZIPCODE | >< | msdyn_primaryaddresszipcode
PRIMARYADDRESSBUILDINGCOMPLIMENT | >< | msdyn_primaryaddressbuildingcompliment
PRIMARYADDRESSCITYINKANA | >< | msdyn_primaryaddresscityinkana
PRIMARYADDRESSSTREETINKANA | >< | msdyn_primaryaddressstreetinkana
PRIMARYADDRESSDESCRIPTION | >< | msdyn_primaryaddressdescription
FORMATTEDPRIMARYADDRESS | >< | msdyn_formattedprimaryaddress
WILLMASTERPLANNEDINTRASITEMOVEMENTSUSETRANSFERJOURNALS | >< | msdyn_masterplannedusestransferjournal
PRIMARYADDRESSPOSTBOX | >< | msdyn_primaryaddresspostbox
PRIMARYADDRESSSTREETNUMBER | >< | msdyn_primaryaddressstreetnumber


## <a name="warehouses"></a>Depósitos

Os depósitos estão disponíveis por meio dos mapeamentos a seguir.

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
DEFAULTCONTAINERTYPEID | >> | msdyn_defaultcontainertypeid
AREITEMSCOVERAGEPLANNEDMANUALLY | >> | msdyn_areitemscoverageplannedmanually
ARELABORSTANDARDSALLOWED | >> | msdyn_arelaborstandardsallowed
PRIMARYADDRESSBUILDINGCOMPLIMENT | >> | msdyn_primaryaddressbuildingcompliment
PRIMARYADDRESSPOSTBOX | >> | msdyn_primaryaddresspostbox
PRIMARYADDRESSSTREETNUMBER | >> | msdyn_primaryaddressstreetnumber
AREWAREHOUSELOCATIONCHECKDIGITSUNIQUE | >> | msdyn_arewarehouselocationcheckdigitsunique
INVENTORYCOUNTINGREASONCODEPOLICYNAME | >> | msdyn_inventorycountingreasoncodepolicyname
AUTOUPDATESHIPMENTRULE | >> | msdyn_autoupdateshipmentrule
WAREHOUSERELEASERESERVATIONREQUIREMENTRULE | >> | msdyn_warehousereleasereservationrequirement
EXTERNALLYLOCATEDWAREHOUSEVENDORACCOUNTNUMBER | >> | msdyn_externallylocatedwarehousevendoraccountnu
INVENTORYSTATUSCHANGERESERVATIONREMOVALLEVEL | >> | msdyn_inventorystatuschangereservationremoval
WAREHOUSEWORKPROCESSINGPOLICYNAME | >> | msdyn_warehouseworkprocessingpolicyname
ISFALLBACKWAREHOUSE | >> | msdyn_isfallbackwarehouse
ISFINANCIALNEGATIVERETAILSTOREINVENTORYALLOWED | >> | msdyn_financialnegativestoreinventoryallowed
ISPALLETMOVEMENTDURINGCYCLECOUNTINGALLOWED | >> | msdyn_palletmovementduringcyclecountingallowed
ISPHYSICALNEGATIVERETAILSTOREINVENTORYALLOWED | >> | msdyn_physicalnegativestoreinventoryallowed
ISREFILLEDFROMMAINWAREHOUSE | >> | msdyn_isrefilledfrommainwarehouse
ISRETAILSTOREWAREHOUSE | >> | msdyn_isretailstorewarehouse
MAINREFILLINGWAREHOUSEID | >> | msdyn_mainrefillingwarehouseid.msdyn_warehouseid
MASTERPLANNINGWORKCALENDARDID | >> | msdyn_masterplanningworkcalendarid
MAXIMUMBATCHPICKINGLISTQUANTITY | >> | msdyn_maximumbatchpickinglistquantity
MAXIMUMPICKINGLISTLINEQUANTITY | >> | msdyn_maximumpickinglistlinequantity
OPERATIONALSITEID | >> | msdyn_operationalsiteid.msdyn_siteid
QUARANTINEWAREHOUSEID | >> | msdyn_quarantinewarehouseid.msdyn_warehouseid
RETAILSTOREQUANTITYALLOCATIONREPLENISMENTRULEWEIGHT | > | msdyn_storeqtyallocationreplenishmentweight
SHOULDWAREHOUSELOCATIONIDINCLUDEAISLEID | >> | msdyn_shouldwarehouselocationincludeaisleid
TRANSITWAREHOUSEID | >> | msdyn_transitwarehouseid.msdyn_warehouseid
WAREHOUSEID | >> | msdyn_warehouseid
WAREHOUSELOCATIONIDBINIDFORMAT | >> | msdyn_warehouselocationidbinidformat
WAREHOUSELOCATIONIDRACKIDFORMAT | >> | msdyn_warehouselocationidrackidformat
WAREHOUSELOCATIONIDSHELFIDFORMAT | >> | msdyn_warehouselocationidshelfidformat
WAREHOUSENAME | >> | msdyn_name
WAREHOUSENAME | >> | msdyn_warehousename
WAREHOUSESPECIFICDEFAULTINVENTORYSTATUSID | >> | msdyn_warehousespecificdefaultinventorystatusid
WAREHOUSETYPE | >> | msdyn_warehousetype
ISPRIMARYADDRESSASSIGNED | >> | msdyn_isprimaryaddressassigned
PRIMARYADDRESSCITY | >> | msdyn_primaryaddresscity
PRIMARYADDRESSCOUNTRYREGIONID | >> | msdyn_primaryaddresscountryregionid
PRIMARYADDRESSCOUNTYID | >> | msdyn_primaryaddresscountyid
PRIMARYADDRESSDISTRICTNAME | >> | msdyn_primaryaddressdistrictname
PRIMARYADDRESSLATITUDE | >> | msdyn_primaryaddresslatitude
PRIMARYADDRESSLONGITUDE | >> | msdyn_primaryaddresslongitude
PRIMARYADDRESSLOCATIONROLES | >> | msdyn_primaryaddresslocationroles
PRIMARYADDRESSLOCATIONSALESTAXGROUPCODE | >> | msdyn_primaryaddresslocationsalestaxgroupcode
PRIMARYADDRESSSTATEID | >> | msdyn_primaryaddressstateid
PRIMARYADDRESSSTREET | >> | msdyn_primaryaddressstreet
PRIMARYADDRESSZIPCODE | >> | msdyn_primaryaddresszipcode
EXTERNALLYLOCATEDWAREHOUSECUSTOMERACCOUNTNUMBER | >> | msdyn_externallylocatedwarehousecustomeraccount
PRIMARYADDRESSCITYINKANA | >> | msdyn_primaryaddresscityinkana
PRIMARYADDRESSSTREETINKANA | >> | msdyn_primaryaddressstreetinkana
PRIMARYADDRESSDESCRIPTION | >> | msdyn_primaryaddressdescription
AREADVANCEDWAREHOUSEMANAGEMENTPROCESSESENABLED | >> | msdyn_uesadvancedwarehousemanagementprocesses
AREPICKINGLISTSDELIVERYMODESPECIFIC | >> | msdyn_arepickinglistsdeliverymodespecific
AREPICKINGLISTSSHIPMENTSPECIFICONLY | >> | msdyn_arepickinglistshipmentspecificonly
FORMATTEDPRIMARYADDRESS | >> | msdyn_formattedprimaryaddress
ISBILLOFLADINGPRINTINGBEFORESHIPMENTCONFIRMATIONENABLED | >> | msdyn_printbillofladingbeforeshipconfirmation
RAWMATERIALPICKINGINVENTORYISSUESTATUS | >> | msdyn_rawmaterialpickinginventoryissuestatus
WILLAUTOMATICLOADRELEASERESERVEINVENTORY | >> | msdyn_willautomaticloadreleaseinventory
WILLINVENTORYSTATUSCHANGEREMOVEBLOCKING | >> | msdyn_willinventorystatuschangeremoveblocking
WILLMANUALLOADRELEASERESERVEINVENTORY | >> | msdyn_willmanualloadreleasereserveinventory
WILLORDERRELEASINGCONSOLIDATESHIPMENTS | >> | msdyn_willorderreleasingconsolidateshipments
WILLPRODUCTIONBOMSRESERVEWAREHOUSELEVELONLY | >> | msdyn_productionbomsreservewarehouselevel
WILLSHIPPINGCANCELLATIONDECREMENTLOADQUANITY | >> | msdyn_shippingcanceldecrementloadquantity
WILLWAREHOUSELOCATIONIDINCLUDEBINIDBYDEFAULT | >> | msdyn_warehouselocationidincludeblindid
WILLWAREHOUSELOCATIONIDINCLUDERACKIDBYDEFAULT | >> | msdyn_warehouselocationincluderackidbydefault
WILLWAREHOUSELOCATIONIDINCLUDESHELFIDBYDEFAULT | >> | msdyn_warehouselocationidincludeshelfid
