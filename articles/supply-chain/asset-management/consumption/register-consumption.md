---
title: Registrar consumo
description: Este tópico explica como registrar o consumo no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 50ace9a2f8f5fa39dc927e11f0acd707167ef126
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346217"
---
# <a name="register-consumption"></a>Registrar consumo

[!include [banner](../../includes/banner.md)]

 

Quando um trabalho de manutenção tiver sido concluído em uma ordem de serviço, a próxima etapa será criar registros de consumo e lançar diários. Você pode criar registros nos seguintes tipos de consumo: horas, itens e despesas. Os diferentes tipos de consumo são registrados e lançados na página **Diários de ordem de serviço**. A configuração de diário em **Gerenciamento de Ativos** é usada para criar e lançar diários separados para horas, itens e despesas no módulo **Gerenciamento e contabilidade de projeto**.

Em alguns casos, você pode adicionar ou excluir linhas de previsão em uma ordem de serviço. A configuração de um estado de ciclo de vida de ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você é capaz de adicionar ou editar linhas de diário. Leia mais sobre os estados de ciclo de vida da ordem de serviço e os estágios do projeto relacionados, consulte [Previsões, ordens de serviço e projetos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>É possível configurar o lançamento automático de diários em um estado de ciclo de vida de ordem de serviço. Consulte [Estados de ciclo de vida de ordem de serviço](../setup-for-work-orders/work-order-lifecycle-states.md) para obter mais informações.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e clique em **Diários**.

3. Clique em **Copiar de previsão** para transferir todas as linhas de previsão que possam estar conectadas à ordem de serviço. Você pode selecionar os tipos de consumo que deseja transferir.

4. Se necessário, você poderá adicionar mais linhas de consumo à Guia Rápida clicando em **Adicionar linha** e preenchendo a linha com dados.

5. Clique em **Validar diários** para validar as linhas de diário antes do lançamento.

6. Clique em **Lançar diários** para lançar as linhas do diário.

7. Após ter lançado os diários de consumo, você pode atualizar o estado do ciclo de vida da ordem de serviço. Por exemplo, para indicar que a ordem de serviço for concluída, você pode atualizar o estado do ciclo de vida para "concluído".

    - No campo **Mostrar**, localizado na parte superior da página **Diários de ordem de serviço**, selecione quais linhas de diário você deseja ver: **Todos**, **Não lançados** ou **Lançados**. Os diários lançados têm uma marca de seleção na caixa de seleção **Lançados**.  
    - Quando linhas de item forem criadas no diário de ordem de serviço, as dimensões de produto e as dimensões de rastreamento relacionadas ao item serão automaticamente transferidas para a linha de diário.  

A captura de tela a seguir mostra um exemplo de registros de hora e item em uma ordem de serviço em **Diários de ordem de serviço**.

![Figura 1.](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Horas divididas em ordens de serviço com vários trabalhos de ordem de serviço

Se uma ordem de serviço contiver vários trabalhos de ordem de serviço, você poderá registrar horas de trabalho usando a funcionalidade **Dividir horas**, o que significa que a linha de registro de uma hora pode ser distribuída uniformemente em cada trabalho de ordem de serviço.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e clique em **Diários**.

3. Selecione a linha de registro de hora que você deseja dividir e clique em **Dividir horas**.

4. No diálogo **Dividir horas em trabalhos de manutenção de ordem de serviço**, o nome do trabalhador conectado é automaticamente mostrado no campo **Trabalhador**. Se necessário, você pode selecionar outro trabalhador.

5. Selecione uma categoria para o registro de horas no campo **Categoria**.

6. Insira o número de horas de trabalho a serem divididas no campo **Horas**.

    ![Figura 2.](media/02-consumption.png)

7. Clique em **OK**.

*Exemplo:* na captura de tela a seguir, as linhas de diário para uma ordem de serviço com três trabalhos de ordem de serviço são mostradas. A primeira linha, com três horas de trabalho, foi dividida e uma hora de trabalho é registrada em cada trabalho de ordem de serviço. Depois que as três linhas de registro de hora tiverem sido criadas, você decidirá o que fazer com a linha de registro de hora original (a primeira linha, no exemplo). É possível mantê-la como está ou excluí-la. 

![Figura 3.](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Dimensões financeiras em registros de consumo

Quando você cria registros de consumo, as dimensões financeiras relacionados a diferentes tipos de registro serão adicionadas aos registros em uma sequência específica. 

- *Registros de Horas e Despesas:* primeiro, as dimensões financeiras do cabeçalho de diário são adicionadas, se houver. Em seguida, as dimensões financeiras do projeto de ordem de serviço relacionado são adicionadas. Por fim, as dimensões financeiras do recurso (trabalhador) são adicionadas.

- *Registros de Item:* primeiro, as dimensões financeiras do cabeçalho de diário são adicionadas, se houver. Então, as dimensões financeiras do projeto de ordem de serviço relacionado são adicionadas. Em seguida, as dimensões financeiras do site são adicionadas. Por fim, as dimensões financeiras do item são adicionadas.

>[!NOTE]
>Para todos os três tipos de registro, a combinação de dimensão financeira é validada, e as combinações inválidas são anuladas. Esta é a configuração padrão com outros aplicativos do Finance and Operations.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]