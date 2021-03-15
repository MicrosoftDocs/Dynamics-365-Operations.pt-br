---
title: Criar e processar uma conformidade
description: Este tópico explica como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008045"
---
# <a name="create-and-process-a-conformance"></a>Criar e processar uma conformidade

[!include [banner](../../includes/banner.md)]

Este tópico explica como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente. Você pode executar esse registro na empresa de demonstração USMF e pode usar os valores sugeridos. Normalmente, esse procedimento é realizado por um encarregado de qualidade.  Como um pré-requisito, siga as instruções em [Inspecionar a qualidade das mercadorias](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). Para processar a aprovação de uma não conformidade, o usuário que executa o registro de tarefa deve ter um valor de "Nome" atribuído na página Usuários. Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.


## <a name="select-a-quality-order"></a>Selecione uma ordem de qualidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade**.
2. Na lista, selecione a ordem de qualidade criada em [Inspecionar a qualidade das mercadorias](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Criar uma não conformidade
1. No Painel de Ações, selecione **Consultas**.
2. Selecione **Não conformidades**.
3. Selecione **Novo**.
4. No menu suspenso do campo **Tipo de problema**, selecione o problema encontrado durante o processo de inspeção.  
5. Selecione **OK**.

## <a name="approvereject-a-nonconformance"></a>Aprovar/rejeitar uma não conformidade
1. Selecione **Funções**.
2. Selecione **Aprovar não conformidade**. Para esse exemplo, aprove a não conformidade. Não conformidades aprovadas podem ser associadas às operações relacionadas para registrar o trabalho que é feito como parte do manuseio da não conformidade e, como neste tópico, o processamento do manuseio de correção.  
3. Selecione **Sim**.

## <a name="create-a-correction-action"></a>Criar uma ação de correção
1. Selecione **Correções**.
2. Selecione **Novo**.
3. No campo **Número da equipe** da nova linha, selecione o registro desejado no menu suspenso.
4. Clique em **Selecionar**.
5. Selecione **Anexar**. Crie uma nota sobre a correção. Neste exemplo, a ação é entrar em contato com o fornecedor para discutir o caso não conformidade.  
6. Selecione **Novo**.
7. Selecione **Nota**. Dependendo da configuração do relatório, diferentes tipos de documentos podem ser impressos em relatórios relacionados ao gerenciamento de não conformidades.  
8. No campo **Descrição**, digite um valor.
9. Feche a página.

## <a name="maintain-a-correction"></a>Manter uma correção
1. Selecione **Marcar como concluída**.
2. Selecione **OK**.
3. Feche a página.

## <a name="close-a-nonconformance"></a>Fechar uma não conformidade
1. Selecione **Funções**.
2. Selecione **Fechar não conformidade**.
3. Selecione **Sim**.
4. Feche as páginas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]