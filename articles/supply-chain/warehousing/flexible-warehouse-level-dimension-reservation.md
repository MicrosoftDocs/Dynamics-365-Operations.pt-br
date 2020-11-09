---
title: Política de reserva de dimensão no nível de depósito flexível
description: Este tópico descreve a política de reserva de estoque que permite às empresas que vendem produtos rastreados por lote e executam suas logísticas como operações habilitadas para WMS reservem lotes específicos para ordens de venda do cliente, mesmo que a hierarquia de reservas associada aos produtos não permita a reserva de lotes específicos.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b9bd4e67ed64218f9c4ac87bd143f73680af9ac4
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017635"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Política de reserva de dimensão no nível de depósito flexível

[!include [banner](../includes/banner.md)]

Quando uma hierarquia de reservas de estoque do tipo "Abaixo do lote\[local\]" é associada a produtos, as empresas que vendem produtos rastreados por lote e executam suas logísticas como operações que são habilitadas para o Microsoft Dynamics 365 Warehouse Management System (WMS) não podem reservar lotes específicos desses produtos para ordens de venda do cliente.

De forma semelhante, as placas de licença específicas não podem ser reservadas para produtos em ordens de venda quando esses produtos são associados à hierarquia de reserva padrão.

Este tópico descreve a política de reserva de estoque que permite a essas empresas reservar lotes específicos ou placas de licença, mesmo quando os produtos são associados a uma hierarquia de reservas "Abaixo do lote\[local\]".

## <a name="inventory-reservation-hierarchy"></a>Hierarquia de reservas de estoque

Esta seção resume a hierarquia de reservas de estoque existente.

A hierarquia de reservas de estoque determina que, no que diz respeito às dimensões de armazenamento, a ordem de demanda comporta as dimensões obrigatórias de site, depósito e status do estoque, enquanto a lógica do depósito é responsável por atribuir um local às quantidades solicitadas e reservar o local. Em outras palavras, nas interações entre a ordem de demanda e as operações de depósito, espera-se que a ordem de demanda indique de onde a ordem deve ser remetida (ou seja, de qual site e depósito). O depósito conta com sua lógica para encontrar a quantidade necessária no local do depósito.

No entanto, para refletir o modelo operacional da empresa, as dimensões de rastreamento (números de série e de lote) estão sujeitas a mais flexibilidade. Uma hierarquia de reservas de estoque pode acomodar cenários nos quais se aplicam as seguintes condições:

- A empresa depende de suas operações de depósito para gerenciar a separação de quantidades que têm números de lote ou de série depois que elas tiverem sido encontradas no espaço de armazenamento do depósito. Esse modelo geralmente é conhecido como *Abaixo do lote\[local\]*. Normalmente, ele é usado quando a identificação de número de série ou lote de um produto não é importante para os clientes que fazem a demanda com a empresa vendedora.
- Se os números de série ou lote fizerem parte da especificação da ordem de um cliente, e eles forem registrados na ordem de demanda, as operações de depósito que encontrarem as quantidades no depósito serão restringidas pelos números específicos solicitados e não podem alterá-los. Esse modelo geralmente é conhecido como *Acima do lote\[local\]*.

Nesses cenários, o desafio é que apenas uma hierarquia de reservas de estoque pode ser atribuída a cada produto liberado. Portanto, para que o WMS manipule itens rastreados, depois que a atribuição de hierarquia determinar quando o número de série ou lote deve ser reservado (seja quando a ordem de demanda é retirada, seja durante o trabalho de separação do depósito), esse tempo não pode ser alterado de modo ad hoc.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Reserva flexível para itens rastreados por lote

### <a name="business-scenario"></a>Cenário de negócios

Neste cenário, uma empresa usa uma estratégia de estoque em que mercadorias concluídas são rastreadas pelos números de lote. Essa empresa também usa a carga de trabalho do WMS. Como essa carga de trabalho tem uma lógica bem montada para planejar e executar operações de separação e remessa de depósito dos itens habilitados para lote, a maioria dos itens concluídos é associada a uma hierarquia de reservas de estoque "Abaixo do lote\[local\]". A vantagem desse tipo de configuração operacional é que as decisões (que são efetivamente decisões de reserva) sobre quais lotes devem ser separados e onde colocá-los no depósito são adiadas até que as operações de separação de depósito comecem. Elas não são tomadas quando a ordem do cliente é realizada.

Embora a hierarquia de reservas "Abaixo do lote\[local\]" também atenda às metas de negócios da empresa, muitos dos clientes estabelecidos da empresa exigem o mesmo lote que compraram anteriormente quando repetiram a ordem de produtos. Portanto, a empresa está procurando flexibilidade no tratamento das regras de reserva de lotes para que, dependendo da demanda dos clientes pelo mesmo item, ocorram os seguintes comportamentos:

- Um número de lote pode ser registrado e reservado quando a ordem é realizada pelo processador de vendas e não pode ser alterado durante as operações de depósito e/ou retirado por outras demandas. Esse comportamento ajuda a garantir que o número do lote que foi pedido seja enviado ao cliente.
- Se o número do lote não for importante para o cliente, as operações de depósito poderão determinar um número de lote durante o trabalho de separação, depois que o registro e a reserva da ordem de venda tiverem sido feitos.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Permitindo a reserva de um lote específico na ordem de venda

Para acomodar a flexibilidade desejada no comportamento de reserva de lotes para os itens associados a uma hierarquia de reservas de estoque "Abaixo do lote\[local\]", os gerentes de estoque devem marcar a caixa de seleção **Permitir reserva na ordem de demanda** para o nível **Número do lote** na página **Hierarquias de reservas de estoque**.

![Tornando flexível a hierarquia de reservas de estoque](media/Flexible-inventory-reservation-hierarchy.png)

Quando o nível **Número do lote** na hierarquia é selecionado, todas as dimensões acima desse nível e até o nível **Local** são automaticamente selecionadas. (Por padrão, todas as dimensões acima do nível **Local** são pré-selecionadas.) Esse comportamento reflete a lógica em que todas as dimensões no intervalo entre o número do lote e o local também são reservadas automaticamente depois que você reserva um número de lote específico na linha da ordem.

