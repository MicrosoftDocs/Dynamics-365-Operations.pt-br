---
title: Definir e gerenciar um programa de benefícios
description: O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este artigo fornece informações sobre como configurar e gerenciar benefícios.
author: andreabichsel
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 033377f7d45bfa2b798c098be2dde0c21739bb51
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517381"
---
# <a name="define-and-manage-a-benefits-program"></a>Definir e gerenciar um programa de benefícios

[!include [banner](includes/banner.md)]

O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este tópico fornece informações sobre como configurar e gerenciar benefícios.

<a name="benefit-setup"></a>Configuração de benefício
-------------

Para que os trabalhadores sejam inscritos nos benefícios, você deve criar os elementos de cada benefício. Esses elementos combinam planos de benefícios semelhantes e definem as configurações padrão, como taxas de dedução e detalhes da contabilidade. Muitas dessas configurações podem ser ajustadas quando os trabalhadores são inscritos posteriormente no benefício. Para cada plano de benefícios, uma organização pode oferecer várias opções de inscrição, ou um trabalhador pode cancelar a inscrição no plano. 

[![Fluxo do processo de benefício](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementos do benefício
Antes de começar a criar benefícios e inscrever trabalhadores neles, você deve definir os elementos que constituem um benefício: o tipo, o plano e as opções.

-   **Tipo** – Um conjunto de planos para um benefício específico, como médico ou estacionamento.
-   **Plano** – Um benefício específico que é contratado por um fornecedor.
-   **Opção** – O nível de cobertura, como apenas do funcionário, ou do funcionário e do cônjuge/parceiro.

Para cada tipo de benefício, como oftalmológico ou dentário, uma organização pode oferecer um ou mais planos para os trabalhadores. Para cada plano, a organização pode oferecer opções diferentes. Por exemplo, os trabalhadores podem comprar cobertura adicional de seguro de vida temporário em uma, duas ou três vezes o salário anual. Cada combinação de um plano e opções se torna um benefício no qual os trabalhadores podem se inscrever. 

[![pic de benefício](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Qualificação
Muitos fatores determinam a qualificação do trabalhador para os vários tipos de benefícios oferecidos por um empregador. Quando você cria um benefício no Microsoft Talent, pode definir o tipo de qualificação que se aplica a esse benefício. 

Você pode tornar um benefício disponível a todos os funcionários. Por exemplo, algumas empresas oferecem estacionamento a todos os funcionários como um benefício adicional. Ao criar esse benefício, você define a qualificação como **Todos os trabalhadores estão qualificados**. 

Para outros benefícios, como consignações e arrecadações de imposto, a qualificação não se aplica. Ao criar esses tipos de benefícios, você definiu a qualificação para **Ignorar processo de qualificação**. 

Por fim, a qualificação de benefícios pode ser baseada na regra. Por exemplo, uma empresa oferece dois tipos de benefícios de seguro de vida aos funcionários. Os funcionários executivos estão qualificados para um plano de seguro de vida, enquanto que todos os funcionários em tempo integral que estão qualificados para outro plano de seguro de vida. No Talent, você poderá criar uma regra de qualificação para o benefício para localizar todos os funcionários executivos e outra regra para localizar todos os outros funcionários de tempo integral e, em seguida, aplicar essas regras ao benefício apropriado.

## <a name="enrollment"></a>Inscrição
Após criar os benefícios oferecidos por sua empresa e determinar a qualificação, você poderá inscrever os trabalhadores em benefícios. Você pode inscrever um único trabalhador em benefícios, ou pode inscrever vários trabalhadores em um ou mais benefícios durante um único processo. 

Às vezes, uma organização deixa de oferecer alguns benefícios. Nesse caso, você deve atualizar o benefício e os trabalhadores que estão incluídos nele. O vencimento de benefício em massa permite que você altere a data de vencimento de um benefício e as inscrições de trabalhadores desse benefício ao mesmo tempo. Você também pode selecionar vários trabalhadores inscritos em um benefício e alterar a data final da cobertura. 

Da mesma forma, a extensão do benefício em massa permite que você estenda a data de vencimento de um benefício e de inscrições de trabalhadores para esse benefício, caso você opte por oferecer um benefício por mais tempo do que planejado originalmente.

<a name="additional-resources"></a>Recursos adicionais
--------

[Políticas de qualificação para benefícios](benefit-eligibility-policies.md)



