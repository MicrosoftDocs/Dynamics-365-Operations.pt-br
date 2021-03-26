---
title: Criar cheques que tenham status Em Branco
description: Este tópico explica como criar cheques em branco para uma conta bancária na página Cheques.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 94d3a4ac8a3906e48f5a6053c031001c111549ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254026"
---
# <a name="create-checks-that-have-blank-status"></a>Criar cheques que tenham status Em Branco

[!include [banner](../includes/banner.md)]

Este tópico explica como criar cheques em branco. Por exemplo, pode criar um cheque em branco para registrar que um cheque foi danificado e não pode ser usado para pagamento.

Na página **Cheques**, você executa tarefas de manutenção para os cheques. Por exemplo, você pode criar novos números de cheque e excluir cheques. Você também pode criar cheques com o status **Em Branco**. Depois que os cheques em branco forem criados, eles não poderão ser excluídos ou reutilizadas no sistema.

> [!NOTE]
> Esse recurso estará disponível na página **Cheques** somente se você ativar o recurso **Criar cheques com um status em branco na página Cheques** na página **Gerenciamento de recursos**. Se o recurso não estiver ativado, os cheques com o status **Em Branco** poderão ser criados somente a partir da caixa de diálogo **Pagamento por cheque** durante o processo de geração de pagamento em Contas a pagar.

Para abrir a página **Cheques**, acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias** e, no Painel de Ações, na guia **Gerenciar pagamentos**, no grupo **Informações relacionadas**, selecione **Cheques**. Alternativamente, acesse **Gerenciamento de caixa e bancos \> Consultas e relatórios \> Cheques**.

Em seguida, para criar cheques com o status **Em Branco**, no Painel de Ações, selecione **Criar cheques em branco**. Enquanto o sistema estiver criando cheques em branco, a conta bancária associada ficará desativada temporariamente. Esse comportamento reduz o risco de pagamentos serem gerados ao mesmo tempo em que os cheques em branco são criados. Quando o processamento for concluído, a conta bancária associada será reativada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]