> [!NOTE]
> A caixa de seleção **Permitir reserva na ordem de demanda** se aplica somente aos níveis de hierarquia de reservas que estão abaixo da dimensão de local do depósito.
>
> **Número do lote** e **Placa de licença** são os únicos níveis na hierarquia que estão abertos para a política de reserva flexível. Em outras palavras, você não pode marcar a caixa de seleção **Permitir reserva na ordem de demanda** para o nível de **Local** ou **Número de série**.
>
> Se a hierarquia de reservas incluir a dimensão de número de série (que deve estar sempre abaixo do nível **Número do lote** ) e se você tiver ativado a reserva específica do lote para o número do lote, o sistema continuará tratando a reserva de número de série e as operações de separação, com base nas regras que se aplicam à política de reserva "Abaixo da série\[local\].

A qualquer momento, você pode permitir a reserva específica de lote para uma hierarquia de reservas "Abaixo do lote\[local\]" existente em sua implantação. Essa alteração não afetará as reservas nem o trabalho de depósito aberto que foram criados antes da alteração. No entanto , a caixa de seleção **Permitir reserva na ordem de demanda** não poderá ser desmarcada se existirem transações de estoque do tipo de saída **Qtd. encomendada** , **Qtd. reservada** ou **Encomendado** para um ou mais itens que são associados a essa hierarquia de reservas.

> [!NOTE]
> Se a hierarquia de reservas existente de um item não permitir especificação de lote na ordem, você poderá reatribuí-la a uma hierarquia de reservas que permita a especificação de lote, desde que a estrutura do nível de hierarquia seja a mesma nas duas hierarquias. Use a função **Alterar hierarquia de reservas de itens** para fazer a reatribuição. Essa alteração pode ser relevante quando você deseja impedir a reserva flexível de lote para um subconjunto de itens rastreados por lote, mas permiti-la para o restante do portfólio de produtos.

Independentemente de você ter marcado a caixa de seleção **Permitir reserva na ordem de demanda** , se não quiser reservar um número de lote específico para o item em uma linha da ordem, ainda será aplicada a lógica padrão de operações de depósito válida para uma hierarquia de reservas "Abaixo do lote\[local\].

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Reservar um número de lote específico para uma ordem de cliente

Depois que uma hierarquia de reservas de estoque "Abaixo do lote\[local\]" do item rastreado por lote é configurada para permitir a reserva de números de lote específicos nas ordens de venda, os processadores de ordem de venda podem tirar as ordens do cliente para o mesmo item das seguintes maneiras, dependendo da solicitação do cliente:

- **Inserir detalhes da ordem sem especificar um número de lote** – essa abordagem deve ser usada quando a especificação de lote do produto não for importante para o cliente. Todos os processos existentes associados ao tratamento de uma ordem desse tipo no sistema permanecerão inalterados. Não são necessárias considerações adicionais sobre a parte dos usuários.
- **Inserir detalhes da ordem e reservar um número de lote específico** – essa abordagem deve ser usada quando o cliente solicita um lote específico. Normalmente, os clientes solicitam um lote específico quando estão repetindo a ordem de um produto que compraram anteriormente. Esse tipo de reserva específica do lote é conhecido como *reserva confirmada na ordem*.

O conjunto de regras seguinte é válido quando as quantidades são processadas, e um número de lote é confirmado para uma ordem específica:

- Para permitir a reserva de um número de lote específico para um item na política de reserva "Abaixo do lote\[local\]", o sistema deve reservar todas as dimensões até local. Esse intervalo normalmente inclui a dimensão da placa de licença.
- As diretivas de local não são usadas quando o trabalho de separação é criado para uma linha de venda que usa a reserva de lotes confirmada na ordem.
- Durante o processamento de trabalho do depósito para lotes confirmados na ordem, nem o usuário, nem o sistema têm permissão para alterar o número do lote. (Esse processamento inclui tratamento de exceção.)

O exemplo a seguir mostra o fluxo de ponta a ponta.

## <a name="example-scenario-batch-number-allocation"></a>Cenário de exemplo: alocação de número de lote

Para este exemplo, os dados de demonstração devem ser instalados, e você deve usar a empresa de dados de demonstração **USMF**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>Configurar uma hierarquia de reservas de estoque para permitir reserva específica de lote

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Estoque \> Hierarquia de reservas**.
2. Selecione **Novo**.
3. No campo **Nome** , insira um nome (por exemplo, **BatchFlex** ).
4. No campo **Descrição** , insira uma descrição (por exemplo, **Abaixo do lote flexível** ).
5. No campo **Selecionado** , selecione **Número de série** e **Proprietário** ; em seguida, selecione o botão de seta para a esquerda a fim de movê-los para o campo **Disponível**.
6. Selecione **OK**.
7. Na linha do nível de dimensão **Número do lote** , marque a caixa de seleção **Permitir reserva na ordem de demanda**. Os níveis **Placa de licença** e **Local** são selecionados automaticamente, e não é possível desmarcar suas caixas de seleção.
8. Selecione **Salvar**.

### <a name="create-a-new-released-product"></a>Crie um novo produto liberado

1. Defina os três parâmetros de dados mestres do produto usando estes valores:

    - No campo **Grupo de dimensões de armazenamento** , selecione **Ware**.
    - No campo **Grupo de dimensões de rastreamento** , selecione **Batch-Phy**.
    - No campo **Hierarquia de reservas** , selecione **BatchFlex**.

2. Crie dois números de lote, como **B11** e **B22**.
3. Adicione as quantidades de item ao estoque disponível usando os valores a seguir.

    | Depósito | Nº do lote | Local | Placa de licença | Quantidade |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | MASSA-001 | Nenhuma          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>Inserir detalhes da ordem de venda

