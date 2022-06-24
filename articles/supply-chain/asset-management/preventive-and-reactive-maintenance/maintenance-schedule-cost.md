---
title: Custo do agendamento de manutenção
description: Este artigo explica o custo de agendamento de manutenção no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 91481f9bcb778796255fad006c6187916d8e6bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908733"
---
# <a name="maintenance-schedule-cost"></a>Custo do agendamento de manutenção

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de Ativos você pode calcular os custos de orçamento nas linhas de agendamento de manutenção. Isso é útil se você quiser obter uma visão geral dos custos esperados, por exemplo, os custos relacionados aos trabalhos de manutenção preventiva planejados para o próximo ano. Os cálculos são baseados nas linhas de agendamento de manutenção existente do tipo "Planos de manutenção" e "Rounds de manutenção" e "Solicitações de manutenção".

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Custo de agendamento de manutenção**.

2. Na caixa de diálogo **Custo de agendamento de manutenção**, é possível selecionar um **Conjunto de dimensões financeiras** se você quiser ver os custos agrupados nas dimensões financeiras.

>[!NOTE]
>Os conjuntos da dimensão financeira são configurados na **Contabilidade** > **Planos de contas** > **Dimensões** > **Conjuntos de dimensões financeiras**.

3. Você pode usar o campo **Nível** para indicar o quão detalhado você deseja que as linhas de agendamento de manutenção sejam relativas aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de agendamento de manutenção em todos os níveis do local funcional ao qual elas estão relacionadas.

4. Se quiser fazer um cálculo para ativos específicos, clique em **Filtro** na Guia Rápida **Registros a serem incluídos** e selecione os ativos relevantes. Se necessário, você também pode especificar uma data de **Início esperado** para o cálculo de custo ou selecionar um **Status** diferente para o cálculo de custo.

5. Clique em **OK** para iniciar o cálculo de custo.

6. Na guia **Custo de agendamento de manutenção** > nos grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo de custo. Os botões do grupo do Painel de Ações selecionado estão destacados. Clique em um botão para ativá-los ou desativá-los.

7. Clique no botão **Calcular custo** se quiser fazer um novo cálculo de custo.

A ilustração a seguir mostra os resultados do cálculo de custo de um agendamento de manutenção.

![Figura 1.](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]