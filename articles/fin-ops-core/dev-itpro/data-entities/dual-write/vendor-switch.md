---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: ffd7a4c01810578b4abb6942aeff76e5147fafa9
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173030"
---
# <a name="switch-between-vendor-designs"></a>Alternar entre designs de fornecedor

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor 

Se você optar por usar a entidade **Conta** para armazenar fornecedores do tipo **Organização** e a entidade **Contato** para armazenar fornecedores do tipo **Pessoa**, configure o seguinte fluxos de trabalho. Caso contrário, essa configuração não é necessária.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Use o design de fornecedor estendido para fornecedores do tipo Organização

O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho. Você criará um fluxo de trabalho para cada modelo.

+ Criar fornecedores na entidade Contas
+ Criar fornecedores na entidade Fornecedores
+ Atualizar fornecedores na entidade Contas
+ Atualizar fornecedores na entidade Fornecedores

Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:

1. Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores na entidade Contas**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Conta**.

    ![Criar fornecedores no processo de fluxo de trabalho da entidade Contas](media/create_process.png)

2. Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores na entidade Contas**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Conta**.
3. Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores na entidade Fornecedores**.
4. Crie um processo de fluxo de trabalho para a entidade **Conta** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores na entidade Fornecedores**.
5. Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos. Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.

    ![Botão Converter para fluxo de trabalho em segundo plano](media/background_workflow.png)

6. Ative os fluxos de trabalho que você criou para as entidades **Conta** e **Fornecedor** para começar a usar a entidade **Conta** para armazenar informações de fornecedores do tipo **Organização**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Use o design de fornecedor estendido para fornecedores do tipo Pessoa

O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho. Você criará um fluxo de trabalho para cada modelo.

+ Criar fornecedores do tipo Pessoa na entidade Fornecedores
+ Criar fornecedores do tipo Pessoa na entidade Contatos
+ Atualizar fornecedores do tipo Pessoa na entidade Contatos
+ Atualizar fornecedores do tipo Pessoa na entidade Fornecedores

Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:

1. Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores do tipo Pessoa na entidade Contatos**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de criação de fornecedor para a entidade **Contato**.
2. Crie um processo de fluxo de trabalho para a entidade **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores do tipo Pessoa na entidade Contatos**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de atualização de fornecedor para a entidade **Contato**.
3. Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Criar fornecedores do tipo Pessoa na entidade Fornecedores**.
4. Crie um processo de fluxo de trabalho para a entidade **Contato** e selecione o modelo de processo de fluxo de trabalho **Atualizar fornecedores do tipo Pessoa na entidade Fornecedores**.
5. Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos. Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.
6. Ative os fluxos de trabalho que você criou nas entidades **Contato** e **Fornecedor** para começar a usar a entidade **Contato** para armazenar informações de fornecedores do tipo **Pessoa**.
