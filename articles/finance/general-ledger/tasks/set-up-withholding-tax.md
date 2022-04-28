---
title: Configurar imposto retido na fonte
description: Este tópico explica como configurar o imposto retido na fonte.
author: twheeloc
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxWithholdTable, TaxWithholdData, TaxWithholdGroup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c3c4992c7ab02793db3650df5624143d0ec090d0
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565574"
---
# <a name="set-up-withholding-tax"></a>Configurar imposto retido na fonte

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar o imposto retido na fonte. O *imposto retido na fonte* é um imposto cobrado dos fornecedores, o que não cria transações de imposto. O imposto retido na fonte calculado sobre os pagamentos do fornecedor é um passivo. Por isso, apenas contas de balanço ou de passivos são contas válidas para o lançamento do imposto retido na fonte. Essa guia da tarefa demonstra como definir a retenção de imposto.

1. Acesse **Painel de navegação > Módulos > Imposto > Impostos indiretos > Imposto retido na fonte > Códigos de imposto retido na fonte**.
2. Selecione **Novo**.
3. No campo **Código de imposto retido na fonte**, digite um valor.
4. No campo **Nome de imposto retido na fonte**, insira o nome do código de imposto retido na fonte.
5. No campo **Conta principal**, selecione a conta principal para lançamento da obrigação da retenção de imposto retido na fonte.
6. Selecione **Salvar**.
7. Selecione **Valores** e marque o registro desejado na lista.
8. No campo **Valor**, insira uma porcentagem usada para o cálculo do imposto retido na fonte.
9. Selecione **Salvar**.
10. Feche a página.
11. Selecione **Salvar**.
12. Feche a página.
13. Acesse **Painel de navegação > Módulos > Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte**.
14. Selecione **Novo**.
15. No campo **Grupo de impostos retidos na fonte**, insira o identificador do grupo de impostos retidos na fonte.
16. No campo **Descrição**, insira o nome do grupo de impostos retidos na fonte.
17. No campo **Código de imposto retido na fonte**, selecione o código do imposto retido na fonte.
18. Selecione **Salvar**.
19. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]