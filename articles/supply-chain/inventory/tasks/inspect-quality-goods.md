---
title: Verificar a qualidade de mercadorias
description: Este procedimento mostra como processar a ordem de qualidade.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e9d750f116db62519ac7148f19bf62050430e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315420"
---
# <a name="inspect-the-quality-of-goods"></a>Verificar a qualidade de mercadorias

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como processar a ordem de qualidade. Você pode executar este guia na empresa USMF de dados de demonstração. Antes de iniciar este procedimento de exemplo, você precisa confirmar a ordem de compra '000016'e lançar um recebimento de produtos. Isso criará automaticamente uma ordem de qualidade. As inspeções de qualidade são realizadas tipicamente por um vendedor de qualidade.


## <a name="select-a-quality-order"></a>Selecione uma ordem de qualidade
1. Vá para Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade.
2. Na lista, marque a linha selecionada.
    * Selecione a ordem de qualidade que foi criada antes do início deste procedimento.  

## <a name="record-test-results"></a>Registrar resultados do teste
1. Clique em Resultados.
2. Clique em Editar.
3. No campo Quantidade de resultado, insira um número.
4. Na lista, marque a linha selecionada.
5. No campo Resultado, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
    * Neste exemplo o resultado é baseado em um resultado predefinido. Normalmente você registraria um resultado de teste mais específico por exemplo, um tamanho ou outra dimensão.  
7. Na lista, clique no link na linha selecionada.
8. Clique em Salvar.
9. Feche a página.

## <a name="validate-the-quality-order"></a>Validar a ordem de qualidade
1. Clique em Validar.
2. No campo Validado por, clique no botão suspenso para abrir a pesquisa.
    * Selecione o usuário realizando a inspeção.  
3. Na lista, clique no link na linha selecionada.
4. Clique em Selecionar.
5. Clique em OK.
6. Feche a página.

