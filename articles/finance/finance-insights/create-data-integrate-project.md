---
title: Criar um projeto de integração de dados
description: Este tópico explica como criar um projeto de integração de dados.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7841f8b31e0ac1a40dce9acaac747f5f378236e0
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752655"
---
# <a name="create-a-data-integration-project"></a>Criar um projeto de integração de dados

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como criar um projeto de integração de dados.

1. Entre no Microsoft Dynamics 365 Finance.
2. Acesse **Espaços de trabalho \> Gerenciamento de dados** e selecione **Entidades de dados**. Aguarde até que todas as entidades de dados tenham sido atualizadas antes de passar para a próxima etapa.
3. Abra o [portal do Power Apps](https://make.powerapps.com/) e siga estas etapas:

    1. Selecione o ambiente apropriado.
    2. No painel de navegação esquerdo, selecione **Dataverse \> Conexões**.
    3. Conecte a instâncias apropriadas dos seguintes itens:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Abra os [ambientes do Power Apps](https://admin.powerapps.com/environments) e siga estas etapas:

    1. Selecione **Integração de dados**.
    2. Selecione **Conjuntos de conexão**.
    3. Selecione **Novo conjunto de conexão**.
    4. Digite o nome da conexão.
    5. Selecione as conexões apropriadas para os seguintes itens:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Selecione o mapeamento de organização apropriado.
    7. Selecione **Criar**.

5. Abra os [ambientes do Power Apps](https://admin.powerapps.com/environments) e siga estas etapas:  

    1. Crie projetos de integração de dados para os seguintes modelos usando o conjunto de conexões que você acabou de criar:

        - Resultado dos insights de pagamentos de clientes (CDS para Fin and Ops 10.0.17+)
        - Resultados de série temporal de fluxo de caixa (CDS a Fin e Ops)
        - Resultados de série temporal de orçamento (CDS a Fin e Ops)

    2. Defina o plano apropriado para cada projeto.

> [!NOTE]
> Se você não vir as entidades necessárias no CDS, Acesse **Crédito e cobranças > Configuração > Insights do Finance > Parâmetros de insights do Finance**, habilite o recurso de previsões de pagamento de cliente e clique no botão **Criar modelo de previsão**. Quando a implantação do modelo de IA é concluída (bem ou mal sucedida), as entidades do CDS necessárias para criar a integração serão implantadas no CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
