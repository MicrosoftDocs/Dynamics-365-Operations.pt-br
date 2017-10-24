--- 
title: Criar e adquirir ativos de contas a pagar
description: "Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9149378047fc22efbd401b7af86df07c1403e4f5
ms.openlocfilehash: cfe920b2ef493ab3ae36a9557001086ed99c3e4e
ms.contentlocale: pt-br
ms.lasthandoff: 10/05/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Criar e adquirir ativos de contas a pagar

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra. Usa os caixeiros de contador e contas a pagar e a empresa USMF de demonstração.


## <a name="set-fixed-assets-parameters"></a>Definir parâmetros dos ativos fixos
1. Vá para Ativos fixos > Configuração > Parâmetros de ativos fixos.
2. Expandir ou recolher a seção Ordens de compra.
3. Marque a caixa de seleção Permitir a aquisição de ativos de Compras.
4. Marque a caixa de seleção Criar um ativo durante o recebimento de produtos ou o lançamento de fatura.

## <a name="create-a-new-vendor-invoice"></a>Criar uma nova fatura de fornecedor
1. Vá para Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor.
2. Clique em Nova fatura de fornecedor.
3. No campo Conta de fatura, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. No campo Número, digite um valor.
6. No campo Lançamento, insira uma data.
7. Clique em Adicionar linha.
8. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
    * Os itens não estocados ou as categorias de aquisição podem ser usados para aquisições de ativo fixo.  
9. Na lista, clique no link na linha selecionada.
10. No campo Quantidade, insira um número.
    * Uma linha da nota fiscal criará somente um ativo fixo, independentemente da quantidade.  O valor do campo de quantidade da nota fiscal será transferido para a quantidade do ativo fixo.  
11. No campo Preço unitário, insira um número.
12. Expandir ou recolher a seção Detalhes de linha.
13. Clique na guia Ativos fixos.
14. Marque a caixa de seleção Criar um novo ativo fixo.
15. No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.
16. Na lista, selecione o grupo de ativos fixos a ser usado quando criar o novo ativo fixo.
17. Na lista, clique no link na linha selecionada.
18. Clique em Lançar.
    * O ativo fixo será criado e adquirido quando a nota fiscal for lançada.  


