---
title: Empréstimos de ativos
description: Este artigo descreve como registrar ativos de empréstimo em Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f70b29ef69b80160f108e6f53edda12b86c2c9db
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015744"
---
# <a name="asset-loans"></a>Empréstimos de ativos

[!include [banner](../../includes/banner.md)]

 

Se a sua empresa recebe ativos para trabalhos de reparo ou manutenção de locais internos ou clientes e se você empresta temporariamente ativos para esses locais ou clientes, o Gerenciamentos de Ativos pode rastrear os empréstimos de ativos.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Registre empréstimos de ativos em uma solicitação de manutenção

1. Selecione **Gerenciamento de ativos** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção** or **Solicitações de manutenção ativas**.
2. Selecione a solicitação de manutenção para registrar um empréstimo de ativo e selecione **Editar**.
3. Na página **Solicitação**, selecione **Enviar ativo de empréstimo**.
4. Selecione o ativo e insira a data de devolução prevista.
5. Selecione **OK**.

> [!NOTE]
> - Você só poderá enviar um ativo de empréstimo se um ativo do mesmo tipo de ativo fixo estiver disponível.
> - O ativo que você empresta deve ter um estado do ciclo de vida do ativo que permita ser usado como um ativo de empréstimo, como **InStorage**. Quando o empréstimo de ativo é registrado, o estado do ciclo de vida do ativo é atualizado automaticamente, por exemplo, para **OnLoan**.

Para exibir uma lista de todos os ativos que você emprestou a outros locais ou clientes, selecione **Gerenciamento de ativos** \> **Empréstimo de ativo** \> **Todos os empréstimos de ativos**. Se a caixa de seleção **Concluído** estiver marcada para um ativo, significa que o ativo foi registrado como devolvido para sua empresa.

![Gerenciar Solicitações de Manutenção.](media/06-manage-maintenance-requests.png)

Na página **Empréstimos de ativos em ação**, exiba uma lista de todos os ativos de empréstimo que ainda não foram devolvidos à sua empresa.

## <a name="register-loan-assets-as-returned"></a>Registre ativos de empréstimo conforme devolvidos

1. Selecione **Gerenciamento de ativos** \> **Empréstimo de ativo** \> **Empréstimos de ativos ativos**.
2. Selecione o empréstimo de ativo para registrar como devolvido e selecione **Devolver empréstimo de ativo**.
3. No campo **Devolvido**, insira a data e a hora.
4. Selecione **OK**.
5. Atualize a página **Empréstimos de ativos em ação** e observe que o empréstimo de ativos não aparece mais na lista.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]