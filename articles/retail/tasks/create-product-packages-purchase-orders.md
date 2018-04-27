--- 
title: Criar pacotes de produto para ordens de compra
description: "Este procedimento mostra a criação de um pacote de produtos e a utilização dele em uma ordem de compra."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d89744a4dbe52d201dc370b5cde151cc579508ea
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="create-product-packages-for-purchase-orders"></a>Criar pacotes de produto para ordens de compra

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimento mostra a criação de um pacote de produtos e a utilização dele em uma ordem de compra. A ordem de compra será usada para criar uma ordem para um conjunto predefinido de produtos. Este procedimento usa a empresa de dados de demonstração USRT.


## <a name="create-a-product-package"></a>Criar um pacote de produtos
1. Vá para Varejo e comércio > Gerenciamento de estoque > Reabastecimento > Pacotes de produto.
2. Clique em Novo.
3. No campo Número do pacote, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
7. Clique em Adicionar.
8. No campo do número de item, digite '0160'.
9. No campo Tamanho, clique no botão suspenso para abrir a pesquisa.
10. Na lista, clique no link na linha selecionada.
11. No campo Quantidade, insira um número.
12. Clique em Adicionar.
13. No campo do número de item, digite '0160'.
14. No campo Número da grade, clique no botão suspenso para abrir a pesquisa.
15. Na lista, clique no link na linha selecionada.
16. No campo Quantidade, insira um número.
17. Clique em Adicionar.
18. No campo Número de item, digite '0175'.
19. No campo Quantidade, insira um número.
20. Clique em Salvar.
21. Feche a página.

## <a name="add-package-to-purchase-order"></a>Adicionar o pacote à ordem de compra
1. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. Na lista, selecione o mesmo fornecedor para o qual o pacote de produtos foi criado anteriormente, se um fornecedor foi selecionado.
5. Alternar a expansão da seção Geral.
6. No campo Local, clique no botão suspenso para abrir a pesquisa.
7. Na lista, clique no link na linha selecionada.
8. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
9. Na lista, clique no link na linha selecionada.
10. Clique em OK.
11. Ative a expansão da seção Detalhes de linha.
12. Clique na guia de Pacotes do produto.
13. Clique na Linha de ordem de compra.
14. Clique em Criar linhas a partir de pacote.
15. Na lista, localize e selecione o grupo de produtos criado na etapa anterior.
16. No campo Quantidade, insira um número.
17. Clique em Criar.
18. Clique em Salvar.


