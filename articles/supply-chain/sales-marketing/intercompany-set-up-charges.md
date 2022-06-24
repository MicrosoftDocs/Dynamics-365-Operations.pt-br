---
title: Configurar encargos em ordens intercompanhia
description: Este artigo explica como configurar encargos em ordens intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7b84c0bac6c31139170a99afc65cd08d70bd018e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885831"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Configurar encargos em ordens intercompanhia

[!include [banner](../../includes/banner.md)]

É possível configurar os encargos a serem adicionados às ordens intercompanhia. Quando um encargo é adicionado a uma ordem de venda intercompanhia, ele é sincronizado automaticamente com a ordem de compra intercompanhia. Isso funciona de duas maneiras – da ordem de venda intercompanhia para a ordem de compra e ao contrário.

Também é possível usar encargos para adicionar um lucro a uma ordem de venda intercompanhia, definindo o encargo como uma porcentagem intercompanhia.

Ao configurar os encargos a serem aplicados às ordens intercompanhia, habilite o cálculo do lucro interno para uma ordem de venda intercompanhia a partir do valor líquido da ordem de venda original. Será possível fazer isso se o fornecedor intercompanhia vender um valor a preço de custo. O procedimento a seguir descreve como fazer isso para clientes intercompanhia. É possível usar o mesmo procedimento para fornecedores.

1. Acesse **Contas a receber \> Configuração \> Encargos \> Grupos de encargos de cliente**.
1. Crie um grupo de encargos.
1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**. Selecione link de conta de cliente. No Painel de Ações, selecione a guia **Cliente** e, em seguida, selecione a Guia Rápida **Ordem de venda**.
1. Selecione **Editar** no Painel de Ações para habilitar edições no campo. No campo **Grupo de encargos**, selecione o grupo de encargos intercompanhia configurado na etapa 2.
1. Acesse **Contas a receber \> Configuração \> Encargos \> Encargos automáticos**.
1. Configure os encargos ao preencher os campos relevantes.
1. No campo **Relação do cliente**, selecione o grupo de encargos intercompanhia configurado na etapa 2.
1. Na Guia Rápida **Linhas**, no campo **Categoria**, selecione **Porcentagem intercompanhia**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
