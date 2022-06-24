---
title: Configurar políticas de fatura de fornecedores
description: Este artigo explica como configurar políticas de fatura de fornecedor.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 049b38b6feba5f4369d79b89b4c81a8195dd7758
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904720"
---
# <a name="set-up-vendor-invoice-policies"></a>Configurar políticas de fatura de fornecedores

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar políticas de fatura de fornecedor. As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página **Fatura do fornecedor** e quando você abre a página **Violações de política** da fatura de fornecedor. Você também pode configurar o fluxo de trabalho da fatura do fornecedor para executar as políticas de fatura do fornecedor todas as vezes que você enviar uma fatura para o fluxo de trabalho. 

- As políticas de fatura do fornecedor não se aplicam às faturas que foram criadas no registro de fatura ou no diário de faturas.  
- A validação de conciliação de fatura não usa as políticas da fatura do fornecedor, mas é configurada na página **Parâmetros de contas a pagar**.  
- Este registro usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas. Antes de começar, verifique se a chave **Configuração conciliação de faturas** está marcada.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Preparar para criar políticas de fatura do fornecedor
1. Acesse **Painel de navegação > Módulos > Contas a pagar > Configuração > Parâmetros de contas a pagar**.
2. Selecione a guia **Validação de fatura**.
3. Marque ou desmarque a caixa de seleção **Atualizar automaticamente cabeçalho de fatura**.
4. Selecione **OK**.
5. No campo **Lançar fatura com discrepâncias**, selecione uma opção.
6. Feche a página.
7. Acesse **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.
8. Selecione **Parâmetros**.
9. Selecione **Adicionar**.
10. Feche a página para voltar à home page.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Criar tipos de regras de política para faturas de fornecedor
1. Acesse **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Tipos de regra de política de fatura de fornecedor**.
2. Selecione **Novo**.
3. Nos campos **Nome da regra** e **Descrição**, digite valores.
4. No campo **Nome da consulta**, selecione o botão suspenso para abrir a pesquisa e então selecione o registro desejado.
5. Selecione **Salvar**.
6. Feche a página para voltar à home page.

## <a name="define-a-vendor-invoice-policy"></a>Definir uma política de fatura de fornecedor
1. Acesse **Painel de navegação > Módulos > Contas a pagar > Configuração de política > Políticas de fatura de fornecedor**.
2. Selecione **Novo**.
3. Nos campos **Nome** e **Descrição**, digite valores.
4. Expanda ou recolha a seção de **Organizações de política**.
5. Na árvore, selecione **Contoso Entertainment System USA**.
6. Selecione **Adicionar**.
7. Expanda ou recolha a seção de **Regras de política**.
8. Selecione **Criar regra de política**.
9. No campo **Descrição de regra de política**, digite um valor.
10. Selecione **Filtro**.
11. Selecione **Adicionar**. Selecione o registro desejado.
12. Nos campos **Tabela**, **Tabela derivada** e **Campo**, selecione ou insira opções dos menus suspensos.
13. Feche a página.
14. No campo **Critérios**, digite um valor.
15. Selecione **OK**.
16. Selecione **OK**.
17. Feche as páginas para voltar à home page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
