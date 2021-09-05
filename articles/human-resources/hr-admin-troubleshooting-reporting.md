---
title: Opções de relatório
description: Este tópico explica como personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 706e901e89fa618540067d68546be1cef1ee7148
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413364"
---
# <a name="reporting-options"></a>Opções de relatório

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Detalhes do ambiente**

Esse problema aplica-se a todos os ambientes.

**Sintoma**

O cliente quer personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.

**Problema**

O usuário não pode personalizar os relatórios do Microsoft Power BI inseridos.

**Solução**

- Os dados do Human Resources que fluem para o Dataverse podem ser relatados por meio do conector Power Apps Dataverse para o Power BI Desktop. Observe que o Dataverse contém um subconjunto de dados do Human Resources. Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- O relatório eletrônico (ER) está disponível para alguns relatórios no Human Resources. Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.
- Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Human Resources fornece por meio da integração do Microsoft Office.

**Solução de longo prazo**

Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Dataverse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
