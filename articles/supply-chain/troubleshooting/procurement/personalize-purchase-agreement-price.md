---
title: Não é possível adicionar o campo Unidade de preço à página Contrato de compra
description: Quando abre a página "Contrato de compra" em um modo de exibição de linha, você não consegue personalizar a página adicionando o campo "Unidade de preço" na visão geral da linha
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 56d2ce94fb4b74d982cb6a052cca71c18190cd04
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475552"
---
# <a name="you-cant-add-the-price-unit-field-to-the-purchase-agreement-page"></a>Não é possível adicionar o campo Unidade de preço à página Contrato de compra

## <a name="symptoms"></a>Sintomas

Quando abre a página **Contrato de compra** em um modo de exibição de linha, você não consegue personalizar a página adicionando o campo **Unidade de preço** na visão geral da linha.

## <a name="resolution"></a>Resolução

Alguns campos compartilhados na estrutura do contrato não podem ser incluídos nas personalizações. Essa limitação ocorre por causa do modelo de dados implementado. Portanto, não é possível personalizar o campo **Unidade de preço**.
