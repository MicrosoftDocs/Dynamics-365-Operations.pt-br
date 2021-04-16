---
title: Gerenciar contêineres de remessa
description: Este tópico descreve como trabalhar com contêineres de remessa. Os contêineres de remessa são usados para agrupar mercadorias que estão fisicamente agrupadas. Eles também são usados nos casos em que os custos devem ser compartilhados somente entre essas mercadorias, geralmente porque estão fisicamente juntas.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9b42292194d40f6b0cc6203130bedc1fbb45eec8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833800"
---
# <a name="manage-shipping-containers"></a>Gerenciar contêineres de remessa

[!include [banner](../../includes/banner.md)]

Os contêineres de remessa são usados para agrupar mercadorias que estão fisicamente agrupadas. Eles também são usados nos casos em que os custos devem ser compartilhados somente entre essas mercadorias, geralmente porque estão fisicamente juntas.

Para exibir e processar mercadorias na página contêiner de remessa, acesse **Custo de entrega \> Contêineres de remessa \> Todos os contêineres de remessa**. A página **Todos os contêineres de remessa** mostra uma lista de todos os contêineres de remessa disponíveis. Você pode usar os botões no Painel de Ações para criar, excluir e trabalhar com contêineres de remessa. Selecione um contêiner de remessa na lista para exibir os detalhes na página **Contêineres de remessa**.

A parte superior da página de detalhes do contêiner de remessa mostra o contêiner de remessa e as informações de custos. A seção **Linhas** mostra os fólios, itens e ordens de compra ou ordens de transferência anexadas ao contêiner.

## <a name="action-pane"></a>Painel de Ações

O Painel de Ações nas páginas **Todos os contêineres de remessa** e **Contêineres de remessa** fornece botões que permitem trabalhar com um contêiner de remessa selecionado. Cada botão executa uma única ação. O Painel de Ações também inclui guias; cada uma, por sua vez, fornece um conjunto de botões relacionados. Exceto onde indicado, todos os botões e guias descritos nas subseções a seguir estão disponíveis na exibição de lista (isto é, na página **Todos os contêineres de remessa**) e na exibição detalhada (isto é, na página **Contêineres de remessa**).

### <a name="buttons-on-the-manage-tab"></a>Botões na guia Gerenciar

A tabela a seguir descreve os botões disponíveis na guia **Gerenciar** do Painel de Ações.

| Botão | Descrições |
|---|---|
| Lançar lista de recibos | Lance uma lista de recebimentos ou exiba as listas de recebimento de produtos para todas as linhas da ordem de compra no contêiner de remessa. Se as remessas de várias empresas forem usadas, uma nova caixa de diálogo lançamento de lista de recebimento será aberta para cada empresa. |
| Lançar recebimento de produto | Lance um recebimento de produtos para todas as linhas de ordem de compra no contêiner de remessa. |
| Lançar fatura | Lance uma fatura para todas as linhas de ordem de compra no contêiner de remessa. Se as remessas de várias empresas forem usadas, uma nova caixa de diálogo lançamento de fatura será aberta para cada empresa. |
| Remeter ordem de transferência | Lance uma remessa de ordem de transferência para todas as linhas de ordem de transferência no contêiner de remessa. Somente as linhas do contêiner de remessa que são um tipo de ordem de transferência aparecem na caixa de diálogo. |
| Receber ordem de transferência | Lance um recebimento de ordem de transferência para todas as linhas de ordem de transferência no contêiner de remessa. A caixa de diálogo receber é a forma mais simples de receber mercadorias em um contêiner de remessa ou viagem e é uma das três opções disponíveis. Você também pode receber por diários de entrada ou processamento de dispositivo móvel. |
| Criar diário de entrada | Você pode gerar um diário de entrada para organizações usando recursos avançados de depósito. As opções são _Inicializar quantidade_ (recomendado), _Criar a partir de mercadorias em trânsito_ ou _Criar a partir de ordens de compra_. As duas últimas opções dependem do uso do processamento de mercadorias em trânsito. |
| Renomear | Abra uma caixa de diálogo na qual você possa renomear um contêiner de remessa selecionado. |
| Alterar modelo de percurso | Altere o modelo de percurso. Depois de alterar o modelo de percurso, talvez seja necessário selecionar **Localizar custos automáticos** ou adicionar custos manualmente novamente, pois os custos de remessa serão excluídos. |
| Converter em aluguel | Converta um contêiner de remessa selecionado em um contêiner de remessa de aluguel. |

