---
title: Margens de segurança
description: Este artigo descreve como as margens de segurança podem ser usadas com o Suplemento de Otimização de Planejamento do Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 08/09/2022
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
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 247b48afab68651cff0ce84c8268a1df35a15c02
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335185"
---
# <a name="safety-margins"></a>Margens de segurança

[!include [banner](../../includes/banner.md)]

Este artigo descreve como as margens de segurança podem ser usadas com o Suplemento de Otimização de Planejamento do Microsoft Dynamics 365 Supply Chain Management.

## <a name="safety-margins-overview"></a>Visão geral das margens de segurança

A finalidade das margens de segurança é habilitar uma configuração que forneça algum tempo de buffer além do prazo de entrega normal. Por exemplo, quando o material deve ser descompactado ou inspecionado após recebê-lo do fornecedor, não será possível adicionar hora extra ao prazo de entrega da compra, porque essa abordagem fornecerá tempo de buffer para o fornecedor. Neste exemplo, a margem de recebimento pode ser usada para garantir que o fornecedor realize a entrega com antecedência. Essa abordagem fornece o tempo de buffer para que as mercadorias possam ser manuseadas internamente.

Existem três tipos de margens de segurança:

- **Margem de segurança** – O tempo de buffer para criar a ordem de fornecimento
- **Margem de recebimento** – O tempo de buffer para manusear fornecimento de entrada
- **Margem de saída** – O tempo de buffer para manusear remessas

A ilustração a seguir mostra como essas margens de segurança se aplicam ao longo do tempo.

![Margens de segurança.](media/safety-margins-1.png)

Todas as margens são definidas em dias. O valor padrão, *0* (zero), indica que nenhuma margem é aplicada. Se você configurar várias margens, todas elas somam o tempo desde a *data da ordem* de fornecimento até a *data da necessidade* da demanda. Por exemplo, uma configuração não tem prazo de entrega e todos os três tipos de margem estão definidos como um dia. Nesse caso, haverá três dias entre a data da ordem de fornecimento e a data obrigatória de demanda, portanto, se a data da ordem for 1° de julho, a data da necessidade seria 4 de julho.

### <a name="receipt-margin"></a>Margem de recebimento

A margem de recebimento é provavelmente a mais usada das três margens de segurança. Ela é aplicada à *data de entrega* e retroativamente a partir da *data obrigatória*. Em outras palavras, os produtos devem receber o número especificado de dias de margem de recebimento antes de serem solicitados.

A ilustração a seguir destaca a margem de recebimento.

![Margem de recebimento.](media/safety-margins-2.png)

A margem de recebimento é geralmente usada como buffer para garantir o tempo para o registro do depósito ou outros processos lentos que não são capturados como parte do prazo de entrega geral no sistema. Para compras, um benefício que é a *data de entrega* da ordem de compra avança de acordo. Se você aumentar o prazo de entrega em vez de usar uma margem de segurança, o fornecedor ainda será solicitado a entregar no último minuto.

Observe que a margem de recebimento não altera a *data obrigatória* do fornecimento. Portanto, a margem de recebimento não está visível diretamente quando as datas obrigatórias de demanda e fornecimento são comparadas (por exemplo, na página **Requisitos líquidos**). Por exemplo, se a margem de recebimento for definida para quatro dias e uma linha for planejada para recebimento no dia 15 do mês, o planejamento mestre calculará a data de recebimento ajustada como sendo o dia 19 do mês.

Observe que a margem de recebimento não é aplicada quando um estoque disponível é usado como fornecimento. Todo o estoque disponível é presumido como disponível imediatamente, independentemente de quando foi realmente recebido.

### <a name="reorder-margin"></a>Margem de segurança

A ilustração a seguir destaca a margem de segurança.

![Margem de segurança.](media/safety-margins-3.png)

A margem de segurança é adicionada antes do prazo de entrega do item para todos os pedidos planejados durante o planejamento mestre. Portanto, garante mais tempo para que uma ordem de fornecimento seja feita. Essa margem é normalmente usada como um buffer para garantir tempo para outros processos de aprovação ou outros processos internos exigidos durante a criação de ordens de fornecimento. A margem de segurança é colocada entre *data da ordem* de fornecimento e *data de início*.

### <a name="issue-margin"></a>Margem de saída

A ilustração a seguir destaca a margem de saída.

![Margem de saída.](media/safety-margins-4.png)

A margem de saída é deduzida da data obrigatória de demanda durante o planejamento mestre. Isso ajuda a garantir que você tenha tempo para reagir e enviar ordens de demanda de entrada. Essa margem é normalmente usada como buffer para garantir o envio e os processos de depósito de saída relacionados.

Observe que quando uma margem de saída é aplicada, as datas obrigatórias e de fornecimento de demanda não correspondem. Em vez disso, eles diferem pela margem de saída, porque a margem de saída é adicionada entre a *data obrigatória* de fornecimento e a *data da necessidade* de demanda.

## <a name="set-up-safety-margins"></a>Configurar margens de segurança

### <a name="turn-safety-margins-on-or-off"></a>Ativar ou desativar as margens de segurança

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Margens para Otimização de Planejamento* no espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="define-safety-margins"></a>Definir margens de segurança

As margens de segurança têm uma configuração flexível. Elas podem ser definidas no *grupo de cobertura* e no *plano mestre*. É importante compreender que as margens são adicionadas uma em cima da outra. Por exemplo, uma margem de recebimento de dois dias no grupo de cobertura e três dias no plano mestre produzirá uma margem de recebimento efetiva de cinco dias.

