---
title: Razão integrado
description: Este tópico descreve a integração de dados do razão entre o Finance and Operations e outros aplicativos do Dynamics 365 usando o Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e5bdef8ef440bd5ef84060b61b4cf1d0088f204c
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416824"
---
# <a name="integrated-ledger"></a>Razão integrado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Em um aplicativo de negócios, os dados do razão definem a configuração principal relacionada ao modo como a empresa faz negócios. Por exemplo, os dados do razão descrevem o ano fiscal seguido pela empresa, as moedas usadas nas transações e as contas que ela utiliza. Este tópico descreve a integração desses dados financeiros principais.

## <a name="templates"></a>Modelos

Os dados do razão incluem um conjunto de mapas de tabelas financeiras centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement     | descrição
---------------------------------|----------------------------------|------------
[Taxas de Câmbio do CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Plano de Contas](mapping-reference.md#121) | msdyn_chartofaccountses |
[Moedas](mapping-reference.md#218) | transactioncurrencies |
[Par de moedas de taxa de câmbio](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Tipo de taxa de câmbio](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Formato da dimensão financeira](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Dimensões financeiras](mapping-reference.md#128) | msdyn_dimensionattributes |
[Entidade de integração do calendário fiscal](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Período do calendário fiscal](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Entidade de integração do ano do calendário fiscal](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Ledger](mapping-reference.md#148) | msdyn_ledgers |
[Conta principal](mapping-reference.md#152) | msdyn_mainaccounts |
[Categorias de conta principal](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
