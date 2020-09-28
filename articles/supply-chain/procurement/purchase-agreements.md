---
title: Contratos de compra
description: Este artigo fornece informações sobre contratos de compras. Um contrato de compra é um contrato que compromete uma organização a comprar uma quantidade ou um valor especificado usando várias ordens de compra ao longo do tempo. Em troca desse compromisso, o comprador obtém preços e descontos especiais.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 253177103435c765bfe45daffeae0c436617af21
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803154"
---
# <a name="purchase-agreements"></a>Contratos de compra

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre contratos de compras. Um contrato de compra é um contrato que compromete uma organização a comprar uma quantidade ou um valor especificado usando várias ordens de compra ao longo do tempo. Em troca desse compromisso, o comprador obtém preços e descontos especiais. 

Os contratos de compra podem ser aplicados a uma quantidade específica de um produto, a um valor de moeda específico de um produto ou a um valor de moeda específico dos produtos em uma categoria de compras. Os preços e os descontos do contrato de compra substituem os preços e os descontos que são especificados em qualquer contrato comercial existente.  

Na página **Contratos de compra**, é possível criar, aplicar e acompanhar os contratos de compra existentes entre sua organização e seus fornecedores. Por exemplo, após criar um contrato de compra, você pode fazer pedidos diretamente usando ele. Cada contrato de compra tem um período de validade que é definido pela pessoa que o cria. A data de entrega de uma compra deve estar nas datas efetivas desse período de validade.  

Depois de criar um contrato de compra, você deverá ativá-lo para que ele entre em vigor. Para ativar um contrato de compra, defina a opção **Marcar contrato como efetivo** como **Sim**. 

Para impedir que seu contrato de compra seja usado e confirmado, marque o status do contrato como **Fechado**. Você ainda pode atualizar o status para **Efetivo** a qualquer momento depois de fazer esta alteração.

## <a name="responsible-workers-on-purchase-agreements"></a>Trabalhadores responsáveis em contratos de compra

Você pode identificar um trabalhador responsável principal e um trabalhador responsável secundário na classificação do contrato de compra. Esses valores serão herdados pelo contrato de compra resultante. Não é necessário adicionar trabalhadores responsáveis ao contrato de compra, e eles podem ser modificados diretamente a cada caso no próprio contrato de compra. Não é possível especificar um trabalhador responsável secundário sem um trabalhador responsável principal, embora você não precise ter um trabalhador responsável secundário. Não é possível especificar o mesmo trabalhador como o trabalhador responsável principal e secundário.

> [!IMPORTANT]
> Para que você possa usar o recurso de participante responsável, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:
> 
> - **Módulo:** *Tarefas de compras e fornecimento*
> - **Nome do recurso:** *participante responsável pelo contrato de compra*

## <a name="commitment-types"></a>Tipos de compromisso
Cada linha em um contrato de compra é um compromisso para comprar algum item. É possível usar linhas de várias ordens de compra (OCs) para atender ao compromisso. Existem quatro tipos de compromisso:

-   **Compromisso de quantidade do produto** – você compra uma quantidade específica de um produto.
-   **Compromisso de valor do produto** – você compra um valor específico de moeda de um produto.
-   **Compromisso de valor de categoria do produto** – você compra um valor específico de moeda em uma categoria de compras. O valor pode ser para um item de catálogo ou de fora do catálogo.
-   **Compromisso de valor** – você compra um valor de moeda específico de qualquer produto ou produtos em qualquer categoria de compras.

## <a name="pricing-terms-for-purchase-agreements"></a>Condições de preço para contratos de compra
As condições de preço podem variar, de acordo com o tipo de compromisso. As condições de preço dos contratos de compra substituem todas as outras condições de preço que são configuradas para contratos comerciais. A tabela a seguir descreve os campos relacionados ao preço que serão afetados por cada tipo de compromisso. Os campos que contêm **Sim** podem ser atualizados em uma linha de ordem.

| Tipo do compromisso                   | Preço unitário | Unidade de preço | Percentual de desconto | Valor de desconto à vista |
|-----------------------------------|------------|------------|------------------|----------------------|
| Compromisso de quantidade do produto       | Sim        | Sim        | Sim              | Sim                  |
| Compromisso de valor do produto          |            |            | Sim              |                      |
| Compromisso de valor de categoria de produto |            |            | Sim              |                      |
| Compromisso de valor                  |            |            | Sim              |                      |

## <a name="policies-for-purchase-agreements"></a>Políticas para contratos de compra
As políticas a seguir afetam o funcionamento do link entre um compromisso de contrato de compra e as linhas da OC correspondente:

