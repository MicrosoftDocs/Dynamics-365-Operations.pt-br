---
title: Políticas de qualificação para benefícios
description: Este artigo fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ad179e505d045dc40898105e1cfd090daafa09a8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "855953"
---
# <a name="benefit-eligibility-policies"></a>Políticas de qualificação para benefícios

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.

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

Você define o escopo da regra na política. Por exemplo, se você criar um tipo de regras de política de qualificação de benefícios que foi nomeada como **Executivo**, você pode qual regra é essa nessa política. Neste exemplo, a regra pode indicar que o título do trabalho que contenha a palavra “executivo” deve ser incluída na regra. Após definir os parâmetros da regra ou das regras que são incluídas na política, você pode atribuir uma regra específica ao benefício.

<a name="additional-resources"></a>Recursos adicionais
--------

[Definir e gerenciar um programa de benefício](manage-benefit-program.md)



