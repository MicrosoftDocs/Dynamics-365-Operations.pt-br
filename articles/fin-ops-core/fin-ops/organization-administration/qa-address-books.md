---
title: Perguntas frequentes sobre catálogos de endereços
description: Este tópico fornece respostas a perguntas frequentes sobre catálogos de endereços.
author: msftbrking
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2f81b6c3ab60f5e0e852d2bc0ae44e6595a90c1
ms.sourcegitcommit: 05868764acd3d77970724a30c49c5ae5ffb6ca5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906664"
---
# <a name="address-books-faq"></a>Perguntas frequentes sobre catálogos de endereços

[!include [banner](../includes/banner.md)]

## <a name="how-do-i-check-for-duplicate-records"></a>Como procurar por registros duplicados?

Você pode verificar registros duplicados diretamente na página de listagem **Catálogo de endereços global**. No Painel de Ação, na guia **Participante**, no grupo **Manter**, clique em **Procurar por duplicatas**. Em seguida, selecione os valores a serem incluídos a busca por duplicatas.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>Posso adicionar ou excluir registros de participante em massa a partir de um catálogo de endereços?

Sim, você pode adicionar vários registros de participante em um catálogo de endereços e também remover vários registros de participante.

- Para adicionar vários registros de participante a um catálogo de endereços, na página de listagem **Catálogo de endereços global**, selecione os participantes na lista. Em seguida, no Painel de Ação, na guia **Participante**, no grupo **Manter**, clique em **Atribuir participantes**. Selecione os catálogos de endereços aos quais adicionar os registros de participantes selecionados e clique em **OK**. Todos os registros de participantes selecionados são adicionados aos catálogos de endereços selecionados.
- Para remover vários registros de participante de um catálogo de endereços, na página de listagem **Catálogo de endereços global**, selecione os participantes na lista. Em seguida, no Painel de Ação, na guia **Participante**, no grupo **Manter**, clique em **Remover participantes**. Selecione os catálogos de endereços dos quais deseja remover os participantes e clique em **OK**. Todos os registros de participantes selecionados são removidos dos catálogos de endereços selecionados.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Posso alterar o tipo de participante de um registro, ou preciso excluir o registro antigo e criar um novo?

Ocasionalmente, pode ser necessário alterar o tipo de participante de um registro de pessoa para organização ou de organização para pessoa. Por exemplo, Nancy é parte da equipe de vendas da Fabrikam U.K. Em uma feira profissional em Londres, ela encontra seis novos clientes potenciais. Nancy cria um registro de cliente potencial participante para cada um deles. Quando Nancy salva os registros, cada registro é criado também no catálogo de endereços global. A Fabrikam definiu o tipo padrão de participante como organização, mas dois dos novos clientes potenciais devem ter um tipo de registro de pessoa. Portanto, quando Nancy retornar de feira profissional, deverá alterar o tipo de participante dos dois registros de clientes potenciais. Para alterar um registro de participante de um tipo para outro, primeiro você deve criar um novo registro de participante do tipo correto no catálogo de endereços global. Associe o registro de participante antigo a esse novo registro. Depois de fazer a nova associação de participante, exclua o registro de participante original que tem o tipo de registro incorreto.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Como alterar o nome ou o endereço de um registro de participante?

Você pode atualizar o nome de um registro de participante e os endereços associados ao registro a qualquer momento.

- Para atualizar o nome de um registro de participante, abra o registro de participante e, em seguida, no Painel de Ação, clique em **Editar**. Na Guia Rápida **Geral**, insira o novo nome do participante e, em seguida, salve o registro.
- Para atualizar um endereço de um registro de participante, abra o registro de participante e, em seguida, na Guia Rápida **Endereços**, selecione o endereço a ser atualizado. Clique em **Editar** e, em seguida, na página **Editar endereço**, faça as alterações necessárias no endereço ou parâmetros do endereço.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Posso mesclar dois ou mais registros de participante em um registro?

Às vezes, você pode querer mesclar dois ou mais registros de participante em um único registro. Isso poderá ocorrer se você criar um ou mais registros de participante duplicados, proposital ou acidentalmente. Ao mesclar registros de participante, selecione um registro a ser mantido As informações dos outros registros serão mescladas neste registro. Por exemplo, você descobre que as informações sobre a Fabrikam estão armazenadas em três registros de participante, denominados A, B e C. Você decide manter o registro de participante A. Sendo assim, as informações armazenadas nos registros B e C serão mescladas no registro A. Há algumas situações onde você não pode mesclar os registros de participante:

