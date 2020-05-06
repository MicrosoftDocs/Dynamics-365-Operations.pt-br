---
title: Concessões do projeto
description: Este tópico explica como criar ou modificar uma concessão.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282812"
---
# <a name="project-grants"></a>Concessões do projeto

[!include [banner](../includes/banner.md)]

Uma concessão é um prêmio em dinheiro para uma finalidade ou um projeto específico. Geralmente, há restrições sobre como uma concessão pode ser gasta. Em Gerenciamento e contabilidade do projeto, você pode inserir e rastrear concessões e definir seus relacionamentos com projetos e contratos de projeto. Por exemplo, é possível executar as seguintes tarefas:

- Associar concessões a projetos e fontes de financiamento por meio de links para o **Projeto** e páginas **Detalhes do contrato de projeto**.
- Inserir e controlar alterações em uma concessão à medida que ela faz a troca de um status para outro.
- Inserir e controlar custos, valores solicitados e os valores do bônus.
- Criar concessões mestre e associar subconcessões a elas.

Você pode criar uma concessão inserindo todos os detalhes em um novo registro ou pode copiar os detalhes de uma concessão existente e, em seguida, atualizá-los.

## <a name="create-a-new-grant"></a>Criar uma nova concessão

1. Vá para **Gerenciamento e contabilidade de projetos** \> **Concessões** \> **Concessões**.
2. Selecione **Novo** \> **Concessão**.
3. Na página de detalhes da concessão, na Guia Rápida **Geral**, no campo **ID de concessão**, insira um identificador alfanumérico para a concessão.
4. No campo **Nome da concessão**, insira um nome para a concessão.
5. No campo **Descrição**, adicione detalhes sobre a nova concessão.

    A maioria dos outros campos na página são opcionais e você pode inserir as informações aos poucos ou todas as informações que desejar.

    A lista a seguir descreve as informações especificadas em cada Guia Rápida da página de detalhes de concessão:

    - **Geral** – Insira o nome, o status, a descrição, a finalidade e o valor da concessão.
    - **Informações de contato** – Insira detalhes sobre os membros da equipe e o departamento que gerencia a concessão e sobre o cliente da concessão ou a organização fonte da concessão. Você também pode indicar se a sua organização é uma entidade de aprovação que receberá a concessão e transmiti-la para outro destinatário. Selecione **Adicionar** para adicionar informações de contato, como números de telefone e endereços de email da organização que fornece a concessão.
    - **Datas e prazos** – Insira as datas relacionadas à concessão e à solicitação da concessão. Os exemplos incluem a data de vencimento do aplicativo, a data de envio e a data em que a concessão foi aprovada ou rejeitada.
    - **Projetos associados e contratos de projeto** – Você pode inserir informações nessa Guia Rápida somente se o campo **Status da concessão** na Guia Rápida **Geral** estiver definida como **Ativa** ou **Concedida**. Selecione entre as seguintes opções para concluir a tarefa relacionada:

        - **Adicionar fonte de financiamento** – Adicionar uma nova fonte de financiamento para a concessão. Você pode inserir todos os detalhes agora ou usar as informações padrão e atualizá-las posteriormente.
        - **Adicionar contrato de projeto** – Adicionar ou atualizar informações de contrato de projeto.
        - **Adicionar projeto** – Adicionar ou atualizar detalhes do projeto.

    - **Configuração** – Insira detalhes sobre fundos correspondentes, se essas informações forem necessárias. Muitas organizações que dão concessões exigem que destinatários gastem um determinado valor de seu próprio dinheiro ou recursos que correspondam ao valor que foi dado na concessão. No campo **Local de projeto ou ID de rastreamento**, você pode inserir um identificador que seja diferente do identificador de projeto.

        > [!NOTE]
        > Se parte da concessão for dada a uma organização diferente, defina a opção **Concessão parcial** como **Sim**. Para concessões dadas nos Estados Unidos, você pode especificar se uma concessão será dada em uma carta de ordem estadual ou federal.

    - **Detalhes de retirada** – Adicionar ou atualizar informações sobre a frequência com que os fundos de concessão podem ser retirados, faturados ou gastos.

## <a name="create-a-new-grant-from-a-copy"></a>Criar uma nova concessão a partir de uma cópia

1. Vá para **Gerenciamento e contabilidade de projetos** \> **Concessões** \> **Concessões**.
2. Selecione **Novo** \> **Copiar a partir da concessão**.
3. Insira um identificador alfanumérico e um nome para a nova concessão e selecione **OK**.
4. Na página detalhes da concessão, revise os detalhes da concessão copiada e faça as alterações necessárias. A maioria dos campos na página são opcionais.

## <a name="view-or-modify-grant-details"></a>Exibir ou modificar detalhes da concessão

1. Vá para **Gerenciamento e contabilidade de projetos** \> **Concessões** \> **Concessões**.
2. Selecione a concessão a ser modificada.
3. No Painel de Ação, na guia **Concessão**, no grupo **Manter**, selecione **Editar**.
4. Revise os detalhes da concessão e faça as alterações necessárias.