1. Vá para **Vendas e marketing** \> **Ordens de venda** \> **Todas as ordens de venda**.
2. Selecione **Novo**.
3. No cabeçalho da ordem de venda, no campo **Conta de cliente** , digite **US-003**.
4. Adicione uma linha para o novo item e insira **10** como a quantidade. Verifique se o campo **Depósito** está definido como **24**.
5. Na FastTab **Linhas da ordem de venda** , selecione **Estoque** e, no grupo **Manter** , selecione **Reserva de lotes**. A página **Reserva de lotes** mostra uma lista de lotes que estão disponíveis para reserva para a linha da ordem. Neste exemplo, ela mostra uma quantidade de **20** para o número do lote **B11** e uma quantidade de **10** para o número do lote **B22**. Observe que a página **Reserva de lotes** não poderá ser acessada de uma linha se o item nessa linha estiver associado à hierarquia de reservas "Abaixo do lote\[local\]", a menos que esteja configurada para permitir reserva específica de lote.

    > [!NOTE]
    > Para reservar um lote específico para uma ordem de venda, você deve usar a página **Reserva de lotes**.
    >
    > Se você inserir o número do lote diretamente na linha da ordem de venda, o sistema se comportará como se você tivesse inserido um valor de lote específico para um item que está sujeito à política de reserva "Abaixo do lote\[local\]". Ao salvar a linha, você receberá uma mensagem de aviso. Se você confirmar que o número do lote deve ser especificado diretamente na linha da ordem, a linha não será manipulada pela lógica de gerenciamento de depósito normal.
    >
    > Se você reservar a quantidade na página **Reserva** , nenhum lote específico será reservado e a execução das operações de depósito para a linha seguirá as regras aplicáveis sob a política de reserva "Abaixo do lote\[local\].

    Em geral, essa página funciona e interage da mesma maneira que funciona e interage para itens que têm uma hierarquia de reservas associada do tipo "Acima do lote\[local\]". No entanto, as seguintes exceções se aplicam:

    - A FastTab **Números de lote confirmados para linha de origem** mostra os números de lote que são reservados para a linha da ordem. Os valores de lote na grade serão mostrados durante todo o ciclo de atendimento da linha da ordem, inclusive nos estágios de processamento do depósito. Em contrapartida, na FastTab **Visão Geral** , a reserva regular da linha da ordem (isto é, a reserva que é feita para as dimensões acima do nível **Local** ) é mostrada na grade até o ponto em que o trabalho de depósito é criado. A entidade de trabalho assume a reserva de linha, e a reserva de linha não aparece mais na página. A FastTab **Números de lote confirmados para linha de origem** ajuda a garantir que o processador de ordem de venda possa ver os números de lotes que foram confirmados na ordem do cliente em qualquer ponto do seu ciclo de vida, até o faturamento.
    - Além de reservar um lote específico, um usuário pode selecionar manualmente o local específico e a placa de licença do lote em vez de permitir que o sistema os selecione automaticamente. Esse recurso está relacionado ao design do mecanismo de reserva de lotes confirmados na ordem. Como foi mencionado anteriormente, quando um número de lote é reservado para um item de acordo com a política de reserva "Abaixo do lote\[local\]", o sistema deve reservar todas as dimensões até local. Portanto, o trabalho de depósito carregará as mesmas dimensões de armazenamento que foram reservadas pelos usuários que trabalharam com as ordens, e isso nem sempre representará o posicionamento de armazenamento do item que é conveniente, ou mesmo possível, para as operações de separação. Se os processadores de ordem estiverem cientes das restrições do depósito, talvez eles queiram selecionar manualmente os locais específicos e as placas de licença quando reservarem um lote. Nesse caso, o usuário deve usar a funcionalidade **Exibir dimensões** no cabeçalho da página, bem como deve adicionar o local e a placa de licença na grade, na FastTab **Visão Geral**.

