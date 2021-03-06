---
title: Tipos de ordem de serviço
description: Este tópico explica os tipos de ordem de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6bdc9d226d8e1aa6960cac38b95b0245e46ee1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825581"
---
# <a name="work-order-types"></a>Tipos de ordem de serviço

[!include [banner](../../includes/banner.md)]

 

Os tipos de ordem de serviço são usados para categorizar ordens de serviço. Por exemplo, você pode ter ordens de serviço relacionadas à manutenção preventiva ou manutenção corretiva.

Um tipo de ordem de serviço define uma afiliação com um modelo de ciclo de vida da ordem de serviço. Um modelo do ciclo de vida da ordem de serviço define os estados do ciclo de vida da ordem de serviço que podem ser definidos em uma ordem de serviço. (Exemplos dos estados de ciclo de vida da ordem de serviço incluem **Criado**, **Em andamento** e **Concluído**).

Para obter mais informações sobre os estados de ciclo de vida da ordem de serviço e as fases do projeto, consulte [Estados de ciclo de vida da ordem de serviço](work-order-lifecycle-states.md).

1. Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Tipos de ordem de serviço**.
2. Selecione **Novo** para criar um tipo de ordem de serviço.
3. No campo **Tipo de ordem de serviço**, insira uma ID para o tipo de ordem de serviço.
4. No campo **Nome**, insira um nome.
5. No campo **Modelo de ciclo de vida da ordem de serviço**, selecione um modelo de ciclo de vida.
5. Defina a opção **Um funcionário de manutenção** como **Sim** se todos os trabalhos de ordem de serviço relacionados a uma ordem de serviço desse tipo devem ser agendados para o mesmo funcionário de manutenção.
6. No campo **Tipo de custo**, selecione **Corretivo**, **Preventivo** ou **Investimento**, conforme apropriado. Todos os trabalhos da ordem de serviço em uma ordem de serviço devem ter o mesmo tipo de custo.
7. Na seção **Obrigatório**, defina as opções relevantes como **Sim** para especificar quais informações relacionadas a falha ou a tempo de inatividade de manutenção são adicionadas a uma ordem de serviço desse tipo.

    > [!NOTE]
    > As opções na seção **Obrigatório** estão relacionadas às opções na Guia Rápida **Validar** da página **Estados de ciclo de vida da ordem de serviço** (**Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Estados de ciclo de vida**).

8. Selecione **Salvar**.

![Tipos de ordem de serviço](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]