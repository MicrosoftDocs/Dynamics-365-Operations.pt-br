---
title: Criar um projeto de integrador de dados (versão prévia)
description: Este tópico explica como criar um projeto de integrador de dados.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646244"
---
# <a name="create-a-data-integrator-project-preview"></a>Criar um projeto de integrador de dados (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como criar um projeto de integrador de dados.

1. Entre no Microsoft Dynamics 365 Finance.
2. Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione **Entidades de dados**. Aguarde até que todas as entidades de dados tenham sido atualizadas antes de passar para a próxima etapa.
3. Abra o [portal do Power Apps](https://make.powerapps.com/) e siga estas etapas:

    1. Selecione o ambiente apropriado.
    2. No painel de navegação esquerdo, selecione **Dados \> Conexões**.
    3. Conecte a instâncias apropriadas dos seguintes itens:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Abra os [ambientes do Power Apps](https://admin.powerapps.com/environments) e siga estas etapas:

    1. Selecione **Integrador de dados**.
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

        - Resultados de insights de pagamentos de clientes (CDS para Fin and Ops)
        - Resultados de série temporal de fluxo de caixa (CDS a Fin e Ops)
        - Resultados de série temporal de orçamento (CDS a Fin e Ops)

    2. Defina o plano apropriado para cada projeto.

> [!NOTE]
> Se você não vir as entidades necessárias no CDS, vá para **Crédito e cobranças > Configuração > Insights do Finance > Parâmetros de insights do Finance**, habilite o recurso de previsões de pagamento de cliente e clique no botão **Criar modelo de previsão**. Quando a implantação do modelo de IA é concluída (bem ou mal sucedida), as entidades do CDS necessárias para criar a integração serão implantadas no CDS.

## <a name="privacy-notice"></a>Aviso de privacidade

As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
