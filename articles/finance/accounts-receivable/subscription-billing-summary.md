---
title: Visão geral da cobrança de assinatura
description: Este tópico descreve a cobrança de assinatura no Microsoft Dynamics 365 Finance.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b94ac36e49d55ad42909877d77903cd40cb22cbe
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182672"
---
# <a name="subscription-billing-overview"></a>Visão geral da cobrança de assinatura

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A cobrança de assinatura permite que as organizações gerenciem oportunidades de receita de assinatura e faturamento recorrente por meio de agendas de cobrança. Os modelos de cobrança e de preços complexos e a alocação de receita são gerenciados facilmente e são cobrados e reconhecidos em nível de linha. A alocação de receita de vários elementos permite a alocação de receita para atender aos Padrões Internacionais de Contabilidade (Padrão Internacional de Relatórios Financeiros 15 \[IFRS 15\]) e os padrões dos Princípios Contábeis Geralmente Aceitos (EUA GAAP) (Tópico 606 da Codificação de Padrões Contábeis \[ASC 606\]).

A solução tem três módulos que podem ser usados independentemente. Como alternativa, todos os três módulos podem ser usados em conjunto.

- **Cobrança recorrente de contrato** – Este módulo permite o gerenciamento de preços e a cobrança recorrente para oferecer controle sobre os parâmetros de cobrança e de preços, renovação de contrato e o faturamento consolidado.
- **Diferimentos de receita e despesas** – Este módulo elimina os processos manuais e a dependência de sistemas externos, gerenciando a receita e permitindo uma visão geral em tempo real da receita recorrente mensal.
- **Alocação de receita de vários elementos** – Este módulo ajuda na conformidade da receita ao lidar com a alocação de receita e preços em vários itens.

A cobrança de assinatura é habilitada por meio do **Gerenciamento de recursos**. No entanto, não pode ser usada com o recurso **Reconhecimento de receita**. Portanto, você deve desabilitar esse recurso antes de habilitar a cobrança de assinatura.

1. No espaço de trabalho **Gerenciamento de recursos**, na guia **Tudo**, insira **Reconhecimento de receita** no filtro e selecione o nome do recurso como o filtro.
2. Selecione o recurso **Reconhecimento de receita** e o botão **Desabilitar**.
3. No filtro **Nome do recurso**, insira **Cobrança de assinatura** e selecione o filtro de módulo.
4. Selecione o recurso **Cobrança de assinatura** e o botão **Habilitar**.
5. Selecione um dos três módulos da lista anterior e, em seguida, selecione **Habilitar**. Repita essa etapa para cada um dos dois outros módulos.

    > [!IMPORTANT]
    > O recurso **Cobrança de assinatura** deve estar habilitado para que você possa habilitar qualquer um dos três módulos.
