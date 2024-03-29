---
title: Gerenciar bloqueios de ordens
description: Este procedimento demonstra como colocar as ordens de venda do cliente em espera, como trabalhar com check-outs de bloqueio de ordem e como remover bloqueios de ordem.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 938b21b66b7b61452be104936877278a3bc120f2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566278"
---
# <a name="manage-order-holds"></a>Gerenciar bloqueios de ordens

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como colocar as ordens de venda do cliente em espera, como trabalhar com check-outs de bloqueio de ordem e como remover bloqueios de ordem. Uma ordem pode ser colocada em espera por diversos motivos. Por exemplo, você pode bloquear uma ordem até o endereço de um cliente ou o método de pagamento poder ser verificado ou até um gerente poder revisar o limite de crédito do cliente. Enquanto a ordem estiver em espera, ela não poderá ser processada pelo depósito para remessa. 

Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-up-order-holds"></a>Configurar bloqueios de ordem
1. Acesse **Painel de navegação > Módulos > Vendas e marketing > Configuração > Ordens de venda > Códigos de bloqueio de ordem**.
2. Clique em **Novo**.
3. No campo **Código de bloqueio**, digite um valor. Por exemplo, digite "Retorno de chamada".  
4. No campo **Descrição**, digite um valor.
    - Por exemplo, ordem bloqueada aguardando retorno de chamada do cliente.  
    - Opcionalmente, marque a caixa de seleção **Remover reservas** para remover qualquer reserva física da ordem quando esse código de bloqueio for adicionado.  
5. Clique em **Salvar**.

## <a name="place-order-on-hold"></a>Colocar ordem em espera
1. Acesse **Painel de navegação > Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Clique em **Novo**.
3. No campo **Conta de cliente**, insira ou selecione um valor.
4. Clique em **OK**.
5. No campo **Número do item**, insira ou selecione um valor.
6. No campo **Quantidade.**, insira um número
7. No **Painel de Ação**, clique em **Ordem de venda**.
8. Clique em **Bloqueios da ordem**.
9. Clique em **Novo**.
10. No campo **Código de bloqueio**, selecione o código que você criou na subtarefa anterior.
11. Clique em **Salvar**.
12. Feche a página.
13. Acesse **Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
14. Na lista, marque a linha selecionada. Ordens que estão atualmente em espera têm os campos "Não processar" e "Em espera" marcados.
15. No Painel de Ação, clique em **Selecionar e empacotar**.

## <a name="manage-order-holds"></a>Gerenciar bloqueios de ordens
1. Acesse **Vendas e marketing > Ordens de venda > Ordens em aberto > Bloqueios da ordem**. A página **Bloqueios da ordem** funciona como uma bancada na qual você pode obter uma visão geral de todos os bloqueios atuais e processados, além de processar esses bloqueios e as ordens de venda associadas.     
2. Na lista, marque a linha selecionada.
3. No **Painel de Ação**, clique em **Bloquear finalização da compra**.
4. Clique em **Fazer check-out**.
5. Na lista, desmarque a linha selecionada. O campo **Fazer check-out para** agora mostra sua ID de usuário.   
6. Clique em **Liberar check-out**.
7. No **Painel de Ação**, clique em **Liberar bloqueio**.
    - Quando estiver pronto para remover o bloqueio e permitir que a ordem siga para a próxima etapa de realização, você precisará limpar o bloqueio. Se a ordem não exigir qualquer alteração, você poderá executar a ação Liberar bloqueios. No entanto, você poderá usar a ação Liberar e modificar se, ao liberar um bloqueio, a ordem precisar ser atualizada.      
    - A ação **Liberar e enviar** só é aplicável quando você usa a funcionalidade de call center.  
8. Clicar em **Liberar bloqueios**. Agora o bloqueio está liberado na ordem e removido da lista de bloqueios ativos. Para ver todos os bloqueios ou seu subconjunto de acordo com um status específico, mude o valor no campo Mostrar.     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]