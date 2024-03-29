---
title: Definir e gerenciar um programa de benefícios
description: O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este artigo contém informações sobre como configurar e gerenciar os benefícios.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 08b80f4f90ce6b4a286120cd6329a45a4ebd3f71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877791"
---
# <a name="define-and-manage-a-benefits-program"></a>Definir e gerenciar um programa de benefícios


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O Human Resources fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este artigo contém informações sobre como configurar e gerenciar os benefícios.

## <a name="benefit-setup"></a>Configuração de benefício

Para que os trabalhadores sejam inscritos nos benefícios, você deve criar os elementos de cada benefício. Esses elementos combinam planos de benefícios semelhantes e definem as configurações padrão, como taxas de dedução e detalhes da contabilidade. Muitas dessas configurações podem ser ajustadas quando os trabalhadores são inscritos posteriormente no benefício. Para cada plano de benefícios, uma organização pode oferecer várias opções de inscrição, ou um trabalhador pode cancelar a inscrição no plano. 

[![Fluxo do processo de benefício.](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementos do benefício

Antes de começar a criar benefícios e inscrever trabalhadores neles, você deve definir os elementos que constituem um benefício: o tipo, o plano e as opções.

-   **Tipo** – Um conjunto de planos para um benefício específico, como médico ou estacionamento.
-   **Plano** – Um benefício específico que é contratado por um fornecedor.
-   **Opção** – O nível de cobertura, como apenas do funcionário, ou do funcionário e do cônjuge/parceiro.

Para cada tipo de benefício, como oftalmológico ou odontológico, uma organização pode oferecer um ou mais planos para os trabalhadores. Para cada plano, a organização pode oferecer opções diferentes. Por exemplo, os trabalhadores podem comprar cobertura adicional de seguro de vida temporário em uma, duas ou três vezes o salário anual. Cada combinação de um plano e opções se torna um benefício no qual os trabalhadores podem se inscrever. 

[![pic de benefício.](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Qualificação
Muitos fatores determinam a qualificação do trabalhador para os vários tipos de benefícios oferecidos por um empregador. Ao criar um benefício no Dynamics 365 Human Resources, você pode definir o tipo de qualificação que se aplica a esse benefício. 

Você pode tornar um benefício disponível a todos os funcionários. Por exemplo, algumas empresas oferecem estacionamento a todos os funcionários como um benefício adicional. Ao criar esse benefício, você define a qualificação como **Todos os trabalhadores estão qualificados**. 

Para outros benefícios, como consignações e arrecadações de imposto, a qualificação não se aplica. Ao criar esses tipos de benefícios, você definiu a qualificação para **Ignorar processo de qualificação**. 

Por fim, a qualificação de benefícios pode ser baseada na regra. Por exemplo, uma empresa oferece dois tipos de benefícios de seguro de vida aos funcionários. Os funcionários executivos estão qualificados para um plano de seguro de vida, enquanto que todos os funcionários em tempo integral que estão qualificados para outro plano de seguro de vida. No Human Resources você pode criar uma regra de elegibilidade de benefícios para encontrar todos os funcionários executivos e outra regra para encontrar funcionários de tempo integral e aplicá-las ao benefício apropriado.

## <a name="enrollment"></a>Inscrição
Após criar os benefícios oferecidos por sua empresa e determinar a qualificação, você poderá inscrever os trabalhadores em benefícios. Você pode inscrever um único trabalhador em benefícios, ou pode inscrever vários trabalhadores em um ou mais benefícios durante um único processo. 

Às vezes, uma organização deixa de oferecer alguns benefícios. Nesse caso, você deve atualizar o benefício e os trabalhadores que estão incluídos nele. O vencimento de benefício em massa permite que você altere a data de vencimento de um benefício e as inscrições de trabalhadores desse benefício ao mesmo tempo. Você também pode selecionar vários trabalhadores inscritos em um benefício e alterar a data final da cobertura. 

Da mesma forma, a extensão do benefício em massa permite que você estenda a data de vencimento de um benefício e de inscrições de trabalhadores para esse benefício, caso você opte por oferecer um benefício por mais tempo do que planejado originalmente.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
