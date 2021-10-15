---
title: Gerenciar fólios
description: Este tópico descreve como trabalhar com fólios. Um fólio geralmente consiste em mercadorias de um fornecedor para uma entidade ou empresa por remessa. As mercadorias em um fólio podem estar em um contêiner ou podem ser espalhadas entre vários contêineres.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5b84237844ec1d8f6c0716a0a13b05c83b358901
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575767"
---
# <a name="manage-folios"></a>Gerenciar fólios

[!include [banner](../../includes/banner.md)]

Um fólio costuma ser determinado pelas regulamentações alfandegárias. Ele consiste em mercadorias de um fornecedor para uma entidade ou empresa por remessa. As mercadorias em um fólio podem estar em um contêiner ou podem ser espalhadas entre vários contêineres.

Para abrir a página **Todos os fólios**, acesse **Custo de entrega \> Fólios \> Todos os fólios**. Esta página mostra uma lista de todos os fólios atuais. Você pode usar os botões no Painel de Ações para criar, excluir e trabalhar com fólios. Selecione um fólio na lista para exibir os detalhes na página **Fólio**.

## <a name="action-pane"></a>Painel de Ações

O Painel de Ações nas páginas **Todos os fólios** e **Fólios** fornece botões que permitem trabalhar com um fólio selecionado. Cada botão executa uma única ação. O Painel de Ações também inclui guias; cada uma, por sua vez, fornece um conjunto de botões relacionados. Exceto onde indicado, todos os botões e guias descritos nas subseções a seguir estão disponíveis na exibição de lista (isto é, na página **Todos os fólios**) e na exibição detalhada (isto é, na página **Fólio**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Botões que aparecem diretamente no Painel de Ações

A tabela a seguir descreve os botões disponíveis diretamente no Painel de Ações.

| Botão | Descrição |
|---|---|
| Novo | Crie um fólio. |
| Excluir | Exclua o fólio aberto ou selecionado. |
| Custos de viagem | Abre a página **Custos de viagem**, em que você pode exibir e adicionar custos de fólio para todas as mercadorias na viagem. Quando os custos de fólio são adicionados manualmente à viagem, eles são adicionados automaticamente à página consulta de custos e distribuídos a cada mercadoria de acordo com o método especificado na página **Custos de viagens**. |

### <a name="buttons-on-the-manage-tab"></a>Botões na guia Gerenciar

A tabela a seguir descreve os botões disponíveis na guia **Gerenciar** do Painel de Ações.

| Botão | Descrição |
|---|---|
| Lançar lista de recebimentos | Lance uma lista de recebimentos para todas as linhas de ordem de compra no fólio. Se as remessas de várias empresas forem usadas, uma nova caixa de diálogo lançamento de lista de recebimento será aberta para cada empresa. |
| Lançar recebimento de produto | Lance um recebimento de produtos para todas as linhas de ordem de compra no fólio. Se as viagens de várias empresas forem usadas, uma nova caixa de diálogo lançamento de recebimentos de produtos será aberta para cada empresa. |
| Lançar fatura | Lance uma fatura para todas as linhas de ordem de compra no fólio. Se as viagens de várias empresas forem usadas, uma nova caixa de diálogo lançamento de fatura será aberta para cada empresa. |
| Remeter ordem de transferência | Lance uma ordem de transferência para todas as linhas de ordem de transferência relacionadas ao fólio atual na remessa relacionada. |
| Receber ordem de transferência | Lance um recebimento de ordem de transferência para todas as linhas de ordem de transferência relacionadas ao fólio atual na remessa relacionada. |
| Receber mercadorias em trânsito | Receba todas as linhas de ordem que estão em trânsito no fólio. |
| Documentos recebidos | Atualize a configuração da opção **Documentos recebidos** como *Sim*. Você pode usar este botão para bloquear o item e/ou a linha de compra para que ele não possa ser atualizado. |
| Localizar custos automáticos | Localize custos relevantes da viagem. Se esses custos já tiverem sido encontrados ou atualizados, você receberá a seguinte mensagem: "Há linhas de custo não faturadas. Deseja substituí-los?" Observe que os custos de viagem anexados ao fólio e que foram faturados não serão substituídos. |
| Criar diário de entrada | Gere um diário de entrada para as organizações usando recursos avançados de depósito. Você pode selecionar **Inicializar quantidade** (recomendado), **Criar a partir de mercadorias em trânsito** e/ou **Criar a partir de ordens de compra**. A última opção depende do uso do processamento de mercadorias em trânsito. |
| Acumular custos | Acumule custos em que um tipo de custo tenha uma conta contábil especificada para o débito. Este botão geralmente é usado quando o estoque está em trânsito ou quando as mercadorias são recebidas e faturadas. |

### <a name="buttons-on-the-general-tab"></a>Botões na guia Geral

A tabela a seguir descreve os botões disponíveis na guia **Geral** do Painel de Ações.

| Botão | descrição |
|---|---|
| Lista de Recebimentos | Lance uma lista de recebimentos para todas as linhas de ordem de compra no fólio. Se as viagens de várias empresas forem usadas, uma nova caixa de diálogo lançamento de lista de recebimentos será aberta para cada empresa. |
| Recebimento de produtos | Exiba o registro de recebimento de produtos, se ele for usado. |
| Entrada de item | Exiba o diário de entrada de itens, se ele for usado. |
| Consulta de custos | Abra a página de consulta de custo para exibir todos os custos de uma viagem, incluindo o contêiner de remessa, o fólio e a ordem de compra. Você pode ajustar a exibição exata da página usando a ação Exibir. Na página de consulta de custo, você pode exibir uma das áreas, além do código de tipo de item e de custo. Ao remover esses itens, você pode ajustar a página agrupando custos juntos. Esse recurso poderá ser útil se você estiver usando tamanhos e cores. Você pode alterar as dimensões que são mostradas na página. A página **Custos** mostra somente códigos de tipo de custo em que a entrada **Dr** na guia **Lançamento** está definida como *Item*. |

## <a name="header-view"></a>Exibição do cabeçalho

Para abrir a exibição **Cabeçalho**, abra um fólio e selecione a guia **Cabeçalho** no canto superior direito do título do fólio.

### <a name="settings-on-the-general-fasttab"></a>Configurações na FastTab Geral

A tabela a seguir descreve os campos disponíveis na FastTab **Geral** na exibição **Cabeçalho** de um fólio.

| Campo | descrição |
|---|---|
| Fólio | O nome do fólio. Esse nome é gerado automaticamente quando o fólio é criado.|
| Viagem | A viagem associada ao fólio. |
| Agente alfandegário | Selecione o agente alfandegário para o fólio. Os agentes alfandegários são definidos no fornecedor. Eles permitem que os custos criados sejam determinados automaticamente. |
| Conhecimento aéreo/conhecimento de embarque doméstico | Especifique o conhecimento de embarque aéreo interno ou o conhecimento de embarque que se aplica ao fólio. |
| Empresa | A entidade legal (empresa) associada ao fólio. |
| Número de controle de carga | Este campo é usado por departamentos de alfândega em alguns países ou regiões. |
| Medição | Este campo permite que uma medida seja especificada no módulo **Custo de entrega**. Medidas costumam ser usadas por organizações que não sabem o volume ou o peso individual de mercadorias, mas que exigem uma divisão mais precisa do o fornecido pelo valor ou pela quantidade. O controlador de frete fornecerá a medida de peso ou cúbica e você pode colocá-la no nível de um item ou da ordem de compra. Ele poderá ser atualizado automaticamente se o parâmetro for selecionado ou inserido manualmente. |
| Unidade de medida | A unidade que se aplica à medida especificada. |
| Número de caixas | O número de caixas no fólio. Este campo pode ser atualizado automaticamente, dependendo da seleção do parâmetro. |
| Conta de fornecedor | Selecione o fornecedor associado ao fólio. Este campo é meramente informativo. Ele não afeta a funcionalidade. |
| Nome | O nome da conta do fornecedor selecionada. |
| Comentários | Insira informações adicionais relacionadas ao fólio. |
| Descrição das mercadorias | Selecione uma descrição de mercadorias para ajudar a identificar o fólio. Para obter mais informações, consulte [Descrição de mercadorias](shipping-information-setup.md#description-of-goods). |
| Data de avaliação | Este campo está relacionado à página de entrada de obrigações. O módulo **Custo de entrega** usará a taxa de câmbio alfandegária para a data definida aqui. O valor padrão é a data na página de entrada de obrigações. |
| ID da Alfândega | Insira a ID de alfândega. Os departamentos alfandegários em países ou regiões fornecem essa ID. |
| Código de tarifa | Insira um código de tarifa para associar ao fólio. Normalmente, esse código é exigido (e definido) pelo país ou região para a qual você está enviando. |

### <a name="settings-on-the-delivery-fasttab"></a>Configurações na FastTab Entrega

A tabela a seguir descreve as configurações disponíveis na FastTab **Entrega** na exibição **Cabeçalho** de um fólio.

| Campo | descrição |
|---|---|
| Data do fólio | Selecione uma data para associar ao fólio. O valor padrão é a data de criação da viagem. |
| ETA na porta de remessa | A data da hora estimada de entrada (ETA) na porta de destino (porta "para"). |
| Data de entrega estimada | Em geral, a data em que as mercadorias devem chegar no depósito. Este campo não é usado quando a data de entrega estimada é calculada. (A data de entrega estimada do controle de acompanhamento é usada.) Para definir este campo de forma que o valor coincida com a data de entrega estimada do controle de acompanhamento, use o [Centro de controle de acompanhamento](delivery-information-setup.md#tracking-control-center). |
| Documentos originais recebidos | A data em que os documentos originais foram recebidos. |
| Agente aconselhado | A data em que o agente foi aconselhado. |
| Conhecimento de embarque original enviado | A data em que o conhecimento de embarque original foi enviado. |
| Mercadorias lançadas | A data em que as mercadorias foram liberadas. |
| Compromisso do cliente | A data de compromisso do cliente. |
| Entrega no depósito | A data em que as mercadorias foram entregues ao depósito. |
| Data de verificação | A data de verificação. |
| Instruções de entrega | A data em que as instruções de entrega foram recebidas. |
| Porta de origem | A porta de onde a viagem parte. |
| Porta de destino | A porta na qual a viagem chega. O contêiner de remessa pode ter uma porta diferente, pois a remessa pode ser interrompida em várias portas. |

### <a name="settings-on-the-export-fasttab"></a>Configurações na FastTab Exportar

A tabela a seguir descreve as configurações disponíveis na FastTab **Exportar** na exibição **Cabeçalho** de um fólio.

| Campo | Descrição |
|---|---|
| Exportador | O exportador pode ser armazenado no fólio. Em comércio internacional, você pode enviar uma ordem de compra para uma empresa, mas receber as mercadorias de outra empresa. O acompanhamento e a documentação são exigidos pela alfândega. O nome e o endereço do exportador podem ser armazenados aqui. |
| Nome | O nome do exportador selecionado. |

## <a name="lines-view"></a>Exibição de linhas

Para abrir a exibição **Linhas**, abra um fólio e selecione a guia **Linhas** no canto superior direito do título do fólio.

### <a name="information-on-the-folio-fasttab"></a>Informações na FastTab Fólio

A FastTab **Fólio** na exibição **Linhas** mostra informações sobre o fólio. A maioria dessas informações também aparecem na exibição **Cabeçalho**, conforme descrito anteriormente neste tópico.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informações e botões na FastTab Linhas

A FastTab **Linhas** na exibição **Linhas** mostra detalhes sobre cada linha de ordem de compra total ou parcial incluída no fólio atual.

A tabela a seguir descreve os botões disponíveis na FastTab **Linhas** na exibição **Linhas**.

| Botão | Descrição |
|---|---|
| Remover | Remova a linha da ordem de compra selecionada da viagem. |
| Estoque \> Transações | Exiba transações de estoque para a linha de ordem de compra selecionada. Observe que, se você estiver usando mercadorias em trânsito, a ordem original e as ordens de mercadorias em trânsito também serão mostradas. |
| Estoque \> Exibir dimensões | Abra uma caixa de diálogo na qual você possa selecionar as dimensões de estoque que aparecem para as transações exibidas. |
| Atualizar | Atualize as informações relacionadas ao valor da linha, ao peso ou ao volume da linha da ordem de compra selecionada. |

### <a name="information-on-the-lines-details-fasttab"></a>Informações na FastTab Detalhes de linhas

A FastTab **Detalhes de linhas** na exibição **Linhas** mostra detalhes sobre a linha de ordem de compra selecionada no momento na FastTab **Linhas**.
