---
title: Cancelar ordens de serviço
description: É possível cancelar uma ordem de serviço ou uma linha de ordem de serviço na própria ordem, ou cancelar várias ordens de serviço executando um trabalho periódico.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce3cb9ebc3536ba1b333a7bef6b5c679e09d7516
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422360"
---
# <a name="cancel-service-orders"></a>Cancelar ordens de serviço   

[!include [banner](../includes/banner.md)]


É possível cancelar uma ordem de serviço ou uma linha de ordem de serviço na própria ordem, ou cancelar várias ordens de serviço executando um trabalho periódico.


> [!NOTE]
> <P>As ordens de serviço não podem ser canceladas se sua fase não permitir o cancelamento, se a ordem de serviço possuir requisitos de item ou se já tiver sido lançada.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Cancelar uma ordem de serviço no formulário Ordens de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**. Selecione a ordem de serviço e, no Painel de Ação, clique em **Cancelar ordem**.

## <a name="cancel-a-service-order-line"></a>Cancelar uma linha de ordem de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**. Clique duas vezes na ordem de serviço que contém a linha que deseja cancelar.

2.  Selecione a linha da ordem de serviço que deseja cancelar e, em seguida, clique em **Cancelar linha de ordem** para alterar o status da linha para **Cancelado**.


> [!TIP]
> <P>Para reverter o cancelamento de uma linha de ordem de serviço e alterar o status novamente para <STRONG>Criado</STRONG>, clique em <STRONG>Revogar cancelamento</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Cancelar várias ordens de serviço

1.  Clique em **Gerenciamento de serviço** \> **Periódico** \> **Ordens de serviço** \> **Cancelar ordens de serviço**.

2.  Clique no botão **Selecionar**.

3.  No formulário **Consulta**, na coluna **Critérios**, selecione as ordens de serviço que deseja cancelar.

4.  Clique em **OK** para fechar o formulário de **Consulta**.

5.  Marque a caixa de seleção **Mostrar Log de Informações** para gerar um Log de informações que lista as ordens de serviço canceladas.

6.  Marque a caixa de seleção **Revogar cancelamento** se quiser reverter o status **Cancelado** de uma ordem de serviço.

7.  Clique em **OK**.

As ordens de serviço selecionadas são canceladas ou seu status de progresso de **Cancelado** é revertido para **Em processo**.


> [!NOTE]
> <P>Se você marcar a caixa de seleção <STRONG>Revogar cancelamento</STRONG>, as ordens de serviço com um status de progresso de <STRONG>Cancelado</STRONG> são revertidas e as ordens de serviço com um status de progresso de <STRONG>Em processo</STRONG> não são canceladas.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]