---
title: Ativos e ordens de serviço
description: Este tópico descreve ativos e ordens de serviço no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cddb0a25286c8ce9d72aef0b835809705ad577a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020930"
---
# <a name="assets-and-work-orders"></a>Ativos e ordens de serviço

[!include [banner](../../includes/banner.md)]

 

Este tópico descreve ativos e ordens de serviço no Asset Management. Os ativos e as ordens de serviço são partes centrais do Asset Management. Um *ativo* é um computador ou uma peça do computador que exige manutenção e serviço contínuos. Os ativos podem ser criados em uma estrutura hierárquica, e podem ser relacionados a locais funcionais. Os trabalhos de manutenção podem ser planejados em todos os níveis na estrutura de ativos.

Vários dados, como informações sobre o produto e as especificações de ativo, os planos de manutenção necessários são configurados em cada ativo. A ilustração a seguir mostra uma visão geral de dados de ativo e a afiliação de ativos a tipos de trabalho. O texto em vermelho será usado para exemplos que mostrem a herança e as dependências.

![Diagrama exibindo dados do ativo relacionados aos tipos de trabalho](media/05-overview-image.png)

Cada ordem de serviço tem um tipo de ordem de serviço, como manutenção preventiva, manutenção corretiva ou inspeção. A ordem de serviço contém um ou vários trabalhos da ordem de serviço. Cada trabalho da ordem de serviço define um trabalho que deve ser realizado em um ativo e um tipo de trabalho relacionado. Os exemplos de tipos de trabalho relacionados incluem vistoria de 10 mil km, 50 mil km, 1 ano e inspeção de segurança. Um ordem de serviço pode ser relatada a vários ativos.

A ilustração a seguir mostra uma visão geral dos dados principais de uma ordem de serviço.

![Diagrama exibindo os principais dados em uma ordem de serviço](media/06-overview-image.png)

Um ordem de serviço pode ser relacionada a outra ordem de serviço, e os tipos de trabalho podem conter os trabalhos subsequentes que criam uma ordem de serviço. Geralmente, não existem dependências entre ordens de serviço. Portanto, elas podem alterar o estado de ciclo de vida da ordem de serviço e podem ser agendadas de forma independente umas das outras.

As ordens de serviço podem ser criadas em várias formas relacionadas à manutenção corretiva, preventiva ou reativa. Você também pode criar ordens de serviço manualmente. A ilustração a seguir mostra uma visão geral do processo para a criação automática ou manual de ordens de serviço.

![Diagrama exibindo a criação automática ou manual de ordens de serviço](media/07-overview-image.png)

Várias etapas devem ser concluídas quando você deseja agendar e executar um trabalho de manutenção em uma ordem de serviço. A ilustração a seguir mostra uma visão geral do processamento para uma ordem de serviço.

![Diagrama exibindo a visão geral do processamento de uma ordem de serviço](media/08-overview-image.png)

> [!NOTE]
> Geralmente, quando você trabalha no Dynamics 365 Supply Chain Management e no módulo **Asset Management**, seleciona **Novo** para criar um novo registro, seleciona **Editar** para atualizar um registro existente e seleciona **Salvar** para salvar dados novos ou editados.
