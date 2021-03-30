---
title: Criar e adquirir ativos de contas a pagar
description: Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb7c92fcab622109b01590d4acadce0d707d3d2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227079"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Criar e adquirir ativos de contas a pagar

[!include [banner](../../includes/banner.md)]

Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra.  Usa os caixeiros de contador e contas a pagar e a empresa USMF de demonstração.


## <a name="set-fixed-assets-parameters"></a>Definir parâmetros dos ativos fixos
1. No **Painel de Navegação**, vá para **Módulos > Ativos fixos > Configuração > Parâmetros de ativos fixos**.
2. Expanda a Guia Rápida **Ordens de compra**.
3. Marque a caixa de seleção **Permitir a aquisição de ativos de Compras**.
4. Marque a caixa de seleção **Criar um ativo durante o recebimento de produtos ou o lançamento de fatura**.

## <a name="create-a-new-vendor-invoice"></a>Criar uma nova fatura de fornecedor
1. No **Painel de Navegação**, vá para **Módulos > Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor**.
2. Clique em **Nova fatura de fornecedor**.
3. No campo **Conta de fatura**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. No campo **Número**, digite um valor.
6. No campo **Data de lançamento**, insira uma data.
7. Clique em **Adicionar linha**.
8. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa. Os itens não estocados ou as categorias de aquisição podem ser usados para aquisições de ativo fixo.  
9. Na lista, clique no link na linha selecionada.
10. No campo **Quantidade.**, insira um número Uma linha da nota fiscal criará somente um ativo fixo, independentemente da quantidade. O valor do campo de quantidade da nota fiscal será transferido para a quantidade do ativo fixo.  
11. No campo **Preço unitário**, insira um número.
12. Expanda a Guia Rápida **Detalhes da linha**.
13. Clique na guia **Ativos fixos**.
14. Marque a caixa de seleção **Criar um novo ativo fixo**.
15. No campo **Grupo de ativo fixo**, clique no botão suspenso para abrir a pesquisa.
16. Na lista, selecione o grupo de ativos fixos a ser usado quando criar o novo ativo fixo.
17. Na lista, clique no link na linha selecionada.
18. Clique em **Enviar**. O ativo fixo será criado e adquirido quando a nota fiscal for lançada.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]