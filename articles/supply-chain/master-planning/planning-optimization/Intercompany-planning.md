---
title: Planejamento intercompanhia
description: Este artigo descreve o planejamento intercompanhia e explica como configurar o planejamento intercompanhia com a Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6ef551e1c2c4d90510f967855a5aa61646dc8eab
ms.sourcegitcommit: d3f7a56eaf788d223ece4cedac4a319eaf5f6112
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2022
ms.locfileid: "9538556"
---
# <a name="intercompany-planning"></a>Planejamento intercompanhia

[!include [banner](../../includes/banner.md)]

Para algumas organizações, as operações de logística dependem de outras entidades legais (empresas) na organização. Essas operações são tratadas com o uso de vendas e compras intercompanhia, pois cada entidade legal tem um plano de contas separado.

Este artigo descreve o planejamento intercompanhia e explica como configurar o planejamento intercompanhia com a Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.

Este artigo usa os seguintes termos importantes intercompanhia:

- **Upstream** – uma referência relativa em uma empresa ou cadeia de fornecimento. Ele indica movimento na direção do fornecedor de matérias-primas.
- **Downstream** – uma referência relativa em uma empresa ou cadeia de fornecimento. Ele indica movimento na direção do cliente.
- **Demanda intercompanhia planejada** – demanda planejada para um produto de uma empresa, com base na demanda planejada para o produto de uma empresa downstream.

No planejamento mestre, um plano em uma empresa pode incluir a demanda intercompanhia planejada relacionada às ordens planejadas de um plano em outra empresa. Esse recurso é útil, pois oferece visibilidade total das ordens planejadas entre as empresas. Ele também garante que todas as ordens de fornecimento planejadas necessárias sejam criadas, mas sem exigir que as ordens planejadas sejam confirmadas para a demanda intercompanhia.

Se você executar o planejamento mestre a partir de um plano mestre que inclui a demanda downstream planejada, as ordens de compra planejadas dos fornecedores intercompanhia relacionadas serão incluídas no plano como demanda.

## <a name="required-setup"></a>Configuração necessária

Para usar o planejamento intercompanhia, você deve preparar o sistema da seguinte maneira:

1. Os produtos relevantes devem ser liberados em todas as empresas relevantes. Para obter mais informações, consulte [Configurar e usar comércio intercompanhia no Dynamics 365 Supply Chain Management](/training/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/).
1. A demanda downstream deve ser coberta pelas compras de um fornecedor que tenha uma relação intercompanhia para a empresa de upstream e as dimensões de estoque padrão relevantes (site e depósito) no cliente. Para obter mais informações, consulte [Configurar e usar comércio intercompanhia no Dynamics 365 Supply Chain Management](/training/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/).
1. O plano mestre na empresa de upstream deve incluir a demanda de downstream planejada; a empresa e o plano mestre relevantes devem ser especificados nos planos downstream.

## <a name="include-planned-downstream-demand"></a>Incluir a demanda downstream planejada

Siga estas etapas para configurar seu plano mestre de forma que inclua a demanda downstream planejada.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione ou crie um plano mestre.
1. Na FastTab **Planejamento intercompanhia**, defina os seguintes campos:

    - **Incluir a demanda downstream planejada** – defina esta opção como *Sim* para habilitar o planejamento intercompanhia para o plano mestre.
    - **Planos downstream** – se você definir a opção **Incluir demanda downstream planejada** como *Sim*, use a barra de ferramentas e a grade para adicionar os planos mestre desejados de outras empresas.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Vincular entre empresas usando vinculação de vários níveis

Na vinculação de vários níveis, você pode exibir a vinculação entre empresas para ver a fonte inicial de demanda que está sendo coberta por um fornecimento.

Para exibir informações de vinculação de vários níveis, siga estas etapas.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**.
1. Selecione ou abra uma ordem planejada.
1. No Painel de Ações, na guia **Exibir**, no grupo **Requisitos**, selecione **Vinculação de vários níveis**.

### <a name="intercompany-example-that-involves-two-companies"></a>Exemplo de intercompanhia que envolve duas empresas

Neste exemplo, uma ordem de produção planejada é criada na empresa USMF para cobrir uma ordem de venda na empresa DEMF. No USMF, a demanda direta é a demanda intercompanhia planejada. Para fazer com que essa demanda apareça no USMF, o planejamento mestre é executado primeiro no DEMF e, depois, no USMF.

A ilustração a seguir mostra como esse exemplo pode aparecer na página **Vinculação de vários níveis** para a ordem de produção planejada.

![Exemplo de intercompanhia que envolve duas empresas.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Exemplo de intercompanhia que envolve três empresas

Neste exemplo, uma ordem de compra planejada é criada na empresa USMF para cobrir uma ordem de venda na empresa FRRT. Nas empresas DEMF e USMF, a demanda direta é a demanda intercompanhia planejada. Para fazer com que essa demanda apareça no USMF, o planejamento mestre é executado primeiro no FRRT, depois no DEMF e, finalmente, no USMF.

A ilustração a seguir mostra como esse exemplo pode aparecer na página **Vinculação de vários níveis** para a ordem de produção planejada.

![Exemplo de intercompanhia que envolve três empresas.](media/IntercompanyPlanning2.png)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
