---
title: Trabalhar com itens serializados no PDV
description: Este tópico explica como gerenciar itens serializados no aplicativo de ponto de venda (PDV).
author: boycezhu
manager: annbe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 1e0d6aa7cd5576578378e70c6ee808833314aff3
ms.sourcegitcommit: 919620b4aca425e6a1248ee12f50a622d2531e58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "3290761"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabalhar com itens serializados no PDV

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Muitos varejistas vendem produtos que exigem controle de série. Esses itens são referidos como *itens serializados*. Alguns varejistas talvez queiram manter números de série para fins de controle. Outros varejistas podem querer capturar números de série durante o processo de vendas, para fins de serviço e garantia. Este tópico explica como como você pode gerenciar itens serializados no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurações de número de série

Um item é considerado um item serializado se ele tiver sido atribuído a um grupo de dimensões de rastreamento configurado para permitir números de série. Em Commerce headquarters, na página **Grupos de dimensões de rastreamento**, selecione a opção **Ativa** para habilitar os números de série para o processo de estoque. Para habilitar números de série para o processo de vendas, selecione a opção **Ativo no processo de vendas**.

Na guia **Dimensões de rastreamento**, se a opção **Recibo em branco permitido** estiver ativada, o número de série será uma entrada opcional durante o processo de recebimento do estoque. Se a opção estiver desativada, o número de série será necessário.

Na guia **Números de série**, se a opção **Controle de números de série** estiver ativada, o número de série deve ser exclusivo por unidade. Em outras palavras, os números de série duplicados não são permitidos.

## <a name="serialized-items-in-the-receiving-process"></a>Itens serializados no processo de recebimento

A operação **Estoque de entrada** no aplicativo de PDV permite que os usuários executem as seguintes tarefas para itens serializados:

- Registrar números de série em itens serializados quando esses itens forem recebidos no armazenamento por uma ordem de compra.
- Validar números de série pré-registrados em itens serializados quando esses itens forem recebidos no armazenamento por uma ordem de compra ou transferir ordem.

> [!NOTE]
> Para usar a operação **Estoque de entrada** para registrar ou validar um item serializado, o item deve receber um grupo de dimensões de rastreamento configurado para permitir números de série para a opção **Ativa**, não a opção **Ativa no processo de vendas**.

Para iniciar o processo de recebimento, na operação de **Estoque de entrada**, você pode iniciar no modo de exibição **Recebendo agora** verificando o código de barras do item ou inserindo a ID do item. Como alternativa, você pode iniciar na exibição **Lista de ordem completa** selecionando manualmente o item.

Se o item que está sendo selecionado ou recebido é um item serializado, o painel **Detalhes** do item contém um link **Gerenciar número de série** que abre a página **Gerenciamento de números de série**. Alternativamente, você pode abrir a página **Gerenciamento de números de série** selecionando o **Número de série** na barra de aplicativos da exibição detalhes da ordem ou selecionando **Gerenciar número de série** na caixa de diálogo que aparece para você durante o processo de recebimento. A página **Gerenciamento de números de série** lista todas as linhas de número de série em aberto que têm registro ou validação pendentes. Pode haver duas guias nesta página: uma para o item atual e outra para todos os itens serializados na ordem.

O campo **Status** na página **Gerenciamento de número de série** fornece informações sobre a fase atual de cada número de série em:

- **Não registrado** – O número de série não foi fornecido ou o número de série registrado ainda não foi validado.
- **Registrando** – O número de série foi registrado e salvo localmente no banco de dados de canal do armazenamento ou o número de série registrado anteriormente foi validado. Somente os números de série que tiverem um status **Registrando** serão enviados para o Commerce Headquarters quando você terminar o recebimento.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de série em itens serializados

Para uma ordem de compra, uma caixa de diálogo que o aparece durante o processo de recebimento de um item serializado oferece a opção **Gerenciar número de série**. Você pode selecionar essa opção para abrir a página **Gerenciamento de números de série** e começar a registrar os números de série. Você também pode ignorar essa etapa durante o processo de recebimento e fornecer a entrada posteriormente, antes do lançamento do recebimento.

Por padrão, a guia para o item atual é exibida. Todas as linhas de número de série têm um valor de número de série vazio e o status **Não registrado**. Você pode verificar os códigos de barras de números de série ou selecionar o **Número de série** na barra de aplicativos para inserir números de série continuamente na caixa de diálogo. Os números de série inseridos aparecem na lista e o status das linhas de número de série é alterado para **Registrando**. O número máximo de números de série que você pode registrar na lista é igual à quantidade recebida. Se cometer um erro, você poderá selecionar **Editar** ou **Limpar** no painel **Detalhes** para alterar os números de série inseridos.

Também é possível registrar os números de série na guia **Todos os itens serializados** da página **Gerenciamento de números de série**. Na lista, selecione o item em relação ao qual você deseja registrar os números de série.

Durante o registro de número de série nesta página, ocorre a validação de duplicidades. Se você tentar inserir um número de série duplicado em um item para o qual o controle de número de série está ativado, você receberá uma mensagem de erro e deverá fornecer um número diferente.

### <a name="validate-serial-numbers-on-serialized-items"></a>Validar números de série em itens serializados

Para uma ordem de transferência, o lado de entrada deve registrar números de série nos itens serializados durante o processo de remessa. Para uma ordem de compra, o fornecedor pode fornecer informações de número de série por meio de um aviso de remessa antecipada (ASN) e você pode registrar os números nos itens que serão enviados. Em ambos os casos, os números de série são conhecidos antes do recebimento. Portanto, no lado de entrada, você só precisará verificar se recebeu o que deveria receber.

Para validar números de série, você pode abrir a página **Gerenciamento de números de série** durante o processo de recebimento ou a qualquer momento antes de o recebimento ser lançado. Para cada item serializado com números de série registrados no registro, todos os números de série são automaticamente definidos com um status inicial de **Não registrado** nesta página. Para validar números de série, você pode examiná-los ou inseri-los. Como o número de série é inserido, o aplicativo valida se eles correspondem a números de série registrados. Se coincidirem, seu status será alterado para **Registrando**. Caso contrário, você receberá uma mensagem de erro. O número máximo de números de série que você pode validar na lista é igual à quantidade recebida.

Também é possível validar os números de série na guia **Todos os itens serializados** da página **Gerenciamento de números de série**. Na lista, selecione o item em relação ao qual você deseja validar os números de série.

## <a name="additional-resources"></a>Recursos adicionais

[Operação de estoque de entrada no PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)
