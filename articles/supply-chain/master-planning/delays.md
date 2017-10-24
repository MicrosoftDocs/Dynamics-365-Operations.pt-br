---
title: Atrasos
description: "Este artigo fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8db5c507fbc68e637dbbc4ef3311d1fbd298f24f
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="delays"></a>Atrasos

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.

O planejamento mestre pode calcular a data de término de vigência mais antiga para uma transação com base nos prazos de entrega, na disponibilidade material, na disponibilidade de capacidade e em vários parâmetros de planejamento. 

Se o planejamento mestre calcular a data de uma ordem como anterior à data atual, a ordem não poderá ser atendida a tempo. Consequentemente, a ordem ficará atrasada. Neste caso, o planejamento mestre antecipado planeja a ordem a partir da data atual e inclui os prazos de entrega. Esses prazos de entrega começam com qualquer item de componente de nível inferior. A ordem então recebe uma data atrasada. Uma data atrasada é uma data de vencimento realista baseada na data atual. O planejamento mestre também calcula o número de dias de atraso. 

Em algumas situações, você poderá optar por não calcular os atrasos, como quando os usuários souberem que podem acelerar os prazos de entrega selecionando modos de entrega alternativos. 

Você pode configurar como os atrasos são calculados para um grupo de cobertura. Você pode então associar o grupo de cobertura a um item posteriormente. 

Na página **Parâmetros de planejamento mestre**, você pode definir a hora de início para o cálculo de atrasos. Se uma ordem for atendida após esse horário, um atraso de um dia será adicionado à data de atraso da ordem. 

**Observação:** em versões anteriores, os atrasos calculados eram conhecidos como *mensagens futuras*, a data atrasada era conhecida como as *datas futuras* e uma transação atrasada foi mencionada como *uma transação definida no futuro*.

<a name="see-also"></a>Consulte também
--------

[Configurações de cobertura](coverage-settings.md)




