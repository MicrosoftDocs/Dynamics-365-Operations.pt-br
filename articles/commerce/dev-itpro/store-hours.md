---
title: Criar e atualizar os horários das lojas
description: Este tópico descreve como criar e atualizar os horários de funcionamento em Commerce Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 4706432234437d2dc7943fb194cd01004ab7e6b7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687502"
---
# <a name="create-and-update-store-hours"></a>Criar e atualizar os horários das lojas

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Visão geral

De um único local, fornecedores podem criar, manter e gerenciar e o horário de funcionamento para diferentes lojas nas regiões. O horário de funcionamento pode ser exibido em terminais do ponto de venda (POS). Assim, os caixas podem compartilhar o horário de funcionamento com clientes e ajudar melhor os clientes que estão interessados em estoque em outras lojas. O horário de funcionamento também pode ser impresso nos recibos, se os clientes desejarem retornar posteriormente à loja.

Vários horários de funcionamento podem ser configurados em diferentes canais. Esses canais incluem lojas físicas, call centers, dispositivos móveis e sites e-Commerce.

Se um cliente tiver um ordem de retirada de uma loja diferente, o caixa poderá selecionar datas em que o recolhimento estará disponível naquela loja. A pesquisa de loja oferecerá uma referência a datas e horário das lojas. O caixa pode selecionar uma data e uma localização e também pode imprimir um recibo de retirada que inclua o horário de funcionamento.

Esta funcionalidade está disponível em versões 8.1.2 do Microsoft Dynamics 365 Retail e posterior.

## <a name="configure-store-hours"></a>Configurar horários das lojas

Siga estas etapas para configurar os horários das lojas.

1. Vá para **Retail e Commerce** \> **Configuração do canal** \> **Horários das lojas**.
2. Selecionar **Novo** para criar um novo modelo de horários das lojas. Para usar um modelo existente, selecione o modelo no painel esquerdo.
3. Na caixa de diálogo **Adicionar intervalo**, defina o intervalo de data, o horário de funcionamento e todos os feriados necessários.

    - Se o horário da loja não se altera, selecione **Nunca terminará** no campo **Data final**.
    - Se o horário de funcionamento para um mês, semana, ou dia específico, defina as datas apropriadas nos campos **Data inicial** e **Data final**.

    > [!NOTE]
    > Você pode criar vários modelos com as datas inicial e final sobrepostas. Portanto, você pode, por exemplo, definir o horário de funcionamento para lojas em fusos horários diferentes.

    ![Adicionar a caixa de diálogo do intervalo](../dev-itpro/media/Storehours1.png "Adicionar a caixa de diálogo do intervalo")

4. Associe o modelo de horário de funcionamento com os armazenamentos que será usado. Na caixa de diálogo **Escolher nós organizacionais**, selecione os armazenamentos, regiões e organizações aos quais o modelo será associado.

    - Apenas um modelo de horário de funcionamento pode ser associado com cada loja.
    - Use os botões de seta para selecionar lojas, regiões ou organizações. O calendário estará disponível para as lojas ou grupos de loja e estará visível na POS para referência.

    ![Escolha a caixa de diálogo dos nós da organização](../dev-itpro/media/Storehours2.png "Escolha a caixa de diálogo dos nós da organização")

5. Na página **Agendamento de distribuição**, execute os trabalhos **1070** e **1090** para deixar o horário de funcionamento disponível na POS.

## <a name="add-store-hours-to-printed-receipts"></a>Adicionar horários de funcionamento a recibos impressos

Siga essas etapas para adicionar horas de funcionamento aos recibos de POS impressos.

1. Abra o designer de recibo.
2. Selecione **Rodapé** no canto inferior esquerdo.
3. Arraste o elemento **Horário de funcionamento** no painel esquerdo do rodapé na parte inferior do recibo.
4. Você pode editar o rótulo padrão no elemento **Horário de funcionamento**.
5. Salve recibo e feche o designer de recibo.
6. Na página **Agenda de distribuição**, execute os trabalhos **1070** e **1090**.
7. Entrar no PDV.
8. Conclua uma venda e selecione para imprimir um recibo.

Recibos de POS agora incluem as horas de funcionamento. Se algum feriado foi incluído no modelo, eles são exibidos no recibo.

![Exemplo de recibo](../dev-itpro/media/Storehours3.png "Exemplo de recibo")
