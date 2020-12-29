---
title: Configurar programas de crédito flexível
description: É possível usar os programas de crédito flexível no Microsoft Dynamics 365 Human Resources para inscrever funcionários em benefícios de acordo com um número predeterminado de créditos flexíveis.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 157984479a041f0bf4555aa96ed3f7e62e415d81
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417240"
---
# <a name="set-up-flex-credit-programs"></a>Configurar programas de crédito flexível

É possível usar os programas de crédito flexível no Microsoft Dynamics 365 Human Resources para inscrever funcionários em benefícios de acordo com um número predeterminado de créditos flexíveis. Os funcionários podem escolher como alocar seus créditos flexíveis. Por exemplo, se um funcionário estiver coberto pelo plano de seguro de saúde de seu cônjuge, ele poderá usar os créditos que usaria na cobertura de saúde para obter outros benefícios. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Planos** , selecione **Programas de crédito flexível**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **ID do crédito do benefício** | O identificador exclusivo do programa de crédito flexível. |
   | **Descrição** | Uma descrição do programa de crédito flexível. | 
   | **Data Inicial** | A data em que o programa de crédito flexível se torna ativo. |
   | **Data Final** | A data final do programa de crédito flexível. Você pode deixar o valor padrão (12/31/2154) para indicar que o programa de crédito flexível não tem uma expiração programada. |
   | **Valor total do crédito** | O número de créditos que cada funcionário precisará usar para seus benefícios. |
   | **Regra de rateio** | A regra a ser usada para ratear créditos flexíveis quando um funcionário é contratado no meio do período do crédito flexível. </br></br><ul><li>**Nenhum** – O funcionário não recebe créditos flexíveis se for contratado após o início do período do programa.</li><li>**Crédito completo** – O funcionário recebe o valor total dos créditos flexíveis, independentemente de quando eles são contratados.</li><li>**Rateio** – O funcionário recebe um valor rateado de créditos flexíveis com base na data de início.</li></ul> |
   | **Fórmula de rateio do crédito flexível** | A regra a ser usada para rateio de créditos flexíveis para funcionários contratados no meio de um período de benefício para o programa de crédito flexível. O rateio é baseado na data de início do emprego. Esse campo é usado apenas se você selecionar **Rateio** no campo **Regra de rateio**. </br></br><ul><li>**Diário** – Rateia o número de créditos flexíveis que um funcionário recebe diariamente. O número total de créditos flexíveis é dividido pelo número de dias no período. Por exemplo, se seu período de benefício for de 400 dias, o sistema dividirá o número total de créditos flexíveis por 400 para calcular o número de créditos flexíveis que os funcionários recebem por dia.</li><li>**Mês atual** – Rateia o número de créditos flexíveis que um funcionário recebe mensalmente, arredondado para o mês atual. O número total de créditos flexíveis é dividido pelo número de meses no período. Por exemplo, se seu período de benefício for de 15 meses, o sistema dividirá o número total de créditos flexíveis por 15 para calcular o número de créditos flexíveis que os funcionários recebem por mês.</li><li>**Mês seguinte** – Rateia o número de créditos flexíveis que um funcionário recebe mensalmente, arredondado para o próximo mês. O número total de créditos flexíveis é dividido pelo número de meses no período. Por exemplo, se seu período de benefício for de 15 meses, o sistema dividirá o número total de créditos flexíveis por 15 para calcular o número de créditos flexíveis que os funcionários recebem por mês.</li></ul> |
   
