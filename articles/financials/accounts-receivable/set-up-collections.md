---
title: Configurar crédito e cobranças
description: Este artigo explica como configurar a funcionalidade das coleções.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b1dcd6ad0ca05a94409d5d23039ccefe53392e3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555710"
---
# <a name="set-up-credit-and-collections"></a>Configurar crédito e cobranças

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar a funcionalidade das coleções.

<a name="set-up-aging-period-definitions"></a>Configurar definições de período de classificação por vencimento
-------------------------------

Configure uma definição de período de classificação por vencimento. Uma definição de período de classificação por vencimento define as colunas que aparecem nas páginas de listagem **Saldos classificados por vencimento**, **Atividades de cobranças** e **Casos de cobranças**. Também define os períodos que aparecem na página **Cobranças**. Se um grupo de clientes for configurado, a definição do período de classificação por vencimento para o grupo será usada. Se nenhum grupo for configurado, a definição do período de classificação por vencimento padrão especificada na página **Parâmetros de contas a receber** será usada. Se nenhuma definição do período de classificação por vencimento padrão for especificada, será usada a primeira definição do período de classificação por vencimento na página **Definições do período de classificação por vencimento**.

## <a name="create-an-aging-snapshot"></a>Criar um instantâneo de classificação por vencimento
Crie registros instantâneos de classificação por vencimento para todos os clientes ou para os clientes de um grupo. As informações do instantâneo de classificação por vencimento aparecem na página de listagem **Saldos classificados por vencimento** e na página **Cobranças**. Você deve criar um instantâneo de classificação por vencimento antes de usar a página de listagem. A página de listagem mostra informações somente para os clientes para os quais um instantâneo de classificação por vencimento foi criado.

## <a name="optional-set-up-customer-pools"></a>Opcional: configurar grupos de clientes
Você pode configurar grupos de clientes para representar grupos de clientes. Você pode usar grupos de clientes como filtros para as informações do cliente que aparecem nas páginas de listagem **Cobranças**, na página **Cobranças** ou quando você cria instantâneos de classificação por vencimento.

## <a name="optional-create-a-collections-team"></a>Opcional: criar uma equipe de cobrança
Se várias pessoas de sua organização fizerem cobrança, você poderá configurar uma equipe de cobrança. Você pode selecionar a equipe na página **Parâmetros de contas a receber**. Se você não criar uma equipe de cobrança, uma será criada automaticamente quando você configurar agentes de cobranças na página **Agente de cobranças**.

## <a name="set-up-a-collections-case-category"></a>Configurar uma categoria de caso de cobrança
Se você usa casos para organizar seu trabalho de cobrança, configure uma categoria de caso que tenha o tipo de categoria **Cobranças**. Essa configuração só será obrigatória caso você queira usar a funcionalidade da página **Cobranças**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Configurar os nomes de diário (liquidação, baixa e NSF)
Configure os nomes dos diários usados quando as transações forem processadas na página **Cobranças**. Esse processamento inclui a liquidação de uma transação, dar baixa em uma transação e o processamento de um pagamento NSF (insuficiência de fundos).

| Descrição | Tipo de diário     |
|-------------|------------------|
| Liquidação  | Pagamento de cliente |
| Baixa contábil   | Diariamente            |
| NSF         | Pagamento de cliente |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Configurar um código de motivo para transações de baixa
Configure o código de motivo padrão usado ao dar baixa em transações na página **Cobranças**. Você pode alterar o código durante o processo de baixa.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Configurar uma pasta para anexos de email e criar modelos de email
Se você enviar mensagens de email da página **Cobranças** com anexos do Microsoft Excel, poderá criar modelos opcionais de email para as mensagens.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Configurar os parâmetros de contas a receber para cobranças
Configure os parâmetros de contas a receber que aparecem na guia **Cobranças**.

## <a name="optional-set-up-collections-agents"></a>Opcional: configurar agentes de cobranças
Se várias pessoas de sua organização fizerem cobrança, você poderá configurar agentes de cobrança. Um agente de cobrança é um trabalhador que está configurado como um usuário na página **Relações de usuário**. Você pode atribuir os grupos de clientes (consultas de cliente) a agentes de cobranças para ajudar os agentes a organizar seu trabalho. Os agentes de cobranças são adicionados à equipe selecionada na página **Parâmetros de contas a receber**. Se uma equipe não estiver selecionada nessa página, uma nova equipe chamada **Cobranças** será criada automaticamente e os agentes de cobranças serão adicionados à equipe.

## <a name="set-up-a-writeoff-account"></a>Configurar uma conta de baixa
Configure uma conta de baixa que será usada para a entrada de baixas da contabilidade quando uma transação for baixada. Essa conta é armazenada no perfil de lançamentos do cliente.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Configurar informações de NSF para contas bancárias
Atualize as contas bancárias de forma que elas tenham o diário correto quando os pagamentos NSF forem identificados na página **Cobranças**. Na guia **Gerenciamento de moeda**, no campo **Diário de pagamento NSF**, selecione um diário de pagamentos.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Definir configurações do Outlook para usuários na página Cobranças
Antes que os trabalhadores possam criar atividades ou enviar mensagens de email usando a página **Cobranças**, você deverá verificar se a chave de configuração **Sincronização do Microsoft Outlook** está selecionada e se a sincronização do Outlook está configurada para o trabalhador.

## <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Definir configurações de email e de endereço para contatos de cliente de cobrança
Configure endereços de email para contatos de cliente se você deseja enviar mensagens de email para os contatos na página **Cobranças**. O contato de cobranças é usado como o contato padrão na página **Cobranças**. Você pode configurar um endereço do demonstrativo para um cliente se os demonstrativos tiverem de usar um endereço diferente do endereço principal. 

Na Guia Rápida **Crédito e Cobranças** para um cliente, no campo **Contato de cobranças**, selecione a pessoa na organização do cliente que trabalha com o agente de cobranças. Essa pessoa é usada como o contato padrão na página **Cobranças** e as mensagens de email são enviadas para ela. 

> [!NOTE] 
> Se um contato de cobranças não for especificado para um cliente, o contato principal do cliente será usado. Se um contato principal não for especificado, as mensagens de email serão enviadas para o primeiro endereço listado na página **Contatos**.

## <a name="set-up-email-settings-for-salespeople"></a>Definir configurações de email para vendedores
Configure endereços de email para vendedores se quiser enviar mensagens de email para eles da página **Cobranças**. Configure um endereço de email para cada representante de vendas em cada grupo de vendas por comissão. O representante de vendas que tiver a opção **Contato** selecionada será o vendedor padrão para quem as mensagens de email serão enviadas. 

Se um representante de vendas não for especificado, o vendedor principal da organização do cliente será usado. Se um vendedor principal não for especificado, as mensagens de email serão enviados para o primeiro vendedor listado no formulário.


Para obter mais informações, consulte os seguintes tópicos:

 - [Criar uma sequência de cartas de cobrança](tasks/create-collection-letter-sequence.md)

 - [Processar cartas de cobrança](tasks/process-collection-letters.md)

 - [Revisar informações sobre cobranças](tasks/review-collections-information.md)

