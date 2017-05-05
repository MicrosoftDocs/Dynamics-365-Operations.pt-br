---
title: "Catálogos de endereços"
description: 
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 444ffcc8a14650085e24d0ea0d7f725e9d324d69
ms.lasthandoff: 03/31/2017


---

# <a name="address-books"></a>Catálogos de endereços

[!include[banner](../includes/banner.md)]




<a name="how-do-i-check-for-duplicate-records"></a>Como procurar por registros duplicados?
-------------------------------------

Você pode verificar registros duplicados diretamente na página de listagem **Catálogo de endereços global**. No Painel de Ação, na guia **Participante**, no grupo **Manter**, clique em **Procurar por duplicatas**. Em seguida, selecione os valores a serem incluídos a busca por duplicatas.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>Posso adicionar ou excluir registros de participante em massa a partir de um catálogo de endereços?
Sim, você pode adicionar vários registros de participante em um catálogo de endereços e também remover vários registros de participante.

-   Para adicionar vários registros de participante a um catálogo de endereços, na página de listagem **Catálogo de endereços global **, selecione os participantes na lista. Em seguida, no Painel de Ação, na guia **Participante **, no grupo **Manter **, clique em **Atribuir participantes**. Selecione os catálogos de endereços aos quais adicionar os registros de participantes selecionados e clique em **OK**. Todos os registros de participantes selecionados são adicionados aos catálogos de endereços selecionados.
-   Para remover vários registros de participante de um catálogo de endereços, na página de listagem **Catálogo de endereços global **, selecione os participantes na lista. Em seguida, no Painel de Ação, na guia **Participante **, no grupo **Manter **, clique em **Remover participantes**. Selecione os catálogos de endereços dos quais deseja remover os participantes e clique em **OK**. Todos os registros de participantes selecionados são removidos dos catálogos de endereços selecionados.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Posso alterar o tipo de participante de um registro, ou preciso excluir o registro antigo e criar um novo?
Ocasionalmente, pode ser necessário alterar o tipo de participante de um registro de pessoa para organização ou de organização para pessoa. Por exemplo, Nancy é parte da equipe de vendas da Fabrikam U.K. Em uma feira profissional em Londres, ela encontra seis novos clientes potenciais. Nancy cria um registro de cliente potencial participante para cada um deles. Quando Nancy salva os registros, cada registro é criado também no catálogo de endereços global. A Fabrikam definiu o tipo padrão de participante como organização, mas dois dos novos clientes potenciais devem ter um tipo de registro de pessoa. Portanto, quando Nancy retornar de feira profissional, deverá alterar o tipo de participante dos dois registros de clientes potenciais. Para alterar um registro de participante de um tipo para outro, primeiro você deve criar um novo registro de participante do tipo correto no catálogo de endereços global. Associe o registro de participante antigo a esse novo registro. Depois de fazer a nova associação de participante, exclua o registro de participante original que tem o tipo de registro incorreto.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Como alterar o nome ou o endereço de um registro de participante?
Você pode atualizar o nome de um registro de participante e os endereços associados ao registro a qualquer momento.

-   Para atualizar o nome de um registro de participante, abra o registro de participante e, em seguida, no Painel de Ação, clique em **Editar**. Na Guia Rápida **Geral**, insira o novo nome do participante e, em seguida, salve o registro.
-   Para atualizar um endereço de um registro de participante, abra o registro de participante e, em seguida, na Guia Rápida **Endereços**, selecione o endereço a ser atualizado. Clique em **Editar** e, em seguida, na página **Editar endereço**, faça as alterações necessárias no endereço ou parâmetros do endereço.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Posso mesclar dois ou mais registros de participante em um registro?
Às vezes, você pode querer mesclar dois ou mais registros de participante em um único registro. Isso poderá ocorrer se você criar um ou mais registros de participante duplicados, proposital ou acidentalmente. Ao mesclar registros de participante, selecione um registro a ser mantido As informações dos outros registros serão mescladas neste registro. Por exemplo, você descobre que as informações sobre a Fabrikam estão armazenadas em três registros de participante, denominados A, B e C. Você decide manter o registro de participante A. Sendo assim, as informações armazenadas nos registros B e C serão mescladas no registro A. Há algumas situações onde você não pode mesclar os registros de participante:

-   Não é possível mesclar os registros associados à mesma função de participante, como um cliente ou um fornecedor, na mesma entidade legal. Por exemplo, o participante A está associado a um cliente na entidade legal 123, e o participante B está associado com um cliente diferente na entidade legal 123. Esses registros de participante não podem ser unidos, porque se eles forem unidos, o registro de participante unido seria associado a clientes múltiplos na mesma entidade legal, e isso não é permitido. No entanto, os registros poderão ser mesclados se o participante B for associado a um fornecedor na entidade legal 123 ou a um cliente em outra entidade legal.
-   Não é possível mesclar registros de organização de participante internos na mesma entidade legal ou unidade operacional.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>Devo que criar um registro de participante no catálogo de endereços global ou em outro local, como na página de cliente ou fornecedor?
Você pode inserir registros de participante no catálogo de endereços global ou na página da entidade apropriada. Ao adicionar um registro em uma localização, o mesmo registro será adicionado sempre em outro local. Por exemplo, se você adicionar um registro de participante para um cliente no catálogo de endereços global, o registro também será adicionado na página **Cliente**. Da mesma forma, se você adicionar um registro de participante para um cliente na página **Cliente**, o registro também será adicionado no catálogo de endereços global. Use as seguintes diretrizes para decidir onde você deve inserir os novos registros de participante:

-   **Criando um registro de participante quando não souber o tipo de entidade** – Se você precisar criar um registro de participante, mas não souber o tipo de entidade (por exemplo, você não sabe se a entidade é um cliente ou uma oportunidade), crie o registro no catálogo de endereços global. Você pode selecionar o tipo de entidade posteriormente.
-   **Criando um registro de participante quando souber o tipo de entidade** – Se você sabe o tipo de entidade do participante, crie um registro na página aplicável para esse tipo. Por exemplo, crie um registro para um cliente na página **Cliente**. Quando você cria e salva um registro usando a página da entidade apropriada, o registro é criado automaticamente no catálogo de endereços global.

## <a name="can-i-translate-address-information-for-party-records"></a>Posso traduzir as informações de endereço para os registros de participante?
Você pode configurar traduções de informações de endereço para que as informações apareçam em seu idioma de usuário (idioma do sistema) no Microsoft Dynamics 365 for Operations, mas em outro idioma em documentos como, por exemplo, ordens de venda. Você pode inserir traduções para nomes de países/regiões, endereços e sequências de nomes. Por exemplo, o idioma do sistema é dinamarquês e você cria uma ordem de venda para um cliente na França. Nesse caso, você pode exibir o registro de cliente em dinamarquês no programa, e exibir as informações de endereço em francês na ordem de venda impressa. Ao configurar as traduções, você deve inserir uma tradução para cada item na lista. Os itens para os quais você não inserir uma tradução aparecerão no idioma do sistema. Por exemplo, o idioma do sistema é dinamarquês e você envia um documento para um cliente na Espanha. Se você não inseriu traduções de espanhol (ESP) para informações de endereço, elas serão exibidas em dinamarquês no seu sistema e no documento impresso.



