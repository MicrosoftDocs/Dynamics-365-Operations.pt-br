---
title: Análise de falhas de ativos
description: Este tópico explica a análise de falhas de ativos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918432"
---
# <a name="asset-fault-analysis"></a>Análise de falhas de ativos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

No Gerenciamento de Ativos, você pode analisar os registros de falhas de ativos para obter uma visão geral do número total de falhas registradas durante um período específico. Os registros de falhas podem ser analisados de diferentes perspectivas; por exemplo, com foco em ativos, tipos de ativos, locais funcionais, sintomas de falhas ou tipos de falhas.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Análise de falhas de ativos**.

2. Na caixa de diálogo **Cálculo da análise de falhas de ativos**, você pode usar o campo**Nível** para indicar o grau de detalhamento nas linhas de falhas de ativos relativas a locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todas as linhas de falhas de ativos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de falhas de ativos em todo o nível do local funcional ao qual elas estão relacionadas.

3. Para limitar a pesquisa, você poderá selecionar ativos específicos, datas de falha, causas de falha e soluções de falha na Guia Rápida **Registros a serem incluídos**.

4. Clique em **OK**para iniciar o cálculo.

5. Na guia **Análise de falhas de ativos**, clique em um ou mais botões nos grupos do Painel de Ações **Agrupar por...** para exibir o nível de detalhes que deseja ver. Os botões ativados são realçados. Ative ou desative os botões clicando neles.

6. Clique em **Atualizar cálculos** para mostrar suas seleções na tela. 

>[!NOTE]
>Sempre que ativar ou desativar botões nos grupos do Painel de Ações **Agrupar por...**, lembre-se de clicar no botão **Atualizar cálculos** depois de alterar as seleções. Isso é necessário porque uma grande quantidade de dados é processada à medida que você recalcula a probabilidade de falha.

Há várias formas de analisar registros de falhas. Abaixo você verá exemplos em cinco capturas de tela de como diferentes seleções de dados fornecem diferentes informações. Você verá como as diferentes seleções fornecem mais informações e detalhes na análise dos registros de falhas de ativos.

Na captura de tela abaixo, apenas o botão **Sintoma** está selecionado.

- Registros de falhas foram feitos com três sintomas de falha: "Vazamento de ar", "Fusível queimado" e "Equipamento danificado".  
- Na coluna **Probabilidade %**, todas as porcentagens somam 100%. A probabilidade é baseada em todos os registros **Sintoma** nessa análise de falha.

![Figura 1](media/06-controlling-and-reporting.png)


Na captura de tela abaixo, **Ano** e **Mês** são adicionados para mostrar como você pode exibir os registros de falhas durante um período selecionado.

- Os sintomas de falha agora são mostrados como registros por ano/mês.  
- Na coluna **Probabilidade %**, se você adicionar todas as porcentagens de cada mês, elas somarão 100%. A probabilidade é baseada nos registros **Sintoma** nessa análise de falha. Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um sintoma de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse sintoma de falha.

![Figura 2](media/07-controlling-and-reporting.png)


- A combinação de ativos e um tipo de ativo é usada como base para os cálculos mostrados nas três capturas de tela abaixo, o que aumentará em nível de detalhes.  
- Geralmente, os botões nos grupos do Painel de Ações **Agrupar por data**, **Agrupar por ativo**, **Agrupar por local funcional**, bem como o botão **Falha** (Fault ID), contêm períodos ou relações de ativos. Os botões **Sintoma**, **Área**, **Tipo**, **Causa** e **Recurso** são categorizações usadas no gerenciamento de falhas para analisar registros de falhas de ativos e identificar áreas problemáticas.  

Na captura de tela abaixo, **Ativo** e **Tipo de ativo** foram adicionados para fornecer mais detalhes sobre os registros de falhas.

- Os sintomas de falha agora são divididos em combinações **Ativo** / **Tipo de ativo** / **Sintoma**.  
- Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** respectivamente, cada uma delas somará 100%. A probabilidade é baseada nos registros **Sintoma** nessa análise de falha. Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um sintoma de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse sintoma de falha.

![Figura 3](media/08-controlling-and-reporting.png)


Na captura de tela abaixo, a **Área** foi adicionada a **Sintoma**, **Ativo** e **Tipo de ativo** para fornecer mais detalhes sobre os registros de falhas.

- Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** em um ativo, cada uma delas somará 100%. A probabilidade é baseada na combinação de **Sintoma** e **Área** nessa análise de falha. Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de uma área de falha a ser examinada com mais cuidado para encontrar uma maneira de limitar o número de registros dessa área de falha.  

![Figura 4](media/09-controlling-and-reporting.png)


Na captura de tela abaixo, o **Tipo** foi adicionado e o cálculo mais detalhado neste exemplo é mostrado.
 
- Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** em um ativo, cada uma delas somará 100%. A probabilidade é baseada na combinação de **Sintoma**, **Área** e **Tipo** nessa análise de falha. Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um tipo de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse tipo de falha.

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
>Para obter uma visão geral de todos os registros de falhas criados em ordens de serviço e solicitações de manutenção, clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo**. Na página **Falhas de ativo**, selecione um registro de falha de ativo e expanda o painel **Informações relacionadas** para ver informações sobre a ordem de serviço ou solicitação de manutenção relacionada.

