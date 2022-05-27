---
title: Registrar o recebimento de itens devolvidos
description: Você pode registrar o recibo de itens devolvidos usando o formulário de Visão geral de entrada ou o formulário de Registro.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4ff01a8c4ed5fb8372ff7b498d0febdcd2f1e89
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672756"
---
# <a name="register-the-receipt-of-returned-items"></a>Registrar o recebimento de itens devolvidos 

[!include [banner](../includes/banner.md)]


Há dois métodos para registrar o recebimento de itens devolvidos. O primeiro método é um processo de recebimento de depósito que use o formulário de **Visão geral de entrada**. O segundo usa o formulário de **Registro**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Registrar o recebimento de itens devolvidos com o formulário Visão geral de entrada

Você pode usar o formulário **Visão geral de entrada** para identificar uma remessa de devolução pelo número da Autorização de Devolução de Material (ADM). Se um nome de diário estiver definido na guia de **Configuração**, e as linhas do diário que correspondem às linhas selecionadas no formulário de **Visão geral de entrada** existirem, um novo cabeçalho de diário é criado quando você clica em **Iniciar entrada**.

1.  Clique em **Gerenciamento de estoque** \> **Periódico** \> **Visão geral de entrada**.

2.  No campo **Nome de instalação**, selecione **Devolver ordem** e clique em **Atualizar**.
    

    > [!TIP]
    > <P>Você pode usar os campos <STRONG>Intervalo</STRONG> para restringir os resultados da pesquisa. Digite ou selecione o número de ADM no campo <STRONG>Número de ADM</STRONG> para obter um resultado exato. Para definir e salvar um conjunto de filtros que restringirá quais entrada de chegada são exibidas, clique na guia <STRONG>Configuração</STRONG>. Os filtros disponíveis incluem tipos, depósitos e docas.</P>

    

    > [!WARNING]
    > <P>As ordens de devolução não podem ser misturadas com outros outras entrada no formulário de <STRONG>Visão geral de entrada</STRONG>. Portanto, a referência será sempre ordem de venda, mas nenhuma ID de ordem de venda será especificado no cabeçalho do diário.</P>



3.  Na tabela **Recibos**, localize a linha que corresponde ao item devolvido e selecione a caixa na coluna **Selecionar para entrada**.

4.  Para excluir determinadas linhas do recibo de devolução, como itens da ordem original que não foram incluídos na remessa de devolução, desmarque as caixas **Selecionar para entrada** associadas na tabela **Linhas** na parte inferior do formulário.

5.  Clique no botão de **Iniciar entrada** para criar um diário de entrada.
    

    > [!NOTE]
    > <P>Você pode selecionar várias ordens de devolução e incluir todas em um único processo de entrada. Cada linha de ordem de devolução será copiada em uma linha de diário de entrada de item correspondente.</P>

    

    > [!NOTE]
    > <P>Você também pode criar manualmente um diário de entrada usando o formulário de <STRONG>Entrada de item</STRONG>. 



6.  Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Chegada de item**.

7.  Selecione o diário de entrada que você acabou de criar e clique em **Linhas** para abrir o formulário de **Linhas do diário, localizações**.

8.  Na guia **Geral**, ajuste o número no campo **Quantidade**, se necessário, e então atribua um código de disposição no campo de **Código de disposição**.
    
    Como alternativa, você pode marcar a caixa de seleção de **Gerenciamento de quarentena** para que os itens devolvidos sejam enviados a um processo de inspeção no contexto de uma ordem de quarentena.
    

    > [!NOTE]
    > <P>Se você envia os itens devolvidos com a quarentena, não é possível especificar um código de disposição.</P>



9.  Clique no botão **Validar**.

10. Se não houver erros no processo de validação, clique em **Lançar**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Registrar o recebimento de itens devolvidos com o formulário Visão geral de entrada

Como uma alternativa ao usar o formulário de **Visão geral de entrada**, você pode usar o formulário de **Registro** para registrar a entrada de itens devolvidos.

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**. Crie uma nova ordem de devolução ou abra a ordem de devolução na lista. Na Guia Rápida **Linhas**, selecione a ordem de devolução apropriada. Clique em **Atualizar linha** e em **Registro**.

2.  Atribua um código de disposição no campo de **Código de disposição**, e clique em **OK**.
    

    > [!NOTE]
    > <P>Não é possível enviar o item para inspeção como uma ordem de quarentena usando o formulário de <STRONG>Registro</STRONG>.</P>



3.  Na grade de **Transações**, selecione a transação a ser registrada.

4.  Na grade **Registrar agora**, clique em **Adicionar**. Repita as duas etapas anteriores até que todos os itens devolvidos apareçam na grade de **Registrar agora**.

5.  Clique em **Lançar todos**.

## <a name="see-also"></a>Consulte também

[Visão geral de entrada (formulário)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]