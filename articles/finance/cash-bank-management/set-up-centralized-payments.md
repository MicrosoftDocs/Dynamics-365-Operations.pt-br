---
title: Configurar pagamentos centralizados
description: Siga essas etapas para se preparar para processar pagamentos em uma entidade legal em nome de outras entidades legais na sua organização.
author: kweekley
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1ab2423a9615bfaf7858a5d1a90de3822ad7174
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995231"
---
# <a name="set-up-centralized-payments"></a>Configurar pagamentos centralizados

[!include [banner](../includes/banner.md)]

Siga essas etapas para se preparar para processar pagamentos em uma entidade legal em nome de outras entidades legais na sua organização. Antes de começar, a seguinte configuração deve ser concluída:

-   Criar entidades legais.
-   Configurar parâmetros da contabilidade e os planos de contas.
-   Configurar parâmetros de contas a pagar e os parâmetros de contas a receber (dependendo dos módulos que estão usando pagamentos centralizados).
-   Configurar contabilidade intercompanhia.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Configurar uma hierarquia organizacional para pagamentos centralizados.
Configure uma hierarquia organizacional para pagamentos centralizados. A mesma hierarquia organizacional é usada para processar pagamentos centralizados de fornecedor e de cliente. **Nota:** Para pagamentos centralizados, a estrutura da hierarquia não importa. A entidade legal na hierarquia poderá processar os pagamentos em nome de outra entidade legal na hierarquia. NA página **Hierarquias da organização**, você pode criar uma nova hierarquia da organização. No campo **Finalidade**, você deve selecionar **Pagamentos centralizados**. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Configurar uma conta intercompanhia para os pagamentos centralizados
Quando as transações de pagamento na entidade legal atual forem liquidadas com faturas em outras entidades legais, serão criadas transações a vencer e vencidas apropriadas para cada entidade legal. Você deve especificar a entidade legal em que os descontos à vista aplicáveis e os lucros realizados ou valores de perda são lançados. Antes de começar, decida qual entidade legal que será usada para processar pagamentos do fornecedor e do cliente. Se uma entidade legal processa os pagamentos do fornecedor, mas outra entidade legal processa os pagamentos do cliente, você deverá alternar para cada entidade legal. Na página **Contabilidade intercompanhia** você pode selecionar um registro intercompanhia da relação para uma entidade legal que você processe pagamentos em nome de. 

Na guia **Pagamentos centralizados**, você pode selecionar se deseja lançar descontos em dinheiro para a entidade jurídica do pagamento (ou outra transação que diminua o saldo da conta do fornecedor) ou a entidade legal da fatura (ou outra transação que aumente o saldo da conta do fornecedor). Esta seleção trabalha com o campo **Administração de descontos à vista** nas páginas **Parâmetros de contas a pagar** e **Parâmetros de contas a receber**. Para pagamentos a maior e tolerâncias de diferença mínima, usa-se a configuração da entidade legal do pagamento. Para pagamentos a menor e tolerâncias de diferença mínima, usa-se a configuração na entidade legal da fatura.

## <a name="map-vendor-accounts-across-legal-entities"></a>Mapear contas de fornecedor por meio da entidade legal
Se você pagar um fornecedor de uma entidade legal e desejar selecionar faturas para esse fornecedor em outras entidades legais, deverá verificar se todas as contas do fornecedor correspondentes em cada entidade legal usam o mesmo ID do livro de endereços. Se você receber um pagamento para um cliente que paga as faturas em mais de uma entidade legal, verifique se as contas de cliente correspondentes em cada entidade legal usam todas a ID de catálogo de endereços.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Configurar perfis de lançamento para pagamentos centralizados
Quando você cria um pagamento em uma entidade legal que liquida faturas em outras entidades legais, as IDs dos perfis de lançamento devem ser iguais nas duas entidades legais. Para ajudar a garantir que os pagamentos foram criados corretamente, em cada entidade legal da fatura, configure um perfil de lançamento que corresponda aos perfis de lançamento que são usados na entidade legal do pagamento. Alterne para a primeira entidade legal da fatura e, na página **Perfis de lançamento de fornecedor**, você pode criar um novo perfil de lançamento ou editar um perfil de lançamento existente. As seleções feitas para o perfil de lançamento na entidade legal da fatura não precisam corresponder à configuração do perfil de lançamento na entidade legal do pagamento.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Configurar métodos de pagamento para pagamentos centralizados
Quando você cria um pagamento em uma entidade legal que liquida faturas em outras entidades legais, o método das IDs de pagamento deve ser igual nas duas entidades legais. Para ajudar a garantir que os pagamentos foram criados corretamente, em cada entidade legal da fatura, configure um método de pagamento que corresponde aos métodos de pagamentos que são usados na entidade legal do pagamento. Alterne para a primeira entidade legal da fatura e, na página **Métodos de pagamento**, você pode criar um novo método de pagamento ou editar um método de pagamento existente. As seleções para o método de pagamento na entidade legal da fatura não precisam corresponder à configuração do método de pagamento na entidade legal do pagamento.

## <a name="set-up-default-descriptions"></a>Configurar descrições padrão
É possível definir as descrições padrão para comprovantes de liquidação intercompanhia. A descrição padrão é incluída nas transações a vencer e vencidas durante o processo de liquidação entre empresas. Na página **Descrições padrão**, você pode criar novas descrições para **Liquidação do cliente intercompanhia** and **Liquidação do fornecedor intercompanhia** ao selecionar um idioma ao inserir texto.



