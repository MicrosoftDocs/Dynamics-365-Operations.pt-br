---
title: Atrasos
description: Este tópico fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9dcb11b3665c5d2f296f1ba2ce4708c4eff241b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977979"
---
# <a name="delays"></a>Atrasos

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.

O planejamento mestre pode calcular a data de término de vigência mais antiga para uma transação com base nos prazos de entrega, na disponibilidade material, na disponibilidade de capacidade e em vários parâmetros de planejamento. 

Se o planejamento mestre calcular a data de uma ordem como anterior à data atual, a ordem não poderá ser atendida a tempo. Consequentemente, a ordem ficará atrasada. Neste caso, o planejamento mestre antecipado planeja a ordem a partir da data atual e inclui os prazos de entrega. Esses prazos de entrega começam com qualquer item de componente de nível inferior. A ordem então recebe uma data atrasada. Uma data atrasada é uma data de vencimento realista baseada na data atual. O planejamento mestre também calcula o número de dias de atraso. 

Em algumas situações, você poderá optar por não calcular os atrasos, como quando os usuários souberem que podem acelerar os prazos de entrega selecionando modos de entrega alternativos. 

Você pode configurar como os atrasos são calculados para um grupo de cobertura. Você pode então associar o grupo de cobertura a um item posteriormente. 

Na página **Parâmetros de planejamento mestre**, você pode definir a hora de início para o cálculo de atrasos. Se uma ordem for atendida após esse horário, um atraso de um dia será adicionado à data de atraso da ordem. 

> [!NOTE]
> Nas versões anteriores, os atrasos calculados eram conhecidos como *mensagens futuras*, a data atrasada era conhecida como *datas futuras* e uma transação atrasada foi mencionada como *uma transação definida no futuro*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Atrasos limitados na configuração da produção com vários níveis de BOM
Ao trabalhar com atrasos em uma configuração de produção que tem vários níveis de BOM, é importante observar que somente os itens diretamente acima do item (na estrutura da BOM) que causam o atraso, serão atualizados com um atraso como parte da execução do planejamento mestre. Os outros itens na estrutura da BOM não receberão o atraso aplicado até que o primeiro planejamento mestre seja executado, quando a ordem planejada para o nível superior for aprovada ou confirmada. 

Para solucionar essa limitação conhecida, as ordens de produção no topo da estrutura da BOM com atrasos podem ser aprovadas (ou confirmadas) antes da próxima execução do planejamento mestre. Dessa forma, o atraso da ordem de produção planejada atrasada aprovada será mantido e todos os componentes subjacentes serão atualizados de acordo.
As mensagens de ação também podem ser usadas para identificar ordens planejadas que podem ser movidas para uma data posterior, devido a outros atrasos na estrutura da BOM.

## <a name="desired-date"></a>Data desejada

Na página **Ordem planejada**, a guia **Atrasos** mostra a **Data desejada** da ordem planejada. A data desejada de uma ordem planejada é a data base para atrasos, que é uma data calculada equivalente à **Data da solicitação** calculada com base na **Necessidade Líquida**. Se a ordem planejada for uma linha de BOM, linha de produção ou linha kanban, a data desejada será baseada na **Data da necessidade** e a data desejada não será exibida na página **Ordem planejada**.

<a name="additional-resources"></a>Recursos adicionais
--------

[​Configurações de cobertura​](coverage-settings.md)
