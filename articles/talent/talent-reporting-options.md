---
title: "Opções de relatório em Talent"
description: "Este tópico explica como resolver o problema onde um cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a>Opções de relatório em Talent

[!include [banner](includes/banner.md)]

**Detalhes do ambiente**

Esse problema aplica-se a todos os ambientes.

**Sintoma**

O cliente quer personalizar relatórios do Microsoft Dynamics 365 for Talent ou criar novos relatórios.

**Saída**

O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.

**Solução**

- Os dados de Core HR que fluem para Common Data Service de aplicativos podem ser relatados por meio do conector PowerApps CDS para Power BI Desktop. Observe que Common Data Service para aplicativos contém um subconjunto de dados Core HR. Para obter mais informações sobre Power BI e painéis, consulte [Criar relatórios do Power BI e painéis com Common Data Service do PowerApps](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- Relatório eletrônico (ER) está disponível para alguns relatórios no Talent. Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.
- Os dados podem ser exportados para Microsoft Excel ou Microsoft Word usando as diversas entidades de dados que Talent fornece por meio da integração do Microsoft Office.

**Solução de longo prazo**

As opções adicionais do Power BI estarão disponíveis, e mais dados e entidades serão parte de Common Data Service para aplicativos.

