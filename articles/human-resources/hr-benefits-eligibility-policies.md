---
title: Políticas de qualificação para benefícios
description: Este tópico fornece informações sobre as diretivas de qualificação de benefício, o que define quem está qualificado para benefícios específicos.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e1f64a0beffe12f6b4e0ad53d3bbaa96822dc7e8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066034"
---
# <a name="benefit-eligibility-policies"></a>Políticas de qualificação para benefícios


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico fornece informações sobre as diretivas de qualificação de benefício, o que define quem está qualificado para benefícios específicos.

Quando você cria benefícios, você decide qual deles estarão disponíveis para quais funcionários. A tabela a seguir mostra exemplos de benefícios que você pode disponibilizar para funcionários específicos.

| Benefício          | Para quem o benefício está disponível |
|------------------|---------------------------------|
| Seguro de saúde | Todos os funcionários                   |
| Telefone celular     | Equipe de vendas, executivos         |
| Estacionamento   | Executivos                      |

Os seguintes componentes são usados para criar políticas de qualificação:

-   Tipos de regra de política
-   Políticas de qualificação para benefícios

Os tipos de regras de política definem os parâmetros de consulta que são usados quando você desenvolve regras de política específicas. Depois de criar tipos de regras de política, você pode criar políticas de qualificação de benefícios. As políticas permitem criar uma coleção de regras que se aplicam a uma ou mais entidades legais. Em cada política, é possível visualizar qualquer um dos tipos de regras de política de qualificação de benefícios criados anteriormente. 

Você define o escopo da regra na política. Por exemplo, se você criar um tipo de regras de política de qualificação de benefícios que foi nomeada como **Executivo**, você pode qual regra é essa nessa política. Neste exemplo, a regra pode indicar que qualquer cargo que contenha a palavra "executivo" deve ser incluído na regra. Após definir os parâmetros da regra ou das regras que são incluídas na política, você pode atribuir uma regra específica ao benefício.






[!INCLUDE[footer-include](../includes/footer-banner.md)]
