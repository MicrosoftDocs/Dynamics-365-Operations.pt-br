---
title: Trabalhar com itens serializados no PDV
description: Este tópico explica como gerenciar itens serializados no aplicativo de ponto de venda (PDV).
author: boycezhu
manager: annbe
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 6ba01abc3d1a4496ec586a621aa03b4981f84d76
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410302"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabalhar com itens serializados no PDV

[!include [banner](includes/banner.md)]

Muitos varejistas vendem produtos que exigem controle de série. Esses produtos são referidos como *itens serializados*. Alguns varejistas talvez queiram manter números de série no estoque da loja ou do depósito para fins de acompanhamento. Outros varejistas podem querer capturar números de série durante o processo de vendas, para fins de serviço e garantia. Este tópico explica como como você pode gerenciar itens serializados no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

## <a name="serial-number-configurations"></a>Configurações de número de série

Um item é considerado um item serializado se ele tiver sido atribuído a um grupo de dimensões de acompanhamento configurado para permitir números de série. Na matriz do Commerce, na página **Grupos de dimensões de acompanhamento**, selecione a opção **Ativo** para habilitar números de série para o processo de estoque ou selecione a opção **Ativar no processo de vendas** para habilitar os números de série para o processo de vendas.

Na FastTab **Dimensões de rastreamento**, ative o parâmetro **Recibo em branco permitido** para permitir que um número de série seja uma entrada opcional durante o processo de recebimento do estoque de um item serializado. A desativação desse parâmetro impõe o número de série a ser uma entrada necessária. Da mesma forma, o parâmetro **Problema em branco permitido** controla se o número de série é necessário durante o processo de remessa do estoque.

> [!NOTE]
> Para usar as operações de PDV de **Estoque de entrada** e **Estoque de saída** para registrar ou validar os números de série em relação a um item serializado. você deve configurar o item a ser atribuído a um grupo de dimensões de rastreamento que seja configurado para permitir a opção **Ativo** para números de série, e não a opção **Ativar no processo de vendas**.

## <a name="serial-number-management-page"></a>Página Gerenciamento de números de série

Nas operações de PDV de **Estoque de entrada** e **Estoque de saída**, se o item que está sendo selecionado, recebido ou enviado for um item serializado, o painel **Detalhes** conterá uma opção **Gerenciar números de série** que vinculará a página **Gerenciamento de números de série** ao local no qual você pode registrar ou validar os números de série de um item. Alternativamente, você pode abrir a página **Gerenciamento de números de série** selecionando a ação **Número de série** na barra de aplicativos da exibição dos detalhes da ordem ou selecionando a opção **Gerenciar número de série** na caixa de diálogo que aparece para você durante o processo de envio ou recebimento. 

A página **Gerenciamento de números de série** lista todas as linhas de número de série em aberto que têm registro ou validação pendentes. Pode haver duas guias nesta página: uma para o item atual e outra para todos os itens serializados na ordem.

O campo **Status** na página **Gerenciamento de número de série** fornece informações sobre a fase atual de cada número de série em:

- **Não registrado** – O número de série não foi fornecido ou o número de série registrado ainda não foi validado (no processo de recebimento).
- **Registrando** – O número de série foi registrado e salvo localmente no banco de dados de canal do armazenamento ou o número de série registrado anteriormente foi validado. Somente os números de série que tiverem um status **Registrando** serão enviados para a matriz do Commerce quando você terminar o recebimento ou o atendimento.

## <a name="receive-serialized-items"></a>Receber itens serializados

A operação de PDV **Estoque de entrada** permite que os usuários executem as seguintes tarefas para itens serializados:

- Registrar números de série em itens serializados quando esses itens forem recebidos no armazenamento por uma ordem de compra.
- Validar números de série pré-registrados em itens serializados quando esses itens forem recebidos no armazenamento por uma ordem de compra ou transferir ordem.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de série em itens serializados

Para uma ordem de compra, você receberá uma solicitação em uma caixa de diálogo com a opção **Gerenciar número de série** durante o processo de recebimento de um item serializado. Você pode selecionar essa opção para abrir a página **Gerenciamento de números de série** e começar a registrar os números de série. Você também pode ignorar essa etapa durante o processo de recebimento e fornecer a entrada posteriormente, antes do lançamento do recebimento.

