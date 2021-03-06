---
title: Configurar imposto global retido na fonte
description: Este tópico lista as etapas para configurar o imposto global retido na fonte para vendas e compras.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3270b3f75d719fef9a7eb991c49e9d6585cd44d8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815299"
---
# <a name="set-up-global-withholding-tax"></a>Configurar imposto global retido na fonte

Este tópico lista as etapas para configurar o imposto global retido na fonte para vendas e compras. 

1. Configure as autoridades de imposto retido na fonte na página **Autoridades de imposto retido na fonte**.

2. Configure os períodos de liquidação de retenção na página **Períodos de liquidação de imposto retido na fonte**.

3. Configure o grupo de lançamentos contábeis na página **Imposto retido na fonte > Grupo de lançamentos do razão**.

   > [!Note] 
   >
   > **A conta de imposto retido na fonte** será atribuída a uma conta principal com o **Tipo de lançamento** Imposto retido na fonte. **A conta de contrapartida de retenção de imposto na fonte** também será atribuída a uma conta principal com o **Tipo de lançamento** Contrapartida de retenção de imposto na fonte. Vá para **Contabilidade > Plano de contas > Contas > Contas principais**, configure o **Tipo de lançamento** no subformulário **Validação de lançamento** para as contas principais.

4. Configure os códigos de imposto retido na fonte na página **Autoridades imposto retido na fonte**.

5. Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte**.

6. Configure os tipos de receita de imposto retido na fonte na página **Tipos** de **Receita de imposto retido na fonte**.

7. Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte do item** para um item ou serviço.

8. Configure o **Valor mínimo da fatura** na página **Parâmetros de contabilidade > Imposto retido na fonte**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]