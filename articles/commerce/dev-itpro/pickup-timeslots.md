---
title: Criar e atualizar os intervalos de tempo para retirada pelo cliente
description: Este tópico descreve como criar, configurar e atualizar os intervalos de tempo para retirada pelo cliente na sede do Commerce.
author: anupamar-ms
manager: AnnBe
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: 6dc2be8a6f62ce13068ce2242f92ef17830c2447
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205738"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Criar e atualizar os intervalos de tempo para retirada pelo cliente

[!include [banner](../../includes/banner.md)]

Este tópico descreve como criar, configurar e atualizar os intervalos de tempo para retirada pelo cliente na sede do Commerce.

O recurso de intervalos de tempo fornece aos varejistas uma forma de definir um intervalo de tempo para os itens para os quais o modo de entrega de retirada pelo cliente está ativado. Os intervalos de tempo permitem que os varejistas definam os dias e os horários em que as ordens podem ser retiradas em uma loja. Os varejistas também podem definir o número de ordens que podem ser retiradas durante um determinado período. Dessa forma, eles podem limitar o número de ordens que podem ser retiradas em um determinado dia e em um determinado horário. O resultado é uma experiência de melhor qualidade para seus clientes.

> [!NOTE]
> O recurso de intervalos de tempo está disponível na versão 10.0.15 e posteriores do Microsoft Dynamics 365 Commerce.

A ilustração a seguir mostra um exemplo de seleção de intervalo de tempo durante uma finalização de compra no comércio eletrônico.

