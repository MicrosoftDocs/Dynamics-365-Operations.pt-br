---
title: Atualização automática de contadores de ativos
description: Este tópico descreve a atualização automática de contadores de ativos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9911d5b96bb58b5def3e7dfee0f36826d99f6ba1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263677"
---
# <a name="automatic-update-of-asset-counters"></a>Atualização automática de contadores de ativo

[!include [banner](../../includes/banner.md)]

Para obter informações sobre o registro manual dos contadores de ativos, consulte [Atualização manual de contadores de ativos](../work-orders/manual-update-of-asset-counters.md). Para obter mais informações sobre como configurar contadores de ativos, consulte [Contadores](../setup-for-objects/counters.md).

Os valores dos contadores também podem ser atualizados automaticamente usando registros de produção, com base nas horas de produção ou na quantidade de produção (ou seja, a quantidade produzida). A atualização é feita na página **Atualizar contadores de ativos**. É possível atualizar um ou vários ativos configurando um parâmetro **Data inicial**. Este parâmetro especifica a data inicial para registros de produção (horas de produção ou quantidades de produção). Em outras palavras, especifica a partir de que data os valores de contador devem ser atualizados.

Todos os ativos relacionados a um recurso *e* com contadores de ativos configurados para serem atualizados com base nas horas ou na quantidade de produção serão incluídos em uma atualização automática. Os novos valores de contador serão criados.

Para os contadores baseados na quantidade de produção, a contagem incluirá a quantidade de acertos e a quantidade de erros registradas. Se a unidade usada para registrar a quantidade produzida for diferente da unidade usada para o contador, a quantidade será convertida de forma a corresponder à unidade do contador.

Como mencionado acima, os contadores automáticos podem ser atualizados por meio de registros de produção. Sendo assim, o ativo para o qual você deseja atualizar automaticamente os contadores deve estar relacionado a um recurso (máquina). Quando quantidades ou horas de produção tiverem sido registradas no recurso, será possível atualizar os contadores de ativos relacionados.

1. Selecione **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Atualizar contadores de ativos**.

2. No campo **Data inicial**, selecione a data de início da atualização automática.

    >[!NOTE]
    >A data nesse campo é a data do "trabalho em andamento" em **Transações de roteiro** ( campo **Controle de produção** > **Consultas e relatórios** > **Produção** > **Transações de roteiro** > **Data física**).

3. Na Guia Rápida **Registros a incluir**, você pode selecionar ativos, tipos de ativo ou recursos específicos para a atualização automática. Selecione **Filtro** e faça as seleções relevantes.

4. Na Guia Rápida **Executar em segundo plano**, você pode configurar a atualização automática como um trabalho em lote, conforme necessário.

    A ilustração a seguir mostra um exemplo do diálogo **Atualizar contadores de ativos**.

    ![Figura 1](media/12-work-orders.png)

5. Selecione **OK**. 

Após a conclusão da atualização automática de contador de ativos, você poderá exibir os registros de contador relacionados a ativos na **Contadores de ativos**. Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**, selecione o ativo e, em seguida, no Painel de Ação, na guia **Ativo**, no grupo **Preventivo** , selecione **Contadores**.

Na página **Valor agregado de ativo**, você pode obter uma visão geral do registro mais recente feito em todos os tipos de contadores em todos os ativos. Selecione **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Valor agregado do ativo**. Essa página se assemelha à página **Contadores de ativos**, mas você não poderá adicionar ou editar registros. É apenas para visão geral.

A ilustração a seguir mostra um exemplo da página **Valor agregado do ativo**.

![Figura 2](media/13-work-orders.png)

Observe os seguintes pontos:

- Você ainda pode criar registros manuais de valores de contador para os tipos de contador que são atualizados automaticamente. Para obter mais informações, consulte [Atualização manual de contadores de ativos](../work-orders/manual-update-of-asset-counters.md).

- Você pode configurar os contadores relacionados a outro contador. Nesse caso, quando um contador é atualizado, os contadores relacionados são atualizados automaticamente ao mesmo tempo. Para obter mais informações sobre como configurar contadores relacionados, consulte [Contadores](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]