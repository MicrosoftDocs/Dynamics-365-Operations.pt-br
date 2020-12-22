---
title: Copiar clientes usando sequências numéricas compartilhadas
description: Este tópico explica como usar sequências numéricas compartilhadas para copiar um cliente para outra entidade legal mantendo a mesma ID.
author: mikefalkner
manager: aolson
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 91f7568ea8364f97de7e514fb207191ee00041a5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4458417"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Copiar clientes usando sequências numéricas compartilhadas

[!include [banner](../includes/banner.md)]

Você pode usar sequências numéricas compartilhadas para atribuir IDs de cliente. As sequências numéricas compartilhadas também permitem copiar clientes de uma entidade legal para outra mantendo as mesmas IDs em ambas.

## <a name="setup"></a>Configurar

O recurso é ativado quando você usa uma sequência numérica compartilhada para atribuir IDs de cliente. Você deve usar a mesma sequência numérica em cada entidade legal para a qual deseja copiar um cliente. É possível alterar a sequência numérica do cliente na página **Parâmetros de contas a receber** para cada entidade legal. Escolha **Contas a receber** \> **Parâmetros** e depois a guia **Sequências numéricas**.

Você também pode configurar sequências numéricas de cliente para cada grupo de clientes. Essas sequências numéricas também devem ser compartilhadas. A sequência numérica é usada primeiro para um grupo de clientes. Se nenhuma sequência numérica for especificada para um grupo de clientes, será usada a sequência especificada na página **Parâmetros de contas a receber**.

Você também pode copiar clientes entre entidades legais se usar as IDs manuais. Entretanto, se você tentar copiar um cliente para uma entidade legal em que a ID já existe, o processo de cópia não será iniciado.

## <a name="copy-a-customer"></a>Copiar um cliente

Para copiar um cliente, escolha **Novo** na página **Todos os clientes**. Depois, será aberta a caixa de diálogo **Criar cliente**. Observe que a nova ID de cliente não é atribuída imediatamente. Esse comportamento difere do comportamento de versões anteriores. Como você ainda não escolheu o grupo de clientes, o sistema não pode determinar a sequência numérica correta a ser usada. Além disso, ele não consegue determinar se você está tentando criar um cliente ou copiar um já existente. Portanto, a ID de cliente não é atribuída até que você escolha **Salvar** na parte inferior da caixa de diálogo.

Se você estiver criando um cliente, continue preenchendo todos os campos da forma usual. Depois que terminar e **Salvar**, você verá que a ID de cliente foi atribuída automaticamente. No caso das sequências numéricas manuais, você verá que a ID manual do cliente foi usada.

Para copiar um cliente, insira no campo **Nome** um ou mais caracteres que representam o cliente que você está procurando. Uma caixa de diálogo de pesquisa mostra uma lista de participantes que podem ser o cliente que você procura. Quando você selecionar um dos participantes, informações adicionais aparecerão no lado direito da caixa de diálogo:

- A guia **Geral** mostra o número de telefone e o endereço do participante.
- A guia **Funções** mostra as funções que o participante selecionado pode ter e as entidades legais correspondentes a cada uma delas.
- A guia **ID do registro de imposto** mostra as IDs de registros de imposto atribuídas ao participante.

Você pode copiar um participante somente se ele tiver uma função de cliente e se tiver essa função em outra entidade legal que não a atual. Quando você encontrar um participante que atenda a esses critérios, realize as etapas a seguir.

1. A opção **Copiar cliente** é exibida. Por padrão, essa opção é definida como **Não**. Para copiar o cliente para a entidade legal atual, defina-a como **Sim**. 
2. O campo **Entidade legal** é exibido. Selecione a entidade legal da qual o cliente será copiado. Se o cliente existir apenas em uma entidade legal, o campo estará definido como a entidade legal correspondente por padrão.
3. Escolha **Selecionar**. O cliente foi criado.

## <a name="validation"></a>Validação

Ao copiar um cliente, o sistema tenta salvar as novas informações dele. São executadas validações para verificar se os dados que foram copiados estão corretos. Você receberá uma mensagem de erro para que cada validação com falha. As mensagens de erro mostram quais informações devem ser atualizadas. A cópia do cliente não pode ser salva até que você corrija os erros de validação.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Copiar um cliente usando o recurso de pesquisa do número de isenção de imposto

Você também pode copiar clientes usando o recurso de pesquisa do número de isenção de imposto, que é encontrado no grupo **Registro** da guia **Cliente**, no Painel de Ações da página **Todos os clientes**. A caixa de diálogo **Pesquisa de número de isenção de imposto** exibida mostra os números de isenção de imposto, a ID e o nome do cliente, e a entidade legal em que a ID de isenção de imposto é usada. Você pode copiar um cliente somente se ele estiver em uma entidade legal que não a atual. Após selecionar um cliente que atende a esse critério, realize as etapas a seguir.

1. A opção **Copiar cliente** é exibida. Por padrão, essa opção é definida como **Não**. Para copiar o cliente para a entidade legal atual, defina-a como **Sim**. 
2. Escolha **Selecionar**. O cliente foi criado.