### <a name="buttons-on-the-general-tab"></a>Botões na guia Geral

A tabela a seguir descreve os botões disponíveis na guia **Geral** do Painel de Ações.

| Botão | Descrições |
|---|---|
| Lista de recebimentos | Lance uma lista de recebimentos para todas as linhas de ordem de compra no contêiner de remessa. Se as viagens de várias empresas forem usadas, uma nova caixa de diálogo lançamento de lista de recebimentos será aberta para cada empresa. |
| Recebimento de produto | Exiba o registro de recebimento de produtos, se ele for usado. O processo de recebimento de produtos só será usado se as mercadorias não usarem a funcionalidade de mercadorias em trânsito. |
| Entrada de item | Exiba o diário de entrada de itens para o contêiner de remessa se o diário for usado. |
| Trechos | Os trechos são usados para identificar partes separadas de um percurso. Os prazos de entrega podem ser associados a cada trecho para ajudar no rastreamento de remessa. Para obter mais informações, consulte [Configuração de percurso de vários trechos](multi-leg-journey-setup.md). |
| Rastreamento | Exiba ou atualize o rastreamento de remessa. |
| Ordens de mercadorias em trânsito | Você pode abrir a página **Mercadorias em trânsito** diretamente do contêiner. Essa página mostra os registros de mercadorias em trânsito somente para o contêiner de remessa selecionado. |

## <a name="header-view"></a>Exibição do cabeçalho

Para abrir a exibição **Cabeçalho**, abra um contêiner de remessa e selecione a guia **Cabeçalho** no canto superior direito do título do contêiner de remessa.

### <a name="settings-on-the-general-fasttab"></a>Configurações na FastTab Geral

A tabela a seguir descreve as configurações disponíveis na FastTab **Geral** na exibição **Cabeçalho** de um contêiner de remessa.

