---
title: Verificar a qualidade de mercadorias
description: Este tópico descreve como processar ordens de qualidade.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956125"
---
# <a name="inspect-the-quality-of-goods"></a>Verificar a qualidade de mercadorias

[!include [banner](../../includes/banner.md)]

Este tópico descreve como processar ordens de qualidade. As inspeções de qualidade costumam ser realizadas por um vendedor de qualidade.

Se os dados de demonstração padrão forem instalados, você poderá usá-los para concluir os procedimentos deste tópico. Para usar os dados de demonstração, selecione a entidade legal *USMF* antes de começar. Você deve confirmar a ordem de compra *000016* e lançar um recebimento de produto. Uma ordem de qualidade é gerada automaticamente.

## <a name="step-1-select-a-quality-order"></a>Etapa 1: Selecione uma ordem de qualidade

Para selecionar uma ordem de qualidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione a ordem de qualidade que foi gerada antes do início deste procedimento.

## <a name="step-2-record-test-results"></a>Etapa 2: Registrar resultados do teste

Para registrar resultados do teste, siga estas etapas.

1. Selecione **Resultados**.
1. Selecione **Editar**.
1. No campo **Quantidade do resultado**, insira um número.
1. No campo **Resultado**, selecione o registro desejado. Neste exemplo, o resultado é baseado em um resultado predefinido. Em geral, você registrará um resultado de teste mais específico, como um tamanho ou outra dimensão.
1. Selecione **Salvar**.
1. Feche a página.

## <a name="step-3-validate-the-quality-order"></a>Etapa 3: Validar a ordem de qualidade

Para validar a ordem de qualidade, siga estas etapas.

1. Selecione **Validar**.
1. No campo **Validado por**, selecione o usuário que está fazendo a inspeção.
1. Escolha **Selecionar**.
1. Selecione **OK**.
1. Feche a página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
