---
title: Receber entregas parciais de itens devolvidos
description: "As entregas parciais são definidas em termos de linhas de ordem de devolução, não nas remessas de ordem de devolução."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f9f596d31f2438a353b02bf939786b284937db86
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="receive-partial-deliveries-of-returned-items"></a>Receber entregas parciais de itens devolvidos    

[!include [banner](../includes/banner.md)]


As entregas parciais são definidas em termos de linhas de ordem de devolução, não nas remessas de ordem de devolução.

Isso significa que se você receber a quantidade total indicada em uma linha da ordem de devolução, mas não receber nada das outras linhas da ordem, a entrega não é uma entrega parcial. No entanto, se uma linha da ordem de devolução precisar de 10 unidades de um determinado item, mas somente quatro forem recebidos, trata-se de uma entrega parcial.

Se uma remessa de devolução contém menos do que a quantidade total de uma linha da ordem de devolução, você pode reservar a remessa e aguardar até a chegada do resto da quantidade devolvida ou pode registrar e lançar a quantidade parcial.

## <a name="register-and-post-a-partial-quantity"></a>Registrar e lançar uma quantidade parcial

1.  Depois de selecionar uma ordem de devolução para entrada no formulário **Visão geral de entrada - Depósito: %1, Doca: %2, Nome do diário: %3**, clique em **Iniciar entrara** para criar o diário de entrada, e clique em **Diários** \> **Exibir entradas de serviço** para abrir o formulário **Diário de localização**.

2.  Selecione a linha do diário com o qual deseja trabalhar e clique em **Linhas** para abrir o formulário **Linhas de diário, locais**.

3.  Selecione a linha do número de item para o qual apenas uma quantidade parcial foi recebida e clique em **Funções** \> **Separar** para abrir o formulário **Separar**.

4.  No campo **Separar quantidade**, insira a quantidade do número total de itens recebidos e, em seguida, clique em **OK**.

5.  No formulário **Linhas de diário, local**, selecione a linha para a quantidade de itens recebidos e clique em **Lançar**. É possível lançar a linha para a quantidade adicional após os itens chegarem.




