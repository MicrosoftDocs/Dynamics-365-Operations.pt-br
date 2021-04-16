---
title: Políticas de qualificação para benefícios
description: Este artigo fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a5046f1d32fb965c7cb3793daf1ba40b9c2a1d10
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805889"
---
# <a name="benefit-eligibility-policies"></a>Políticas de qualificação para benefícios

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.

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