---
title: Configurar intervalos de serviço
description: Este artigo descreve como configurar intervalos de serviço. O intervalo de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço.
author: sorenva
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b8a31af061b90aeddfb460f6e86c2c5636b280
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845943"
---
# <a name="set-up-service-intervals"></a>Configurar intervalos de serviço  

[!include [banner](../includes/banner.md)]

O intervalo de serviço indica a frequência com a qual as linhas de ordem de serviço são criadas para linhas de contrato de serviço quando você cria ordens de serviço.

1. Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Intervalos de serviço**.
2. Crie um novo intervalo de serviço.
3. Insira a ID e a descrição do intervalo de serviço.
4. No campo **Intervalo**, selecione o intervalo.
5. No campo **Frequência**, digite a frequência. A frequência é o fator pelo qual você deve multiplicar o intervalo para obter o intervalo de um contrato de serviço.
6. Pressione **Alt+S** para salvar o intervalo de serviço.

## <a name="example"></a>Exemplo

Você deseja criar um intervalo de serviços de 10 dias.

**Crie um intervalo de serviços de 10 dias**

1. Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Intervalos de serviço**.
2. Crie um novo intervalo de serviço.
3. Insira a ID e a descrição do intervalo de serviço.
4. No campo **Intervalo**, selecione **Diário**.
5. No campo **Frequência**, digite 10.
6. Pressione **Alt+S** para salvar o intervalo de serviço.

## <a name="related-articles"></a>Artigos relacionados

[Intervalos de serviço](service-intervals.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]