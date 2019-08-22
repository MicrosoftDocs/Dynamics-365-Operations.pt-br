---
title: Ordens de transferência (Brasil)
description: Este tópico fornece informações sobre as ordens de transferência do Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 80e0db1c8f3d87c19314a8e1f22c1e17388459e8
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849393"
---
# <a name="transfer-orders-brazil"></a>Ordens de transferência (Brasil)

[!include [banner](../includes/banner.md)]

Você pode usar ordens de transferência para transferir itens de estoque entre os depósitos que estão localizados em estabelecimentos fiscais diferentes. Você também pode transferir itens de estoque para outro estabelecimento fiscal.

Quando você transfere os itens entre estabelecimentos fiscais diferentes, as notas fiscais de transferência são emitidas ou recebidas:

  - Nota fiscal de saída – emitido quando você envia itens a um depósito que está localizado em um estabelecimento fiscal diferente.
  
  - Nota fiscal de entrada – recebido quando você recebe itens de um depósito que está localizado em um estabelecimento fiscal diferente.

Você pode fazer o seguinte para transferir itens entre estabelecimentos fiscais usando ordens de transferência:

  - Configurar uma matriz de Código Fiscal de Operações e Prestações (CFOP) para a transferência de estabelecimento fiscal ou tipos de transação de transferência de terceiros. Para obter mais informações, consulte [Configurar a matriz CFOP](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-the-cfop-matrix?branch=master).

  - Configurar uma matriz de imposto para um grupo de estabelecimento fiscal usando o tipo de transação de estabelecimento fiscal. Para obter mais informações, consulte [Configurar uma matriz de imposto](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-a-tax-matrix?branch=master).

  - Criar e enviar uma ordem de transferência para criar uma nota fiscal de saída. Para obter mais informações, consulte [Criar um documento fiscal para transferência de saída](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-create-an-outbound-transfer-fiscal-document?branch=master).

  - Receber uma ordem de transferência para criar uma nota fiscal de entrada. Para obter mais informações, consulte [Receber nota fiscal para transferência de entrada](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-receive-an-inbound-transfer-fiscal-document?branch=master).

  - Retornar uma nota fiscal de transferência. Para obter mais informações, consulte [Retornar uma nota fiscal de transferência](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-return-a-transfer-fiscal-document?branch=master).

  - Cancelar uma ordem de transferência incorreta. Para obter mais informações, consulte [Cancelar uma nota fiscal de transferência](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-cancel-a-transfer-fiscal-document?branch=master).