-   **Imposição de valor máx.** – a quantidade ou o valor total de todas as linhas da ordem não pode exceder a quantidade ou o valor que é especificado no compromisso relacionado.
-   **O preço e o desconto são fixos** – O preço em uma linha da ordem e o preço no compromisso relacionado devem ser iguais. Se o preço foi alterado na linha da ordem, o link para o compromisso será desfeito. Se o link foi desfeito, a linha da ordem não contribuirá com o atendimento do compromisso.
-   **Valor de liberação mínimo e Valor de liberação máximo** – se um valor for especificado, você receberá uma mensagem se fizer alguma alteração em uma linha da ordem que faça com que ela seja diferente do compromisso relacionado.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Cálculos de preenchimento para contratos de compra
As quantidades e os valores do atendimento são mostrados na guia **Atendimento** na Guia Rápida **Detalhes da linha** da página **Contratos de compra**.  

A área **Atendimento** mostra o valor ou a quantidade restante necessário para atender ao compromisso.  

A área **Contrato** mostra a quantidade total ou o valor total da linha para a qual o contrato de vendas é válido.  

Você pode acessar as linhas da OC e as linhas da fatura que contribuem para o cálculo de atendimento ao selecionar a ação **Informações relacionadas** nas linhas ou no cabeçalho de um contrato de compra.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Histórico de versões e confirmações para contratos de compra
Quando você confirma um contrato de compra, a versão atual do contrato é armazenada em uma tabela histórica. Ao alterar o contrato de compra, você o confirma novamente para armazenar outra versão do contrato de compra no histórico. Se não confirmar um contrato de compra, você ainda poderá usá-lo para criar ordens de pagamento. No entanto, as informações do histórico do contrato de compra não são armazenadas. É possível visualizar ou imprimir todas as versões do contrato. Você pode compartilhar as revisões com seu fornecedor para obter aprovação.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Aplicando contratos de compra no processo de ordem
Quando você cria uma OC, pode aplicar um contrato de compra a ela. As informações sobre as condições do contrato, como as condições de pagamento, as condições de entrega e endereço de entrega, são copiadas para o cabeçalho da OC. Se a OC contiver uma ou mais linhas produtos ou categorias especificados no contrato de compra, os preços e os descontos do contrato de compra serão usados para essas linhas. O valor ou a quantidade na linha da ordem contribui para o atendimento ao compromisso no contrato de compra. A mesma OC pode incluir linhas que não estejam relacionadas a um contrato de compra e linhas com um compromisso para um contrato de compra.  

Você só poderá selecionar um contrato de compra quando estiver criando uma OC. Você não poderá selecionar um contrato de compra depois que a OC for criada.  
Em algumas situações em que as OCs são criadas indiretamente, você pode controlar se o Supply Chain Management pesquisará automaticamente os contratos de compra aplicáveis. Por exemplo, você pode fazer isso quando estiver confirmando automaticamente OCs planejadas ou criando OCs baseadas em ordens de venda.

## <a name="matching-policy-on-purchase-agreements"></a>Política de conciliação em contratos de compra
Você pode definir uma política de conciliação de linha no cabeçalho do contrato de compra. Essa política de conciliação de linha respeitará a política de conciliação de linha dos parâmetros de contas a pagar quando o campo **Permitir substituição de política de conciliação** na página **Parâmetros de Contas a pagar** (na Guia Rápida **Conciliação de preço e quantidade**) estiver definido como **Maior do que a política da empresa**. Os documentos que fazem referência ao contrato de compra usam a política de conciliação de linha definida no cabeçalho do contrato de compra, a menos que seja definido de outra forma em item correspondente, item e fornecedor ou política de compra de categoria.

## <a name="purchase-agreements-and-intercompany-trade"></a>Contratos de compra e comércio intercompanhia
As relações comerciais intercompanhia podem ser criadas entre contas de fornecedor e contas de cliente que estão em entidades legais diferentes. Quando uma ordem de venda ou uma OC é criada para um dos participantes, é criada uma cadeia de ordem intercompanhia. Na cadeia de ordem, a ordem de venda e a OC são criadas nas entidades legais apropriadas.  

Você pode criar um contrato de compra ou um contrato de venda para um dos participantes comerciais intercompanhia. Assim, é possível gerar o contrato de venda ou contrato de compra correspondente para o outro participante comercial intercompanhia na outra entidade legal.  

Se você criar uma OC intercompanhia que usa o contrato de compra intercompanhia em uma entidade legal, a ordem de venda intercompanhia correspondente usará o contrato de venda intercompanhia correspondente na outra entidade legal. O preenchimento dos compromissos do contrato de venda e o preenchimento dos contratos de compra são sincronizados, assim como a ordem de venda intercompanhia e a OC intercompanhia.

## <a name="financial-dimensions-on-purchase-agreements"></a>Dimensões financeiras nos contratos de compra
Você pode copiar as dimensões financeiras para os cabeçalhos de documento ou para as linhas individuais de um contrato de compra. Se você alterar as dimensões no cabeçalho do contrato ou na linha do contrato, a alteração não afetará nenhuma ordem liberada, mas se refletirá em todas as ordens novas.

<a name="additional-resources"></a>Recursos adicionais
--------

[Criar um contrato de compra](tasks/create-purchase-agreement.md)

[Criar uma ordem de liberação de compra de um contrato de compra](tasks/create-purchase-release-order-purchase-agreement.md)



