---
title: Configurar imposto global retido na fonte
description: Este artigo lista as etapas para configurar o imposto global retido na fonte para vendas e compras.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f2cdd388d790b48135561f740b63dc97875e85a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902448"
---
# <a name="set-up-global-withholding-tax"></a>Configurar imposto global retido na fonte

Este artigo lista as etapas para configurar o imposto global retido na fonte para vendas e compras. 

1. Configure as autoridades de imposto retido na fonte na página **Autoridades de imposto retido na fonte**.

2. Configure os períodos de liquidação de retenção na página **Períodos de liquidação de imposto retido na fonte**.

3. Configure o grupo de lançamentos contábeis na página **Imposto retido na fonte > Grupo de lançamentos do razão**.

   > [!Note] 
   >
   > **A conta de imposto retido na fonte** será atribuída a uma conta principal com o **Tipo de lançamento** Imposto retido na fonte. **A conta de contrapartida de retenção de imposto na fonte** também será atribuída a uma conta principal com o **Tipo de lançamento** Contrapartida de retenção de imposto na fonte. Acesse **Contabilidade > Plano de contas > Contas > Contas principais**, configure o **Tipo de lançamento** no subformulário **Validação de lançamento** para as contas principais.

4. Configure os códigos de imposto retido na fonte na página **Autoridades imposto retido na fonte**.

5. Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte**.

6. Configure os tipos de receita de imposto retido na fonte na página **Tipos** de **Receita de imposto retido na fonte**.

7. Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte do item** para um item ou serviço.

8. Configure o **Valor mínimo da fatura** na página **Parâmetros de contabilidade > Imposto retido na fonte**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
