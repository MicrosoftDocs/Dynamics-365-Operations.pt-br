---
title: Opções de relatório em Talent
description: Este tópico explica como resolver o problema onde um cliente quer personalizar relatórios do Microsoft Dynamics 365 Talent ou criar novos relatórios.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 50342c847200d015a66c6f22007070bb26c6caef
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009343"
---
# <a name="reporting-options-in-talent"></a>Opções de relatório no Talent

[!include [banner](includes/banner.md)]

**Detalhes do ambiente**

Esse problema aplica-se a todos os ambientes.

**Sintoma**

O cliente quer personalizar relatórios do Microsoft Dynamics 365 Talent ou criar novos relatórios.

**Saída**

O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.

**Solução**

- Os dados do Core HR que fluem para o Common Data Service podem ser relatados por meio do conector PowerApps Common Data Service para o Power BI Desktop. Observe que o Common Data Service contém um subconjunto de dados do Core HR. Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do PowerApps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Relatório eletrônico (ER) está disponível para alguns relatórios no Talent. Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.
- Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Talent fornece por meio da integração do Microsoft Office.

**Solução de longo prazo**

Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Common Data Service.
