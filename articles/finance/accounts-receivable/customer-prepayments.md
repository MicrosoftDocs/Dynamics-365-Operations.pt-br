---
title: Pagamentos antecipados do cliente
description: Este tópico explica como configurar e processar pagamentos antecipados do cliente (também conhecido como depósitos do cliente).
author: twheeloc
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb0f2290a38d89d90ac0d30a59e21fb3e9a6d894
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691881"
---
# <a name="customer-prepayments"></a>Pagamentos antecipados do cliente

[!include [banner](../includes/banner.md)]

Pagamentos antecipados do cliente são usados quando você recebe um pagamento de um caixa, mas não há fatura mediante à qual o pagamento pode ser liquidado. Esses tipos de pagamentos também são chamados de depósitos do cliente.

O processo de configurar e trabalhar com pagamentos antecipados do cliente consiste nas seguintes etapas básicas.

1. Crie um perfil de postagem do cliente para pagamentos antecipados.
2. Defina o parâmetro **Perfil de postagem com comprovante de diário do pagamento antecipado**.
3. Crie um diário de pagamento do cliente e marque a caixa de seleção **Comprovante de diário do pagamento antecipado** em cada linha.
4. Lançar o diário de pagamentos do cliente.
5. Quando uma fatura é gerada, liquide o pagamento antecipado com ela usando a página **Liquidar transações em aberto**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Criar um perfil de postagem do cliente para pagamentos antecipados

Normalmente, quando você aceita pagamentos antecipados ou depósitos de seus clientes antes que os produtos ou serviços sejam entregues, ou antes que uma fatura exista no seu sistema, é recomendável que você registre o caixa como um passivo em vez de um ativo em sua tabela de contas. Entretanto, os requisitos para registrar esses valores na sua contabilidade geral podem variar, dependendo do seu país ou região. Entretanto, certifique-se de consultar seus contadores sobre quaisquer regulamentos locais que se apliquem.

No geral, o processo para criar um perfil de postagem que pode ser usado para pagamentos antecipados é igual ao processo de criar outros perfis de postagem. A principal diferença é a conta principal que você seleciona no campo **Conta de resumo**. Para obter mais informações, consulte [Perfis de postagem do cliente](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Definir parâmetros para pagamentos antecipados do cliente

Há dois principais parâmetros de Contas a receber que você deve considerar ao configurar o sistema para pagamentos antecipados do cliente. Siga essas etapas para configurar os parâmetros.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
2. Opcional: na guia **Razão e imposto de vendas**, na FastTab **Pagamento**, defina a opção **Imposto de vendas no comprovante no diário do pagamento antecipado** como **Sim**.
3. No campo **Perfil de postagem com comprovante no diário do pagamento antecipado**, selecione o perfil de postagem do cliente para usar quando pagamentos antecipados do cliente são postados.
4. Feche a página.

## <a name="create-customer-prepayment-vouchers"></a>Criar comprovantes de pagamento antecipado do cliente

Quando você cria o diário de pagamento do cliente, para todo pagamento antecipado, é necessário definir a opção **Comprovante no jornal de pagamento antecipado** como **Sim** na página **Diário de pagamento do cliente**. Siga essas etapas para criar um pagamento antecipado do cliente.

1. Acesse **Contas a receber \> Pagamentos \> Diário de pagamento do cliente**.
2. Para criar um diário, selecione **Novo**.
3. No campo **Nome**, selecione o nome de diário para usar.

    > [!IMPORTANT]
    > Se você definir a opção **Imposto de vendas no comprovante no diário do pagamento antecipado** como **Sim** no procedimento anterior, você deve selecionar um nome de diário em que o parâmetro **Valor inclui imposto de vendas**. 

4. Opcional: no campo **Descrição**, insira uma descrição detalhada.
5. Selecione **Linhas**.
6. Se não houver uma linha em branco, selecione **Novo** para criar uma linha.
7. No campo **Data**, insira a data em que o pagamento antecipado deve ser postado.
8. No campo **Conta**, selecione o cliente para o pagamento antecipado.
9. Opcional: no campo **Descrição**, insira uma descrição detalhada da transação.
10. No campo **Crédito**, insira o valor do pagamento antecipado.
11. No campo **Conta de compensação**, selecione a conta com a qual o pagamento será compensado. Por exemplo, selecione o banco ou conta principal à qual postar o pagamento.
12. No campo **Método de pagamento**, selecione o método de pagamento do cliente.
13. Na guia **Pagamento**, defina a opção **Comprovante no jornal do pagamento antecipado** como **Sim**.
14. Repita as etapas 7 a 13 para cada pagamento antecipado adicional que deve ser postado.
15. Selecione **Postar** para finalizar o diário.

## <a name="settle-prepayments-with-invoices"></a>Liquidar pagamentos antecipados com faturas

Você pode usar o espaço de trabalho **Pagamentos do cliente** para encontrar e liquidar facilmente pagamentos que não foram totalmente liquidados.

1. No painel **Início**, selecione o bloco **Pagamentos do cliente**.
2. Na seção **Transações do cliente**, na guia **Pagamentos não liquidados**, pesquise e selecione o pagamento a ser liquidado.
3. Selecione **Liquidar transações**.
4. Marque a caixa de seleção **Marcar** para a fatura e o pagamento que serão liquidados.
5. Selecione **Lançar**.

Para obter mais informações sobre como liquidar transações em aberto, consulte [Visão geral da liquidação](/dynamics365/finance/cash-bank-management/settlement-overview).
