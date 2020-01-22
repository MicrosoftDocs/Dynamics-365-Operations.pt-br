---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar entre a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902716"
---
# <a name="switch-between-vendor-designs"></a>Alternar entre designs de fornecedor

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor 

Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer separar as informações de fornecedores das informações de clientes, utilize este design básico de fornecedor.  

![Fluxo básico de fornecedores](media/dual-write-vendor-data-flow.png)
 
Se você usa outros aplicativos do Dynamics 365 para controlar os fornecedores e quer continuar usando a entidade **Conta** para armazenar informações de fornecedores, utilize este design de fornecedor estendido. Neste design, informações estendidas de fornecedores, como status em espera e o perfil do fornecedor, são armazenadas na entidade **fornecedores** do Common Data Service. 

![Fluxo estendido de fornecedores](media/dual-write-vendor-detail.jpg)
 
Siga as etapas abaixo para usar o design estendido de fornecedor: 
 
1. O pacote de soluções **SupplyChainCommon** contém os modelos do processo de fluxo de trabalho mostrados na imagem a seguir.
    > [!div class="mx-imgBorder"]
    > ![Modelos do processo de fluxo de trabalho](media/dual-write-switch-3.png)
2. Crie novos processos de fluxo de trabalho usando os modelos do processo de fluxo de trabalho: 
    1. Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Criar Fornecedores na Entidade Conta** e clique em **OK**. Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.
        > [!div class="mx-imgBorder"]
        > ![Criar Fornecedores na Entidade Conta](media/dual-write-switch-4.png)
    2. Crie um novo processo de fluxo de trabalho para a entidade **Fornecedor** usando o modelo de processo de fluxo de trabalho **Atualizar Entidade Contas** e clique em **OK**. Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**. 
        > [!div class="mx-imgBorder"]
        > ![Atualizar Entidade Contas](media/dual-write-switch-5.png)
    3. Crie novos processos de fluxo de trabalho com base nos modelos criados na entidade **Contas**. 
        > [!div class="mx-imgBorder"]
        > ![Criar fornecedores na entidade fornecedores](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Atualizar a entidade fornecedores](media/dual-write-switch-7.png)
    4. Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos. 
        > [!div class="mx-imgBorder"]
        > ![Converter para fluxo de trabalho em segundo plano](media/dual-write-switch-8.png)
    5. Ative os fluxos de trabalho que você criou nas entidades **Conta** e **Fornecedor** para começar a usar a entidade **Conta** para armazenar informações de fornecedor. 
 
