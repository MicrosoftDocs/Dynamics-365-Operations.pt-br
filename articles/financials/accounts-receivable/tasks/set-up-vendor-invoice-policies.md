--- 
title: "Configurar políticas de fatura de fornecedores"
description: "As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f51c117da75a0382a38e75154ecef758f9a5d6c1
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-vendor-invoice-policies"></a>Configurar políticas de fatura de fornecedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor. Você também pode configurar o fluxo de trabalho da fatura do fornecedor para executar as políticas de fatura do fornecedor todas as vezes que você enviar uma fatura para o fluxo de trabalho. 

As políticas de fatura do fornecedor não se aplicam às faturas que foram criadas no registro de fatura ou no diário de faturas. 

A validação de conciliação de fatura não usa as políticas da fatura do fornecedor, mas é configurada na página de parâmetros de contas a pagar.

Este registro usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas. Antes de começar, verifique se a configuração conciliação de faturas está marcada.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Preparar para criar políticas de fatura do fornecedor
1. Ir para Contas a pagar > Configuração > Parâmetros de contas a pagar.
2. Clique na guia Validação de fatura.
3. Marque ou desmarque a caixa de seleção automaticamente do status do cabeçalho da nota fiscal da atualização.
4. Clique em OK.
5. No campo Lançar nota fiscal com discrepâncias, selecione uma opção.
6. Feche a página.
7. Ir para Contas a pagar > Configuração de política > Políticas de fatura de fornecedor.
8. Clique em Parâmetros.
9. Clique em btnAdd.
10. Feche a página.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Criar tipos de regras de política para faturas de fornecedor
1. Ir para Contas a pagar > Configuração de política > Tipos de regra de políticas de fatura de fornecedor.
2. Clique em Novo.
3. No campo Nome da regra, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Nome da consulta, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. Clique em Salvar.
9. Feche a página.

## <a name="define-a-vendor-invoice-policy"></a>Definir uma política de fatura de fornecedor
1. Ir para Contas a pagar > Configuração de política > Políticas de fatura de fornecedor.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. Expanda ou recolha a seção de organizações de diretivas.
6. Na árvore, selecione 'Contoso Entertainment System USA'.
7. Clique em Adicionar.
8. Expanda ou recolha a seção de regras de diretivas.
9. Clique em Criar regra de política.
10. No campo Descrição de regra de política, digite um valor.
11. Clique em Filtro.
12. Clique em Adicionar.
13. Na lista, marque a linha selecionada.
14. No campo Tabela, clique no botão suspenso para abrir a pesquisa.
15. Na lista, clique no link na linha selecionada.
16. No campo Tabela derivada, clique no botão suspenso para abrir a pesquisa.
17. Na lista, clique no link na linha selecionada.
18. No campo Campo, clique no botão suspenso para abrir a pesquisa.
19. No campo Campo, digite um valor.
20. Feche a página.
21. No campo Critérios, digite um valor.
22. Clique em OK.
23. Clique em OK.
24. Feche a página.
25. Feche a página.


