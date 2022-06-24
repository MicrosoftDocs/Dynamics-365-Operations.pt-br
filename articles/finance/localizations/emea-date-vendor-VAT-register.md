---
title: Data do registro de IVA do fornecedor
description: Este artigo fornece informações sobre um recurso para habilitar a data do registro de IVA do fornecedor
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b1368e0c7764bed42aa7549f36a6f4bcbb96eff4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849766"
---
# <a name="date-of-vendor-vat-register"></a>Data do registro de IVA do fornecedor

No Microsoft Dynamics 365 Finance versão 10.0.24, há um novo campo **Data do registro de IVA do fornecedor** disponível para faturas de fornecedor. Este campo especifica a data do fornecimento tributável para uma compra.

Para habilitar o novo campo, vá para o espaço de trabalho **Gerenciamento de recursos**, localize e selecione o recurso **Habilitar data do registro de IVA do fornecedor em faturas de fornecedor** e, em seguida, selecione **Habilitar agora**.

As faturas de entrada dos fornecedores podem ter duas datas: a data em que o fornecedor emitiu a fatura e a data do fornecimento tributável (ou seja, a data em que o fornecedor cobrou o IVA (imposto sobre valor agregado) a pagar). Em alguns cenários, essas duas datas podem ser diferentes.

Você pode deduzir o valor de IVA de entrada para uma fatura de compra e incluir a fatura em relatórios de IVA mais tarde, em uma data diferente das datas previamente mencionadas. Essa data é controlada por regras de legislação local sobre dedução de IVA de entrada adiada para alguns cenários. Varia por país ou região.

Alguns relatórios de IVA, como o [Relatório do demonstrativo Controle de IVA](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) na República Tcheca, exigem que a data do fornecimento tributável seja relatada para um documento de compra. Essa data deve ser relatada para que as autoridades fiscais possam reconciliar o relatório de IVA entre as partes.

No Finance, você pode definir datas nos seguintes campos:

- **Data da fatura** – a data em que a fatura foi emitida pelo fornecedor.
- **Data do registro de IVA** – a data da dedução do valor de IVA para a fatura de compra.
- **Data do registro de IVA do fornecedor** – a data do fornecimento tributável do fornecedor.
- **Data de recebimento do documento** – a data em que você recebeu a fatura.

Esses campos estão incluídos nas seguintes páginas:

- Fatura de fornecedor
- Registro de fatura de fornecedor
- Aprovação de fatura de fornecedor
- Diário de faturas de fornecedores

Após o lançamento da fatura de fornecedor, você poderá revisar as datas nas páginas **Diário de faturas** e **Transações do fornecedor**.
