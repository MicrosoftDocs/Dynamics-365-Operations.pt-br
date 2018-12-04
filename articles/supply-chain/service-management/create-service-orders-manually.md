---
title: "Criar ordens de serviço manualmente"
description: "Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a0cc6b2646929776f4efb20474de6b0fc5c4719c
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-manually"></a>Criar ordens de serviço manualmente    

[!include [banner](../includes/banner.md)]


Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**. Também é possível criar uma ordem de serviço a partir de um projeto.

> [!TIP]
> <P>Você pode usar processos automatizados para criar ordens de serviço. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Criar uma ordem de serviço manualmente a partir de um contrato de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.

2.  Selecione um contrato de serviço ou crie um novo.

3.  Clique na guia **Entregar** e no grupo **Criar** clique em **Ordens de serviço planejadas** para abrir o formulário **Criar ordens de serviço**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Criar uma ordem de serviço manualmente no formulário Ordens de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Pressione Ctrl+N para criar uma nova ordem de serviço.

3.  Criar as linhas de ordem de serviço para a ordem de serviço.

> [!NOTE]
> <P>Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço. Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</P>

## <a name="create-a-service-order-from-a-project"></a>Criar uma ordem de serviço a partir de um projeto

1.  Clique em **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.

2.  No formulário **Projetos**, no **Painel de Ação**, clique na guia **Gerenciar** \> clique e **Serviço** \> **Ordens de serviço**.

3.  Siga o procedimento anterior para criar uma ordem de serviço manualmente no formulário **Ordens de serviço**. O campo **ID de projeto** exibe a referência do projeto.

> [!NOTE]
> <P>Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço. Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Criar uma ordem de serviço a partir de um formulário de ordem de Venda

Você pode criar uma ordem de serviço do formulário **Ordens de venda** usando o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.

2.  Abra a ordem de venda relevante.

3.  Na guia **Ordem de venda**, clique em **Ordem de serviço** para iniciar o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.

4.  Clique em **Avançar \>**, e conclua as seguintes etapas na página **Selecionar o contrato de ordem de serviço**:
    
      - Use o campo **Contrato de serviço** para selecionar o contrato de serviço ao qual a nova ordem de serviço deve ser associada.
    
      - Opcional: Use a lista **ID de projeto** para associar a ordem de serviço a um determinado projeto.

5.  Clique em **Avançar \>**, e conclua as seguintes etapas na página **Criar ordem de serviço**:
    
      - Insira uma data e hora para que a chamada de serviço seja iniciada no campo **Hora de serviço preferencial**.
    
      - Opcional: Modifique o texto no campo **Descrição**. Por padrão, este campo contem a descrição do contrato de serviço selecionado na página anterior.
    
      - No campo **Responsável**, selecione a ID do funcionário responsável pelo contrato e, se souber, a ID do técnico preferido do cliente para a chamada de serviço.
    
      - No campo **ID de contato**, selecione a pessoa na empresa do cliente que deve ser contatada referente a ordem de serviço.

6.  Clique em **Avançar \>** e depois em **Finalizar**.


## <a name="see-also"></a>Consulte também

[Ordens de serviço](service-orders.md)

[Criar ordens de serviço automaticamente](create-service-orders-automatically.md)

[Criar ordens de serviço (formulário de classe)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\)) 


