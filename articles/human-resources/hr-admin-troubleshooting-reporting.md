---
title: Opções de relatório
description: Este artigo explica como resolver o problema em que um cliente deseja personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ee6dba5e37877f1c0b3b9df8306b3194ea2f3e4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008163"
---
# <a name="reporting-options"></a>Opções de relatório

**Detalhes do ambiente**

Esse problema aplica-se a todos os ambientes.

**Sintoma**

O cliente quer personalizar relatórios do Microsoft Dynamics 365 Human Resources ou criar novos relatórios.

**Saída**

O usuário não pode personalizar os relatórios do Microsoft Power BI integrados.

**Solução**

- Os dados do Human Resources que fluem para o Common Data Service podem ser relatados por meio do conector Power Apps Common Data Service para o Power BI Desktop. Observe que o Common Data Service contém um subconjunto de dados do Human Resources. Para obter mais informações sobre o Power BI e os painéis, consulte [Criar relatórios e painéis do Power BI com o Common Data Service do Power Apps](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- O relatório eletrônico (ER) está disponível para alguns relatórios no Human Resources. Personalizações voltadas para clientes podem ser realizadas por meio de opções de configuração ER.
- Os dados podem ser exportados para o Microsoft Excel ou o Microsoft Word usando as diversas entidades de dados que o Human Resources fornece por meio da integração do Microsoft Office.

**Solução de longo prazo**

Opções adicionais do Power BI estarão disponíveis e mais dados e entidades farão parte do Common Data Service.
