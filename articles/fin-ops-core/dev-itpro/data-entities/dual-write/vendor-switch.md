---
title: Alternar entre designs de fornecedor
description: Este tópico descreve como alternar a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/20/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 90e29359aa2a367fe540411a8a808d86abb06dcc
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781311"
---
# <a name="switch-between-vendor-designs"></a>Alternar entre designs de fornecedor

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor 

Se você optar por usar a tabela **Conta** para armazenar fornecedores do tipo **Organização** e a tabela **Contato** para armazenar fornecedores do tipo **Pessoa**, configure os seguintes fluxos de trabalho. Caso contrário, essa configuração não é necessária.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Use o design de fornecedor estendido para fornecedores do tipo Organização

O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho. Você criará um fluxo de trabalho para cada modelo.

+ Criar Fornecedores na Tabela Contas
+ Criar Fornecedores na Tabela Fornecedores
+ Atualizar Fornecedores na Tabela Contas
+ Atualizar Fornecedores na Tabela Fornecedores

Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:

1. Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Contas**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de criação de fornecedores para a tabela **Conta**.

    ![Processo de fluxo de trabalho Criar Fornecedores na Tabela Contas.](media/create_process.png)

2. Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Contas**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de atualização de fornecedores para a tabela **Conta**.
3. Crie um processo de fluxo de trabalho para a tabela **Conta** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores na Tabela Fornecedores**.
4. Crie um processo de fluxo de trabalho para a tabela **Conta** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores na Tabela Fornecedores**.
5. Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos. Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.

    ![Botão Converter para fluxo de trabalho em segundo plano.](media/background_workflow.png)

6. Ative os fluxos de trabalho que você criou para as tabelas **Conta** e **Fornecedor** a fim de começar a usar a tabela **Conta** para armazenar informações de fornecedores do tipo **Organização**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Use o design de fornecedor estendido para fornecedores do tipo Pessoa

O pacote de solução **Dynamics365FinanceExtended** contém os seguintes modelos de processo de fluxo de trabalho. Você criará um fluxo de trabalho para cada modelo.

+ Criar Fornecedores do tipo Pessoa na Tabela Fornecedores
+ Criar Fornecedores do tipo Pessoa na Tabela Contatos
+ Atualizar Fornecedores do tipo Pessoa na Tabela Contatos
+ Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores

Para criar processos de fluxo de trabalho usando os modelos de processo de fluxo de trabalho, siga estas etapas:

1. Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Criar Fornecedores do tipo Pessoa na Tabela Contatos**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de criação de fornecedores para a tabela **Contato**.
2. Crie um processo de fluxo de trabalho para a tabela **Fornecedor** e selecione o modelo de processo de fluxo de trabalho **Atualizar Fornecedores do tipo Pessoa na Tabela Contatos**. Em seguida, selecione **OK**. Este fluxo de trabalho lida com o cenário de atualização de fornecedores para a tabela **Contato**.
3. Crie um processo de fluxo de trabalho para a tabela **Contato** e selecione o modelo **Criar Fornecedores do tipo Pessoa na Tabela Fornecedores**.
4. Crie um processo de fluxo de trabalho para a tabela **Contato** e selecione o modelo **Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores**.
5. Você pode configurar os fluxos de trabalho como fluxos de trabalho em tempo real ou em segundo plano de acordo com seus requisitos. Para configurar um fluxo de trabalho como um fluxo de trabalho em segundo plano, selecione **Converter para fluxo de trabalho em segundo plano**.
6. Ative os fluxos de trabalho que você criou nas tabelas **Contato** e **Fornecedor** para começar a usar a tabela **Contato** para armazenar informações de fornecedores do tipo **Pessoa**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]