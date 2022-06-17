---
title: Copiar fornecedores usando sequências numéricas compartilhadas
description: Este artigo explica como usar sequências numéricas compartilhadas para copiar um fornecedor para outra entidade legal mantendo a mesma ID.
author: sunfzam
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 7b7285cdf454955656c4fb20c3abf68f3f9c39dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904891"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Copiar fornecedores usando sequências numéricas compartilhadas

[!include [banner](../includes/banner.md)]

Você pode usar sequências numéricas compartilhadas para atribuir IDs de fornecedor. As sequências numéricas compartilhadas também permitem copiar fornecedores de uma entidade legal para outra mantendo as mesmas IDs em ambas.

## <a name="setup"></a>Configurar

O recurso é ativado quando você usa uma sequência numérica compartilhada para atribuir IDs de fornecedor. Você deve usar a mesma sequência numérica em cada entidade legal para a qual deseja copiar um fornecedor. É possível alterar a sequência numérica do fornecedor na página **Parâmetros de contas a pagar** para cada entidade legal. Escolha **Contas a pagar** \> **Configurar** \> **Parâmetros de contas a pagar** e depois clique na guia **Sequências numéricas**.

Você também pode configurar sequências numéricas de fornecedor para cada grupo de fornecedores. Essas sequências numéricas também devem ser compartilhadas. A sequência numérica é usada primeiro para um grupo de fornecedores. Se nenhuma sequência numérica for especificada para um grupo de fornecedores, será usada a sequência especificada na página **Parâmetros de contas a pagar**.

Você também poderá copiar fornecedores entre entidades legais se usar as IDs manuais. No entanto, se você tentar copiar um fornecedor para uma entidade legal em que a ID já exista, o processo de cópia não será iniciado.

## <a name="copy-a-vendor"></a>Copiar um fornecedor

Para copiar um fornecedor, selecione **Novo** na página da lista **Todos os fornecedores** para abrir a página **Todos os fornecedores, novo registro**. A nova ID de fornecedor não é atribuída imediatamente. Esse comportamento difere do comportamento de versões anteriores. Como você ainda não escolheu o grupo de fornecedores, a sequência numérica correta a ser usada não poderá ser determinada. Além disso, ele não consegue determinar se você está tentando criar um fornecedor ou copiar um já existente. Portanto, a ID de fornecedor não é atribuída até que você escolha **Salvar** na parte inferior da página.

Se você estiver criando um fornecedor, continue preenchendo todos os campos da forma usual. Depois de terminar e selecionar **Salvar**, a ID do fornecedor é atribuída automaticamente. No caso das sequências numéricas manuais, você verá que a ID manual do fornecedor foi usada.

Para copiar um fornecedor, insira no campo **Nome** um ou mais caracteres que representam o fornecedor que você está procurando. Uma caixa de diálogo de pesquisa mostra uma lista de participantes que podem ser o fornecedor que você procura. Quando você selecionar um dos participantes, informações adicionais aparecerão no lado direito da caixa de diálogo:

- A guia **Geral** mostra o número de telefone e o endereço do participante.
- A guia **Funções** mostra as funções que o participante selecionado pode ter e as entidades legais correspondentes a cada uma delas.
- A guia **ID do registro de imposto** mostra as IDs de registros de imposto atribuídas ao participante.

Você pode copiar um participante somente se ele tiver uma função de fornecedor e se tiver essa função em outra entidade legal que não a atual. Quando você encontrar um participante que atenda a esses critérios, realize as etapas a seguir.

1. A opção **Copiar fornecedor** é exibida. Por padrão, essa opção é definida como **Não**. Para copiar o fornecedor para a entidade legal atual, defina-a como **Sim**. 
2. O campo **Entidade legal** é exibido. Selecione a entidade legal da qual o fornecedor será copiado. Se o fornecedor existir apenas em uma entidade legal, o campo estará definido como a entidade legal correspondente por padrão.
3. Escolha **Selecionar**. O fornecedor foi criado.

## <a name="validation"></a>Validação

Ao copiar um fornecedor, haverá uma tentativa de salvar as informações sobre o novo fornecedor. São executadas validações para verificar se os dados que foram copiados estão corretos. Você receberá uma mensagem de erro para que cada validação com falha. As mensagens de erro mostram quais informações devem ser atualizadas. A cópia do fornecedor não pode ser salva até que você corrija os erros de validação.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Copiar um fornecedor usando o recurso de pesquisa do número de isenção de imposto

Você também pode copiar fornecedores usando o recurso de pesquisa **Número de isenção de imposto** no grupo **Registro** da guia **Fornecedor**, no Painel de Ações da página **Todos os fornecedores**. A caixa de diálogo **Pesquisa de número de isenção de imposto** exibida mostra os números de isenção de imposto, a ID e o nome do fornecedor, e a entidade legal em que a ID de isenção de imposto é usada. Você pode copiar um fornecedor somente se ele estiver em uma entidade legal que não a atual. Após selecionar um fornecedor que atende a esse critério, realize as etapas a seguir.

1. A opção **Copiar fornecedor** é exibida. Por padrão, essa opção é definida como **Não**. Para copiar o fornecedor para a entidade legal atual, defina-a como **Sim**.
2. Escolha **Selecionar**. O fornecedor foi criado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
