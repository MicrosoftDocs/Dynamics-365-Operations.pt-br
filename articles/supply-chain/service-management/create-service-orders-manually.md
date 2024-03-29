---
title: Criar ordens de serviço manualmente
description: Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1764d97d4492e7b982a5d2c9f7e7f1c15380be1d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014841"
---
# <a name="create-service-orders-manually"></a>Criar ordens de serviço manualmente    

[!include [banner](../includes/banner.md)]


Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**. Também é possível criar uma ordem de serviço a partir de um projeto.

> [!TIP]
> <P>Você pode usar processos automatizados para criar ordens de serviço. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Criar uma ordem de serviço manualmente a partir de um contrato de serviço

1.  Selecione **Gerenciamento de serviços** \> **Contratos de serviço** \> **Contratos de serviço**.

2.  Selecione um contrato de serviço ou crie um novo.

3.  Selecione a guia **Entregar** e, no grupo **Criar**, selecione **Ordens de serviço planejadas** para abrir o formulário **Criar ordens de serviço**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Criar uma ordem de serviço manualmente no formulário Ordens de serviço

1.  Selecione **Gerenciamento de serviços** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Selecione **Novo** para criar uma nova ordem de serviço.

3.  Criar as linhas de ordem de serviço para a ordem de serviço.

> [!NOTE]
> <P>Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço. Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</P>

## <a name="create-a-service-order-from-a-project"></a>Criar uma ordem de serviço a partir de um projeto

1.  Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.

2.  No formulário **Projetos**, no **Painel de Ações**, selecione a guia **Gerenciar** \> selecione **Serviço** \> **Ordens de serviço**.

3.  Siga o procedimento anterior para criar uma ordem de serviço manualmente no formulário **Ordens de serviço**. O campo **ID de projeto** exibe a referência do projeto.

> [!NOTE]
> <P>Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço. Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Criar uma ordem de serviço a partir de um formulário de ordem de Venda

Você pode criar uma ordem de serviço do formulário **Ordens de venda** usando o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.

1.  Acesse **Vendas e marketing** \> **Ordens de venda** \> **Todas as ordens de venda**.

2.  Abra a ordem de venda relevante.

3.  Na guia **Ordem de venda**, selecione **Ordem de serviço** para iniciar o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.

4.  Selecione **Avançar \>** e conclua as seguintes etapas na página **Selecionar o contrato de ordem de serviço**:
    
      - Use o campo **Contrato de serviço** para selecionar o contrato de serviço ao qual a nova ordem de serviço deve ser associada.
    
      - Opcional: Use a lista **ID de projeto** para associar a ordem de serviço a um determinado projeto.

5.  Selecione **Avançar \>** e conclua as seguintes etapas na página **Criar ordem de serviço**:
    
      - Insira uma data e hora para que a chamada de serviço seja iniciada no campo **Hora de serviço preferencial**.
    
      - Opcional: Modifique o texto no campo **Descrição**. Por padrão, este campo contem a descrição do contrato de serviço selecionado na página anterior.
    
      - No campo **Responsável**, selecione a ID do funcionário responsável pelo contrato e, se souber, a ID do técnico preferido do cliente para a chamada de serviço.
    
      - No campo **ID de contato**, selecione a pessoa na empresa do cliente que deve ser contatada referente a ordem de serviço.

6.  Selecione **Avançar \>** e, em seguida, **Concluir**.


## <a name="see-also"></a>Consulte também

[Ordens de Serviço](service-orders.md)

[Criar ordens de serviço automaticamente](create-service-orders-automatically.md)

[Criar ordens de serviço (formulário de classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]