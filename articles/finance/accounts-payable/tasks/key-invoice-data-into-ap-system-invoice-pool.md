---
title: Dados-chave de fatura no sistema de AP usando grupo de faturas
description: Este tópico descreve como usar o registro de fatura para criar faturas.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e53de7091fd818bdc7085c404794e16dc84dd156
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979279"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Dados-chave de fatura no sistema de AP usando grupo de faturas

[!include [banner](../../includes/banner.md)]

Este tópico descreve como usar o registro de fatura para criar faturas. Use o grupo de notas fiscais para fazer a correspondência da nota fiscal para uma ordem de compra e finalizar as despesas na página da nota fiscal do fornecedor.


## <a name="create-a-purchase-order"></a>Criar uma ordem de compra
1. No painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Ordens de compra**.
2. Selecione **Novo** para criar uma ordem de compra.
3. No campo **Conta do fornecedor**, selecione um fornecedor da lista suspensa. Por exemplo, selecione o fornecedor **1001**.
4. Selecione **OK**.
5. No campo **Número do item**, selecione o número do item de serviços na lista suspensa. Por exemplo, selecione **S0001**. O total líquido é 75,00.  Esse é o valor que esperaremos na nota fiscal.  
6. No painel de ação, selecione **Compra**.
7. Selecione **Confirmar**.

## <a name="create-and-post-and-invoice"></a>Criar e lançar e faturar
1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Registro de faturas**.
2. Selecione **Novo**.
3. Abra a busca para selecionar o nome do registro de fatura que você deseja usar.
4. Selecione o nome do registro de fatura que você deseja usar.
5. Selecione **Linhas** para abrir o registro e inserir as linhas de despesa.
6. Na busca, selecione um fornecedor. Por exemplo, selecione o fornecedor **1001**.
7. No campo **Fatura**, insira o número da fatura.
8. No campo **Descrição**, digite um valor.
9. No campo **Crédito**, insira um número.
10. No campo **Ordem de compra**, abra a lista suspensa para selecionar a ordem de compra criada anteriormente.
11. No campo **Aprovado por**, realce um aprovador na lista suspensa e clique em **Selecionar** para selecionar esse aprovador.
12. Selecione **Lançar**.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Abra uma fatura do grupo e corresponda-a a ordem de compra para concluir o processo de fatura
1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Grupo de faturas**.
2. Selecione **Ordem de compra** para criar uma fatura de fornecedor usando a fatura do grupo.
3. Selecione a fatura que você deseja revisar.
4. Selecione **Atualizar status de conciliação** para concluir a conciliação.
5. No painel de ações, selecione **Opções**.
6. Selecione **Alterar exibição**.
7. Selecione **Exibição de grade**.
8. Selecione **Lançar**.
9. Feche o formulário.
10. No painel de navegação, vá para **Módulos > Contas a pagar > Fornecedores > Fornecedores**.
11. Selecione o fornecedor que estava na ordem de compra. Por exemplo, selecione o fornecedor **1001**.
12. No painel de ação, selecione **Fornecedor**.
13. Selecione **Transações**.
14. Selecione a nota fiscal que você criou. O acúmulo de registro de nota fiscal foi estornada e lançada na conta de despesas apropriada.  

