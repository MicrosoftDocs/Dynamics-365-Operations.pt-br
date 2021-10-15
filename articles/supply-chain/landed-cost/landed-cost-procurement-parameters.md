---
title: Parâmetros de compras e fornecimento para custo de entrega
description: Este tópico descreve como configurar os parâmetros relevantes de Compras e fornecimento ao usar o módulo Custo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb41fc6477acb005912c735a691de6d1a659c020
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569832"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Parâmetros de compras e fornecimento para custo de entrega

[!include [banner](../../includes/banner.md)]

A página **Parâmetros de compras e fornecimento** tem algumas configurações que são especialmente relevantes ao usar o módulo **Custo de entrega**. Use a caixa de diálogo **Atualizar linhas de ordem** que é aberta na página **Parâmetros de compras e fornecimento** para especificar se as linhas da ordem de compra devem ser atualizadas automaticamente quando são feitas alterações no cabeçalho da ordem de compra.

Para concluir essa configuração, siga essas etapas.

1. Acesse **Compras e fornecimento \> Configuração \> Parâmetros de compras**.
1. Na guia **Geral**, selecione o link **Atualizar linhas da ordem**.
1. A caixa de diálogo **Atualizar linhas da ordem** lista os campos no cabeçalho da ordem que também podem aplicar atualizações automáticas a campos relacionados nas linhas da ordem. Defina cada campo na lista com um dos seguintes valores:

    - **Sempre** – As linhas de ordem devem ser atualizadas automaticamente quando o cabeçalho da ordem é atualizado.
    - **Nunca** – As linhas de ordem nunca devem ser atualizadas quando o cabeçalho da ordem é atualizado.
    - **Aviso** – O usuário será solicitado a selecionar se as linhas da ordem devem ser atualizadas.
