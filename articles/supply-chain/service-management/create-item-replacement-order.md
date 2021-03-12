---
title: Criar uma ordem de substituição de item
description: Em geral, as ordens de substituição de item são criadas após um produto ser devolvido e inspecionado.
author: josaw1
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0006ea9ec64cd95a709ec91509cb3a9828df160
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996642"
---
# <a name="create-an-item-replacement-order"></a>Criar uma ordem de substituição de item 

[!include [banner](../includes/banner.md)]


Em geral, as ordens de substituição de item são criadas após um produto ser devolvido e inspecionado. Contudo, quando for necessário substituir um antes da devolução ou quando o item original não será devolvido, você pode criar imediatamente uma ordem de substituição de item depois que criar uma ordem de devolução.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Criar uma ordem de substituição após receber um item que foi devolvido

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.

2.  Crie uma nova ordem de devolução ou selecione uma ordem devolvida na lista para abrir o formulário **Ordem de devolução - Número de ADM: %1, %2**.

3.  Clique em **Linha de devolução** e depois selecione **Item de substituição**.

4.  Selecione o item a ser substituído pelo item devolvido. Insira as especificações do item e clique em **Aplicar**.

5.  Clique em **Guia de remessa** para gerar a guia de remessa da ordem de devolução. Uma ordem de venda é gerada para o item de substituição selecionado.
    
    Depois que a ordem de venda é criada para o item de substituição, os contratos de venda são pesquisados automaticamente e, se houver um contrato de venda aplicável, ele será aplicado à ordem de venda.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Criar uma ordem de substituição antes de receber um item que será devolvido

1.  Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.

2.  Crie uma nova ordem de devolução ou selecione uma na lista para abrir o formulário **Ordem de devolução - Número de ADM: %1, %2**.

3.  Clique em **Localizar ordem de venda** se quiser identificar a ordem de venda para o item devolvido. Preencha o formulário **Localizar ordem de venda** e clique em **OK** para fechá-lo e voltar ao formulário **Ordem de devolução - Número de ADM: %1, %2**. A linha da ordem de venda para o item devolvido é copiado na ordem de devolução.

4.  Clique em **Ordem de substituição** para abrir o formulário **Criar ordem de venda**.

5.  Marque a caixa de seleção **Copiar linhas de ordem de devolução** para transferir detalhes da ordem de devolução selecionada no formulário **Ordem de devolução - Número de ADM: %1, %2** para esta ordem de venda.

6.  Insira ou modifique os detalhes, conforme a necessidade.
    
    Se você identificou a ordem de venda na etapa 3, e se a linha da ordem de venda para o item devolvido estiver vinculada a um contrato de venda, o identificador do contrato de venda aplicável para a ordem de substituição do item será exibido automaticamente no campo **ID do contrato de venda**.

7.  Clique em **OK** para fechar o formulário **Criar ordem de venda** e abrir o formulário **Ordem de venda**, onde é possível continuar inserindo informações para a nova ordem de venda. Todas as linhas da ordem de devolução aplicável serão copiadas na nova ordem de venda. 
    
    Se o identificador do contrato de venda for exibido automaticamente no campo **ID do contrato de venda**, então o contrato de venda foi vinculado ao cabeçalho da ordem de venda para a ordem de substituição do item. Se houver um compromisso aplicável no contrato de venda que ainda não tenha sido preenchido, e a ordem de venda foi criada antes da expiração do contrato de venda, um link será estabelecido entre a linha do contrato de venda e a linha da ordem de venda. Consequentemente, as informações do contrato de venda, como o preço do item, serão copiadas na nova linha da ordem de venda. 
  


