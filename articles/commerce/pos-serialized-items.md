---
title: Trabalhar com itens serializados no PDV
description: Este tópico explica como gerenciar itens serializados no aplicativo de ponto de venda (PDV).
author: boycezhu
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7b1b004d7a910e3b53eb584dbceb4d52d41fe409
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022674"
---
# <a name="work-with-serialized-items-in-the-pos"></a>Trabalhar com itens serializados no PDV

[!include [banner](includes/banner.md)]

Muitos varejistas vendem produtos que exigem controle de série. Esses produtos são referidos como *itens serializados*. Alguns varejistas talvez queiram manter números de série no estoque da loja ou do depósito para fins de acompanhamento. Outros varejistas podem querer capturar números de série durante o processo de vendas, para fins de serviço e garantia. Este tópico explica como você pode gerenciar itens serializados no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

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

## <a name="sell-serialized-items-in-pos"></a>Vender itens serializados no PDV

Embora o aplicativo PDV sempre tenha suporte para a venda de itens serializados, no Commerce versão 10.0.17 e posterior, as organizações podem habilitar funcionalidades que aprimoram a lógica comercial que é disparada ao vender produtos que são configurados para controle de números de série.

Quando o recurso **Validação do número de série aprimorado na captura de ordem PDV e no atendimento de ordem** é habilitado, as seguintes configurações de produto são avaliadas ao vender produtos serializados no PDV:

- Configuração de **tipo de série** do produto (**ativo** ou **ativo em vendas**).
- Configurações de **Saída em branco permitida** para o produto.
- Configurações de **Estoque físico negativo** para o produto e/ou para o depósito de vendas.

### <a name="active-serial-configurations"></a>Configurações de série ativas

Quando itens vendidos no PDV são configurados com uma dimensão de controle de número de série **Ativa**, o PDV inicia a lógica de validação que impede que os usuários concluam a venda de um item serializado com um número de série que não pode ser encontrado no estoque atual do depósito de vendas. Há duas exceções a essa regra de validação:

- Se o item também for configurado com **Saída em branco permitida** habilitada, os usuários poderão ignorar a entrada do número de série e vender o item sem designação de número de série.
- Se o item e/ou o depósito de vendas for configurado com **Estoque físico negativo** habilitado, o aplicativo aceitará e venderá um número de série que não possa ser confirmado de estar em estoque no depósito ao qual ele está sendo vendido. Essa configuração permite que a transação de estoque desse item/número de série específico fique negativa. Assim, o sistema permitirá vendas de números de série desconhecidos.

> [!IMPORTANT]
> Para garantir que o aplicativo PDV valide corretamente se os números de série vendidos para itens do tipo de série **Ativo** estão no estoque do depósito de vendas, é necessário que as organizações executem o trabalho **Disponibilidade do produto com dimensões de rastreamento** na sede do Commerce e o trabalho de distribuição de disponibilidade de produtos **1130** por meio da sede do Commerce com frequência. Quando um novo estoque serializado é recebido em depósitos de venda, para que o PDV valide a disponibilidade de estoque de números de série que está sendo vendido, o estoque mestre deve atualizar com frequência o banco de dados de canal com os dados de disponibilidade de estoque mais atualizados. O trabalho **Disponibilidade do produto com dimensões de rastreamento** usa um instantâneo atual do estoque mestre, incluindo números de série, para todos os depósitos da empresa. O trabalho de distribuição **1130** usa esse instantâneo de estoque e o compartilha com todos os bancos de dados de canal configurados.

### <a name="active-in-sales-process-serial-configurations"></a>Configurações seriais de Ativo no processo de vendas

Os itens configurados com a dimensão serial como **Ativo no processo de vendas** não passam por lógica de validação de estoque, pois essa configuração implica que os números de série do estoque não são registrados previamente em estoque e os números de série são capturados somente no momento da venda.  

Se **Saída em branco permitida** também estiver configurada para itens configurados de **Ativo no processo de vendas**, a entrada de número de série poderá ser ignorada. Se **Saída em branco permitida** não estiver configurada, o aplicativo exigirá que o usuário insira um número de série, mesmo que ele não seja validado em relação ao estoque disponível.

### <a name="apply-serial-numbers-during-creation-of-pos-transactions"></a>Aplicar números de série durante a criação de transações PDV

O aplicativo PDV solicita imediatamente aos usuários a captura de número de série durante a venda de um item serializado, mas o aplicativo permite que os usuários ignorem a entrada de números de série até um determinado ponto no processo de vendas. Quando o usuário começa a capturar o pagamento, o aplicativo impõe e requer uma entrada de número de série para itens que não estejam configurados para serem atendidos por remessas ou retiradas futuras. Todos os itens serializados configurados para o cumprimento de cash and carry ou execução exigem que o usuário capture o número de série (ou concorde em deixá-lo em branco se a configuração do item permitir) antes de concluir a venda.

Para itens serializados para retirada ou remessa futura, os usuários do PDV podem ignorar a inserção do número de série inicialmente e ainda concluir a criação da ordem do cliente.   

> [!NOTE]
> Ao vender ou atender produtos serializados por meio do aplicativo PDV, uma quantidade de "1" é imposta para os itens serializados na transação de venda. Isso é um resultado de como as informações de número de série são rastreadas na linha de venda. Durante a venda ou o atendimento de uma transação para vários itens serializados por meio do PDV, cada linha de venda deve ser configurada apenas com uma quantidade de "1". 

### <a name="apply-serial-numbers-during-customer-order-fulfillment-or-pickup"></a>Aplicar números de série durante a atendimento ou retirada da ordem do cliente

Ao atender linhas de ordem de cliente para produtos serializados usando a operação **Atendimento de Ordem** no PDV, o PDV impõe a captura do número de série antes do atendimento final. Portanto, se um número de série não foi fornecido durante a captura inicial da ordem, ele deverá ser capturado durante os processos de separação, embalagem ou remessa no PDV. Uma validação é feita em cada etapa e o usuário só será solicitado a fornecer dados de número de série se eles estiverem faltando ou não forem mais válidos. Por exemplo, se um usuário ignorar as etapas de separação ou embalagem e iniciar logo uma remessa, e um número de série não tiver sido registrado para a linha, o PDV exigirá que o número de série seja inserido antes da conclusão da etapa final da fatura. Ao impor a captura do número de série durante as operações de atendimento de ordem no PDV, todas as regras mencionadas anteriormente neste tópico ainda se aplicam. Somente os itens serializados configurados como **Ativos** passam por uma validação de estoque de número de série. Os itens configurados como **Ativos no processo de vendas** não serão validados. Se o **Estoque físico negativo** for permitido para produtos **Ativos**, qualquer número de série será aceito, independentemente da disponibilidade do estoque. Para itens **Ativos** e **Ativos no processo de vendas**, se **Saída em branco permitida** estiver configurada, um usuário poderá deixar números de série em branco, se desejado, durante as etapas de separação, embalagem e envio.

As validações para números de série também ocorrerão quando um usuário executar as operações de retirada em ordens de cliente no PDV. O aplicativo PDV não permite que uma retirada seja finalizada em um produto serializado, a menos que ele passe nas validações, conforme mencionado anteriormente. As validações sempre se baseiam na dimensão de rastreamento do produto e nas configurações de depósito de vendas. 

## <a name="additional-resources"></a>Recursos adicionais

[Operação de estoque de entrada no PDV](./pos-inbound-inventory-operation.md)

[Operação de estoque de saída no PDV](./pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]