---
title: Pesquisar ou resolver exceções
description: As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8110010"
---
# <a name="research-or-resolve-exceptions"></a>Pesquisar ou resolver exceções

[!include [banner](../../includes/banner.md)]

As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página **Fatura do fornecedor** e quando você abre a página **Violações de política** da fatura de fornecedor. Você também pode configurar o fluxo de trabalho da fatura do fornecedor para executar as políticas de fatura do fornecedor todas as vezes que você enviar uma fatura para o fluxo de trabalho. 

As políticas de fatura do fornecedor não se aplicam às faturas que foram criadas no **Registro de fatura** ou no **Diário de faturas**. 

A validação de conciliação de fatura não usa as políticas da fatura do fornecedor, mas é configurada na página **Parâmetros de contas a pagar**.

Este registro usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas. Antes de começar, verifique se a chave **Configuração conciliação de faturas** está marcada.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Preparar para criar políticas de fatura do fornecedor
1. Acesse **Contas a pagar > Configuração > Parâmetros de contas a pagar**.
2. Clique na guia **Validação de fatura**.
3. Marque ou desmarque a caixa de seleção **Atualizar automaticamente cabeçalho de fatura**.
4. Clique em **OK**.
5. No campo **Lançar fatura com discrepâncias**, selecione uma opção.
6. Feche a página.
7. Ir para **Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.
8. Clique em **Parâmetros**.
9. Clique em **Adicionar**.
10. Feche a página.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Criar tipos de regras de política para faturas de fornecedor
1. Ir para **Contas a pagar > Configuração de política > Tipos de regra de políticas de fatura de fornecedor**.
2. Clique em **Novo**.
3. No campo **Nome da regra**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Nome da consulta**, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. Clique em **Salvar**.
9. Feche a página.

## <a name="define-a-vendor-invoice-policy"></a>Definir uma política de fatura de fornecedor
1. Ir para **Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.
2. Clique em **Novo**.
3. No campo **Nome**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Expanda ou recolha a seção de **Organizações de política**.
6. Na árvore, selecione 'Contoso Entertainment System USA'.
7. Clique em **Adicionar**.
8. Expanda ou recolha a seção de **Regras de política**.
9. Clique em **Criar regra de política**.
10. No campo **Descrição de regra de política**, digite um valor.
11. Clique em **Filtrar**.
12. Clique em **Adicionar**.
13. Na lista, marque a linha selecionada.
14. No campo **Tabela**, clique no botão suspenso para abrir a pesquisa.
15. Na lista, clique no link na linha selecionada.
16. No campo **Tabela derivada**, clique no botão suspenso para abrir a pesquisa.
17. Na lista, clique no link na linha selecionada.
18. No campo **Campo**, clique no botão suspenso para abrir a pesquisa.
19. No campo **Campo**, digite um valor.
20. Feche a página.
21. No campo **Critérios**, digite um valor.
22. Clique em **OK**.
23. Clique em **OK**.
24. Feche a página.
25. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
