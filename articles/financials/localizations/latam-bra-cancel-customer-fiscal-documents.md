---
title: Cancelar uma nota fiscal do cliente (Brasil)
description: Este tópico fornece informações sobre como cancelar uma nota fiscal do cliente para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 06/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 1be08d285044ee8d530cffae6aaa603d63c46810
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570067"
---
# <a name="cancel-a-customer-fiscal-document-brazil"></a>Cancelar uma nota fiscal do cliente (Brasil)

[!include [banner](../includes/banner.md)]

Você pode cancelar uma nota fiscal de cliente incorreta usando a página **Cancelar nota fiscal** . Ao cancelar uma nota fiscal, ela é marcada como cancelada e todas as transações financeiras e contábeis são revertidas.

1.  Clique em **Contas a receber** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.
    
    –ou–
    
    Clique em **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.

2.  Selecione uma ordem de venda a ser cancelada.

3.  No Painel Ação, clique na guia **Vender** e, em seguida, clique em **Cancelar nota fiscal** para abrir a página **Cancelar nota fiscal**. 

4.  No campo **Código de motivo**, selecione o código de identificação do motivo que foi usado para cancelar a nota fiscal do cliente.

5.  No campo **Comentário do motivo**, insira ou atualize o motivo para cancelar a nota fiscal.

    > [!NOTE]
    > O motivo para o cancelamento deve conter pelo menos 15 caracteres.

6.  Na guia **Fatura**, marque as caixas de seleção **Marcar** para selecionar as linhas de ordem de venda individuais. Como alternativa, você pode marcar a caixa de seleção **Selecionar tudo** para selecionar todas as linhas da ordem de venda.

7.  Clique em **OK** para criar transações que tenham quantidades negativas.

8.  Na página de listagem **Todas as ordens de venda**, selecione as transações que têm quantidades negativas.

9.  No **Painel de Ação**, clique na guia **Fatura** e em **Fatura** para abrir a página **Lançando fatura**.

10. Marque as caixas de seleção **Lançando** e **Imprimir fatura** para lançar e imprimir a fatura.

11. Clique em **OK** para cancelar a ordem de venda e para reverter todas as transações contábeis e financeiras.

## <a name="additional-resources"></a>Recursos adicionais

[Cancelar uma nota fiscal de fornecedor](latam-bra-cancel-vendor-fiscal-documents.md)