6. Na página **Reserva de lotes** , selecione a linha para o lote **B11** e, em seguida, selecione **Reservar linha**. Não há lógica designada para atribuir locais e placas de licença durante a reserva automática. Você pode inserir manualmente a quantidade no campo **Reserva**. Observe que, na FastTab **Números de lote confirmados para linha de origem** , o lote **B11** é mostrado como **Confirmado**.

    ![Confirmando um número de lote específico para uma linha da ordem de venda na página Reserva de lotes](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > A reserva da quantidade em uma linha da ordem de venda pode ser realizada em vários lotes. Da mesma forma, é possível fazer reservas do mesmo lote em vários locais e placas de licença (se as placas de licença estiverem habilitadas para os locais).
    >
    > A reserva de um lote específico para a quantidade em uma linha da ordem de venda também pode ser parcial. Por exemplo, a quantidade total de 100 unidades pode ser reservada para que um lote específico seja confirmado em 20 unidades, enquanto 80 unidades são reservadas nos níveis de site e depósito para qualquer lote disponível. Nesse caso, o WMS manipulará as operações de separação usando duas linhas de trabalho separadas.

7. Vá para **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**. Selecione seu item e, em seguida , selecione **Gerenciar estoque** \> **Exibir** \> **Transações**.

    ![Reserva confirmada na ordem como um tipo de transação de estoque](media/Inventory-transactions-for-order-committed-reservation.png)

8. Revise as transações de estoque do item relacionadas à reserva da linha da ordem de venda.

    - Uma transação em que o campo **Referência** é definido como **Ordem de venda** e o campo **Saída** é definido como **Qtd. reservada** representa a reserva da linha da ordem para as dimensões de estoque acima do nível **Local**. De acordo com a hierarquia de reservas de estoque do item, essas dimensões são site, depósito e status do estoque.
    - Uma transação em que o campo **Referência** é definido como **Reserva confirmada na ordem** e o campo **Saída** é definido como **Qtd. reservada** representa a reserva da linha da ordem para o lote específico e todas as dimensões de estoque acima dele. De acordo com a hierarquia de reservas de estoque do item, essas dimensões são número do lote e local. Neste exemplo, o local é **Massa-001**.

9. No cabeçalho da ordem de venda, selecione **Depósito** \> **Ações** \> **Liberar para o depósito**. A linha da ordem agora é ondulada, e são criados uma carga e um trabalho.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>Revisar e processar trabalho de depósito que tenha números de lote confirmados na ordem

1. Na FastTab **Linhas de ordem de venda** , selecione **Depósito** \> **Detalhes do trabalho**.

    O trabalho que manipula a operação de separação para quantidades de lote que são confirmadas na linha da ordem de venda tem as seguintes características:

    - Para criar o trabalho, o sistema usa modelos de trabalho, mas não diretivas de local. Todas as configurações padrão definidas para modelos de trabalho, como um número máximo de linhas de separação ou uma unidade de medida específica, serão aplicadas para determinar quando um novo trabalho deve ser criado. No entanto, as regras associadas a diretivas de local para identificar locais de separação não são consideradas, pois a reserva confirmada da ordem já especifica todas as dimensões de estoque. Essas dimensões de estoque incluem as dimensões no nível de armazenamento do depósito. Portanto, o trabalho herda essas dimensões sem ter que consultar diretivas de local.
    - O número do lote não é mostrado na linha de separação (como é o caso da linha de trabalho que é criada para um item que tem uma hierarquia de reservas "Acima do lote\[local\]" associada.) Em vez disso, o número do lote "de" e todas as outras dimensões de armazenamento são mostrados na transação de estoque de trabalho da linha de trabalho referenciada a partir das transações de estoque associadas.

        ![Transação de estoque de depósito para trabalho que se origina da reserva confirmada na ordem](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - Depois que o trabalho é criado, a transação de estoque do item na qual o campo **Referência** está definido como **Reserva confirmada na ordem** é removida. A transação de estoque na qual o campo **Referência** está definido como **Trabalho** agora contém a reserva física em todas as dimensões de estoque da quantidade.

        As operações de depósito podem continuar para manipular a execução do trabalho da maneira usual. No entanto, as instruções no dispositivo móvel orientarão o trabalhador a separar um número de lote específico. Em ambientes de depósito em que os locais são controlados pela placa de licença, depois que um trabalhador chega a um local que armazena o mesmo lote em várias placas de licença, ele pode fazer a separação em qualquer placa de licença que ainda não esteja reservada (por exemplo, por outra reserva confirmada na ordem ou trabalho que se origina de uma reserva desse tipo).

        Se for impraticável fazer a separação no local que é especificado na linha de trabalho, os operadores de depósito poderão usar uma das seguintes ações para redirecionar a separação do lote específico de um local mais conveniente:

        - A ação padrão **Substituir local** em um dispositivo móvel (desde que a configuração **Permitir substituição de local de separação** do trabalhador do depósito esteja ativada)
        - A ação **Alterar local** na página **Detalhes da lista de trabalho**. 

2. No dispositivo móvel, termine a separação e a colocação do trabalho.

    A quantidade de **10** para o número de lote **B11** agora está separada para a linha da ordem de venda e foi posicionada no local **Porta da baía**. Neste ponto, ele está pronto para ser carregado no caminhão e enviado para o endereço do cliente.

## <a name="flexible-license-plate-reservation"></a>Reserva de placa de licença flexível

### <a name="business-scenario"></a>Cenário de negócios

Neste cenário, uma empresa usa o gerenciamento de depósito e o processamento de trabalho e manipula o planejamento de carga no nível de paletes/contêineres individuais fora do Supply Chain Management, antes que o trabalho seja criado. Esses recipientes são representados por placas de licença nas dimensões de estoque. Portanto, para essa abordagem, as placas de licença específicas devem ser previamente atribuídas a linhas de ordem de venda, antes da realização do trabalho de separação. A empresa está procurando flexibilidade na forma como as regras de reserva da placa de licença são manipuladas, de forma que os seguintes comportamentos ocorram:

- Uma placa de licença pode ser registrada e reservada quando a ordem for realizada pelo processador de vendas e não pode ser alterada durante as operações de depósito e/ou retirada por outras demandas. Esse comportamento ajuda a garantir que a placa de licença que foi planejada seja enviada ao cliente.
- Se a placa de licença ainda não estiver atribuída a uma linha da ordem de venda, o pessoal do depósito poderá selecionar uma placa de licença durante o trabalho de separação, depois que o registro e a reserva da ordem de venda forem concluídos.

### <a name="turn-on-flexible-license-plate-reservation"></a>Ativar reserva de placa de licença flexível

Antes de usar a reserva de placa de licença flexível, dois recursos devem ser ativados em seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status desses recursos e ativá-los, se necessário. Você deve ativar os recursos na seguinte ordem:

1. **Nome do recurso:** *Reserva de dimensão em nível de depósito flexível*
1. **Nome do recurso:** *Reserva de placa de licença confirmada por ordem flexível*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>Reservar uma placa de licença específica na ordem de venda

Para habilitar a reserva da placa de licença em uma ordem, você deve marcar a caixa de seleção **Permitir reserva na ordem de demanda** para o nível da **Placa de licença** na página **Hierarquias da reserva de estoque** da hierarquia associada ao item relevante.

![Página de hierarquias da reserva de estoque para uma hierarquia flexível de reservas da placa de licença](media/Flexible-LP-reservation-hierarchy.png)

Você pode habilitar a reserva da placa de licença na ordem em qualquer ponto da implantação. Essa alteração não afetará as reservas nem o trabalho de depósito aberto que foram criados antes da alteração. No entanto , a caixa de seleção **Permitir reserva na ordem de demanda** não poderá ser desmarcada se existirem transações de estoque de saída que tem um status de emissão de *Na ordem* , *Encomendada reservada* ou *Encomendada* para um ou mais itens que são associados a essa hierarquia de reservas.

Mesmo que a caixa de seleção **Permitir reserva em ordem de demanda** esteja marcada para o nível de **Placa de licença** , ainda é possível *não* reservar uma placa de licença específica na ordem. Nesse caso, a lógica de operações de depósito padrão válida para a hierarquia de reserva é aplicada.

Para reservar uma placa de licença específica, você deve usar um processo [Protocolo de Dados Aberto (OData)](../../fin-ops-core/dev-itpro/data-entities/odata.md). No aplicativo, é possível fazer essa reserva diretamente de uma ordem de venda usando a opção de **Reservas confirmadas na ordem por placa de licença** do comando **Abrir no Excel**. Nos dados da entidade que são abertos no suplemento do Excel, você deve inserir os seguintes dados relacionados à reserva e selecionar **Publicar** para enviar os dados de volta ao Supply Chain Management:

- Referência (só o valor *Ordem de venda* é suportado.)
- Número da ordem (o valor pode ser derivado do lote.)
- ID do lote
- Placa de licença
- Quantidade

Se for necessário reservar uma placa de licença específica para um item controlado por lote, use a página **Reserva de lote** , conforme descrito na seção [Inserir detalhes da ordem de venda](#sales-order-details).

Quando a linha da ordem de venda que usa uma reserva de placa de licença confirmada por ordem é processada pelas operações de depósito, as diretivas de localização não são usadas.

Se um item de trabalho de depósito consistir em linhas que são iguais a um palete completo e têm uma placa de licença – quantidades confirmadas, você poderá otimizar o processo de separação usando um item de menu de dispositivo móvel no qual a opção **Manipular por placa de licença** está definida como *Sim*. Um trabalho de depósito pode, então, verificar uma placa de licença para concluir uma separação, em vez de ter que verificar os itens do trabalho, um a um.

![Item de menu de dispositivo móvel no qual a opção Manipular por placa de licença está definida como Sim](media/Handle-by-LP-menu-item.png)

Como a funcionalidade **Manipular por placa de licença** é incompatível com o trabalho que cobre vários paletes, é melhor ter um item de trabalho separado para placa de licença diferentes. Para usar essa abordagem, adicione o campo **ID da placa de licença confirmada por ordem** como uma quebra de cabeçalho de trabalho na página **Modelo de trabalho**.

> [!NOTE]
> Para o processo de criação de trabalho confirmado por ordem, um valor de "dimensão de estoque confirmada por ordem" será atribuído às linhas de trabalho de separação e não será possível exibir o valor da placa de licença diretamente. Somente o processo *Direcionado pelo usuário* tem suporte durante a configuração de um item de menu de dispositivo móvel.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>Exemplo de cenário: configurar e processar uma reserva de placa de licença confirmada por ordem

Este cenário mostra como configurar e processar uma reserva de placa de licença confirmada por ordem.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Este cenário faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Supply Chain Management. Se quiser trabalhar no cenário usando os valores fornecidos aqui, trabalhe em um sistema em um ambiente no qual os dados de demonstração estejam instalados. Além disso, defina a entidade legal **USMF** antes de começar.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>Criar uma hierarquia de reserva de estoque que permite reservas de placas de licença

1. Vá para **Gerenciamento de depósito \> Configuração \> Estoque \> Hierarquia da reserva**.
1. Selecione **Novo**.
1. No campo **Nome** , insira um valor (por exemplo, *FlexibleLP* ).
1. No campo **Descrição** , insira um valor (por exemplo, *Reserva de placa de licença flexível* ).
1. Na lista **Selecionada** , selecione o **Número do lote** , **Número de série** e o **Proprietário**.
1. Selecione o botão **Remover** ![seta para trás](media/backward-button.png) para mover os registros selecionados para a lista **Disponível**.
1. Selecione **OK**.
1. Na linha do nível de dimensão **Placa de licença** , marque a caixa de seleção **Permitir reserva na ordem de demanda**. O nível **Local** é selecionado automaticamente, e não é possível desmarcar a caixa de seleção dele.
1. Selecione **Salvar**.

### <a name="create-two-released-products"></a>Crie dois produtos lançados

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Novo produto lançado** , defina os seguintes valores:

    - **Número do produto:** *Item1*
    - **Número do item:** *Item1*
    - **Grupo de modelo do item:** *FIFO*
    - **Grupo de itens:** *Áudio*
    - **Grupo de dimensões de armazenamento:** *Ware*
    - **Grupo de dimensões de rastreamento:** *Nenhum*
    - **Hierarquia de reserva:** *FlexibleLP*

1. Selecione **OK** para criar o produto e fechar a caixa de diálogo.
1. O novo produto é aberto. Na guia rápida **Depósito** , no campo **ID do grupo de sequências de unidade** , insira *cada*.
1. Repita as etapas anteriores para criar um segundo produto que tenha as mesmas configurações, mas defina os campos **Número do produto** e **Número do item** como *Item2*.
1. No Painel de Ação, na guia **Gerenciar estoque** , no grupo **Exibir** , selecione **Estoque físico**. Em seguida, selecione **Ajuste de quantidade**.
1. Ajuste o estoque disponível dos novos itens, conforme especificado na tabela a seguir.

    | Item   | Depósito | Localização | Placa de licença | Quantidade |
    |-------|-----------|----------|---------------|----------|
    | Item1 | 24        | FL-010   | LP01          | 10       |
    | Item1 | 24        | FL-011   | LP02          | 10       |
    | Item2 | 24        | FL-010   | LP01          | 5        |
    | Item2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > Você deve criar as duas placas de licença e os locais de uso que permitem itens mistos, como *FL-010* e *FL-011*.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>Criar uma ordem de venda e reservar uma placa de licença específica

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *24*

1. Selecione **OK** para fechar a caixa de diálogo **Criar ordem de venda** e abrir a nova ordem de venda.
1. Na guia rápida **Linhas da ordem de venda** , adicione uma linha que tenha as seguintes configurações:

    - **Número do item:** *Item1*
    - **Quantidade:** *10*

1. Adicione uma segunda linha da ordem de venda com as seguintes configurações:

    - **Número do item:** *Item2*
    - **Quantidade:** *5*

1. Selecione **Salvar**.
1. Na guia rápida **Detalhes da linha** , na guia **Configuração** , anote o valor do **ID do lote** de cada linha. Esses valores serão necessários durante a reserva de placas de licença específicas.

    > [!NOTE]
    > Para reservar uma placa de licença específica, você deve usar a entidade de dados **Reservas confirmadas na ordem por placa de licença**. Para reservar um item controlado por lote em uma placa de licença específica você também pode usar a página **Reserva de lote** , conforme descrito na seção [Inserir detalhes da ordem de venda](#sales-order-details).
    >
    > Se você inserir a placa de licença diretamente na linha da ordem de venda e confirmá-la no sistema, o processamento do gerenciamento de depósito não será usado para a linha.

1. Selecione **Abrir no Microsoft Office** , selecione **Reservas confirmadas na ordem por placa de licença** e baixe o arquivo.
1. Abra o arquivo baixado no Excel e selecione **Habilitar edição** para permitir que o suplemento do Excel seja executado.
1. Caso esteja executando o suplemento do Excel pela primeira vez, selecione **Confiar nesse Suplemento**.
1. Se for solicitado que você entre no sistema, selecione **Entrar** e use as mesmas credenciais usadas para entrar no Supply Chain Management.
1. Para reservar um item em uma placa de licença específica, no suplemento do Excel, selecione **Novo** para adicionar uma linha de reserva e, em seguida, defina os seguintes valores:

    - **ID do lote:** Insira o **ID do lote** encontrado para a linha da ordem de venda para *Item1*.
    - **Placa de licença:** *LP02*
    - **ReservedInventoryQuantity:** *10*

1. Selecione **Novo** para adicionar outra linha de reserva e defina os seguintes valores:

    - **ID do lote:** Insira o **ID do Lote** encontrado para a linha da ordem de venda para *Item2*.
    - **Placa de licença:** *LP02*
    - **ReservedInventoryQuantity:** *5*

1. No suplemento do Excel, selecione **Publicar** para enviar os dados novamente para o Supply Chain Management.

    > [!NOTE]
    > A linha de reserva será exibida no sistema somente se a publicação for concluída sem erros.

1. Volte para Supply Chain Management. 
1. Para revisar a reserva do item, na guia rápida **Linhas da ordem de venda** , no menu **Estoque** , selecione **Manter \> Reserva**. Observe que, para a linha da ordem de venda para *Item1* , o estoque de *10* é reservado e para a linha da ordem de venda para *item2* , o estoque de *5* é reservado.
1. Para revisar as transações de estoque relacionadas à reserva da linha da ordem de venda, na guia rápida **Linhas da ordem de venda** , no menu **Estoque** , selecione **Exibir \> Transações**. Observe que há duas transações relacionadas à reserva: uma na qual o campo **Referência** está definido como *Ordem de venda* e outra na qual o campo **Referência** está definido como *Reserva de ordem confirmada*.

    > [!NOTE]
    > Uma transação na qual o campo **Referência** é definido como *Ordem de venda* representa a reserva da linha para dimensões de estoque que estão acima do nível do **Local** (status de local, depósito e estoque). Uma transação na qual o campo **Referência** está definido como *Reserva confirmada na ordem* representa a reserva da linha da ordem para a placa e a localização da licença específica.

1. Para liberar a ordem de venda, no Painel de Ação, na guia **Depósito** , no grupo **Ações** , selecione **Liberar para o depósito**.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>Revisar e processar trabalho de depósito com placas de licença confirmadas por ordem atribuídas

1. Na guia rápida **Linhas da ordem de venda** , no menu **Depósito** , selecione **Detalhes do trabalho**.

    Como quando a reserva é feita para um lote específico, o sistema não usa diretivas de localização quando cria o trabalho para a ordem de venda que usa a reserva da placa de licença. Como a reserva de ordem confirmada especifica todas as dimensões de estoque, incluindo a localização, as diretivas de local não precisam ser usadas, pois essas dimensões de estoque são inseridas no trabalho. São mostradas na seção **Das dimensões de estoque** na página **Transações de estoque de trabalho**.

    > [!NOTE]
    > Depois que o trabalho é criado, a transação de estoque do item na qual o campo **Referência** está definido como *Reserva confirmada na ordem* é removida. A transação de estoque na qual o campo **Referência** está definido como *Trabalho* agora contém a reserva física para todas as dimensões de estoque da quantidade.

1. No dispositivo móvel, termine a separação e coloque o trabalho usando um item de menu no qual a caixa de seleção **Manipular por placa de licença** está marcada.

    > [!NOTE]
    > A funcionalidade **Manipular por placa de licença** o ajuda a processar toda a placa de licença. Se você precisar processar parte da placa de licença, não poderá usar essa funcionalidade.
    >
    > É recomendável que você tenha um trabalho separado gerado para cada placa de licença. Para obter esse resultado, use o recurso **Quebras de cabeçalho de trabalho** na página **Modelo de trabalho**.

    A placa de licença *LP02* agora está separada para as linhas da ordem de venda e colocada no local *Baydoor*. Neste ponto, ele está pronto para ser carregado e enviado para o cliente.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>Tratamento de exceção do trabalho de depósito que tem números de lote confirmados na ordem

O trabalho de depósito para separação de números de lote confirmados na ordem está sujeito ao mesmo tratamento de exceção de depósito e às mesmas ações que o trabalho regular. De modo geral, o trabalho em aberto ou linha do trabalho pode ser cancelado, pode ser interrompido porque o local de um usuário está cheio, a quantidade separada é insuficiente e pode ser atualizado devido a uma movimentação. Da mesma forma, a quantidade separada de trabalho que já foi concluída pode ser reduzida, ou o trabalho pode ser revertido.

A importante regra a seguir é aplicada a todas as ações de tratamento de exceção: o número do lote que foi reservado para o cliente nunca pode ser substituído por outro número de lote, mas suas dimensões de armazenamento (local e placa de licença) podem ser alteradas por uma atualização manual feita pelo usuário ou uma atualização automática feita pelo sistema. A atualização automática se baseia na mesma atribuição aleatória de dimensões de armazenamento que é aplicada quando um lote específico foi reservado automaticamente, mas nenhuma dimensão de armazenamento foi especificada.

### <a name="example-scenario"></a>Cenário de exemplo

Um exemplo desse cenário é uma situação em que o trabalho concluído anteriormente está sendo retirado usando a função **Reduzir quantidade separada**. Este exemplo supõe que você já tenha concluído as etapas descritas no [Exemplo de cenário: alocação de número de lote](#Example-batch-allocation). Ele continua com base nesse exemplo.

1. Vá para **Gerenciamento de depósito** \> **Cargas** \> **Cargas ativas**.
2. Selecione a carga que foi criada em relação à remessa da ordem de venda.
3. Na FastTab **Linhas de ordem da carga** , selecione **Reduzir quantidade separada**.
4. Na página **Reduzir quantidade separada** , no campo **Mover para local** , selecione **FL-001**.
5. No campo **Mover para placa de licença** , selecione **LP33**.
6. No campo **Quantidade de estoque para desfazer separação** da grade, digite **10**.
7. Selecione **OK**.

Veja a seguir os resultados da ação de desfazer a separação:

- O status do trabalho anteriormente fechado é definido como **Cancelado**.
- O novo trabalho do tipo **Movimento do estoque** é criado para a quantidade não separada de **10** para o número de lote **B11**. Esse trabalho representa o movimento do local **Porta da baía** para a placa de licença **LP33** no local **FL-001**. O status é definido como **Fechado**.
- O sistema reserva novamente o número do lote que foi originalmente pedido e atribui as IDs de local e placa de licença. (Esse processo equivale a executar a função **Reservar linha** para a linha de ordem de um determinado número de lote.) Consequentemente, o lote **B11** é mostrado como confirmado na FastTab **Números de lote confirmados para linha de origem** da página **Reserva de lote** , e o campo **Reserva** contém uma quantidade de **10** para o número de lote **B11**. Além disso, o campo **Local** é definido como **FL-001** e o campo **Placa de licença** é definido como **LP11**. (Você pode adicionar esses campos à grade se eles não estiverem visíveis.)

As tabelas a seguir fornecem uma visão geral que mostra como o sistema manipula a reserva de lotes confirmada na ordem para ações de depósito específicas. Para interpretar o conteúdo das tabelas, suponha que cada ação de depósito seja executada no contexto do trabalho de depósito existente que se origina de uma reserva de lotes confirmada na ordem ou que a execução de cada ação de depósito afete trabalhos desse tipo.

> [!NOTE]
> Nessas tabelas, a coluna "Quantidade de lotes disponível" indica se há uma quantidade de lotes disponível além da quantidade já reservada para as atuais reservas confirmadas na ordem ou já reservada pelo trabalho de depósito que se origina das reservas desse tipo.

#### <a name="override-the-pick-location-on-the-open-work"></a>Substituir o local de separação no trabalho em aberto

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A opção <strong>Permitir substituição de local de separação</strong> está habilitada no trabalhador.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Substituir local</strong> no aplicativo de depósito quando iniciar o trabalho de separação.</li>
<li>Selecione <strong>Sugerir</strong>.</li>
<li>Confirme o novo local que é sugerido com base na disponibilidade da quantidade de lotes.</li>
</ol>
</td>
<td>No trabalho atual, ocorrem as seguintes ações:
<ul>
<li>O local na linha de separação é atualizado para o novo local. (Se o local for controlado pela placa de licença, uma placa de licença aleatória será atribuída à transação de estoque de trabalho, e o trabalhador poderá fazer a separação a partir de qualquer placa de licença que tenha a quantidade disponível.)</li>
<li>Se a quantidade for encontrada em mais de uma placa de licença no novo local, a linha de separação original será dividida em várias linhas para correspondência com cada placa de licença.</li>
</ul>
</td>
<td>Não Aplicável</td>
</tr>
<tr>
<td>Não</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Substituir local</strong> no aplicativo de depósito quando iniciar o trabalho de separação.</li>
<li>Insira um local manualmente.</li>
</ol>
</td>
<td>A ação <strong>Substituir local</strong> não é possível. Ela falha e um erro é lançado.</td>
<td>Não aplicável</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Botão Completo – divide uma linha de trabalho devido ao estouro no local do usuário

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td>A opção <strong>Permitir divisão do trabalho</strong> está habilitada no item de menu do dispositivo móvel.</td>
<td>Não Aplicável</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Completo</strong> no aplicativo de depósito ao processar o trabalho de separação.</li>
<li>No campo <strong>Qtd da Separação</strong>, insira uma quantidade parcial da separação necessária para indicar a capacidade total.</li>
</ol>
</td>
<td>
<ul>
<li>No trabalho atual, a quantidade é atualizada para a quantidade restante que deve ser separada.</li>
<li>O novo trabalho para a quantidade separada é criado e fechado.</li>
</ul></td>
<td>Não aplicável</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>Reduzir a quantidade separada de trabalho concluído (de uma carga)

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Não aplicável</td>
<td>Sim</td>
<td>
<ol>
<li>Abra a página <strong>Reduzir quantidade separada</strong> na linha de carga.</li>
<li>Insira a quantidade total para anulação da separação.</li>
<li>Selecione um local/placa de licença "mover para".</li>
</ol>
</td>
<td>
<ul> 
<li>O trabalho associado à linha de carga é cancelado.</li>
<li>O novo trabalho o movimento de estoque é criado e fechado.</li>
</ul>
</td>
<td>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>Consulte a linha anterior.</td>
<td>A quantidade é reservada novamente para o mesmo lote, assim como para o mesmo local e placa de licença (se o local for controlado pela placa de licença) que foram inseridos durante a anulação da separação.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Mover um item em um depósito

> [!NOTE]
> Essa ação de depósito se aplica somente ao movimento do tipo **Processo de criação de trabalho** , e não ao movimento por modelo.

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>A opção <strong>Permitir movimento de estoque com trabalho associado</strong> está habilitada no trabalhador.</td>
<td>Sim</td>
<td>
<ol>
<li>Inicie uma movimentação no aplicativo de depósito.</li>
<li>Insira os locais "de" e "para".</li>
</ol></td>
<td>
<ul>
<li>Em todo o trabalho existente que é afetado pelo movimento, o local de separação é atualizado para o novo local "para".</li>
<li>O novo trabalho o movimento de estoque é criado e fechado.</li>
</ul>
</td>
<td>Todas as reservas existentes que são afetadas pelo movimento da quantidade do local especificado são reservadas novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>Consulte a linha anterior.</td>
<td>Todas as reservas existentes que são afetadas pelo movimento da quantidade do local especificado são reservadas novamente para o mesmo lote, assim como para o novo local "para" e a placa de licença (se o local for controlado pela placa de licença).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>Reverter a quantidade separada de trabalho concluído (de uma carga ou uma onda)

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>Não aplicável</td>
<td>Sim</td>
<td>
<ol>
<li>Abra a página <strong>Reverter trabalho</strong>.</li>
<li>Na página de solicitação, selecione a opção <strong>Deixar os itens no local atual</strong>.</li>
</ol>
</td>
<td>Todo o trabalho associado à carga é cancelado.</td>
<td>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>Consulte a linha anterior.</td>
<td>A quantidade é reservada novamente para o mesmo lote, assim como para o local e a placa de licença onde a quantidade foi deixada no estorno.</td>
</tr>
<tr>
<td>Sim</td>
<td>
<ol>
<li>Abra a página <strong>Reverter trabalho</strong>.</li>
<li>Na página de solicitação, selecione a opção <strong>Atribuir itens a este local</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>O trabalho atual é cancelado.</li>
<li>O novo trabalho o movimento de estoque é criado e fechado.</li>
</ul>
</td>
<td>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>Consulte a linha anterior.</td>
<td>A quantidade é reservada novamente para o mesmo lote, assim como para o local e a placa de licença aos quais a quantidade foi atribuída no estorno.</td>
</tr>
<tr>
<td>Sim/Não</td>
<td>
<ol>
<li>Abra a página <strong>Reverter trabalho</strong>.</li>
<li>Na página de solicitação, selecione a opção <strong>Mover itens para este local</strong>.</li>
</ol>
</td>
<td>O estorno não é permitido.</td>
<td>Não aplicável</td>
</tr>
<tr>
<td>Sim/Não</td>
<td>
<ol>
<li>Abra a página <strong>Reverter trabalho</strong>.</li>
<li>Na página de solicitação, selecione a opção <strong>Mover itens com base em diretivas de local</strong>.</li>
</ol>
</td>
<td>O estorno não é permitido. </td>
<td>Não aplicável</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Separar uma quantidade insuficiente – registre a quantidade como fisicamente não encontrada no local/placa de licença ao executar o trabalho de separação

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Nenhum</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não</strong>.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar quantidade</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, insira <strong>Nenhuma realocação</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>O trabalho atual é fechado e a quantidade separada é 0 (zero).</li>
<li>Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</li>
</ul>
</td>
<td>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>
<ul>
<li>A ação de separação insuficiente falha e um erro é lançado.</li>
<li>O trabalho atual permanece aberto.</li>
</ul>
</td>
<td>Não aplicável</td>
</tr>
<tr>
<td rowspan='2'>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Nenhum</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Sim</strong>.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar quantidade</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, insira <strong>Nenhuma realocação</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>O trabalho atual é fechado e a quantidade separada é 0 (zero).</li>
<li>Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</li>
</ul>
</td>
<td>Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local da separação insuficiente são reservadas novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>Consulte a linha anterior.</td>
<td>Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local da separação insuficiente são removidas.</td>
</tr>
<tr>
<td>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não/Sim</strong>. Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</li>
<li>Selecione o local/placa de licença na lista.</li>
</ol>
</td>
<td>
<ul>
<li>No trabalho atual, ocorrem as seguintes ações:
<ul>
<li>A linha de separação é fechada e a quantidade separada é 0 (zero).</li>
<li>A linha de colocação é cancelada.</li>
<li>Uma nova linha de separação é criada. Ela usa o local/placa de licença que o usuário selecionou.</li>
<li>Uma nova linha de colocação é criada.</li>
</ul>
</li>
<li>Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</li>
</ul>
</td>
<td>Não aplicável</td>
</tr>
<tr>
<td>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não</strong>. Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</td>
<td>Não</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</li>
</ol>
</td>
<td>A ação de separação insuficiente falha e um erro é lançado.</td>
<td>Não aplicável</td>
</tr>
<tr>
<td>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Sim</strong>. Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</td>
<td>Não</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</li>
<li>Selecione o local/placa de licença na lista.</li>
</ol>
</td>
<td>
<ul>
<li>No trabalho atual, ocorrem as seguintes ações:
<ul>
<li>A linha de separação é fechada e a quantidade separada é 0 (zero).</li>
<li>A linha de colocação é cancelada.</li>
</ul>
</li>
<li>Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</li>
</ul>
</td>
<td>Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local/placa de licença da separação insuficiente são removidas.</td>
</tr>
<tr>
<td>Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Automática</strong>, <strong>Ajustar estoque</strong> = <strong>Sim/Não</strong> e <strong>Remover reservas</strong> = <strong>Sim/Não</strong>.</td>
<td>Não Aplicável</td>
<td>
<ol>
<li>Selecione o item de menu <strong>Separação insuficiente</strong> no aplicativo de depósito ao executar o trabalho de separação.</li>
<li>No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</li>
<li>No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação automática</strong>.</li>
</ol>
</td>
<td>A separação insuficiente que envolve a realocação automática não é permitida.</td>
<td>A separação insuficiente que envolve a realocação automática não é permitida.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>Alterar o status do estoque

> [!NOTE]
> Essa ação de depósito pode ser executada a partir de vários pontos de entrada. O exemplo mostrado aqui usa a ação **Alteração do status do estoque** na página **Disponibilidade por local**.

<table>
<thead>
<tr>
<th>Principal parâmetro de configuração</th>
<th>Quantidade de lotes disponível</th>
<th>Principais etapas do usuário</th>
<th>Trabalho de depósito</th>
<th>Reserva de lotes confirmada na ordem</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Na guia <strong>Depósito</strong>, no registro <strong>Depósito</strong>, o campo <strong>Remover reservas e marcações</strong> está definido como <strong>Reservas</strong> ou <strong>Marcações e reservas</strong>.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione um local específico.</li>
<li>Selecione uma linha que tenha um item específico, um local e uma placa de licença (se o local for controlado pela placa de licença).</li>
<li>Selecione <strong>Alteração do status do estoque</strong>.</li>
<li>Defina o campo <strong>Status do estoque</strong> como <strong>Bloqueio</strong>.</li>
</ol>
</td>
<td>As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</td>
<td>
<ul>
<li>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</li>
<li>Duas transações de estoque do tipo <strong>Alteração do status do estoque</strong> são criadas para representar a alteração na dimensão de status do estoque.</li>
<li>Uma transação de estoque do tipo <strong>Bloqueio de estoque</strong> e do tipo de saída <strong>Qtd. reservada</strong> é criada para representar a reservar da quantidade bloqueada.</li>
</ul>
</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</td>
<td>
<ul>
<li>A reserva é removida.</li>
<li>Duas transações de estoque do tipo <strong>Alteração do status do estoque</strong> são criadas para representar a alteração na dimensão de status do estoque.</li>
<li>Uma transação de estoque do tipo <strong>Bloqueio de estoque</strong> e do tipo de saída <strong>Qtd. reservada</strong> é criada para representar a reservar da quantidade bloqueada.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>Na guia <strong>Depósito</strong>, no registro <strong>Depósito</strong>, o campo <strong>Remover reservas e marcações</strong> está definido como <strong>Nenhum</strong>.</td>
<td>Sim</td>
<td>
<ol>
<li>Selecione um local específico.</li>
<li>Selecione uma linha que tenha um item específico, um local e uma placa de licença (se o local for controlado pela placa de licença).</li>
<li>Selecione <strong>Alteração do status do estoque</strong>.</li>
<li>Defina o campo <strong>Status do estoque</strong> como <strong>Bloqueio</strong>.</li>
</ol>
</td>
<td>As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</td>
<td>A quantidade é reservada novamente para o mesmo lote. O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</td>
</tr>
<tr>
<td>Não</td>
<td>Consulte a linha anterior.</td>
<td>As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</td>
<td>Alterações de status do estoque não são permitidas.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Limitações

- A funcionalidade de reserva de dimensão no nível de depósito flexível não oferece suporte aos seguintes recursos:

    - Gerenciamento de peso variável
    - Estoque físico negativo
    - Reserva em relação ao fornecimento solicitado
    - Ordens de transferência e separação de matéria-prima

- A regra de consolidação de contêineres para empacotamento por unidade de diretiva tem limitações. Para as reservas confirmadas na ordem, é recomendável não usar os modelos de compilação de contêiner em que o campo **Empacotar por unidade de diretiva** esteja habilitado. No design atual, as diretivas de local não são usadas quando o trabalho de depósito é criado. Portanto, somente a menor unidade no grupo de sequências de unidades (a unidade de estoque) é aplicada durante a etapa da onda de transporte em contêineres.
