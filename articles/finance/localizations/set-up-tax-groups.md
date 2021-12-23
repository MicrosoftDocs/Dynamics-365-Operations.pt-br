---
title: Configurar grupos de impostos
description: Este tópico explica como configurar grupos de impostos no serviço de Cálculo de Imposto.
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
ms.openlocfilehash: 50abafb958edfb8476434ff5842cd84cb186962f
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883841"
---
# <a name="set-up-tax-groups"></a>Configurar grupos de impostos

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar grupos de impostos no serviço de Cálculo de Imposto. Ele também explica como configurar a matriz da regra de aplicabilidade do grupo de impostos e como configurar linhas na matriz.

O conceito de grupos de impostos no serviço de Cálculo de Impostos é semelhante ao conceito de grupos de impostos no Microsoft Dynamics 365 Finance. Eles são grupos de códigos de imposto. O serviço de Cálculo de Imposto usa a interseção de um grupo de impostos e um grupo de impostos de item para determinar os códigos de imposto.

No entanto, os grupos de impostos no serviço de Cálculo de Imposto diferem dos grupos de impostos no Finance, pois não há parâmetros adicionais neles, como **Imposto sobre o uso** e **Isento de impostos**. Em vez disso, esses parâmetros estão disponíveis no nível do código de imposto.

> [!IMPORTANT]
> A configuração dos grupos de impostos no Serviço de Cálculo de Imposto é agnóstica à entidade legal. Você pode concluir essa configuração no RCS (Regulatory Configuration Service) somente uma vez. Quando você habilitar o serviço de Cálculo de Imposto no Finance, os grupos de impostos serão sincronizados automaticamente com a entidade legal selecionada.

## <a name="set-up-a-tax-group"></a>Configurar um grupo de impostos

Siga estas etapas para configurar um grupo de impostos:

1. Entre no [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Acesse **Espaços de trabalho** \> **Recursos de globalização** \> **Cálculo de imposto**.
3. Selecione o recurso e a versão que deseja configurar e selecione **Editar**.
4. Na guia **Geral**, selecione **Versão da configuração**.
5. Na guia **Grupo de impostos**, selecione **Gerenciar Coluna**. Se você estiver configurando um grupo de impostos pela primeira vez, os campos na caixa de diálogo **Gerenciar Coluna** serão definidos automaticamente.
6. Na lista à esquerda, expanda o nó **Linhas** e marque a caixa de seleção para o **Grupo de impostos**.

    ![Grupo de impostos selecionado no Nó Linhas da caixa de diálogo Gerenciar colunas.](media/select-tax-group.png)

7. Selecione o botão de seta para a direita para adicionar **Grupo de Impostos** à lista **Colunas selecionadas** à direita.

    ![Grupo de impostos adicionado à lista Colunas selecionadas.](media/add-tax-group.png)

8. Selecione **OK**.

## <a name="configure-a-tax-group"></a>Configurar um grupo de impostos

Depois que você configurar um grupo de impostos, a matriz da regra de aplicabilidade do grupo de impostos será criada. Você pode adicionar linhas à matriz para configurar o grupo de impostos.

1. Na guia **Grupo de impostos**, selecione **Adicionar**.
2. No campo **Grupo de impostos**, insira o nome do grupo de impostos.

    > [!IMPORTANT]
    > Recomendamos que você limite o nome do grupo de impostos a 10 caracteres. Esse nome é sincronizado com o Finance, que tem um limite de 10 caracteres para os nomes dos grupos de impostos.

3. No campo **Códigos de imposto**, marque a caixa de seleção para cada código de imposto que você deseja incluir no grupo de impostos. Você pode incluir vários códigos de imposto em um grupo de impostos.

    ![Vários códigos de imposto selecionados no campo Códigos de imposto.](media/multiple-tax-codes-selection.png)

4. Repita as etapas de 1 a 3 para adicionar mais grupos de impostos.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
