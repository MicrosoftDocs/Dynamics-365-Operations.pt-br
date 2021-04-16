---
title: Configurar estágios da ordem de serviço
description: Configurar estágios da ordem de serviço.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4b6e245b351b66724eedf8e0d1a0ebf0202df857
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824405"
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