- Não é possível mesclar os registros de participante associados à mesma função de participante, como um cliente ou fornecedor, na mesma entidade legal. Por exemplo, o participante A está associado a um cliente na entidade legal 123, e o participante B está associado com um cliente diferente na entidade legal 123. Esses registros de participante não podem ser mesclados pois, se eles fossem mesclados, o registro de participante mesclado seria associado a vários clientes na mesma entidade legal e isso não é permitido. No entanto, os registros poderão ser mesclados se o participante B for associado a um fornecedor na entidade legal 123 ou a um cliente em outra entidade legal.
- Não é possível mesclar registros de organização de participantes internos na mesma entidade legal, equipe ou unidade operacional.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>Devo que criar um registro de participante no catálogo de endereços global ou em outro local, como na página de cliente ou fornecedor?

Você pode inserir registros de participante no catálogo de endereços global ou na página da entidade apropriada. Ao adicionar um registro em uma localização, o mesmo registro será adicionado sempre em outro local. Por exemplo, se você adicionar um registro de participante para um cliente no catálogo de endereços global, o registro também será adicionado na página **Cliente**. Da mesma forma, se você adicionar um registro de participante para um cliente na página **Cliente**, o registro também será adicionado no catálogo de endereços global. Use as seguintes diretrizes para decidir onde você deve inserir os novos registros de participante:

- **Criando um registro de participante quando não souber o tipo de entidade** – Se você precisar criar um registro de participante, mas não souber o tipo de entidade (por exemplo, você não sabe se a entidade é um cliente ou uma oportunidade), crie o registro no catálogo de endereços global. Você pode selecionar o tipo de entidade posteriormente.
- **Criando um registro de participante quando souber o tipo de entidade** – Se você sabe o tipo de entidade do participante, crie um registro na página aplicável para esse tipo. Por exemplo, crie um registro para um cliente na página **Cliente**. Quando você cria e salva um registro usando a página da entidade apropriada, o registro é criado automaticamente no catálogo de endereços global.

## <a name="can-i-translate-address-information-for-party-records"></a>Posso traduzir as informações de endereço para os registros de participante?

Você pode configurar traduções de informações de endereço para que as informações apareçam em seu idioma de usuário (idioma do sistema) no programa, mas em outro idioma em documentos, como ordens de venda. Você pode inserir traduções para nomes de países/regiões, endereços e sequências de nomes. Por exemplo, o idioma do sistema é dinamarquês e você cria uma ordem de venda para um cliente na França. Nesse caso, você pode exibir o registro de cliente em dinamarquês no programa, e exibir as informações de endereço em francês na ordem de venda impressa. Ao configurar as traduções, você deve inserir uma tradução para cada item na lista. Os itens para os quais você não inserir uma tradução aparecerão no idioma do sistema. Por exemplo, o idioma do sistema é dinamarquês e você envia um documento para um cliente na Espanha. Se você não inseriu traduções de espanhol (ESP) para informações de endereço, elas serão exibidas em dinamarquês no seu sistema e no documento impresso.

## <a name="after-importing-addresses-when-i-access-the-records-why-am-i-unable-to-edit-imported-addresses"></a>Depois de importar os endereços, quando acesso os registros, por que não consigo editar os endereços importados?

Ao importar endereços, há um campo denominado **IsLocationOwner**, que indica se o participante associado ao local (endereço) é o proprietário do endereço. Se o participante for o proprietário do endereço, o endereço poderá ser editado quando for acessado usando o participante no catálogo de endereços global ou no formulário do registro mestre (como cliente, fornecedor ou trabalhador). Se o participante não for o proprietário do endereço, o registro não poderá ser editado a partir dos formulários listados anteriormente. Ao importar endereços, **IsLocationOwner** deverá ser definido como **Sim**, se você quiser que o endereço seja editado usando o participante associado. No entanto, há ocasiões em que este campo é importado incorretamente. Para corrigir esse problema, o proprietário do local pode ser atualizado no catálogo de endereços global do registro do participante ou na página **Confirmar os proprietários do local**. Para atualizar um único registro de participante, vá para **Catálogo de Endereços Global > Endereço**. Selecione **Editar** para iniciar a página **Editar endereço** para alterar o proprietário do local. Selecione **Alterar proprietário do local** para ver o proprietário anterior do local com que o participante selecionado está sendo o novo proprietário do local. Se o proprietário anterior do local estiver em branco, isso significa que o proprietário do local não foi estabelecido. Selecionar a opção **Avançado** abrirá a página **Gerenciar endereços** na qual o proprietário do local também pode ser definido. Selecione o local a ser atualizado e selecione **Definir proprietário do local** no menu. Para atualizar o proprietário do local de vários registros, vá para **Catálogo de Endereços Global > Locais > Confirmar proprietários de local**. A lista contém locais que estão vinculados a um único participante, mas esse participante não é o proprietário. Selecionar **Confirmar proprietário** definirá a **ID do participante proprietário proposto** como proprietário do endereço vinculado. Depois que o participante for definido como o proprietário, o endereço vinculado será editável do registro do participante. Para alterar o proprietário do local, você deve receber o privilégio **Definir proprietário do local** na página **Configuração de segurança**.  O administrador do sistema recebe esse privilégio por padrão.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

