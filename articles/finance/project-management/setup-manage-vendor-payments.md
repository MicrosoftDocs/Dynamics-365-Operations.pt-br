---
title: Configurar e usar pagamentos de fornecedor de pagamento quando pago
description: Este tópico explica como criar condições de pagamento quando pago (PWP) para que você possa liberar pagamentos parciais de fornecedor, com base nos pagamentos de cliente.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
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
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284104"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Configurar e usar pagamentos de fornecedor de pagamento quando pago

[!include [banner](../includes/banner.md)]

Quando você aprova um fornecedor para trabalhar como subcontratado, pode reter o pagamento ao fornecedor até que seu cliente pague pelo projeto. Para oferecer suporte a esse cenário, você pode configurar as condições de pagamento quando pago (PWP) ao configurar a ordem de compra (OC) com o fornecedor.

Por exemplo, quando um cliente paga um valor em uma fatura de projeto, você pode liberar parte ou todo o valor da fatura do fornecedor. Basta configurar as condições de PWP que especificam que o fornecedor será pago depois que você receber uma porcentagem do pagamento relacionado do cliente. Se você receber o pagamento parcial de um cliente, você pode liberar manualmente algumas das faturas de fornecedores relacionadas para pagamento.

O exemplo a seguir descreve o processo quando as condições de PWP são usadas.

## <a name="example"></a>Exemplo

Sua organização concorda em fornecer a um cliente 100 computadores com software instalado, por um preço de 150,00 dólares americanos (USD) por computador. Você contrata um fornecedor para fornecer os computadores com o software instalado. De acordo com o contrato, o cliente deve aprovar a qualidade dos computadores antes de pagar à sua organização. A política da sua organização é reter o pagamento aos fornecedores até que o cliente pague. Portanto, configure o projeto para que ele tenha uma porcentagem de PWP de 100%.

O fornecedor envia a você os 100 computadores que possuem software instalado, juntamente com uma fatura de US$ 10.000,00. Como as condições de PWP estão configuradas para o seu projeto, você não paga o fornecedor após o recebimento dos computadores. Em vez disso, você envia os computadores ao cliente, juntamente com uma fatura de 15.000,00. O cliente inspeciona os computadores e aprova o valor total da fatura do projeto.

Depois de receber o pagamento total do cliente, você paga ao fornecedor 10.000,00, o valor total da fatura do fornecedor.

## <a name="set-up-pwp-terms-for-a-project"></a>Estabelecer condições PWP de um projeto

Ao configurar as condições de PWP de um projeto, você deve especificar, como porcentagem, o valor mínimo que um cliente deve pagar pelo projeto antes de você pagar ao fornecedor. O valor limite é calculado automaticamente nas faturas de cliente do projeto. Siga estas etapas para configurar a porcentagem limite das condições de PWP.

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.
2. Localize e abra o projeto para o qual deseja configurar as condições de PWP.
3. Na guia rápida **Contratos de fornecedor**, selecione **Adicionar linha**.
3. No campo **Código da conta**, selecione uma das seguintes opções:

    - **Tabela** – as condições PWP se aplicam a um único fornecedor.
    - **Grupo** – as condições PWP se aplicam a todos os fornecedores em um grupo de fornecedores.
    - **Todos** – as condições PWP se aplicam a todos os fornecedores.

4. Se você selecionou **Tabela** ou **Grupo** na etapa anterior, no campo **Fornecedor/grupo de fornecedores**, selecione o fornecedor ou grupo de fornecedores aos quais as condições de PWP se aplicam. Se você selecionou **Tudo** na etapa anterior, o campo **Fornecedor/grupo de fornecedores** não poderá ser editado.
5. Se as condições de retenção de fornecedor estiverem estabelecidas para o fornecedor no projeto, no campo **Condições de retenção de fornecedor**, selecione a ID de regra das condições de retenção.
6. No campo **Porcentagem de limite PWP**, digite a porcentagem de limite para o projeto. A porcentagem que você insere para o projeto define o valor mínimo que o cliente deve pagar antes de você pagar o fornecedor.

## <a name="create-a-po-that-has-pwp-terms"></a>Criar uma OC com condições de PWP

Quando você lança uma fatura de um fornecedor, se o fornecedor estiver sujeito às condições de PWP, essas condições serão mostradas nas linhas de OC. Para criar uma OC com condições de PWP, siga estas etapas:

1. Acesse **Compras e fornecimento** \> **Ordens de compra** \> **Todas as ordens de compra**.
2. No Painel de Ações, selecione **Novo**. Em seguida, na caixa de diálogo **Criar ordem de compra**, insira as informações necessárias e selecione **OK**.

    Como alternativa, abra uma OC existente na página da lista **Todas as ordens de compra**.

4. Na página **Ordem de compra**, na FastTab **Linhas de ordem de compra**, examine os detalhes da linha da OC do fornecedor. A opção **Pagar quando pago** é selecionada automaticamente e o valor no campo **Porcentagem de limite PWP** é automaticamente copiado do campo **Porcentagem de limite PWP** na página **Projetos**.
6. Se você não deseja aplicar as condições de PWP ao fornecedor para uma linha de OC, desmarque a opção **Pagar quando pago**. Nesse caso, o campo **Porcentagem de limite PWP** para a linha de OC será redefinido como 0 (zero).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Atualizar o pagamento do cliente e pagar o fornecedor

Quando um fornecedor concluir seu trabalho em um projeto e enviar uma fatura, você deve analisar o status do projeto e as faturas do cliente para determinar se as condições de PWP foram atendidas para o projeto. Se as condições PWP do fornecedor foram atendidas, você pode determinar quais linhas da fatura de fornecedor serão pagas, com base nos pagamentos do cliente pelo projeto. Se você decidir pagar ao fornecedor, mesmo que as condições de PWP não tenham sido atendidas, poderá substituí-las na página **Faturas de fornecedor com pagamento quando pagas**.

1. Acesse **Gerenciamento e contabilidade do projeto** \> **Consultas e relatórios** \> **Consultas de retenção** \> **Faturas de fornecedor com pagamento quando pagas**.
2. Na página **Faturas de fornecedor com pagamento quando pagas**, no campo de pesquisa, insira valores para localizar a fatura do fornecedor que você deseja revisar e selecione **Pesquisar**.
3. Na FastTab **Linhas da fatura de fornecedor**, selecione as linhas que você deseja alterar.
4. Se as condições de **Pagar quando pago** forem atendidas para a linha da fatura, selecione **Liberar pagamento do fornecedor**. A opção **Pagar quando pago** estará desmarcada, e o valor do campo **Pronto para pagamento** será alterada como **Sim**.
