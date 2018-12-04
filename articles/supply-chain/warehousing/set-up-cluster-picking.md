---
title: "Configurar separação de cluster"
description: "Este tópico descreve como configurar a separação do cluster e como aplicar a confirmação do item com a separação do cluster."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2ec0890963b2b01407acac8003453faf370894b4
ms.openlocfilehash: 1c23421ddfda8c5f6fa27a31831a00ead6094db9
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2018

---

[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a>Configurar separação de cluster

Este tópico descreve como habilitar os operadores para usarem os dispositivos móveis para agrupar o trabalho de separação em clusters, de forma que possam selecionar itens de um único local para várias ordens de trabalho ao mesmo tempo. Isso é chamado de *separação de cluster*.

## <a name="about-cluster-picking"></a>Sobre separação de cluster

Depois que as ordens de trabalho são liberadas para o depósito, o trabalhador pode usar um dispositivo móvel para atribuir as ordens a um cluster. O cluster organizará o trabalho de separação para o trabalhador. Quando uma ordem de trabalho é atribuída a um cluster, o trabalhador deve usar a separação de cluster para executar o trabalho de separação da ordem. O trabalhador não pode usar outros métodos de separação. Se uma ordem de trabalho for atribuída a um cluster por engano, o trabalhador deverá dividir o cluster e recriá-lo.

Se for necessário, um trabalhador poderá passar um cluster para outro trabalhador. Isso altera o status do cluster para Aprovado. Quando o trabalhador usa um dispositivo móvel para indicar que o trabalho de separação e armazenamento foi concluído, a remessa ou a carga deve ser confirmada no cliente do Dynamics 365 for Finance and Operations.

## <a name="set-up-cluster-picking"></a>Configurar separação de cluster

Para habilitar a separação de cluster, você deverá configurar o seguinte:

-   **Perfis do cluster** – especifique se deseja gerar automaticamente as IDs do cluster, o número de posições a serem usadas, quando dividir os clusters e como sequenciar e verificar o trabalho de separação.

-   **Modelos de trabalho** – defina como criar o trabalho de separação para a separação do cluster.

-   **Diretivas de local** – especifique de onde separar itens e onde colocá-los.

-   **Itens de menu do dispositivo móvel** – configure um item de menu do dispositivo móvel para usar o trabalho existente que é direcionado pela separação de cluster. Você deve adicionar o item de menu a um menu do dispositivo móvel de forma que seja exibido em dispositivos móveis.

-   **Parâmetros de gerenciamento de depósito** – especifique a sequência numérica que será usada se você quiser gerar identificadores para clusters.

## <a name="set-up-a-cluster-profile"></a>Configurar um perfil de cluster

Para configurar um perfil de cluster, siga estas etapas:

1.  Clique em **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Perfis do cluster**.

2.  Clique em **Novo** para criar um novo perfil.

3.  Clique em **Criar cluster** e, em **Classificação de cluster**, clique em **Novo** para configurar os critérios de classificação para o cluster. Os critérios de classificação controlam a ordem na qual o trabalhador realizará o trabalho de separação. É possível adicionar quantos critérios forem necessários.

4.  No campo **Número de sequência**, insira um número para definir a ordem na qual os critérios de classificação são processados.

5.  No campo **Nome do campo**, selecione o campo que determinará a classificação. Por exemplo, se você selecionar o campo **WMSLocationId**, o trabalho será classificado por local.

6.  No campo **Classificação**, selecione uma das seguintes opções.

| **Opção**     | **Descrição**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Crescente**  | O trabalho de separação é ordenado em ordem crescente com base nos critérios de classificação. Por exemplo, se você usa o campo **WMSLocationId** como critério de classificação e as IDs do local são 1, 2, 3, 4, você escolherá primeiro do local 4. |
| **Decrescente** | O trabalho de separação é ordenado em ordem decrescente com base nos critérios de classificação. Por exemplo, se você usa o campo **WMSLocationId** como critério de classificação e as IDs do local são 1, 2, 3, 4, você escolherá primeiro do local 1. |

## <a name="item-confirmation"></a>Confirmação do item

Quando a separação do cluster é aplicada, confirmação do item é importante para verificar os itens adicionados aos clusters. Você pode verificar os itens na separação do cluster durante o processo de separação do cluster. A configuração é baseada na configuração de código de barras de produto.

### <a name="set-up-item-verification-with-cluster-picking"></a>Configurar verificação do item com separação de cluster

1.  No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: **Gerenciamento de depósito** \> **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.

2.  Do item de menu de dispositivo móvel, abra a **Configuração de confirmação de trabalho**. A opção **Confirmação do produto** permite que você verifique cada peça de estoque no dispositivo móvel quando verificado.

