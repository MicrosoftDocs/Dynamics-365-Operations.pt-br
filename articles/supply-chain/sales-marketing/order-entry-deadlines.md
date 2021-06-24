---
title: Prazos finais de entrada da ordem
description: Este artigo oferece informações sobre prazos finais de entrada de ordem. Um prazo final de entrada de ordem é uma hora de fechamento que determina se uma ordem do cliente será tratado (e atendida) como se tivesse sido recebida no dia atual ou no dia seguinte.
author: omulvad
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable, MCRAutoTaxRules
audience: Application User
ms.reviewer: kamaybac
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d64729d6da5c57267d6d62274cce496888548d7
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189983"
---
# <a name="order-entry-deadlines"></a>Prazos finais de entrada da ordem

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre prazos finais de entrada de ordem. Um prazo final de entrada de ordem é uma hora de fechamento que determina se uma ordem do cliente será tratado (e atendida) como se tivesse sido recebida no dia atual ou no dia seguinte.

Em muitas empresas, somente ordens de venda que são recebidas antes de um determinado horário do dia são consideradas como recebidas naquele dia. Todas as ordens recebidas após esse tempo são tratadas como se fossem recebidas no próximo dia útil. Essa hora de suspensão para ordens é conhecida como o prazo final de entrada de ordem.  

Os prazos finais de entrada de ordem são usados como a entrada da promessa da ordem. Consequentemente, ajudam a gerenciar as expectativas do cliente sobre entregas de ordem. Por exemplo, os clientes podem ver se fazem um pedido antes de um horário específico, você confirmará a entrega das mercadorias no mesmo dia. Entretanto, se eles perderem esse prazo, podem esperar a remessa apenas no próximo dia útil. Você define os prazos finais da entrada de ordem baseados em suas capacidades de depósito e agenda da transportadora.  

Na página **Prazos finais de entrada da ordem**, você configura os horários dos prazos finais da entrada de ordem para todos os dias da semana. Se as ordens forem recebidas após os horários especificados, elas são tratadas como se fossem recebidas no próximo dia útil. Por padrão, esses horários são definidos como 23:59 (ou seja, um minuto antes da meia-noite no final do dia relevante). É possível alterar os horários padrão para que coincidam com os horários reais do prazo final de envio ou recebimento.  

Você pode definir os prazos finais de entrada de ordem para um grupo específico de clientes. Por exemplo, pode ser que você queira que um grupo específico de clientes tenha os prazos finais de entrada de ordem posteriores aos de outros clientes. Nesse caso, você define primeiro grupos para prazos de entrada de ordem na página **Grupos de prazos finais de entrada da ordem**. Em seguida, você atribui grupos aos clientes na página **Clientes**.  

Se sua empresa consistir em vários sites, você poderá configurar prazos finais de entrada de ordem para cada site. Se os sites estiverem localizados em fusos horários diferentes, os prazos finais de entrada de ordem serão configurados em cada fuso horário do site. Entretanto, ao trabalhar com ordens de venda e cotações de venda, o prazo final de entrada da ordem é convertido para seu fuso horário na página **Datas de remessa e de recebimento disponíveis**.  

Na página **Ativar combinações de prazo final de entrada da ordem**, você define as combinações de sites e grupos de prazos finais de entrada de ordem que são permitidos.

## <a name="example-order-entry-deadline"></a>Exemplo: prazo final de entrada de ordem
O prazo final de entrada de ordem nas terças-feiras foi definido como 16h. Em uma terça-feira específica, às 17h, você tenta definir a data atual como a data de remessa. (Observe que não há nenhum prazo de entrega neste exemplo.) Se a caixa de seleção **Controle da data de entrega** estiver marcada, você receberá um aviso informando que a data não é válida. Esse aviso aparece na página **Datas de remessa e de recebimento disponíveis**, na qual é possível selecionar datas alternativas.

## <a name="example-different-order-entry-deadlines-per-site"></a>Exemplo: prazos finais diferentes da entrada da ordem por site
Sua empresa consiste em dois sites. Os sites estão localizados em fusos horários diferentes, como mostra a tabela a seguir.

| Local A                      | Local B                      |
|-----------------------------|-----------------------------|
| Califórnia                  | Flórida                     |
| PST (Hora Padrão do Pacífico) | EST (Hora Padrão do Leste dos EUA) |

Os sites A e B definiram os seguintes prazos finais de entrada de ordem.

| Dia da semana             | A: Prazos finais de entrada da ordem (PST) | B: Prazos finais de entrada da ordem (EST) |
|-----------------------------|--------------------------------|--------------------------------|
| Segunda-feira                      | 13:00:00                          | 14:00:00                          |
| Terça-feira                     | 13:00:00                          | 14:00:00                          |
| Quarta-feira                   | 13:00:00                          | 14:00:00                          |
| Quinta-feira                    | 13:00:00                          | 14:00:00                          |
| Sexta-feira                      | 13:00:00                          | 14:00:00                          |

Você é o processador de ordens em Utah, cujo fuso horário é o MST (Hora Padrão das Montanhas). Portanto, desde que faça pedidos no site A antes de 14:00 MST e no site B antes de 12:00 MST, você atenderá aos prazos de entrada de ordem dos dois sites.  

A tabela a seguir mostra como os prazos finais da ordem de entrada para os sites A e B são convertidos para a hora MST.

| Local A: PST         | Local A: MST        | Local B: EST           | Local B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 14:00:00                 | 12:00:00              |

**Observação:** Se o ajuste para horário de verão estiver em vigor, os prazos finais de entrada de ordem serão ajustados adequadamente.

## <a name="example-same-order-entry-deadline-per-site"></a>Exemplo: mesmo prazo final de entrada de ordem por site
Sua empresa consiste em dois sites. Os sites estão localizados em fusos horários diferentes, como mostra a tabela a seguir.

| Local A                      | Local B                      |
|-----------------------------|-----------------------------|
| Califórnia                  | Flórida                     |
| PST (Hora Padrão do Pacífico) | EST (Hora Padrão do Leste dos EUA) |

Os sites A e B definiram os seguintes prazos finais de entrada de ordem.

| Dia da semana | PST e EST |
|-----------------|-------------|
| Segunda-feira          | 13:00:00       |
| Terça-feira         | 13:00:00       |
| Quarta-feira       | 13:00:00       |
| Quinta-feira        | 13:00:00       |
| Sexta-feira          | 13:00:00       |

Você é o processador de ordens em Utah, cujo fuso horário é o MST (Hora Padrão das Montanhas). Portanto, desde que faça pedidos no site A antes de 14:00 MST e no site B antes de 11:00 MST, você atenderá aos prazos de entrada de ordem dos dois sites. 

A tabela a seguir mostra como os prazos finais da ordem de entrada para os sites A e B são convertidos para a hora MST.

| Local A: PST         | Local A: MST        | Local B: EST           | Local B: MST        |
|---------------------|--------------------|-----------------------|--------------------|
| 13:00:00               | 14:00:00              | 13:00:00                 | 11:00:00              |

**Observação:** Se o ajuste para horário de verão estiver em vigor, os prazos finais de entrada de ordem serão ajustados adequadamente.

## <a name="additional-resources"></a>Recursos adicionais

[Agendas de entrega](delivery-schedules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]