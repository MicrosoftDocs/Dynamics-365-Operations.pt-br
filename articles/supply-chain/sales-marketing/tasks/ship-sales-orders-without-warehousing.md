---
title: Enviar ordens de venda sem armazenamento
description: Este tópico explica como atualizar uma ordem de venda quando produtos são enviados ao cliente.
author: omulvad
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b6b1dbb4d53785c226f7c9d40339d9dd19f47152
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422460"
---
# <a name="ship-sales-orders-without-warehousing"></a>Enviar ordens de venda sem armazenamento

[!include [banner](../../includes/banner.md)]

Este tópico explica como atualizar uma ordem de venda quando produtos são enviados ao cliente. Este guia é aplicável ao fluxo de realizações que não está definido para o gerenciamento de depósito (sem armazenamento básico ou avançado) e, portanto, não requer separação de produtos que serão registrados antes da remessa. Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração. Em ambos os casos, antes de começar esta tarefa, crie uma ordem de venda para um produto inventariado com uma quantidade maior que 1. Para evitar um erro de lançamento, você precisa verificar se a quantidade disponível do produto no site e o depósito que você selecionou na ordem abrangem a quantidade da ordem.

## <a name="post-packing-slip-for-an-order"></a>Lançar guia de remessa para uma ordem
1. No painel de navegação, acesse **Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Na lista, localize e selecione a ordem que você criou para essa tarefa.
3. No Painel de Ação, selecione **Separar e empacotar**.
4. Selecione **Lançar guia de remessa**.
5. Expanda e recolha a seção **Parâmetros**.
6. No campo **Quantidade**, selecione **Todas**.
    - Outras opções incluem **Entregar agora** e **Separado**. Se a linha da ordem estiver pronta para ser parcialmente remetida e o campo **Entregar agora** na linha da ordem contiver uma quantidade, você selecionará **Entregar agora**. Se o fluxo de realizações da sua organização incluir a separação como um processo à parte que é gerenciado por e registrado com uma lista de separação, você selecionará **Separado**.  
    - Verifique se a opção **Lançamento** está definida como **Sim**.  
7. Defina a opção **Imprimir guia de remessa** como **Sim**. A guia **Visão geral** contém uma lista de guias de remessa que serão geradas nesse lançamento. Se estiver remetendo uma ordem individual, normalmente haverá uma guia de remessa. No entanto, se as linhas dessa ordem estiverem prontas para ser enviadas de sites diferentes, o lançamento será automaticamente dividido no número apropriado de documentos. Essa é uma condição obrigatória que não pode ser alterada. De modo semelhante, o lançamento também será dividido em vários documentos se as linhas da ordem estiverem prontas para ser enviadas a endereços de entrega diferentes, e a política de envio é definida para requerer divisão.  
8. Na guia **Linhas**, selecione a linha para a linha de ordem que será remetida.
9. No campo **Atualizar**, insira um número menor que a quantidade original.
10. Selecione **OK**.
11. Selecione **Sim**.
12. Feche a página.
13. No Painel de Ações, selecione **Opções**.
14. Selecione **Alterar exibição**.
15. Selecione **Exibição do cabeçalho**.
    - Se todas as linhas na ordem foram completamente enviadas, o status da ordem muda de Aberto para Entregue.  
    - Neste exemplo, a linha da ordem foi remetida parcialmente. É por isso que o status da ordem permanece Aberto.     
    - Se o campo **Status do documento** estiver definido como Guia de remessa, é porque pelo menos uma das linhas da ordem foi enviada.  
16. No Painel de Ação, selecione **Geral**.
17. Selecione **Quantidade da linha**.
18. Feche a página.
19. No Painel de Ação, selecione **Separar e empacotar**.
20. Selecione **Guia de remessa**. A página **Diário de guias de remessa** contém todos os documentos de guia de remessa que foram gerados para sua ordem. Você pode revisar os detalhes de cada documento e imprimi-los, se desejar.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]