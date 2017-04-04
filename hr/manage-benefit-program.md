---
title: "Definir e gerenciar um programa de benefícios"
description: "O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este artigo fornece informações sobre como configurar e gerenciar benefícios."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Definir e gerenciar um programa de benefícios

O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este tópico fornece informações sobre como configurar benefícios gerenciar.

<a name="benefit-setup"></a>Configuração de benefício
-------------

Para que os trabalhadores sejam inscritos nos benefícios, você deve criar os elementos de cada benefício. Esses elementos combinam planos de benefícios semelhantes e definem as configurações padrão, como taxas de dedução e detalhes da contabilidade. Muitas dessas configurações podem ser ajustadas quando os trabalhadores são inscritos posteriormente no benefício. Para cada plano de benefícios, uma organização pode oferecer várias opções de inscrição, ou um trabalhador pode cancelar a inscrição no plano. 

[fluxo de processo de benefício![(]. /media/benefit-process-flow1.png)](. /media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementos do benefício
Antes de começar a criar benefícios e inscrever trabalhadores neles, você deve definir os elementos que constituem um benefício: o tipo, o plano e as opções.

-   **Tipo** – Um conjunto de planos para um benefício específico, como médico ou estacionamento.
-   **Plano** – Um benefício específico que é contratado por um fornecedor.
-   **Opção** – O nível de cobertura, como apenas do funcionário, ou do funcionário e do cônjuge/parceiro.

Para cada tipo de benefício, como oftalmológico ou dentário, uma organização pode oferecer um ou mais planos para os trabalhadores. Para cada plano, a organização pode oferecer opções diferentes. Por exemplo, os trabalhadores podem comprar cobertura adicional de seguro de vida temporário em uma, duas ou três vezes o salário anual. Cada combinação de um plano e opções se torna um benefício no qual os trabalhadores podem se inscrever. 

[PIC de benefício![(]. /media/benefit-pic.png)](. /media/benefit-pic.png)

## <a name="eligibility"></a>Qualificação
Muitos fatores determinam a qualificação do trabalhador para os vários tipos de benefícios oferecidos por um empregador. Quando você cria um benefício no Microsoft Dynamics 365 para operações, defina o tipo de qualificação que se aplica ao benefício. 

Você pode fazer um benefício disponível a todos os funcionários. Por exemplo, o estacionamento oferta de algumas empresas transmite a todos os funcionários como uma benefícios extras. Ao criar esse benefício, você define a qualificação como **Todos os trabalhadores estão qualificados**. 

Benefícios para outros, como decorações e de imposto, arrecadações qualificação não se aplica. Soro criar esses tipos de benefícios, você definiu a qualificação ** ignorar o processo de qualificação **. 

Finalmente, qualificação de lucro pode se basear em regras. Por exemplo, uma empresa oferece dois tipos de benefícios de seguro de vida funcionários. Os funcionários executivos estão qualificadas para um sistema de seguro de vida, enquanto que todos os funcionários em tempo integral que estão qualificadas para outro sistema de seguro de vida. Em dynamics 365 para operações, você poderá criar uma regra de qualificação de benefício localizar todos os funcionários executivos e outra regra localizar todos funcionários em tempo integral outros, e aplicar nessas regras o benefício apropriado.

## <a name="enrollment"></a>Inscrição
Após criar os benefícios oferecidos por sua empresa e determinar a qualificação, você poderá inscrever os trabalhadores em benefícios. Você pode inscrever um único trabalhador em benefícios, ou pode inscrever vários trabalhadores em um ou mais benefícios durante um único processo. 

Às vezes, uma organização deixa de oferecer alguns benefícios. Nesse caso, você deve atualizar o benefício e os funcionários que são inseridos em. O vencimento massa de lucro permite alterar simultaneamente a data de vencimento de um benefício e de registros de trabalho para o benefício. Você também pode selecionar vários trabalhadores inscritos em um benefício e alterar a data final da cobertura. 

Da mesma forma, a extensão do benefício em massa permite que você estenda a data de vencimento de um benefício e de inscrições de trabalhadores para esse benefício, caso você opte por oferecer um benefício por mais tempo do que planejado originalmente.

<a name="see-also"></a>Consulte também
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


