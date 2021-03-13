---
title: Nível e descrição de serviço
description: Este tópico explica nível de serviço e descrição no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019370"
---
# <a name="service-level-and-description"></a>Nível e descrição de serviço

[!include [banner](../../includes/banner.md)]

 

Quando você cria uma ordem de serviço, você pode desejar definir os níveis de serviço para ela e adicionar uma descrição geral a ela. Você pode criar níveis de serviço da ordem de serviço na página **Níveis de serviço da ordem de serviço** e descrições na página **Descrição da ordem de serviço**.

## <a name="create-a-service-level"></a>Criar um nível de serviço

1. Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Nível de serviço**.
2. Selecione **Novo**.
3. No campo **Nível de serviço**, insira o nível de serviço (por exemplo, um número).
4. No campo **Nome**, insira um nome.

    Na Guia Rápida **Ordens de serviço**, você pode definir as datas e horas de início e término. Os campos nessa Guia Rápida definem o período que as ordens de serviço devem ser iniciados e terminados. Eles são usados para ordens de serviço que são criadas manualmente e ordens de serviço que são criadas com base em solicitações de manutenção. 

5. No campo **Dia Inicial**, insira um número de dias para definir o período em que a ordem de serviço deve iniciar. O número de dias é calculado a partir da data de criação da ordem de serviço. Por exemplo, se a ordem de serviço começa quando é criada, insira **0**. Se a ordem de serviço começa uma semana depois de ser criada, insira **7**.
6. Para definir uma hora inicial para a ordem de serviço, além de uma data de início, defina **Definir hora inicial** como **Sim**. Insira a hora inicial no campo **Hora inicial**. Se você definir a opção como **Não**, a hora atual será usada.
7. No campo **Dia final**, insira um número de dias para definir o período em que a ordem de serviço deve terminar. O número de dias é calculado a partir da data de início da ordem de serviço. Por exemplo, se a ordem de serviço finalizar dentro de uma semana da data de início, insira **7**.
8. Para definir uma hora final para a ordem de serviço, além de uma data de término, defina **Definir hora final** como **Sim**. Insira a hora final no campo **Hora final**. Se você definir a opção como **Não**, a hora atual será usada.
9. Selecione **Salvar**.

![Página do nível de serviço das ordens de serviço](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Criar uma descrição

1. Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Descrições**.
2. Selecione **Novo**.
3. No campo **Descrição**, insira a descrição.
4. Selecione **Salvar**.
