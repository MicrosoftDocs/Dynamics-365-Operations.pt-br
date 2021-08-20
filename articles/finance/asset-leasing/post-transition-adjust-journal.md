---
title: Lançar entradas de diário de ajuste de transição em Arrendamento de ativo
description: Este tópico descreve a funcionalidade que permite a transição de um portfólio de arrendamento para os novos padrões contábeis de arrendamento, os padrões contábeis Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b764902e2e7178548c17901b310f0798ff6fcfd5455e8071d716e165409a6f9f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775905"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Lançar entradas de diário de ajuste de transição em Arrendamento de ativo

[!include [banner](../includes/banner.md)]

Este tópico descreve a funcionalidade que permite a transição de um portfólio de arrendamento para os novos padrões de contabilização de arrendamento: Tópico 842 da Codificação de Padrões Contábeis (ASC 842), que é o padrão nos Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP), e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).

Para obter informações sobre como configurar um registro para a transição para os novos padrões, consulte [Configurar registros de arrendamento](set-up-lease-books.md).

Quando você cria uma entrada de diário de ajuste de transição, uma entrada de diário é gerada. Essa entrada reflete o impacto da folha de equilíbrio do registro do arrendamento sob os novos padrões nessa data. A conta de ativo apropriada é debitada no valor de transporte dessa data e a conta de passivo é creditada. A diferença é debitada ou creditada nos ganhos retidos.

Para lançar um ajuste de transição em conformidade com os novos padrões contábeis, siga estas etapas.

1. Na página **Resumo do arrendamento**, selecione o arrendamento e selecione **Registros**.
2. No registro, selecione **Agenda de pagamento**.
3. Na caixa de diálogo **Agenda de pagamento**, selecione **Confirmar**. Em seguida, feche a caixa de diálogo.
4. Selecione **Ajuste de transição**.

    > [!NOTE]
    > Um ajuste de transição pode ser criado somente para os catálogos de arrendamento atribuídos a um registro no qual o campo **Registro de transições** está disponível. Se o valor no campo **Início do arrendamento** for posterior à data de transição, o valor no campo **Ajuste de transição** não será atualizado.

5. Para exibir a entrada de diário, selecione **Diários de arrendamento de ativo**.
6. Selecione o novo diário e depois **Lançar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]