---
title: Amostragem de item de gerenciamento de qualidade
description: Este artigo descreve como configurar a amostragem de item.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 644eae4fbd9f82027c1cb69efba00dc893f8fc66
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865140"
---
# <a name="quality-management-item-sampling"></a>Amostragem de item de gerenciamento de qualidade

[!include [banner](../includes/banner.md)]

A amostragem de item é usada como parte de uma associação de qualidade. Ela define a quantidade de estoque físico atual que deve ser inspecionada. A amostragem pode se basear em quantidades fixas, em uma porcentagem ou em uma placa de licença completa.

## <a name="set-up-item-sampling"></a>Configurar amostragem de item

Siga estas etapas para configurar a amostragem de item.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Amostragem de item**.
1. Selecione **Novo**.
1. No campo **Amostragem de item**, insira um valor.
1. No campo **Descrição**, insira um valor.
1. No campo **Valor**, insira um número. Esse valor é relacionado ao valor de especificação de quantidade selecionado no campo adjacente.
1. Na seção **Processar**, marque a caixa de seleção **Bloqueio total** para a quantidade de linhas da ordem ou do lote inteiro ser bloqueada se um teste falhar. Se essa caixa de seleção estiver desmarcada, somente os itens na ordem de qualidade serão bloqueados se um teste falhar.
1. Selecione **Salvar**.
1. Feche a página.

> [!NOTE]
> *Gestão de qualidade para processos de depósito* fornece recursos adicionais de amostragem de itens. Ele adiciona o conceito de *escopo de amostragem de item* e permite definir uma placa de licença completa como especificação de quantidade. Se você ativou esse recurso, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
