---
title: Aprovar fornecedores para produtos específicos
description: Este procedimento mostra como aprovar fornecedores de produto específico.
author: RichardLuan
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, PdsApprovedVendorList, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d08791caba34908903ce330df0f91e44fbdfcaea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237266"
---
# <a name="approve-vendors-for-specific-products"></a>Aprovar fornecedores para produtos específicos

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como aprovar fornecedores de produto específico. Isso permite que você controle fornecedores que podem ser usados quando os produtos são adicionados a uma ordem de compra. Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Normalmente essa tarefa é realizada por um Gerente de compras.

1. No Painel de Navegação, vá para **Módulos > Gerenciamento de informações sobre produtos > Produtos > Produtos liberados**.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Expanda a Guia Rápida **Comprar**. Se houver um fornecedor principal mostrado no campo **Fornecedor**, você precisará adicionar esse fornecedor como um fornecedor aprovado nas etapas a seguir. Faça uma nota do número do fornecedor, se for mostrado.  
5. No Painel de Ação, clique em **Compra**.
6. Clique em **Configuração**.
7. Clique em **Adicionar**.
8. No campo Fornecedor, insira ou selecione um valor. Selecione o fornecedor aprovado. Pelo menos uma das linhas tem de ser o fornecedor principal se houver um registro do produto. Se você tiver feito uma anotação do número do fornecedor anterior, selecione-a aqui.  
9. No campo **Vencimento**, insira uma data. Escolha uma data que é daqui alguns meses.  
10. Clique em **Adicionar**.
11. No campo **Fornecedor**, insira ou selecione um valor.
12. No campo **Vencimento**, insira uma data. Escolha uma data diferente da data de vencimento anterior.  
13. Feche a página.
14. No Painel de Ações, clique em **Fornecedores aprovados**.
15. No campo **Vencimento**, insira uma data. Essa data atua como um filtro para que você possa ver quais os fornecedores são aprovados até uma determinada data.  
16. Feche a página.
17. No Painel de Ações, clique em **Período efetivo**.
18. No campo **Mostrar fornecedores expirados por**, insira uma data. Você pode usar a página para identificar os fornecedores em que o status de aprovação expirará após uma determinada data.  
19. Feche a página.
20. Clique em **Editar**.
21. No campo **Método de verificação de fornecedores aprovados**, selecione uma opção. Este campo permite que você selecione a diretiva para o que deve acontecer se os produtos forem adicionados a uma linha da ordem de compra no qual o fornecedor não é um fornecedor aprovado.  
22. Clique em **Salvar**.
23. Feche a página.
24. Feche a página.
25. No Painel de Navegação, vá para **Módulos > Aquisição e fornecimento > Fornecedores > Relações fornecedor/item > Lista de fornecedores aprovados por item**. Essa página apresenta uma visão geral de todos os produtos e fornecedores aprovados.  
26. Feche a página.
27. No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**. Também é possível partir de um fornecedor e ir para a lista de produtos aprovados da conta do fornecedor.  
28. Na lista, localize e selecione o PDV desejado.
29. No Painel de Ações, clique em **Compras**.
30. Clique em **Lista de fornecedores aprovados por fornecedor**.
31. Feche a página.
32. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]