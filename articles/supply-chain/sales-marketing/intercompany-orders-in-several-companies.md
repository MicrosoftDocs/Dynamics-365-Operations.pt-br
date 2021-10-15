---
title: Criação de ordens de compra e de venda intercompanhia em várias empresas
description: Este tópico explica como criar ordens de compra intercompanhia ou ordens de venda em várias empresas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5d756a82abb7e7b19080128353d863f29837fc5b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548097"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Criação de ordens de compra e de venda intercompanhia em várias empresas

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management não está limitado a lidar somente com uma empresa de produção e várias empresas de vendas. Todas as empresas configuradas para a intercompanhia podem ser empresas comerciais e empresas de produção.

Se mais empresas puderem fornecer o mesmo item, você poderá escolher livremente de quem comprar, e as atualizações serão processadas mesmo que uma ordem de venda se torne várias ordens de compra.

Da mesma maneira que cria automaticamente uma ordem de compra intercompanhia, você poderá criar uma ordem de venda original na sua empresa e ter várias empresas fornecedoras intercompanhia para atender à ordem criando mais de uma ordem de compra intercompanhia. O Microsoft Dynamics 365 Supply Chain Management cria automaticamente ordens de venda intercompanhia nas empresas fornecedoras.

Para isso, todas as empresas devem ser configuradas como relações comerciais. As empresas fornecedoras devem ser configuradas no Microsoft Dynamics 365 Supply Chain Management como fornecedores intercompanhia, e devem ser o fornecedor principal do item relevante. Na ordem de venda, em **Exibição do cabeçalho**, você deve selecionar o campo **Criar ordens intercompanhia automáticas** e o campo **Entrega direta** na Guia Rápida **Configurações intercompanhia**. Essa é configuração padrão.

Você cria as linhas de venda da maneira normal. Quando você sai do registro, uma mensagem é mostrada e informa quais ordens de compra intercompanhia e ordens de venda intercompanhia foram criadas. A mensagem contém links para novas ordens. Ao exibir a ordem de venda intercompanhia criada nas empresas fornecedoras, abra a ordem de venda original na guia **Geral**, o grupo **Informações relacionadas**, selecione **Referências**.

Se abrir as ordens de compra intercompanhia para os fornecedores, você verá que o Microsoft Dynamics 365 Supply Chain Management preenche automaticamente o número da ordem de venda original e o número da ordem de venda intercompanhia de cada fornecedor.

Da mesma forma, se abrir as ordens de venda intercompanhia para os fornecedores, você verá que o Microsoft Dynamics 365 Supply Chain Management preenche automaticamente o número da ordem de venda original e o número da ordem de compra intercompanhia de cada fornecedor.

> [!NOTE]
> Se os itens da ordem existirem em uma de suas empresas fornecedoras intercompanhia, então o Microsoft Dynamics 365 Supply Chain Management criará as ordens intercompanhia para a empresa fornecedora onde os itens existem, porém, ele interromperá a criação da ordem para a outra empresa. Quando isso acontecer, será exibida uma mensagem de notificação.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
