---
title: Gerenciamento de falhas
description: Este tópico explica o gerenciamento de falhas no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 72d6c8d750a5a0903017b4c77b3ce5d9521cf99b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422086"
---
# <a name="fault-management"></a>Gerenciamento de falhas

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de ativos, você pode usar o designer de falhas para configurar sintomas, áreas e tipos de falha nos tipos de ativos. Assim, você pode gerenciar falhas detectadas nos ativos. Além disso, as causas e sugestões de falha para corrigir falhas podem ser registradas em uma ordem de serviço.

O processo para registro e gerenciamento de falhas consiste nessas etapas.

1. Crie uma lista de sintomas, áreas e tipos de falhas que podem ocorrer nos seus tipos de ativos.
2. No designer de falhas, configure sintomas, áreas e tipos de falhas.

Veja alguns exemplos que podem ajudar você a entender a diferença entre sintomas, áreas e tipos de falha.

**Sintomas de falha:**

- Tensões desequilibradas
- Curto-circuito
- Ruído
- Vazamento
- Vibrações

**Áreas de falha:**

- Elétrica
- Mecânica
- Hidráulica
- Pneumático

**Tipos de falha:**

- Enrolamento do estator principal com defeito
- Diodo defeituoso
- Enrolamentos sujos
- Gerador defeituoso
- Sensor defeituoso

## <a name="create-fault-symptoms"></a>Criar sintomas de falha

Siga estas etapas para criar uma lista de sintomas que podem ser usados no designer de falhas.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Sintomas de falha**.
2. Selecione **Novo** para criar um registro.
3. No campo **Sintoma de falha**, insira um nome para o sintoma de falha.
4. No campo **Descrição**, insira uma descrição.
5. Selecione **Salvar**.

## <a name="create-fault-areas"></a>Criar áreas de falha

Siga estas etapas para criar uma lista de áreas ou locais que podem ser usados no designer de falhas.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Áreas de falha**.
2. Selecione **Novo** para criar um registro.
3. No campo **Área com falha**, insira um nome para a área com falha.
4. No campo **Descrição**, insira uma descrição.
5. Selecione **Salvar**.

## <a name="create-fault-types"></a>Criar tipos de falha

Siga estas etapas para criar uma lista de tipos de falhas que podem ser usados no designer de falhas.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Tipos de falha**.
2. Selecione **Novo** para criar um registro.
3. No campo **Tipo de falha**, insira um nome para o tipo de falha.
4. No campo **Descrição**, insira uma descrição.
5. Selecione **Salvar**.

## <a name="set-up-the-fault-designer"></a>Configurar o designer de falha

No designer de falhas, você configura os dados das falhas nos tipos de ativos.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Designer de falha**.
2. No painel esquerdo, selecione o tipo de ativo para o qual configurar um registro de falha.
3. Na Guia Rápida **Sintoma de falha**, selecione **Adicionar linha** e, no campo **Sintoma de falha**, selecione um sintoma de falha.
4. Na Guia Rápida **Área com falha**, selecione **Adicionar linha** e, no campo **Área com falha**, selecione uma área com falha.
5. Na Guia Rápida **Tipo de falha**, selecione **Adicionar linha** e, no campo **Tipo de falha**, selecione um tipo de falha.
6. Para criar rapidamente combinações de todos os sintomas, áreas e tipos de falha existentes para o tipo de ativo selecionado, selecione **Criar combinações de falhas**. Essa função é útil se você adicionou muitos sintomas, áreas e tipos de falha. É mais fácil excluir as linhas de qualquer combinação irrelevante para o tipo de ativo que criar novas linhas manualmente.

    > [!NOTE]
    > Para copiar a configuração de sintomas, áreas e tipos de falha de um tipo de ativo para o tipo de ativo selecionado, selecione **Copiar do tipo de ativo**.

7. Selecione **Salvar** para salvar as alterações.

![Página do designer de falha](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Criar causas de falha

Siga estas etapas para criar uma lista de causas conhecidas de falhas que podem ser adicionadas a uma ordem de serviço ou solicitação de manutenção.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Causas da falha**.
2. Selecione **Novo** para criar um registro.
3. No campo **Causa da falha**, insira um nome para a causa da falha.
4. No campo **Descrição**, insira uma descrição.
5. Selecione **Salvar**.

## <a name="create-fault-remedies"></a>Criar soluções de falha

Siga estas etapas para criar uma lista de sugestões para correção e reparo que podem ser adicionadas a uma ordem de serviço ou solicitação de manutenção.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Soluções de falha**.
2. Selecione **Novo** para criar um registro.
3. No campo **Solução de falha**, insira um nome para a solução de falha.
4. No campo **Descrição**, insira uma descrição.
5. Selecione **Salvar**.

> [!NOTE]
> Você pode alterar os nomes dos sintomas, áreas, tipos, causas e soluções de suas falhas, conforme necessário. As alterações de nome são refletidas automaticamente nos registros de falha relacionados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]