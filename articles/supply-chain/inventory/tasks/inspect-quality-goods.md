---
title: Verificar a qualidade de mercadorias
description: Este tópico explica como processar uma ordem de qualidade.
author: perlynne
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10acb9aadfeb11ede1d66dd525ace7b70db3bd1c
ms.sourcegitcommit: fbaccf72df82e6b6927f0c9f0d35af0ca3ecbc2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1855677"
---
# <a name="inspect-the-quality-of-goods"></a>Verificar a qualidade de mercadorias

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como processar uma ordem de qualidade. Você pode executar este guia na empresa USMF de dados de demonstração. Antes de iniciar este procedimento de exemplo, você precisa confirmar a ordem de compra '000016'e lançar um recebimento de produtos. Isso criará automaticamente uma ordem de qualidade. As inspeções de qualidade são realizadas tipicamente por um vendedor de qualidade.


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

