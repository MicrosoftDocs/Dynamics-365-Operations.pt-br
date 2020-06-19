---
title: Políticas de qualificação para benefícios
description: Este artigo fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: fd4def17bf60ae2812927221c45547c5ac379f2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430822"
---
# <a name="benefit-eligibility-policies"></a>Políticas de qualificação para benefícios

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