![Exemplo de seleção de intervalo de tempo durante uma finalização de compra no comércio eletrônico](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Propriedades do intervalo de tempo

Um intervalo de tempo é um período determinado em que um cliente pode optar por retirar uma ordem em uma loja ou um local específico. O recurso de gerenciamento de intervalos de tempo está disponível apenas quando o modo de entrega de retirada pelo cliente está configurado no Dynamics 365 Commerce.

Um intervalo de tempo é definido usando as propriedades a seguir:

- **Modo de entrega** – Especifique o modo de entrega de retirada ao qual o intervalo de tempo se aplica.
- **Mínimo de Dias** e **Máximo de Dias** – Especifique as datas mais antigas e mais recentes que podem ser selecionadas para retirada em relação à data em que a ordem foi realizada. 

    A propriedade **Mínimo de Dias** garante que haja tempo suficiente para o varejista processar a ordem antes que ela esteja pronta para retirada. A propriedade **Máximo de Dias** garante que o usuário não possa selecionar uma data muito distante no futuro. Por exemplo, se o valor mínimo for definido como **1** e uma ordem for realizada em 20 de setembro, o primeiro dia em que a ordem estará disponível para retirada será o próximo dia elegível (21 de setembro). De forma semelhante, ao estabelecer um valor máximo, você pode definir o número máximo de dias em que uma ordem poderá ser retirada. Quando os valores mínimo e máximo estiverem definidos, os usuários do site poderão ver e selecionar somente um conjunto específico de dias durante sua experiência de finalização de compra.

    Você pode definir o valor mínimo como um valor decimal menor do que 1. Por exemplo, se a retirada estiver disponível quatro horas depois que uma ordem for realizada, defina o valor mínimo como **0,17** (= 4 ÷ 24, arredondado para duas casas decimais). No entanto, se você definir o valor mínimo como um valor decimal maior do que 1, ele sempre será arredondado para o número inteiro mais próximo. Por exemplo, um valor de **1,2** será arredondado para **2**. Da mesma forma, se você definir o valor máximo como um valor decimal, ele sempre será arredondado para o número inteiro mais próximo. 

- **Data de Início** e **Data de Término** – Especifique as datas de início e de término do intervalo de tempo. Cada entrada de intervalo de tempo tem uma data de início e uma data de término. Portanto, você tem a flexibilidade de adicionar diferentes intervalos de tempo durante o ano (por exemplo, retiradas durante o horário de funcionamento em feriados). Se as datas de início e de término de um intervalo de tempo forem alteradas depois que uma ordem for realizada, as alterações não serão aplicadas a essa ordem. Ao definir datas de início e de término, você deve considerar as datas de fechamento da loja (por exemplo, dia de Natal) e garantir que os intervalos de tempo não sejam definidos para esses dias.
- **Horário Ativo de Retirada** – Especifique o período em que a retirada é permitida. Por exemplo, o horário de retirada pode ser entre 14h e 17h todos os dias. Essa propriedade permite que os horários de retirada sejam independentes dos horários de funcionamento da loja. Portanto, o varejista pode configurar os horários de retirada de acordo com suas necessidades comerciais específicas. Ao definir o horário ativo de retirada, você deve considerar o horário de funcionamento da loja e garantir que os horários de retirada não sejam definidos para quando a loja estiver fechada.

    > [!NOTE]
    > O horário para retirada na loja deve ser definido no fuso horário da loja apropriada.

- **Duração do Intervalo de Tempo** – Especifique a duração que pode ser alocada para cada intervalo de tempo. Por exemplo, a duração de cada intervalo de tempo pode ser em incrementos de 15 minutos, 30 minutos ou uma hora. Se o valor do slot de tempo for 0, a alocação de tempo estará disponível para toda a duração entre as horas de início e término.
- **Atendimentos por Intervalo** – Especifique o número de clientes ou ordens que podem ser atendidos para retirada durante cada intervalo de tempo. Por exemplo, insira **1**, **2**, **3** ou qualquer outro número inteiro.
- **Dias Ativos** – Especifique os dias da semana em que os intervalos de tempo de retirada estão ativos. Esta propriedade permite que o varejista defina os dias em que deseja oferecer suporte à retirada de ordens.
- **Canais de Varejo** – Especifique os canais de varejo. Cada intervalo de tempo pode ser associado a uma ou mais lojas de varejo. Dependendo do horário de funcionamento de cada loja, uma ou mais entradas de intervalo de tempo podem ser criadas e associadas a um canal. 

<!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Somente um modelo de intervalo de tempo pode ser configurado por canal. Esses canais incluem lojas físicas, call centers, dispositivos móveis e sites e-Commerce.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Configurar o recurso de intervalos de tempo na sede do Commerce

Os intervalos de tempo devem ser definidos para cada modo de entrega de retirada na sede do Commerce, de forma que os canais de ponto de venda (PDV) e comércio eletrônico possam referenciá-los.

- Somente um modelo de intervalo de tempo pode ser associado a cada loja ou canal.
- Cada intervalo de tempo criado deve ser exclusivo para cada modo de entrega em cada modelo.
- Depois que o recurso de intervalos de tempo for configurado, o calendário de intervalos de tempo ficará disponível para as lojas ou os grupos de lojas selecionados. Ele também ficará visível no PDV, para referência.

Para configurar o recurso de intervalos de tempo na sede do Commerce, siga estas etapas.

1. Vá para **Commerce** \> **Configuração de canal** \> **Intervalo de tempo para retirada na loja**.
1. Selecione **Novo** para criar um novo modelo de intervalo de tempo. Para usar um modelo existente, selecione o modelo no painel esquerdo.
1. Insira os valores nos campos **ID do Intervalo de Tempo** e **Descrição**.
1. Na FastTab **Retirada de Ordens - Configurações de Tempo**, selecione **Adicionar**.
1. Na caixa de diálogo **Retirada de Ordens - Configurações de Tempo**, defina intervalo de datas, modo de entrega, horário ativo de entrega, dias ativos, duração do intervalo de tempo, atendimentos por intervalo e outras configurações.

    Se os intervalos de tempo forem estáticos no futuro próximo, defina o campo **Data de Término** como **Nunca**.

    > [!NOTE]
    > Você pode criar vários modelos, mas somente um modelo pode ser associado a um único canal ou loja.

    ![Caixa de diálogo Retirada de Ordens - Configurações de Tempo](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Quando terminar, selecione **OK**.
1. Se os intervalos de tempo em um dia forem variar, crie entradas adicionais na FastTab **Retirada de Ordens - Configurações de Tempo** para garantir que as datas e os horários não se sobreponham.
1. Na FastTab **Canais de Varejo**, selecione **Adicionar** para associar o modelo de intervalo de tempo às lojas ou aos canais em que ele será usado.
1. Na caixa de diálogo **Escolher os nós da organização**, use os botões de seta para selecionar (ou limpar a seleção de) lojas, regiões e organizações às quais o modelo deve ser associado.

    <!-- ![HQ Timeslot overview](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Quando terminar, selecione **OK**.
1. Na página **Agenda de distribuição**, execute os trabalhos **1070** e **1135** para sincronizar os dados com os canais.

## <a name="time-slot-selection-for-pos-orders"></a>Seleção de intervalo de tempo para ordens no PDV

No PDV, quando uma ordem ou linha de ordem é identificada para retirada, o operador de caixa pode selecionar a loja ou o local de retirada e um dia e horário. Se um cliente tiver um ordem de retirada de uma loja diferente, o caixa poderá selecionar datas em que o recolhimento estará disponível naquela loja. A pesquisa de loja oferecerá uma referência a datas e horário das lojas.

A ilustração a seguir mostra um exemplo de seleção de intervalo de tempo para uma ordem no PDV.

![Um exemplo de seleção de intervalo de tempo para uma ordem no PDV](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Seleção de intervalo de tempo para ordens no comércio eletrônico

Para obter informações sobre como disponibilizar a seleção de intervalo de tempo para ordens no comércio eletrônico, consulte [Módulo de informações sobre retirada](../pickup-info-module.md).

> [!NOTE]
> Os usuários poderão exibir ou editar os intervalos de tempo de retirada na página de finalização de compra de um site do Commerce somente se o módulo de informações sobre retirada tiver sido adicionado a essa página. Se a página de finalização de compra não incluir o módulo de informações sobre retirada, as ordens serão realizadas sem permitir que os usuários especifiquem ou exibam informações do intervalo de tempo.

A ilustração a seguir mostra um exemplo de uma ordem de comércio eletrônico em que um intervalo de tempo de retirada foi selecionado.

![Exemplo de uma ordem de comércio eletrônico em que um intervalo de tempo de retirada foi selecionado](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Seleção de intervalo de tempo para ordens de call center

No aplicativo de call center, os agentes de call center podem selecionar o local ou o armazenamento de retirada, bem como uma data e um slot de tempo como destacado na ilustração a seguir.

![Exemplo de uma ordem de call center em que um intervalo de tempo de retirada foi selecionado](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de informações sobre retirada](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]