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
ms.openlocfilehash: ceb5547b6c1d4c44e53faba0d6e2c1f0368fb95768a2520ecc39066ff73a03d2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755346"
---
# <a name="inspect-the-quality-of-goods"></a>Verificar a qualidade de mercadorias

[!include [banner](../../includes/banner.md)]

Este tópico descreve como processar ordens de qualidade. As inspeções de qualidade costumam ser realizadas por um vendedor de qualidade.

Se os dados de demonstração padrão forem instalados, você poderá usá-los para concluir os procedimentos deste tópico. Para usar os dados de demonstração, selecione a entidade legal *USMF* antes de começar. Você deve confirmar a ordem de compra *000016* e lançar um recebimento de produto. Uma ordem de qualidade é gerada automaticamente.

## <a name="step-1-select-a-quality-order"></a>Etapa 1: Selecione uma ordem de qualidade

Para selecionar uma ordem de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
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
