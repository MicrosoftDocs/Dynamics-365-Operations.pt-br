--- 
title: Criar um contrato de compra
description: "Este procedimento irá guiá-lo na criação de um contrato de compra."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0d0cc6508071bea3f622bc21f06aa55d2b757b6f
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-agreement"></a>Criar um contrato de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento irá guiá-lo na criação de um contrato de compra. Isso seria feito normalmente por um gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Você precisa ter classificações do contrato de compra configuradas antes de começar. Após criar um contrato é possível usá-lo quando você criar um PO, e isso irá copiar as condições do contrato de compra para o cabeçalho e para todas as linhas da ordem que são afetadas pelo contrato.


## <a name="create-a-new-purchase-agreement"></a>Criar um novo contrato de compra
1. Vá para Aquisição e fornecimento > Contratos de compra > Contratos de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo Classificação do contrato de compra, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o PDV desejado.
8. Na lista, clique no link na linha selecionada.
9. Expanda a seção Geral.
10. No campo Data de validade, insira uma data.
    * Essa data de vencimento será o padrão para todas as linhas de compromisso e irá determinar por quanto tempo cada compromisso específico é válido.  
11. No campo Título do documento, digite um nome para o contrato de compra.
    * Deixe o campo Comprometimento padrão definido como Comprometimento de quantidade do produto (ou altere-o caso não esteja definido assim).  
    * O valor de compromisso padrão determina suas opções nas linhas do contrato. Se for necessário um novo tipo de compromisso ao criar as linhas do contrato, é preciso alterar o compromisso padrão no cabeçalho.  Existem 4 tipos de compromissos: Compromisso da quantidade do produto - para uma quantidade específica de um produto; Compromisso de valor do produto - para um valor monetário específico de um produto; Compromisso de valor da categoria do produto - para um valor monetário específico em uma categoria de aquisição em que o valor pode ser para um item de catálogo ou um item não catalogado; Compromisso de valor - para um valor monetário específico que pode ser atendido por qualquer produto ou por qualquer categoria de aquisição.  
12. Clique em OK.

## <a name="add-a-commitment"></a>Adicionar um compromisso
1. Clique em Adicionar linha.
2. Na lista, marque a linha selecionada.
3. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
4. Selecione o produto para o qual você deseja adicionar um compromisso.
5. Na lista, clique no link na linha selecionada.
6. No campo Quantidade, insira um número.
    * Esta é a quantidade total que você concordou em comprar do fornecedor.  
7. No campo Preço unitário, insira um número.
8. Expanda a seção Detalhes da linha.
9. Defina a opção Máximo é forçado para Sim.
    * A opção Máximo é forçado limita o uso do compromisso. Você só pode comprar até a quantidade especificada no campo Quantidade para a linha.  
10. Recolha a seção Detalhes de linha.

## <a name="add-header-conditions"></a>Adicionar condições de cabeçalho
1. No Painel de Ação, clique em Opções.
2. Clique em Alterar exibição.
3. Clique em Exibição do cabeçalho.
4. Expandir a seção Condições.
5. No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.
    * As condições de pagamento da conta do fornecedor são exibidas aqui por padrão.       
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. No campo Modo de entrega, clique no botão suspenso para abrir a pesquisa.
9. Na lista, clique no link na linha selecionada.
10. No campo Condições de entrega, clique no botão suspenso para abrir a pesquisa.
11. Na lista, clique no link na linha selecionada.

## <a name="confirm-and-activate-the-agreement"></a>Confirmar e ativar o contrato
1. No Painel de Ação, clique em Contrato de compra.
2. Clique em Confirmação.
    * Defina a opção Marcar contrato como efetivo para Sim.  
3. Clique em OK.
4. No Painel de Ação, clique em Contrato de compra.
5. Clique em Confirmações do contrato de compra.
    * A opção de Visualizar/Imprimir permite que você gere um documento para o contrato de compra, o qual você poderá imprimir ou enviar ao fornecedor. Se você atualizar o contrato mais tarde e o reconfirmá-lo, ambas as versões serão exibidas aqui.  
6. Feche a página.


