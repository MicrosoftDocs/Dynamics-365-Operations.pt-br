---
title: Recebimento de placa de licença mista
description: Este artigo descreve como usar o recebimento de placa de licença mista para registrar e criar trabalho para vários itens com um dispositivo móvel.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ba316a5ed55902aed35acb4ef21623c7676b38
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907048"
---
# <a name="mixed-license-plate-receiving"></a>Recebimento de placa de licença mista

[!include [banner](../includes/banner.md)]

O recebimento de placa de licença mista permite criar uma placa de licença que consiste em vários itens antes de você registrar e criar trabalho de armazenamento. 

Uma placa de licença que consiste em vários itens não precisa ser dividida na doca de recebimento para que você registre cada item. 

Ao usar um fluxo relacionado ao item para identificar as linhas do documento de origem, você pode procurar códigos de barras no controle de item. Se o código de barras tiver uma quantidade e uma UOM (unidade de medida) configuradas nele, o item e a quantidade serão adicionados automaticamente à placa de licença mista, e você será redirecionado à tela para verificar outro item. Isso permite a você verificar rapidamente todos os itens sem a necessidade de uma confirmação a cada etapa. 

No fluxo para o recebimento de placa de licença mista, você pode exibir a lista de itens que já foram verificados pela placa de licença e, assim, alterar ou corrigir a quantidade de um item.

## <a name="where-it-applies"></a>Aplica-se a

O recebimento de placa de licença mista é um dispositivo móvel de recebimento de fluxo para registrar e criar trabalho para várias linhas/itens ao mesmo tempo. Isso é útil caso você receba placas de licença de entrada com diversos itens. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Como configurar o recebimento de placa de licença mista
O recebimento de placa de licença mista é configurado como um item de menu de dispositivo móvel.

Você precisa criar um novo item de menu com o modo de trabalho que não usa o trabalho existente, e sim um dos seguintes métodos:

- Recebimento de placa de licença mista
- Recebimento e armazenamento de placa de licença mista

As opções para identificar as linhas do documento de origem são: item da ordem de compra, linha da ordem de compra, ordem de devolução, item da ordem de transferência e linha da ordem de transferência. Essas opções podem alterar a ordem de recebimento em uma única placa de licença. A última opção é por item de carga. Você pode adicionar vários itens a uma placa de licença, mas não pode alternar entre várias cargas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]