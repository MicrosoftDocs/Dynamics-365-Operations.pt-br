---
title: Abrir modelos de diário financeiro no Office
description: Este artigo descreve problemas que podem ocorrer ao criar diários financeiros personalizados usando um modelo do Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a29ab1cb2980ebfed6c6fa6409538bc802849156
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896337"
---
# <a name="open-financial-journal-templates-in-office"></a>Abrir modelos de diário financeiro no Office

[!include [banner](../includes/banner.md)]

Este artigo descreve problemas que podem ocorrer ao criar diários financeiros personalizados usando um modelo do Microsoft Excel.

## <a name="symptom"></a>Sintoma

Você criou um modelo personalizado do Excel para diários financeiros, mas ele não aparece no menu **Abrir linhas no Excel**. Como alternativa, ele é exibido no menu, um modelo diferente é aberto, mas quando selecionado.

## <a name="resolution"></a>Resolução

A funcionalidade padrão Abrir no Excel usa a fonte de dados raiz (tabela) da página atual para determinar quais modelos ou entidades de dados do Office aparecerão como opções no menu **Abrir no Excel**. Esse comportamento não é uma experiência ideal para diários financeiros, porque os eles usam as mesmas tabelas (LedgerJournalTable e LedgerJournalTrans) como a fonte de dados raiz de muitos outros tipos de diários.

Para diários financeiros, a funcionalidade Abrir linhas no Excel destina-se a mostrar modelos que foram criados para o diário no qual você está trabalhando no contexto no momento, como o diário geral ou um diário de pagamentos. Por exemplo, um modelo que deve ser usado com um diário de pagamentos do fornecedor será criado para impor sua conta principal como uma conta de fornecedor.

Se quiser promover um modelo para que fique disponível nos menus **Abrir linhas no Excel** e **Abrir no Excel**, uma experiência fácil para desenvolvedores é implementar a interface de **LedgerIJournalExcelTemplate** e estender a classe de **DocuTemplateRegistrationBase**. Vários exemplos dessa abordagem estão implementados no sistema. Um exemplo que pode ser usado para referência é a interface de **LedgerDailyJournalExcelTemplate** que foi criada para o diário geral (ou diário).

Quando a interface de **LedgerIJournalExcelTemplate** é implementada para o seu modelo, o menu **Abrir linhas no Excel** filtrará os modelos pelo tipo de diário do seu diário e mostrará somente os modelos disponíveis para o diário. A interface também fornece um método de validação que garante que um modelo não possa ser aberto para um diário se ele não atender aos requisitos de tipo de conta. Por exemplo, você pode especificar que o tipo de conta deve ser de **Fornecedor** ou do tipo **Razão**.

Para obter mais informações sobre essa funcionalidade, consulte [adicionar modelos ao menu Abrir linhas no Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).
