---
title: Definir frequência de pagamento
description: O Microsoft Dynamics 365 Human Resources usa frequências de pagamento para calcular o salário anual de benefício, determinar o valor Premium do benefício que um funcionário paga a cada período de pagamento e com qual frequência os fornecedores são pagos.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a5d562b64a161891bf34b0dfa94fbf68325e21b5
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429948"
---
# <a name="set-up-payment-frequencies"></a>Definir frequência de pagamento

O Microsoft Dynamics 365 Human Resources usa frequências de pagamento para calcular o salário anual de benefício, determinar o valor Premium do benefício que um funcionário paga a cada período de pagamento e com qual frequência os fornecedores são pagos.

As frequências de pagamento de benefício usam os fatores de conversão para converter os períodos de pagamento de benefício entre frequências mensais, quinzenais, semanais e diárias. Isso permite que as empresas definam a interdependência entre as frequências de pagamento em um plano de benefícios.

Os campos de fatores de conversão identificam o fator de conversão da frequência de pagamento para os períodos de pagamento padrão e permitem que o sistema faça cálculos entre frequências de pagamento. O valor do fator de conversão também determina o valor Premium do benefício que um funcionário deve pagar a cada frequência de pagamento.

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Frequências de pagamento**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Frequência de pagamento** | Um nome exclusivo da frequência de pagamento. |
   | **Descrição** | Uma descrição da frequência de pagamento. |
   | **Período** | O período apropriado que melhor corresponde ao provedor de benefícios e à frequência de pagamento do funcionário. A lista de períodos é composta pelos períodos de pagamento padrão. |
   | **Número de períodos de pagamento** | O número de períodos de pagamento que representam a frequência com que os funcionários ou o fornecedor de benefícios são pagos. Esse valor será usado para calcular o valor do salário do benefício anual do funcionário. |
   | **Fator de Conversão Anual** | O fator de conversão anual para a frequência de pagamento. Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais/1 ano) = 12 |
   | **Fator de conversão semestral** | O fator de conversão semestral para a frequência de pagamento. Por exemplo, o fator de conversão semestral para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 2 vezes ao ano) = 6 |
   | **Fator de conversão trimestral** | O fator de conversão trimestral para a frequência de pagamento. Por exemplo, o fator de conversão trimestral para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais por 4 trimestres) = 3 |
   | **Fator de conversão mensal** | O fator de conversão mensal para a frequência de pagamento. Por exemplo, o fator de conversão mensal para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 12 meses) = 1 |
   | **Fator de conversão quinzenal** | O fator de conversão quinzenal para a frequência de pagamento. Por exemplo, o fator de conversão quinzenal para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 24 (2x ao mês)) = 0,5 | 
   | **Fator de conversão quinzenal** | O fator de conversão anual para a frequência de pagamento. Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 26 semanas) = 0,461538 |
   | **Fator de conversão semanal** | O fator de conversão anual para a frequência de pagamento. Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 52 semanas) = 0,230769 |
   | **Fator de conversão diário** | O fator de conversão anual para a frequência de pagamento. Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 365 dias) = 0,032877 |
   | **Fator de conversão por hora** | O fator de conversão anual para a frequência de pagamento. Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é: </br></br>(12 pagamentos mensais / 2080 horas) = 0,005769

4. Selecione **Salvar**. 
