---
title: Configurar grupos de impostos do item
description: Este artigo explica como configurar grupos de impostos do item no serviço Cálculo de Imposto.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 3bc705bc8173ad2bc8ef883e6dc80b0a187314ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846453"
---
# <a name="set-up-item-tax-groups"></a>Configurar grupos de impostos do item

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar grupos de impostos do item no serviço Cálculo de Imposto. Ele também explica como configurar a matriz da regra de aplicabilidade do grupo de impostos do item e como configurar linhas na matriz.

O conceito de grupos de impostos do item no serviço Cálculo de Imposto é semelhante ao conceito de grupos de impostos do item no Microsoft Dynamics 365 Finance. Eles são grupos de códigos de imposto. O serviço de Cálculo de Imposto usa a interseção de um grupo de impostos e um grupo de impostos de item para determinar os códigos de imposto.

> [!IMPORTANT]
> A configuração dos grupos de impostos do item no serviço de Cálculo de Imposto é agnóstica à entidade legal. Você pode concluir essa configuração no RCS (Regulatory Configuration Service) somente uma vez. Quando você habilitar o serviço de Cálculo de Imposto no Finance, os grupos de impostos do item serão sincronizados automaticamente com a entidade legal selecionada.

## <a name="set-up-an-item-tax-group"></a>Configurar um grupo de impostos do item 

Siga estas etapas para configurar um grupo de impostos do item.

1. Entre no [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Acesse **Espaços de trabalho** \> **Recursos de globalização** \> **Cálculo de imposto**.
3. Selecione o recurso e a versão que deseja configurar e selecione **Editar**.
4. Na guia **Geral**, selecione **Versão da configuração**.
5. Na guia **Grupo de impostos do item**, selecione **Gerenciar coluna**. Se você estiver configurando um grupo de impostos do item pela primeira vez, os campos na caixa de diálogo **Gerenciar coluna** serão definidos automaticamente.
6. Na lista à esquerda, expanda o nó **Linhas** e marque a caixa de seleção **Grupo de impostos do item**.

    ![Grupo de impostos do item selecionado no nó "Linhas" da caixa de diálogo "Gerenciar colunas".](media/select-item-tax-group.png)

7. Selecione o botão de seta para a direita para adicionar **Grupo de impostos do item** à lista **Colunas selecionadas** à direita.

    ![Grupo de impostos do item adicionado à lista "Colunas selecionadas".](media/add-item-tax-group.png)

8. Selecione **OK**.

## <a name="configure-an-item-tax-group"></a>Configurar um grupo de impostos do item

Depois que você configurar um grupo de impostos do item, a matriz da regra de aplicabilidade será criada. Você pode adicionar linhas à matriz para configurar o grupo de impostos do item.

1. Na guia **Grupo de impostos do item**, selecione **Adicionar**.
2. No campo **Grupo de impostos do item**, insira o nome do grupo.

    > [!IMPORTANT]
    > Recomendamos que você use no máximo 10 caracteres no nome do grupo de impostos do item. Esse nome é sincronizado com o Finance, que tem um limite de 10 caracteres para os nomes dos grupos de impostos do item.

3. No campo **Códigos de imposto**, marque a caixa de seleção para cada código de imposto que você deseja incluir no grupo de impostos do item. Você pode incluir vários códigos de imposto em um grupo de impostos do item.

    ![Vários códigos de imposto selecionados no campo Códigos de imposto.](media/multiple-tax-codes-selection.png)

4. Repita as etapas de 1 a 3 para adicionar mais grupos de impostos do item.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