Por padrão, a guia para o item atual é exibida. Todas as linhas de número de série têm um valor de número de série vazio e o status **Não registrado**. Você pode verificar os códigos de barras dos números de série ou selecionar o **Número de série** na barra de aplicativos para inserir os números de série. Os números de série inseridos aparecem na lista e seus status são alterados para **Registrando**. O número máximo de números de série que você pode registrar na lista é igual à quantidade recebida. Se cometer um erro, você poderá selecionar **Editar** ou **Limpar** no painel **Detalhes** para alterar os números de série inseridos.

Também é possível registrar os números de série na guia **Todos os itens serializados** da página **Gerenciamento de números de série**. Na lista, selecione o item em relação ao qual você deseja registrar os números de série.

### <a name="validate-serial-numbers-on-serialized-items"></a>Validar números de série em itens serializados

Para uma ordem de transferência, o lado de entrada deve registrar números de série nos itens serializados durante o processo de remessa. Para uma ordem de compra, o fornecedor pode fornecer informações de número de série por meio de um aviso de remessa antecipada (ASN) e você pode registrar os números nos itens que serão enviados. Em ambos os casos, os números de série são conhecidos antes do recebimento. Portanto, no lado de entrada, você só precisará verificar se recebeu o que deveria receber.

Para validar números de série, você pode abrir a página **Gerenciamento de números de série** durante o processo de recebimento ou a qualquer momento antes de o recebimento ser lançado. Para cada item serializado com números de série registrados no registro, todos os números de série são automaticamente definidos com um status inicial de **Não registrado** nesta página. Para validar números de série, você pode examiná-los ou inseri-los. Como o número de série é inserido, o aplicativo valida se eles correspondem a números de série registrados. Se coincidirem, seu status será alterado para **Registrando**. Caso contrário, você receberá uma mensagem de erro. Você também pode selecionar diretamente um número de série e, em seguida, selecionar a opção **Validar número de série** no painel **Detalhes** para marcar rapidamente o número de série como validado. O número máximo de números de série que você pode validar na lista é igual à quantidade recebida.

Também é possível validar os números de série na guia **Todos os itens serializados** da página **Gerenciamento de números de série**. Na lista, selecione o item em relação ao qual você deseja validar os números de série.

## <a name="ship-serialized-items"></a>Enviar itens serializados

Você pode usar a operação de PDV **Estoque de saída** para registrar números de série em relação a itens serializados ao enviá-los da loja atual por de uma ordem de transferência.

### <a name="register-serial-numbers-against-serialized-items"></a>Registrar números de série em itens serializados

Para uma ordem de transferência, você receberá uma solicitação em uma caixa de diálogo com a opção **Gerenciar número de série** durante o processo de envio de um item serializado. Você pode selecionar a opção para abrir a página **Gerenciamento de números de série** e começar a registrar os números de série. Você também pode ignorar essa etapa durante o processo de envio e fornecer a entrada posteriormente, antes da remessa.

Por padrão, a guia para o item atual é exibida. Todas as linhas de número de série têm um valor de número de série vazio e o status **Não registrado**. Você pode verificar os códigos de barras dos números de série ou selecionar o **Número de série** na barra de aplicativos para inserir os números de série. Os números de série inseridos aparecem na lista e seus status são alterados para **Registrando**. O número máximo de números de série que você pode registrar na lista é igual à quantidade de envio. Se cometer um erro, você poderá selecionar **Editar** ou **Limpar** no painel **Detalhes** para alterar os números de série inseridos.

Também é possível registrar os números de série na guia **Todos os itens serializados** na página **Gerenciamento de números de série**. Na lista, selecione o item em relação ao qual você deseja registrar os números de série.

Opcionalmente, você pode habilitar a validação de disponibilidade de número de série durante o registro de número de série em relação a uma ordem de transferência de saída. Com essa validação, se você tentar enviar um número de série que não esteja disponível no estoque da loja de remessa, receberá uma mensagem de erro e deverá fornecer um número diferente.

Para habilitar tal validação, como pré-requisito, é necessário agendar os seguintes trabalhos a serem executados de forma recorrente:

- **Varejo e Comércio** > **TI de Varejo e Comércio** > **Produtos e estoque** > **Disponibilidade de produtos com dimensões de rastreamento**
- **Varejo e Comércio** > **Agendas de distribuição** > **1130** (**Disponibilidade de produtos**)

## <a name="additional-resources"></a>Recursos adicionais

[Operação de estoque de entrada no PDV](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation)

[Operação de estoque de saída no PDV](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation)


[!INCLUDE[footer-include](../includes/footer-banner.md)]