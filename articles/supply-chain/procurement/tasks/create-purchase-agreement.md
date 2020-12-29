---
title: Criar um contrato de compra
description: Neste tópico, você entenderá como criar um contrato de compra.
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422126"
---
# <a name="create-a-purchase-agreement"></a>Criar um contrato de compra

[!include [banner](../../includes/banner.md)]

Neste tópico, você entenderá como criar um contrato de compra. Isso seria feito normalmente por um gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Você precisa ter classificações do contrato de compra configuradas antes de começar. Após criar um contrato é possível usá-lo quando você criar um PO, e isso irá copiar as condições do contrato de compra para o cabeçalho e para todas as linhas da ordem que são afetadas pelo contrato.


## <a name="create-a-new-purchase-agreement"></a>Criar um novo contrato de compra
1. Vá para **Painel de Navegação > Módulos > Compras e fornecimento > Contratos de compra > Contratos de compra**.
2. Clique em **Novo**.
3. No campo **Conta do fornecedor**, selecione o menu suspenso e selecione a linha do registro desejado.
4. No campo **Classificação de contrato de compra**, selecione o menu suspenso e selecione a linha do registro desejado.
5. Expanda a Guia Rápida **Geral**.
6. No campo **Data de validade**, insira uma data.

    - Essa data de vencimento será o padrão para todas as linhas de compromisso e irá determinar por quanto tempo cada compromisso específico é válido.  

7. No campo **Título do documento**, digite um nome para o contrato de compra.

    - Deixe o campo **Comprometimento padrão** definido como **Comprometimento de quantidade do produto** (ou altere-o caso não esteja definido assim).  
    - O valor de compromisso padrão determina suas opções nas linhas do contrato. Se for necessário um novo tipo de compromisso ao criar as linhas do contrato, é preciso alterar o compromisso padrão no cabeçalho. Existem 4 tipos de compromissos: **Compromisso da quantidade do produto** - para uma quantidade específica de um produto; **Compromisso de valor do produto** - para um valor monetário específico de um produto; **Compromisso de valor da categoria do produto** - para um valor monetário específico em uma categoria de aquisição em que o valor pode ser para um item de catálogo ou um item não catalogado; **Compromisso de valor** - para um valor monetário específico que pode ser atendido por qualquer produto ou por qualquer categoria de aquisição.  

8. Selecione **OK**.

## <a name="add-a-commitment"></a>Adicionar um compromisso
1. Selecione **Adicionar linha**.
2. No campo **Número do item**, selecione o registro desejado no menu suspenso.
3. No campo **Quantidade.**, insira um número Esta é a quantidade total que você concordou em comprar do fornecedor.  
4. No campo **Preço unitário**, insira um número.
5. Expanda a seção **Detalhes da linha**.
6. Defina a opção **Máximo é forçado** como **Sim**. A opção **Máximo é forçado** limita o uso do compromisso. Você só pode comprar até a quantidade especificada no campo **Quantidade** para a linha.  

## <a name="add-header-conditions"></a>Adicionar condições de cabeçalho
1. No Painel de Ações, selecione **Opções**.
2. Selecione **Alterar exibição**.
3. Selecione **Exibição do cabeçalho**.
4. Expandir a seção **Condições**.
5. No campo **Método de pagamento**, selecione o registro desejado no menu suspenso. As condições de pagamento da conta do fornecedor são exibidas aqui por padrão.  
6. No campo **Modo de entrega**, selecione o registro desejado no menu suspenso.
7. No campo **Condições de entrega**, selecione o botão suspenso para abrir a pesquisa.

## <a name="confirm-and-activate-the-agreement"></a>Confirmar e ativar o contrato
1. No Painel de Ações, selecione **Contrato de compra**.
2. Selecione **Confirmação**. Defina a opção **Marcar contrato como efetivo** como **Sim**.  
3. Selecione **OK**.
4. No Painel de Ações, selecione **Contrato de compra**.
5. Selecione **Confirmações de contrato de compra**. A opção **Visualizar/Imprimir** permite que você gere um documento para o contrato de compra, o qual você poderá imprimir ou enviar ao fornecedor. Se você atualizar o contrato mais tarde e o reconfirmá-lo, ambas as versões serão exibidas aqui.  
6. Feche a página.