| Campo | Descrição |
|---|---|
| Contêiner de remessa | O nome do contêiner de remessa. |
| Viagem | A viagem é associada ao contêiner de remessa. |
| Tipo de contêiner de remessa | Insira o tipo de contêiner de remessa. Este campo deve ser definido. Você pode usá-lo para determinar o custo do frete, por exemplo, selecionando o custo automático associado ao tipo de contêiner de remessa. |
| Embarcação | Insira ou selecione a embarcação. Se a embarcação não estiver listada como um valor, você poderá inserir a ID da embarcação como texto livre. Nesse caso, a tabela principal não é atualizada de forma que a ID da embarcação possa ser selecionada neste campo posteriormente. Para obter mais informações, consulte [Embarcações](shipping-information-setup.md#vessels). |
| Tipo de Unidade | Os tipos de unidade são usados como um meio adicional de agrupar e identificar contêineres de remessa. Eles são mostrados e selecionados na página contêiner de remessa. Para obter mais informações, consulte [Configurar tipos de unidades](shipping-container-setup.md#unit-types). |
| Tipo de refrigeração | Os tipos de refrigeração são usados como um meio adicional de agrupar e identificar contêineres de remessa, em geral contêineres refrigerados. Eles são mostrados e selecionados na página contêiner de remessa. Para obter mais informações, consulte [Configurar tipos de refrigeração](shipping-container-setup.md#refrigeration-types). |
| Medição | Este campo permite que uma medida seja especificada no módulo **Custo de entrega**. Medidas costumam ser usadas por organizações que não sabem o volume ou o peso individual de mercadorias, mas que exigem uma divisão mais precisa do o fornecido pelo valor ou pela quantidade. O controlador de frete fornecerá o peso em quilogramas ou a medida cúbica. Você pode colocá-la no nível de um item ou da ordem de compra. Ele poderá ser atualizado automaticamente se o parâmetro for selecionado ou poderá ser inserido manualmente. |
| Unidade de medida | A unidade de medida que se aplica ao número no campo **Medida**. |
| Peso real | Você pode registrar o peso real da caixa ou do contêiner. Esse valor pode ser usado para verificação em relação ao peso máximo permitido na configuração de um contêiner de remessa. |
| Número de caixas | O número de caixas será atualizado automaticamente se o parâmetro for selecionado. |
| Descrição das mercadorias | É possível selecionar uma descrição das mercadorias no contêiner de remessa ou no cabeçalho do fólio. Ela é usada para ajudar a identificar uma viagem, um contêiner de remessa ou um fólio de mercadorias. Para obter mais informações, consulte [Descrição de mercadorias](shipping-information-setup.md#description-of-goods). |
| Conhecimento aéreo/conhecimento de embarque doméstico | Você pode especificar o conhecimento de embarque aéreo interno ou o conhecimento de embarque para o contêiner de remessa. |
| Comentários | Informações adicionais relacionadas ao contêiner de remessa. |
| Retornável | Um valor que indica se o contêiner de remessa pode ser devolvido após a viagem. |
| Status da viagem | O status do percurso associado ao contêiner de remessa. |
| Status da ordem de compra | O status da ordem de compra associada ao contêiner de remessa. |

### <a name="settings-on-the-delivery-fasttab"></a>Configurações na FastTab Entrega

A tabela a seguir descreve as configurações disponíveis na FastTab **Entrega** na exibição **Cabeçalho** de um contêiner de remessa.

| Campo | Descrição |
|---|---|
| Data e hora de criação | A data e a hora em que o contêiner foi criado. |
| Data da ex-fábrica | Geralmente, essa data é fornecida para a fábrica/fornecedor para indicar quando você espera que as mercadorias saiam do local. Quando você trabalha com uma fábrica na Ásia, essa data costuma ser necessária em vez da data em que as mercadorias são esperadas. (Por outro lado, para uma entrega local, é necessário indicar a data em que as mercadorias são esperadas). Este campo pode ser preenchido nas linhas da ordem de compra na lista do contêiner de remessa. Você também pode inseri-la manualmente aqui. |
| Data da remessa | Essa data pode ser impressa no documento da ordem de compra. Normalmente, ela informa o fornecedor/fábrica sobre a data em que as mercadorias devem ser entregues na porta. Este campo é meramente informativo. Ela não é usada para estimar a data de entrega esperada das mercadorias no contêiner de remessa. Este campo pode ser definido para ser atualizado automaticamente quando a página controle de acompanhamento é atualizada. |
| Na data de armazenamento | A primeira data em que as mercadorias das ordens de compra vinculadas à viagem estarão disponíveis para venda.|
| Data de entrega estimada | Em geral, a data em que as mercadorias devem chegar no depósito. Este campo é meramente informativo. Ele não é usado para calcular o planejamento mestre nas linhas da ordem de compra no contêiner de remessa. A data de entrega esperada nas linhas da ordem de compra é atualizada por meio do controle de acompanhamento. Este campo pode ser configurado para ser atualizado quando a página controle de acompanhamento é atualizada. |
| Data da partida | Em geral, a data em que o avião ou a embarcação realmente deixa o porto do exterior. |
| ETA na porta de remessa | A data de entrada estimada na porta de destino (porta "para"). |
| Documentos originais recebidos | Opcional: atualize a data em que os documentos originais foram recebidos. |
| Agente aconselhado | Opcional: atualize a data em que o agente foi aconselhado. |
| Conhecimento de embarque original enviado | Opcional: atualize a data em que o conhecimento de embarque original foi enviado. |
| Mercadorias lançadas | Opcional: atualize a data em que as mercadorias foram liberadas. |
| Compromisso do cliente | Opcional: atualize a data de compromisso do cliente. |
| Entrega no depósito | Opcional: atualize a data em que as mercadorias foram entregues ao depósito. |
| Data de verificação | Opcional: atualize a data de verificação. |
| Instruções de entrega | Opcional: Atualize a data das instruções de entrega. |
| Porta de origem | A porta da qual os itens serão enviados. |
| Porta de destino | A porta para a qual os itens serão enviados. |
| Encaminhador local | Este campo é meramente informativo. O encaminhador local deve ser selecionado na tabela de fornecedores. |
| Data de transporte local | Insira a data para a qual o transporte local está reservado. Este campo pode ajudar o depósito no planejamento. |
| Hora de transporte local | Insira o intervalo de tempo. Este campo pode ajudar o depósito no planejamento. |
| Modelo de diário | O modelo de percurso especificado para a viagem. O modelo de percurso fornece os detalhes das portas "para" e "de", e os prazos de entrega associados ao controle de acompanhamento do contêiner de remessa. |

### <a name="settings-on-the-other-fasttab"></a>Configurações na FastTab Outro

A tabela a seguir descreve as configurações disponíveis na FastTab **Outro** na exibição **Cabeçalho** de um contêiner de remessa.

| Campo | Descrição |
|---|---|
| Aluguel​ | Um valor que indica se o contêiner de remessa é um contêiner de remessa de aluguel. Os custos de aluguel podem ser associados a contêineres de aluguel. |
| Convertido em aluguel | Um valor que indica se o contêiner de remessa foi convertido em um contêiner de remessa de aluguel. Os custos de aluguel podem ser associados a contêineres de aluguel. |
| Viagem original | Se o contêiner de remessa foi movido para uma nova viagem, a viagem original. |
| Usado | Use esta opção para registrar se um contêiner de remessa de aluguel foi usado. Ela é meramente informativa. |
| Data de carregamento esperada | A data em que o contêiner de remessa deve ser carregado com mercadorias. |
| Nosso número de série | Insira o número de série usado internamente pela sua empresa para o contêiner de remessa. |
| Número de série da empresa de remessa | Insira o número de série fornecido pelo agente ou empresa de remessa para o contêiner de remessa. |
| Data de aplicação do certificado de exame | A data em que um exame foi solicitado para o contêiner de remessa. |
| Data de recebimento do certificado de exame | A data em que o certificado de exame foi recebido. |
| Data de validade do certificado de exame | A data em que o certificado de exame expirará. |
| Número do certificado de exame | O número do certificado que foi emitido após a realização do exame. |

## <a name="lines-view"></a>Exibição de linhas

Para abrir a exibição **Linhas**, abra um contêiner de remessa e selecione a guia **Linhas** no canto superior direito do título do contêiner de remessa.

### <a name="information-on-the-shipping-container-fasttab"></a>Informações sobre a FastTab Contêiner de remessa

A FastTab **Contêiner de remessa** na exibição **Linhas** mostra informações sobre o fólio. A maioria dessas informações também aparecem na exibição **Cabeçalho**, conforme descrito anteriormente neste tópico.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informações e botões na FastTab Linhas

A FastTab **Linhas** na exibição **Linhas** mostra detalhes sobre cada linha de ordem de compra total ou parcial incluída no contêiner de remessa atual.

A tabela a seguir descreve os botões disponíveis na FastTab **Linhas** na exibição **Linhas**.

| Botão | Descrição |
|---|---|
| Remover | Remova a linha da ordem de compra selecionada da viagem. |
| Estoque \> Transações | Exiba transações de estoque para a linha de ordem de compra selecionada. Observe que, se você estiver usando mercadorias em trânsito, a ordem original e as ordens de mercadorias em trânsito também serão mostradas. |
| Estoque \> Exibir dimensões | Abra uma caixa de diálogo na qual você possa selecionar as dimensões de estoque que aparecem para as transações exibidas. |
| Atualizar | Atualize as informações relacionadas ao valor da linha, ao peso ou ao volume da linha da ordem de compra selecionada. |

### <a name="information-on-the-lines-details-fasttab"></a>Informações na FastTab Detalhes de linhas

A FastTab **Detalhes de linhas** na exibição **Linhas** mostra detalhes sobre a linha de ordem de compra selecionada no momento na FastTab **Linhas**.