A capacidade para definir a margem no plano mestre pode ser útil quando quiser simular prazos de entrega mais longos ou a incerteza de um plano específico, mas sem afetar o planejamento diário.

#### <a name="coverage-group-safety-margins"></a>Margens de segurança do grupo de cobertura

Para aplicar uma margem de segurança a um grupo de cobertura, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Grupos de cobertura**.
1. No painel de lista, selecione o grupo de cobertura desejado.
1. Na Guia Rápida **Outro**, na seção **Margens de segurança em dias**, use os campos a seguir para definir as margens de segurança necessárias (em dias):

    - Margem de recebimento adicionada à data obrigatória
    - Margem de emissão deduzida da data obrigatória
    - Reordenar margem adicionada ao prazo de entrega do item

#### <a name="master-plan-safety-margins"></a>Plano mestre com margens de segurança

Para aplicar uma margem de segurança a um plano mestre, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. No painel de lista, selecione o plano mestre desejado.
1. Na Guia Rápida **Margens de segurança em dias**, na seção Margens de segurança em dias, use os campos a seguir para definir as margens de segurança necessárias (em dias):

    - Margem de recebimento adicionada à data obrigatória
    - Margem de emissão deduzida da data obrigatória
    - Reordenar margem adicionada ao prazo de entrega do item

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a>Definir se os cálculos são baseados em dias do calendário ou em dias úteis

Você pode definir todas as margens de segurança para serem calculadas com base em dias do calendário ou dias úteis.

1. Acesse **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**.
1. Na guia **Geral**, na seção **Margens de segurança em dias**, defina a opção **Dias úteis** como *Sim* para calcular margens com base em dias úteis. Defina a opção *Não* para calcular margens com base em dias do calendário.

Por exemplo, um calendário é aberto de segunda a sexta e fechado de sábado a domingo. Se houver uma margem de recebimento de um dia, uma data obrigatória na segunda-feira gera uma data de entrega na sexta-feira anterior, porque sábado e domingo não são dias úteis.

O calendário usado para determinar os dias úteis depende da configuração e do tipo de fornecimento. Ele pode ser controlado pelos calendários do grupo de cobertura, do depósito e do fornecedor.

> [!NOTE]
> Se o *depósito* não for parte da dimensão de cobertura (em outras palavras, o planejamento for baseado somente no *site*), o calendário do depósito não será usado.

O sistema pode manipular uma configuração na qual um ou mais calendários são definidos. As subseções a seguir descrevem as possíveis combinações que podem ser usadas para controlar o resultado.

#### <a name="calendar-that-is-used-for-the-duration"></a>Calendário usado para a duração

Os calendários definidos controlam o prazo de entrega total real em dias do calendário, desde a data da ordem de fornecimento até a data obrigatória de demanda. A seguinte priorização de calendário é usada:

- **Prazo de entrega da compra** – somente o calendário do grupo de cobertura é considerado.
- **Margem de recebimento** – o calendário do grupo de cobertura é usado, se estiver definido. Caso contrário, o calendário do depósito será usado.
- **Margem de saída** – o calendário do grupo de cobertura é usado, se estiver definido. Caso contrário, o calendário do depósito será usado.
- **Margem da ordem** – somente o calendário do grupo de cobertura é considerado.

#### <a name="calendar-that-is-used-for-the-final-date"></a>Calendário usado para a data final

As regras a seguir são aplicadas para determinar se o mecanismo de planejamento pode usar uma determinada data para um tipo de data específico:

- **Data de recebimento da compra** – o calendário do fornecedor é usado, se estiver definido. Caso contrário, o calendário do grupo de cobertura é usado, se estiver definido. Se nenhum desses calendários estiver definido, o calendário do depósito será usado.
- **Data de recebimento da transferência** – o calendário do grupo de cobertura é usado, se estiver definido. Caso contrário, o calendário do depósito será usado.
- **Data de recebimento de produção** – o calendário do grupo de cobertura é usado, se estiver definido. Caso contrário, o calendário do depósito será usado.
- **Dia da abertura do problema de demanda** – o calendário do depósito é usado, se estiver definido. Caso contrário, o calendário do grupo de cobertura é usado.
- **Dia de abertura da ordem** – é usada uma combinação (interseção) do calendário do grupo de cobertura e do calendário do fornecedor. Ambos os calendários devem se abertos para usar a data. Se apenas um desses calendários estiver definido, somente ele será usado.

#### <a name="calendar-setup-overview-matrix"></a>Matriz de visão geral da configuração do calendário

A ilustração a seguir apresenta uma matriz que resume quais calendários se aplicam quando as margens de segurança são calculadas. (Selecione a imagem para abrir uma versão de alta resolução dela.) As seguintes abreviações e cores são usadas para indicar onde cada tipo de calendário é especificado:

- **Grupo de cobertura (CG):** verde
- **Depósito (WH):** amarelo
- **Fornecedor (V):** azul

[![Matriz de visão geral da configuração do calendário.](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)

## <a name="calculating-delays"></a>Calculando atrasos

Os três tipos de margens de segurança são incluídos quando o sistema determina se uma ordem está atrasada.

Por exemplo, um item tem prazo de entrega de um dia e uma margem de recebimento de três dias. Uma ordem de venda para este item é definida como exigida hoje. Nesse caso, o atraso é calculado como *prazo de entrega* + *margem de recebimento* = quatro dias. Portanto, se hoje for 14 de agosto, os quatro dias de atraso geram uma entrega em 18 de agosto. A ilustração a seguir mostra esse exemplo.

![Exemplo de cálculo de atraso.](media/safety-margins-delays.png)

## <a name="additional-resources"></a>Recursos adicionais

[Introdução à Otimização do Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]