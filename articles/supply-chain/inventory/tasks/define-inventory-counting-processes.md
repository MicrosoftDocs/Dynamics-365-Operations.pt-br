---
title: Definir processos de contagem de estoque
description: Este tópico descreve a configuração dos processos de contagem básicos de estoque criando um grupo de contagem e um diário de contagem.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4f83ae0e33520f1777cea31e2f986af1691bfa1
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145539"
---
# <a name="define-inventory-counting-processes"></a>Definir processos de contagem de estoque

[!include [banner](../../includes/banner.md)]

Este tópico descreve a configuração dos processos de contagem básicos de estoque criando um grupo de contagem e um diário de contagem. Ele também mostra como habilitar diretivas de contagem em um nível de depósito e do item. Essas tarefas normalmente seriam realizadas por um supervisor do depósito. É um pré-requisito para alguns produtos liberados e depósitos existentes. Se você for utilizar uma empresa de dados demonstrativos, você pode executar esse procedimento na empresa USMF com qualquer item em estoque.


## <a name="create-a-counting-group"></a>Crie um grupo de contagem
1. No Painel de Navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Estoque > Grupos de contagem**.
2. Selecione **Novo**.
3. No campo **Grupo de contagem** da nova linha, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Código de contagem**, selecione uma opção.

    - **Manual** – inclui linhas toda vez que você executa o trabalho. Em outras palavras, você escolhe o intervalo de contabilização do grupo de contabilização.  
    - **Período** - Inclui linhas para o período no diário de contagem depois que o intervalo de períodos expira.  
    - **Zero no estoque** - Se o estoque disponível chegar a zero (0), linhas serão geradas no diário de contagem quando o trabalho for executado. Se o estoque disponível chegar a 0 após uma contabilização, linhas serão geradas na próxima vez que você iniciar a contabilização.  
    - **Mínimo** – insere linhas no diário de contagem se o estoque disponível é igual ou menor que o mínimo especificado.  
    - Opcional: Se tiver especificado o **Período** no campo **Código de contagem**, você deverá digitar nesse campo o intervalo do período no **Período de contagem**. A unidade dos intervalos é dias.  
    - Quando você executa o trabalho para criar novas linhas do diário de contagem, as novas linhas são criadas no intervalo especificado neste campo, independentemente da frequência na qual você executa o mesmo trabalho. Por exemplo, se o **Período de contagem** for definido como 7, e as linhas do diário forem geradas por último para uma contagem em 1º de janeiro, se outro trabalho for iniciado em 5 de janeiro, não se passaram sete dias e assim nenhuma linha é gerada no diário do intervalo do período. Se você recomeçar o trabalho no dia 8 de janeiro, linhas serão geradas para o período no diário de contagem, pois já se passaram 7 dias.  

6. Selecione **Salvar**.

## <a name="create-a-counting-journal-name"></a>Criar um nome de diário de contabilidade
1. No Painel de Navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Nomes de diário > Estoque**.
2. Selecione **Novo**.
3. No campo **Nome**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Tipo de diário**, selecione **Contagem**. Opcional: você pode selecionar uma ID de série de comprovante diferente se desejar que uma sequência numérica específica das IDs do comprovante gerados ao criar diários de contagem. A série de comprovantes é criada na página **Sequências numéricas**.  
6. No campo **Nível de detalhe**, selecione uma opção.  

    - Este é o nível de detalhe que é aplicado quando o diário é lançado.  
    - Opcional: É possível exibir ou alterar o valor no campo Reserva. Este é o método usado para reservar itens durante a contagem.   
    - **Manual** – os itens são reservados manualmente no formulário Reserva.  
    - **Automático** - A quantidade da ordem é reservada a partir do disponível, estoque disponível para o item.   
    - **Detalhamento** – a reserva é parte do planejamento mestre da transação.  

7. Selecione **Salvar**.

## <a name="set-standard-counting-journal-name"></a>Defina o nome de diário padrão de contagem
1. No Painel de Navegação, vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque**.
2. Selecione a guia **Diários**.
3. No menu suspenso do campo **Contagem**, selecione o diário que você criou anteriormente. Este diário será o diário padrão para diários de estoque do tipo **Contagem**.  
4. Selecione a guia **Geral**. Opcional: Selecione esta opção para bloquear um item durante o processo de contagem para evitar atualizações para guias de remessa, listas de separação, ou registros de lista de separação.  

## <a name="set-the-counting-policy-for-an-item"></a>Configure a política de contabilidade para um item
1. No Painel de Navegação, vá para **Módulos > Gerenciamento de informações sobre produtos > Produtos > Produtos liberados**.
2. Na lista, selecione o link no número de item dos produtos que você deseja definir sobre diretivas de contagem. Você precisa selecionar um item que é rastreado por estoque. Um produto não estocado não pode ser contabilizado. Se você estiver usando dados de demonstração de USMF você pode selecionar o item A0001.  
3. Selecione **Editar**.
4. Alternar a expansão da seção **Gerenciar estoque**.
5. No menu suspenso do campo **Grupo de contagem**, selecione o grupo de contagem que você criou anteriormente. Agora esse produto será incluído quando as linhas do diário de contagem de estoque forem criadas usando este grupo de contagem.  
6. Selecione **Salvar**.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Definir a diretiva de um item em um depósito específico
1. No Painel de Ação, selecione **Gerenciar estoque**.
2. Selecione **Itens de depósito**.
3. Selecione **Novo**.
4. No menu suspenso do campo **Depósito**, selecione o armazém para o qual você deseja configurar políticas de contagem específicas.
5. No menu suspenso do campo **Grupo de contagem**, selecione um grupo de contagem. Você pode selecionar um grupo específico de contagem que será aplicado ao item no depósito específico selecionado. Quando a contagem é feita naquele depósito, essa diretiva de contagem substituirá a diretiva geral do item.  
6. Selecione **Salvar**.

