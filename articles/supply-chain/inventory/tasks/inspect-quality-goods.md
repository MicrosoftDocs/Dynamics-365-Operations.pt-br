---
title: Verificar a qualidade de mercadorias
description: Este tópico explica como processar uma ordem de qualidade.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e37ac8c9320d427b9f9a3ca32b0e4667c7023339
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244414"
---
# <a name="inspect-the-quality-of-goods"></a>Verificar a qualidade de mercadorias

[!include [banner](../../includes/banner.md)]

Este tópico explica como processar uma ordem de qualidade. Você pode executar este guia na empresa USMF de dados de demonstração. Antes de iniciar este procedimento de exemplo, você precisa confirmar a ordem de compra "000016" e lançar um recebimento de produtos. Isso criará automaticamente uma ordem de qualidade. As inspeções de qualidade são realizadas tipicamente por um vendedor de qualidade.


## <a name="select-a-quality-order"></a>Selecione uma ordem de qualidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade**.
2. Selecione a ordem de qualidade que foi criada antes do início deste procedimento.  

## <a name="record-test-results"></a>Registrar resultados do teste
1. Selecione **Resultados**.
2. Selecione **Editar**.
3. No campo **Quantidade do resultado**, insira um número.
4. No campo **Resultado**, selecione o registro desejado no menu suspenso.  
- Neste exemplo o resultado é baseado em um resultado predefinido. Normalmente você registraria um resultado de teste mais específico por exemplo, um tamanho ou outra dimensão.  
5. Selecione **Salvar**.
6. Feche a página.

## <a name="validate-the-quality-order"></a>Validar a ordem de qualidade
1. Selecione **Validar**.
2. No campo **Validado por**, selecione o usuário que executa a inspeção do menu suspenso.  
3. Clique em **Selecionar**.
4. Selecione **OK**.
5. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]