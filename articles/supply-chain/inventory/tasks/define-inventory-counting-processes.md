--- 
title: Definir processos de contagem de estoque
description: "Este procedimento mostra a configuração dos processos de contagem básicos de estoque criando um grupo de contagem e um diário de contagem."
author: MarkusFogelberg
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c14c846c55a3d821945160835817cd4f467deda9
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-inventory-counting-processes"></a>Definir processos de contagem de estoque

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra a configuração dos processos de contagem básicos de estoque criando um grupo de contagem e um diário de contagem. Ele também mostra como habilitar diretivas de contagem em um nível de depósito e do item. Essas tarefas normalmente seriam realizadas por um supervisor do depósito. É um pré-requisito para alguns produtos liberados e depósitos existentes. Se você for utilizar uma empresa de dados demonstrativos, você pode executar esse procedimento na empresa USMF com qualquer item em estoque.


## <a name="create-a-counting-group"></a>Crie um grupo de contagem
1. Vá para Gerenciamento de estoque > Configuração > Divisão de estoque > Grupos de contabilidade.
2. Clique em Novo.
3. No campo grupo de Contabilidade, digite um valor.
4. No campo Nome, digite um valor.
5. No campo de código de contabilidade, selecione uma opção.
    * Manual – inclui linhas toda vez que você executa o trabalho. Em outras palavras, você escolhe o intervalo de contabilização do grupo de contabilização.  Período - Inclui linhas para o período no diário de contagem depois que o intervalo de períodos expira.   Zero no estoque - Se o estoque disponível chegar a zero (0), linhas serão geradas no diário de contagem quando o trabalho for executado. Se o estoque disponível chegar a 0 após uma contabilização, linhas serão geradas na próxima vez que você iniciar a contabilização.   Mínimo – insere linhas no diário de contagem se o estoque disponível é igual ou menor que o mínimo especificado.  
    * Opcional: Se tiver especificado o Período no campo Código de Contagem, você deverá digitar nesse campo o intervalo do período no Período de contagem. A unidade dos intervalos é dias.  
    * Quando você executa o trabalho para criar novas linhas do diário de contagem, as novas linhas são criadas no intervalo especificado neste campo, independentemente da frequência na qual você executa o mesmo trabalho. Por exemplo, se o Período de contagem for definido para 7, e as linhas do diário forem geradas por último para uma contagem em 1º de janeiro, se outro trabalho for iniciado em 5 de janeiro, não se passaram sete dias e assim nenhuma linha é gerada no diário do intervalo do período. Se você recomeçar o trabalho no dia 8 de janeiro, linhas serão geradas para o período no diário de contagem, pois já se passaram 7 dias.  
6. Clique em Salvar.

## <a name="create-a-counting-journal-name"></a>Criar um nome de diário de contabilidade
1. Vá para Gerenciamento de estoque > Configuração > Nomes de diário > Estoque.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de diário, selecione 'Contabilidade'.
    * Opcional: você pode selecionar uma ID de série de comprovante diferente se desejar que uma sequência numérica específica das IDs do comprovante gerados ao criar diários de contagem. A série de comprovantes é criada na página Sequências numéricas.  
6. No campo Nível de detalhe, selecione uma opção.
    * Este é o nível de detalhe que é aplicado quando o diário é lançado.  
    * Opcional: É possível exibir ou alterar o valor no campo Reserva. Este é o método usado para reservar itens durante a contagem.   
    * Manual – os itens são reservados manualmente no formulário Reserva.   Automático - A quantidade da ordem é reservada a partir do disponível, estoque disponível para o item.   Detalhamento – a reserva é parte do planejamento mestre da transação.  
7. Clique em Salvar.

## <a name="set-standard-counting-journal-name"></a>Defina o nome de diário padrão de contagem
1. Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.
2. Clique na guia Diários.
3. No campo Contabilidade, clique no botão suspenso para abrir a pesquisa.
4. Selecione o diário criado anteriormente.
    * Este diário será o diário padrão para diários de estoque do tipo Contagem.  
5. Clique na guia Geral.
    * Opcional: Selecione esta opção para bloquear um item durante o processo de contagem para evitar atualizações para guias de remessa, listas de separação, ou registros de lista de separação.  

## <a name="set-the-counting-policy-for-an-item"></a>Configure a política de contabilidade para um item
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, clique em no link no número de item dos produtos que você deseja definir sobre diretivas de contagem.
    * Observe que você precisa selecionar um item que é rastreado por estoque. Um produto não estocado não pode ser contabilizado. Se você estiver usando dados de demonstração de USMF você pode selecionar o item A0001.  
3. Clique em Editar.
4. Alternar a expansão da seção Gerenciar estoque.
5. No campo Grupo de contabilidade, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique em no grupo de contagem que você tiver criado anteriormente.
    * Agora esse produto será incluído quando as linhas do diário de contagem de estoque forem criadas usando este grupo de contagem.  
7. Clique em Salvar.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Definir a diretiva de um item em um depósito específico
1. No Painel de Ação, clique em Gerenciar estoque.
2. Clique em item de depósito.
3. Clique em Novo.
4. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
5. Na lista, selecione o depósito para o qual você deseja especificar políticas de contabilidade.
6. No campo Grupo de contabilidade, clique no botão suspenso para abrir a pesquisa.
7. Na lista, selecione um grupo de contabilidade
    * Aqui você pode selecionar um grupo específico de contagem que será aplicado ao item no depósito específico selecionado. Quando a contagem é feita naquele depósito, essa diretiva de contagem substituirá a diretiva geral do item.  
8. Clique em Salvar.


