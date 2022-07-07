---
title: Crie ordens de serviço a partir de solicitações de manutenção
description: Este artigo explica como criar uma ordem de serviço a partir de uma solicitação de manutenção em Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb54ec3466086afbd87a023a40e346a6a3464c98
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017164"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Crie ordens de serviço a partir de solicitações de manutenção

[!include [banner](../../includes/banner.md)]

 


Depois de criar solicitações de manutenção, você poderá facilmente convertê-las em ordens de trabalho. Este artigo descreve a maneira mais rápida de trabalhar com solicitações de manutenção, atualizar várias solicitações de manutenção ao mesmo tempo e criar uma ordem de serviço para várias solicitações de manutenção simultaneamente. Na página **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção local funcional**, é possível trabalhar com uma solicitação de serviço por vez e converter uma solicitação de manutenção em uma ordem de serviço.

> [!NOTE]
> Toda solicitação de manutenção pode estar relacionado a apenas uma ordem de serviço. Porém, várias solicitações de manutenção podem ser incluídas em uma ordem de serviço, mesmo que as solicitações de manutenção tenham diferentes ativos.

1. Selecione **Gerenciamento de ativos** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção**.
2. Antes de criar uma ordem de serviço a partir de solicitações de manutenção, selecione, pelo menos, um tipo de trabalho de manutenção para as solicitações de manutenção. Selecione também a grade e o comércio de um tipo de trabalho de manutenção, caso essas informações sejam relevantes. Na exibição de grade, você pode facilmente atualizar informações para uma solicitação de manutenção.
3. Quando estiver pronto para criar uma ordem de serviço, selecione as solicitações de manutenção a serem incluídas nela.

    - Se você selecionar várias solicitações de manutenção para converter em uma ordem de serviço, defina os campos **Ativo** e **Tipo de trabalho de manutenção** antes de criar a ordem de serviço.
    - Se você selecionar uma solicitação de manutenção para converter em uma ordem de serviço, defina apenas o campo **Ativo** antes de criar a ordem de serviço. Porém, quando você criar a ordem de serviço, selecione um tipo de trabalho de manutenção (e uma grade e um comércio relacionados ao tipo de trabalho de manutenção, se essas informações forem relevantes) na caixa de diálogo **Criar ordem de serviço**.

4. Selecione **Ordem de serviço**.
5. Na caixa de diálogo **Criar ordem de serviço**, defina os campos e selecione **OK**.

    Uma barra de mensagem pode notificá-lo de que uma nova ordem de serviço foi criada.

    Além disso, quando você criar uma ordem de serviço com base em uma solicitação de manutenção, se o ativo relacionado à solicitação de manutenção estiver incluído em um contrato de garantia, uma barra de mensagem o notificará sobre o contrato de garantia.

6. Selecione **Gerenciamento de ativos** \> **Ordens de serviço** \> **Todas as ordens de serviço**, e abra a nova ordem de serviço.

    ![Abrir nova ordem de serviço.](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]