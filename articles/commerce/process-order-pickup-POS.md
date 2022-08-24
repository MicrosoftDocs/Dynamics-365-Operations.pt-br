---
title: Processar retiradas de ordem do cliente no POS
description: Este artigo explica a funcionalidade disponível no aplicativo de PDV (ponto de venda) para processar retiradas de ordem do cliente.
author: hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 7fd7d08ac59f6fe7381b79d854160188ef1c325a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286348"
---
# <a name="process-customer-order-pickups-in-pos"></a>Processar retiradas de ordem do cliente no POS

[!include [banner](includes/banner.md)]

Quando uma [ordem do cliente](customer-orders-overview.md) é criada para retirada na loja, um usuário da loja pode usar o aplicativo de POS (ponto de venda) para iniciar a retirada do estoque. O PDV obterá o pagamento final, conforme necessário. Ele também concluirá o lançamento de estoque e financeiro para as quantidades retiradas.

Se você for um usuário de armazenamento, poderá realizar a retirada usando a operação de **Ordem de cancelamento** ou a operação de **Atendimento de ordem** no PDV. Para poder acessar a operação de **Retirada**, primeiro você deve seguir uma das seguintes etapas:

- Para usar a operação **Cancelar ordem**, pesquise e selecione a ordem que será retirada.
- Para usar a operação de **Atendimento da ordem**, pesquise e selecione uma ou mais linhas da ordem.

Se a ordem ou linhas da ordem selecionadas não estiverem configuradas para retirada nessa loja específica ou se a ordem já tiver sido totalmente retirada, a operação de **Retirada** não estará disponível.

![Operação de retirada.](media/pickupoperation.png)

Na versão 10.0.17 e posterior do Microsoft Dynamics 365 Commerce, o recurso **Experiência de usuário aprimorada para o processamento de ordens de retirada no Ponto de venda** pode ser ativada com o gerenciamento de recursos no Commerce headquarters. Se esse recurso estiver desativado, os usuários não poderão selecionar as quantidades de retirada. Por padrão, a quantidade total pedida da linha é a quantidade que será retirada. Essa experiência pode causar problemas, já que os usuários podem esquecer de selecionar alguns itens para retirada ao executarem a retirada usando o atendimento da ordem.

O recurso **Experiência de usuário aprimorada para o processamento de ordens de retirada no Ponto de venda** oferece aos usuários mais controle sobre a seleção de produtos que serão retirados e a quantidade de produtos que serão retirados. Os usuários não precisam selecionar cada linha da ordem de venda na página de atendimento da ordem para selecionar **Retirada**. Todos os itens que podem ser retirados serão mostrados. Os usuários podem especificar várias linhas para retirada, mesmo que apenas uma linha de produto tenha sido selecionada.

Quando o recurso **Experiência de usuário aprimorada para o processamento de ordens de retirada no Ponto de venda** está ativado e você seleciona a operação de **Retirada**, a caixa de diálogo **Retirada** é exibida. Nela, você pode selecionar os itens e as quantidades que serão retirados. Por padrão, qualquer quantidade pedida que tenha estoque em um estado separado ou embalado é considerada qualificada para retirada. Por padrão, essa quantidade é definida como a quantidade de retirada. Você pode alterar a quantidade que foi inserida, desde que a quantidade não seja 0 (zero) e não exceda a quantidade total aberta (ou seja, não faturada) da linha selecionada.

![Caixa de diálogo Retirada.](media/pickupselect.png)

Depois de selecionar as quantidades que serão retiradas e selecionar **Retirada**, a página de transação será exibida. Se o recurso [pagamentos de omni-channel](omni-channel-payments.md) estiver ativado e houver pagamentos de cartão de crédito pré-qualificados no arquivo, você deverá aplicar o pagamento.

Na página de transação, o sistema calcula os valores vencidos calculando o total devido dos itens de retirada selecionados e subtraindo os depósitos ou pagamentos de cartão de crédito autorizados aplicados anteriormente. Você deve processar o pagamento para concluir a transação de retirada. Se o [layout de tela](pos-screen-layouts.md) da página de transação for configurado de forma que inclua a operação de **Concluir transação** e nenhum valor seja vencido, você poderá concluir a transação sem selecionar um método de pagamento. Se a operação **Concluir transação** não estiver disponível, você poderá selecionar o link **$0,00 valor devido** no painel **Totais** para concluir a transação sem precisar selecionar um método de pagamento.

![Página de transação para uma transação de retirada de ordem de cliente.](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Alterar linhas ou quantidades de retirada

Se você precisar alterar a quantidade de retirada após selecionar os itens que serão retirados, selecione **Definir quantidade**. Não é possível definir a quantidade de retirada como **0** (zero) ou aumentá-la para um valor que exceda a quantidade não faturada que permanece para a linha perdida. Para remover uma linha de retirada do carrinho de transações, selecione **Anular transação**. A transação atual será interrompida e o fluxo da operação de **Retirada** será reiniciado.

Se o recurso **Experiência de usuário aprimorada para o processamento de ordens de retirada no Ponto de venda** estiver ativada, as organizações poderão adicionar um botão para a operação **Alterar linhas de retirada** ao modelo de tela da página de transação. Depois de criar o carrinho de transações de retirada no POS e selecionar os itens, você pode selecionar **Alterar linhas de retirada** se precisar alterar os itens de retirada, mas não desejar anular toda a transação. Na caixa de diálogo **Alterar linhas de retirada** que é exibida, você pode alterar os itens e as quantidades de retirada. O carrinho de transações é atualizado para aplicar as alterações.

![Caixa de diálogo Alterar itens de retirada.](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
