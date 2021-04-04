---
title: Configurar estágios da ordem de serviço
description: Configurar estágios da ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9774d5f4e97d3f768366ba552e5928929bacf508
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470920"
---
# <a name="set-up-service-order-stages"></a>Configurar estágios da ordem de serviço 

[!include [banner](../includes/banner.md)]


1.  Vá para **Gerenciamento de serviços** \> **Configuração** \> **Ordens de serviço** \> **Fases de serviço**.

2.  Selecione **Novo** para criar um novo registro.

3.  Nos campos **Etapa de serviço** e **Descrição**, especifique uma ID de etapa de serviço e uma descrição.

4.  Selecione os parâmetros apropriados para o estágio.

5.  Selecione a fase pai da fase atual ou deixe o campo **Pai** em branco, se a fase for a fase inicial na configuração de fase.


> [!NOTE]
> <P>Depois que você salvar o estágio, não poderá modificar o campo <STRONG>Pai</STRONG>. Em vez disso, você pode excluir o registro e criá-lo novamente com uma seleção diferente no campo <STRONG>Pai</STRONG>.</P>
> <P>Além disso, você pode criar apenas um estágio com um campo <STRONG>Pai</STRONG> em branco. Ou seja, apenas um estágio inicial é permitido.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]