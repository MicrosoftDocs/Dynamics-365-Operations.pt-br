---
title: Gerenciamento de qualidade para processos de depósito
description: Este artigo fornece informações sobre o recurso Gestão de qualidade para processos de depósito. Ele amplia os recursos de gerenciamento da qualidade e permite que os usuários integrem controles de amostragem de item ao processo de recebimento do depósito, usando os processos de gerenciamento de depósito (WMS).
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-04-02
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: b4d0b09ea4bee58799a659217e2236fe74102949
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335425"
---
# <a name="quality-management-for-warehouse-processes"></a>Gerenciamento de qualidade para processos de depósito

[!include [banner](../includes/banner.md)]

O recurso _Gerenciamento de qualidade para processos de depósito_ permite integrar controles de amostragem de item ao processo de recebimento do depósito, usando os processos de gerenciamento de depósito (WMS). O trabalho de depósito pode ser gerado automaticamente para mover o estoque para o local de controle de qualidade, com base em uma porcentagem ou quantidade fixa ou com base na posição que a placa de licença ocupa. Após a conclusão de uma ordem de qualidade, o trabalho pode ser gerado automaticamente para mover o estoque para o próximo local no processo, dependendo dos resultados da qualidade.

O recurso _Gerenciamento de qualidade para processos de depósito_ estende as possibilidades do recurso básico de gerenciamento da qualidade. Ele fornece a opção de criar ordens de qualidade para o estoque enviado ao local de controle de qualidade, embora nem sempre sejam necessárias. Portanto, ele permite um processo simples de controle de qualidade baseado no trabalho de depósito.

## <a name="turn-on-the-quality-management-for-warehouse-processes-feature"></a>Ativar o recurso Gestão de qualidade para processos de depósito

Para poder usar esse recurso, você deve habilitá-lo para o seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Gestão de qualidade para processos de depósito*

## <a name="key-benefits"></a>Principais benefícios

O recurso _Gestão de qualidade para processos de depósito_ gera automaticamente trabalho como parte do processo de recebimento, para mover a quantidade de estoque necessária no controle de qualidade para um local de controle de qualidade. Se a quantidade recebida exceder a quantidade necessária no controle de qualidade (de acordo com a configuração de amostragem do item), a quantidade excedente será movida para um local de entrada definido na configuração da diretiva de localização. Após a validação da ordem de qualidade, o trabalho será gerado automaticamente para mover a quantidade da ordem de qualidade para um novo local de entrada ou devolução, com base no resultado da validação e na configuração da diretiva de localização. A geração automática de trabalho que possui apenas a quantidade que deve ser movida para e do controle de qualidade fornece uma experiência de processo integrada.

> [!NOTE]
> Quando o recurso _Gestão de qualidade para processos de depósito_ está ativado, você ainda pode tirar proveito do processo manual. No processo manual, a movimentação de estoque e a movimentação por modelo são usadas para fazer com que um funcionário de depósito acione a criação do trabalho de depósito para mover o estoque de um local de controle de qualidade para um novo local. Você também pode configurar uma diretiva de localização de entrada que mova o estoque inteiramente de um local de recebimento para um local de controle de qualidade sem considerar a configuração de amostragem de item.

## <a name="quality-management-and-the-quality-management-for-warehouse-processes-feature"></a>Gestão de qualidade e o recurso Gestão de qualidade para processos de depósito

Quando o recurso _Gestão de qualidade para processos de depósito_ é ativado, ele altera a configuração das principais entidades de gerenciamento de depósito e gerenciamento de qualidade. A ilustração a seguir fornece uma visão geral das entidades que permitem ordens de qualidade para os processos de depósito. O texto entre parênteses indica ações sugeridas quando o gerenciamento de qualidade foi aplicado antes que o recurso _Gestão de qualidade para processos de gerenciamento de depósito_ fosse ativado.

![Entidades de gerenciamento de qualidade.](media/quality-management-entity-diagram.png "Entidades de gerenciamento de qualidade")

## <a name="enablers-the-quality-item-sampling-and-quality-order-work-order-types"></a>Ativadores: os tipos de amostragem de item de qualidade e ordem de serviço de ordem de qualidade

O recurso _Gestão de qualidade para processos de depósito_ apresenta dois tipos de ordem de serviço que permitem o processo de criação de trabalho:

- **Amostragem de item de qualidade** – Este tipo de ordem de serviço é usado para criar um trabalho que move o estoque registrado para o controle de qualidade.
- **Ordem de qualidade** – Este tipo de ordem de serviço é usado para criar um trabalho que move o estoque do controle de qualidade para um novo local, com base na configuração da diretiva de localização.

### <a name="work-classes-location-directives-and-work-templates"></a>Classes de trabalho, diretivas de localização e modelos de trabalho

Os tipos de ordem de serviço _Amostragem de item de qualidade_ e _Ordem de qualidade_ são consumidos por diretivas de localização, classes de trabalho e modelos de trabalho.

Antes que o trabalho de depósito possa ser gerado automaticamente para mover o estoque para o controle de qualidade, siga estas etapas para configurar seu sistema.

1. Crie classes de trabalho separadas para os tipos de ordem de serviço _Amostragem de item de qualidade_ e _Ordem de qualidade_. Dessa forma, você garante que o trabalho apropriado possa ser gerado automaticamente com base nos dois tipos de ordem de serviço e que esse trabalho possa ser executado usando o aplicativo móvel do Gerenciamento de Depósito.
1. Configure um modelo de trabalho para cada tipo de ordem de serviço:

    - Configure um modelo de trabalho que use o tipo de ordem de serviço _Amostragem de item de qualidade_ para mover automaticamente o estoque registrado para um local de controle de qualidade.
    - Configure um modelo de trabalho que use o tipo de ordem de trabalho _ordem de qualidade_ para mover o estoque de um local de controle de qualidade após a conclusão do controle de qualidade.

1. Para cada tipo de ordem de serviço, configure diretivas de localização que apliquem os locais de controle de qualidade corretos para os quais o estoque deve ser movido. Após a conclusão do controle de qualidade, a diretiva de localização do tipo de ordem de serviço _Ordem de qualidade_ garante que um novo local de destino seja selecionado para que o estoque possa ser movido para fora do local de controle de qualidade.
1. Configure os itens de menu relevantes do dispositivo móvel para apoiar a movimentação do estoque recebido para o local do controle de qualidade e a movimentação do estoque que passa ou falha no controle de qualidade do local de controle de qualidade para um novo local.

Para um exemplo passo a passo que mostra como concluir essa configuração, consulte o [cenário de exemplo](#example-scenario) no final deste artigo.

## <a name="enable-a-warehouse-for-quality-management"></a>Habilitar um depósito para gerenciamento da qualidade

Antes que o recurso _Gestão de qualidade para processos de depósito_ possa ser aplicado a um depósito específico, você deve seguir as etapas a seguir para disponibilizar o recurso desse depósito.

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Selecione o depósito para habilitar o gerenciamento de qualidade.
1. Na FastTab **Depósito**, defina a opção **Habilitar ordem de qualidade para processos de depósito** como _Sim_. (Observe que essa opção pode ser definida como _Sim_ apenas para depósitos que usam processos de gerenciamento de depósito (WMS).)

Quando a opção **Habilitar ordem de qualidade para processos de depósito** é definida como _Sim_, a configuração da associação de qualidade monitora se o recurso _Gestão de qualidade para processos de depósito_ é realmente aplicado ao depósito selecionado. Você pode alterar a configuração da opção para _Não_ a qualquer momento. Nesse caso, o recurso não será mais aplicado ao depósito, independentemente da configuração da associação de qualidade.

## <a name="quality-control"></a>Controle de qualidade

O recurso _Gestão de qualidade para processos de depósito_ controla várias configurações importantes para associações de qualidade e amostragem de item.

### <a name="quality-associations"></a>Associações de qualidade

Cada [registro de associação de qualidade](enable-quality-management.md) também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas. Para configurar um registro de associação de qualidade, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Associações de qualidade**.
1. Crie ou selecione a entrada de associação de qualidade para o item ou grupo com o qual você está trabalhando ou para todos os itens.
1. Na FastTab **Condições**, defina o campo **Tipo de depósito aplicável** para um dos seguintes valores:

    - **Gestão de qualidade somente para processos de depósito** – Ative o recurso _Gestão de qualidade para processos de depósito_. Você pode selecionar esse valor apenas se o tipo de referência for *Compra* ou *Produção*.
    - **Todos** – Desative o recurso _Gestão de qualidade para processos de depósito_. Selecione esse valor para todos os tipos de referência, exceto *Compra* e *Produção*.

> [!NOTE]
> O recurso _Gerenciamento de qualidade para processos de depósito_ entra em vigor somente se o item na linha de documento de origem usar processos gerenciamento de depósito (WMS) e se a opção **Habilitar ordem de qualidade para processos de depósito** estiver definida como _Sim_ para o depósito na linha do documento de origem.

À medida que cada item é registrado (ou relatado como concluído), o sistema determina quais associações de qualidade se aplicam a ele.

Quando o recurso _Gestão de qualidade para processos de depósito_ é ativado, o tipo de depósito aplicável é inserido logicamente no quarto grupo de pesquisa da hierarquia de pesquisa da associação de qualidade. A tabela a seguir fornece uma representação lógica da hierarquia de pesquisa.

| Grupo de pesquisa | descrição |
|---|---|
| Grupo 1 | Para cada associação de qualidade, verifique os valores **Tipo de referência**, **Tipo de evento** e **Correspondência de execução** em relação ao item. Se houver uma correspondência na linha do documento de origem, Acesse o grupo 2. |
| Grupo 2 | Para cada associação de qualidade, verifique o valor **Código do item** (_Tabela_, _Grupo_ ou _Todos_) em relação ao item. _Tabela_ é mais específica que _Grupo_ e _Grupo_ é mais específico que _Todos_. Se houver uma correspondência para _Tabela_ (um item específico), Acesse o grupo 3. Se não houver correspondência para _Tabela_, procure uma correspondência para _Grupo_. Se não houver correspondência para _Grupo_, _Todos_ se aplica. Se houver uma correspondência, Acesse o grupo 3. |
| Grupo 3 | Para cada associação de qualidade, verifique os valores **Código da conta** e **Código do recurso** em relação ao item. A lógica aplicada é semelhante à lógica aplicada ao valor **Código do item**. |
| Grupo 4 | Para cada associação de qualidade, verifique o valor **Tipo de depósito aplicável** (_Gestão de qualidade somente para processos de depósito_ ou _Todos_) em relação ao item. Se a opção **Habilitar ordem de qualidade para processos de depósito** estiver definida como _Sim_ para o depósito no documento de origem e o item na linha do documento de origem estiver definido como _Usar processos de gerenciamento de depósito_, as associações onde há correspondência para _Gestão de qualidade somente para processos de depósito_ e as associações onde há correspondência para _Todos_ serão aplicáveis em paralelo, se ambos os tipos existirem. Se a opção **Habilitar ordem de qualidade para processos de depósito** estiver definida como _Não_ para o depósito no documento de origem e o item na linha do documento de origem estiver definido como _Usar processos de gerenciamento de depósito_, somente o gerenciamento da qualidade será aplicável. |

Por exemplo, você definiu um depósito em que a opção **Habilitar ordem de qualidade para processos de depósito** está definida como _Sim_ e você tem duas associações de qualidade definidas para o tipo de referência *Compra*: uma para todos os itens e outra para o tipo de evento *Registro*. A única diferença entre as duas associações de qualidade é o valor **Tipo de depósito aplicável**: é definido como _Todos_ para uma associação de qualidade e _Gestão de qualidade somente para processos de depósito_ para a outra. Nesse caso, ambas as associações de qualidade são igualmente específicas e serão aplicáveis.

O valor do campo **Grupo de teste** para as associações de qualidade também é um fator. Esse campo define o procedimento de teste que deve ser aplicado. Se o valor **Grupo de teste** é o mesmo para as duas associações, apenas uma ordem de qualidade será criada, para a associação da qualidade em que o valor **Tipo de depósito aplicável** é _Gestão de qualidade somente para processos de depósito_. Se o valor **Grupo de teste** não for o mesmo para as duas associações, serão criados duas ordens de qualidade. A primeira ordem de qualidade será criada para a associação de qualidade em que o valor **Tipo de depósito aplicável** é _Gestão de qualidade somente para processos de depósito_. A segunda ordem de qualidade será criada para a associação de qualidade em que o valor **Tipo de depósito aplicável** é _Todos_.

> [!NOTE]
> O valor _Gestão de qualidade somente para processos de depósito_ é considerado mais específico que _Todos_ quando os critérios para as associações de qualidade dos grupos 1 e 2 são os mesmos e quando o grupo de teste é o mesmo. Duas ordens de qualidade serão criadas somente quando os grupos de teste forem diferentes.

#### <a name="reference-types"></a>Tipos de referências

Quando o valor **Tipo de referência** é _Compra_ e o valor **Tipo de depósito aplicável** é _Gestão de qualidade somente para processos de depósito_, o campo **Tipo de evento** na FastTab **Processo** deve ser definido como _Registro_. O _Registro_ é o único tipo de evento compatível com o tipo de referência _Purchase_ quando você está usando o recurso _Gestão de qualidade para processos de depósito_.

#### <a name="quality-processing-policy"></a>Política de processamento de qualidade

O recurso _Gestão de qualidade para processos de depósito_ permite que o trabalho seja criado com base apenas na amostragem de itens. Portanto, ele permite um processo leve. O estoque em que o trabalho é criado depende da amostragem do item que está vinculada à associação da qualidade. Quando o processo simples é usado, depois que um trabalhador coloca a quantidade no local de controle de qualidade, o departamento de qualidade pode criar manualmente uma ordem de qualidade, se for necessário.

O campo **Política de processamento de qualidade** na FastTab **Processo de ordem de qualidade** controla se uma ordem de qualidade também é gerada quando o trabalho é criado para mover um item para o local do controle de qualidade. Esse campo pode ser definido como _Criar ordem de qualidade_ ou _Criar somente trabalho_. O valor padrão é _Criar ordem de qualidade_.

> [!NOTE]
> Independentemente de você criar ordens de qualidade manual ou automaticamente, o sistema gera automaticamente trabalho para mover itens para fora do local de controle de qualidade quando a ordem de qualidade é marcada como validada.

A criação do trabalho da ordem da qualidade não está relacionada à configuração da associação da qualidade. Se existir um modelo de trabalho com um valor de **Tipo de ordem de serviço** de *Ordem de qualidade* e se os critérios de consulta forem atendidos para esse modelo de trabalho, a validação de uma ordem de qualidade acionará a criação do trabalho da ordem de qualidade.

#### <a name="referenced-item-sampling"></a>Amostragem de item referenciado

Cada associação de qualidade deve fazer referência a uma amostragem de item. Uma amostragem de item define a quantidade que será enviada para controle de qualidade. Ela pode ser configurada para se aplicar apenas à associações de qualidade em que o valor **Tipo de depósito aplicável** é _Gestão de qualidade somente para processos de depósito_. Se o valor **Escopo de amostragem** de uma amostragem de item for _Carga_ ou _Remessa_ ou o valor **Especificação da quantidade** para _Placa de licença completa_, a amostragem de item pode ser referenciada apenas por associações de qualidade em que o valor **Tipo de depósito aplicável** é _Gestão de qualidade somente para processos de depósito_.

Se você definir uma amostragem de item que use o tipo de depósito aplicável _Gestão de qualidade somente para processos de depósito_, você receberá um erro se tentar referenciá-lo usando uma associação de qualidade que não usa o recurso _Gestão de qualidade para processos de depósito_.

> [!NOTE]
> A amostragem de item que usa bloqueio completo não é compatível com associações de qualidade em que o campo **Tipo de depósito aplicável** está definido como _Gestão de qualidade somente para processos de depósito_.

### <a name="item-sampling"></a>Amostragem de item

A amostragem de item controla a frequência com que os itens são enviados para controle de qualidade. O recurso _Gestão de qualidade para processos de depósito_ apresenta o conceito de _escopo de amostragem de item_. O sistema usa o escopo de amostragem de item quando avalia se e como as ordens de qualidade e/ou a amostragem de item de qualidade e o trabalho da ordem de qualidade devem ser criados.

Para configurar a amostragem de item, Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Amostragem de item** e defina o campo **Escopo de amostragem** para um dos seguintes valores:

- **Ordem** – A linha do documento de origem será a base para avaliar se e como os pedidos de qualidade e/ou a amostragem de item de qualidade funcionam e o trabalho da ordem de qualidade é criado. Esse valor é o valor padrão e, quando selecionado, o sistema funciona da mesma maneira que quando o recurso _Gestão de qualidade para processos de depósito_ não está ativado.
- **Carga** – As cargas serão usadas como base para avaliar se e como uma ordem e/ou trabalho de qualidade é criado. Esse valor está disponível apenas quando o recurso _Gestão de qualidade para processos de depósito_ está ativado.
- **Remessa** – As remessas serão usadas como base para avaliar se e como uma ordem de qualidade e/ou trabalho é criado. Esse valor está disponível apenas quando o recurso _Gestão de qualidade para processos de depósito_ está ativado.

> [!NOTE]
> Quando o campo **Escopo de amostragem** é definido como *Carga* ou *Remessa*, a entidade de carga e as entidades de remessa serão usadas, se estiverem disponíveis. Se elas não estiverem disponíveis, a entidade da ordem será usada.

O recurso _Gestão de qualidade para processos de depósito_ também apresenta o valor *Placa de licença completa* do campo **Especificação da quantidade**. Esse valor permite a criação de trabalhos de ordens de qualidade e amostragem de item de qualidade, com base em placas de licença. Quando você seleciona esse valor, ocorrem as seguintes alterações:

- A opção **Contagem de intervalos por item** e o campo **Por enésima placa de licença** na FastTab **Processo** ficam disponíveis.
- O campo **Valor** na FastTab **Quantidade de amostragem** se torna indisponível.
- As opções **Quantidade por atualização**, **Local** e **Placa de licença** são todas definidas como *Sim* e as configurações não podem ser alteradas.

A opção **Contagem de intervalos por item** controla se a contagem de placas é avaliada por item ou por todos os itens no escopo de amostragem. As variantes de produtos são tratadas como o mesmo item. Essa opção também controla se a contagem de placas de licença é redefinida para cada item.

O valor do campo **Por enésima placa de licença** controla a frequência com que as ordens de qualidade são criadas em relação ao número de itens registrados. Por exemplo, um valor de *3* enviará cada terceiro item ao controle de qualidade, começando com o primeiro item. O valor deve ser maior que 0 (zero).

Enquanto os trabalhadores recebem itens usando o aplicativo móvel do Gerenciamento de Depósito, o sistema valida se uma associação de qualidade está configurada para cada item recebido. Se uma associação de qualidade for configurada, o sistema utilizará o registro de amostragem de item configurado para essa associação de qualidade para determinar como criar ordens de qualidade, trabalho de amostragem de item de qualidade e trabalho de ordem de compra.

> [!NOTE]
> Quando o registro de recebimento é feito no cliente Web (usando a pequena página de registro ou o diário de entrada de itens para linhas de ordens), nenhum trabalho de amostragem de item de qualidade ou trabalho de ordens será criado, independentemente da configuração. Em vez disso, para itens que correspondem a uma associação de qualidade, a amostragem de item referenciado será usada para controlar apenas a criação de ordens de qualidade.

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exemplos de geração automática de ordens de qualidade

Os exemplos a seguir mostram como a configuração de uma associação de qualidade e uma amostragem de item associada afeta a geração de ordens de qualidade quando o campo **Tipo de depósito aplicável** é definido como _Gestão de qualidade somente para processos de depósito_.

Quando o valor **Especificação da quantidade** for _Placa de licença completa_, o campo **Por enésima placa de licença** controla para qual trabalho de amostragem de item de qualidade de placas de licença é criado. A primeira placa sempre passa para o controle de qualidade e, em seguida, o valor desse campo especifica que todas as *enésimas* placas de licença após essa placa também devem ir.

O valor **Tipo de referência** para os seguintes exemplos é _Compra_ e o valor **Tipo de evento** é *Registro*.

| Escopo de amostragem | Especificação de quantidade | Quantidade por atualização | Por dimensão de armazenamento | Dividir contagem por item | Placa de licença por enésimo | Resultado |
|---|---|---|---|---|---|---|
| Ordem | Placa de licença completa | Sim _(bloqueado/não editável)_ | <p>Local: Sim</p><p>Placa de licença: Sim _(bloqueado/não editável)_</p> | Não | 3 | <p>**Quantidade da linha da ordem: 100 EA**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP1<p>Trabalho de amostragem de item de qualidade para 20 EA</p><p>Ordem de qualidade 1 para 20 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP2<p>Trabalho de ordem de compra para 20 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP3<p>Trabalho de ordem de compra para 20 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP4<p>Trabalho de amostragem de item de qualidade para 20 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP5<p>Trabalho de ordem de compra para 20 EA (armazenamento)</p></li></ol> |
| Ordem | Quantidade fixa = 1 | Sim | <p>Local: Sim</p><p>Placa de licença: Sim</p> | Não | Não Aplicável | <p>**Quantidade da linha da ordem: 100**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP1<p>Trabalho de amostragem de item de qualidade para 1 EA</p><p>Ordem de qualidade 1 para 1 EA</p><p>Trabalho de ordem de compra para 19 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP2<p>Trabalho de amostragem de item de qualidade para 1 EA</p><p>Ordem de qualidade 1 para 1 EA</p><p>Trabalho de ordem de compra para 19 (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP3<p>Trabalho de amostragem de item de qualidade para 1 EA</p><p>Ordem de qualidade 1 para 1 EA</p><p>Trabalho de ordem de compra para 19 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP4<p>Trabalho de amostragem de item de qualidade para 1 EA</p><p>Ordem de qualidade 1 para 1 EA</p><p>Trabalho de ordem de compra para 19 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 20 EA, LP5<p>Trabalho de amostragem de item de qualidade para 1 EA</p><p>Ordem de qualidade 1 para 1 EA</p><p>Trabalho de ordem de compra para 19 EA (armazenamento)</p></li></ol> |
| Ordem | Porcentagem = 10 | Não | <p>Local: Não</p><p>Placa de licença: Não</p> | Não | Não Aplicável | <p>**Quantidade da linha da ordem: 100 EA**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP1<p>Trabalho de amostragem de item de qualidade para 10 EA</p><p>Ordem de qualidade 1 para 10 EA</p><p>Trabalho de ordem de compra para 40 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP2<p>Trabalho de ordem de compra para 50 EA (armazenamento)</p></li></ol> |
| Carregar | Porcentagem = 5 | Sim _(bloqueado/não editável)_ | <p>Local: Não</p><p>Placa de licença: Não</p> | Não | Não Aplicável | <p>**Quantidade da linha da ordem: 500 EA**</p><p>**Duas cargas: primeira carga 200 EA, segunda carga 300 EA**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para a primeira carga de 100 EA<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 95 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para a primeira carga de 100 EA<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 95 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para a segunda carga de 300 EA<p>Trabalho de amostragem de item de qualidade para 15 EA</p><p>Ordem de qualidade 1 para 15 EA</p><p>Trabalho de ordem de compra para 285 EA (armazenamento)</p></li></ol> |
| Ordem | Porcentagem = 10 | Sim | <p>Local: Sim</p><p>Placa de licença: Sim</p> | Não | Não Aplicável | <p>**Quantidade da linha da ordem: 100**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP1<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 45 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP2<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 45 (armazenamento)</p></li></ol> |
| Carregar | Placa de licença completa | Sim _(bloqueado/não editável)_ | <p>Local: Sim</p><p>Placa de licença: Sim _(bloqueado/não editável)_</p> | Não | 3 | <p>**Dois itens:**</p><ul><li>**Quantidade da linha de ordem para o item A: 120 EA (4 paletes)**</li><li>**Quantidade da linha de ordem para o item B: 90 EA (3 paletes)**</li></ul><p>**Uma carga, duas linhas de carga com cada linha de ordem**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP1<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP2<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP3<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP4<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item B, 30 EA, LP5<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item B, 30 EA, LP6<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP7<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li></ol> |
| Carregar | Placa de licença completa | Sim _(bloqueado/não editável)_ | <p>Local: Sim</p><p>Placa de licença: Sim _(bloqueado/não editável)_</p> | Sim | 3 | <p>**Dois itens:**</p><ul><li>**Quantidade da linha de ordem para o item A: 120 EA (4 paletes)**</li><li>**Quantidade da linha de ordem para o item B: 90 EA (3 paletes)**</li></ul><p>**Uma carga, duas linhas de carga com cada linha de ordem**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP1<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP2<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP3<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP4<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item B, 30 EA, LP5<p>Trabalho de amostragem de item de qualidade para 30 EA</p><p>Ordem de qualidade 1 para 30 EA</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item B, 30 EA, LP6<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 30 EA, LP7<p>Trabalho de ordem de compra para 30 EA (armazenamento)</p></li></ol> |
| Carregar | Porcentagem = 10 | Sim _(bloqueado/não editável)_ | <p>Local: Não</p><p>Placa de licença: Não</p> | Não | Não Aplicável | <p>**Quantidade da linha da ordem: 100 EA**</p><p>**Nenhuma carga é criada. O escopo da ordem é aplicado.**</p><ol><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP1<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 45 EA (armazenamento)</p></li><li>Registrar o recebimento no aplicativo móvel do Gerenciamento de Depósito para item A, 50 EA, LP2<p>Trabalho de amostragem de item de qualidade para 5 EA</p><p>Ordem de qualidade 1 para 5 EA</p><p>Trabalho de ordem de compra para 45 EA (armazenamento)</p></li></ol> |

Quando um trabalhador valida uma das ordens de qualidade mostradas na tabela anterior, o sistema gera automaticamente o trabalho da ordem de qualidade para mover o estoque do local do controle de qualidade para o local definido na diretiva de localização para o tipo de ordem de serviço _Ordem de qualidade_. Você pode configurar qualquer local para esse fim, como um local de devolução ou armazenamento, dependendo do resultado do teste da ordem de qualidade. Para obter um exemplo dessa configuração, consulte o [exemplo de cenário](#example-scenario) no final deste artigo.

É possível reabrir uma ordem de qualidade que já foi validada, desde que o trabalho da ordem de qualidade relacionada à movimentação do estoque do local do controle de qualidade não tenha um valor **Status de trabalho** de *Fechado* ou *Em andamento*.

## <a name="process-insights-when-multiple-quality-associations-coexist"></a>Insights do processo quando várias associações de qualidade coexistem

Mais de uma associação de qualidade pode ser definida e aplicada à mesma linha de documento de origem, e o campo **Tipo de depósito aplicável** pode ser definido como _Gestão de qualidade somente para processos de depósito_ para algumas dessas associações de qualidade e _Todos_ para outras.

No exemplo a seguir, o valor **Tipo de referência** é _Compra_.

1. A primeira associação de qualidade é configurada da seguinte maneira:

    - **Tipo de depósito aplicável:** *Gestão de qualidade somente para processos de depósito*
    - **Código do item:** *A0001*
    - **Código da conta:** *Todos*
    - **Grupo de teste:** *Anexo*
    - **Amostragem de item:** *5 pcs*

1. A segunda associação de qualidade é configurada da seguinte maneira:

    - **Tipo de depósito aplicável:** *Todos*
    - **Código do item:** *Todos*
    - **Código da conta:** *Todos*
    - **Grupo de teste:** *Anexo*
    - **Amostragem de item:** *1 pcs*

1. A terceira associação de qualidade é configurada da seguinte maneira:

    - **Tipo de depósito aplicável:** *Gestão de qualidade somente para processos de depósito*
    - **Código do item:** *Todos*
    - **Código da conta:** *104*
    - **Grupo de teste:** *Impedância*
    - **Amostragem de item:** *Cada segunda placa de licença* (Essa configuração significa que a primeira, terceira, quinta, e assim por diante, placas de licença recebidas criarão uma ordem de qualidade.)

1. A quarta associação de qualidade é configurada da seguinte maneira:

    - **Tipo de depósito aplicável:** *Todos*
    - **Código do item:** *Todos*
    - **Código da conta:** *Todos*
    - **Grupo de teste:** *Impedância*
    - **Amostragem de item:** *5 pcs*

1. A quinta associação de qualidade é configurada da seguinte maneira:

    - **Tipo de depósito aplicável:** *Todos*
    - **Código do item:** *Todos*
    - **Código da conta:** *Todos*
    - **Grupo de teste:** *Cone*
    - **Amostragem de item:** *10%*

Uma ordem de compra para uma quantidade de 10 do item A0001 agora é criada para o fornecedor 104. Em seguida, uma linha da ordem de compra com uma quantidade de 10 é registrada como recebida em uma placa de licença usando o aplicativo móvel do Gerenciamento de Depósito. Este é o resultado:

- Há uma ordem de qualidade da primeira associação de qualidade para o grupo de teste *Anexo*. A quantidade é 5. Não há ordem de qualidade da segunda associação de qualidade, porque os critérios para a primeira associação de qualidade são mais específicos em relação ao grupo *Anexo*.
- Há uma ordem de qualidade da terceira associação de qualidade para o grupo de teste *Impedância*. A quantidade é 10. Não há ordem de qualidade da quarta associação de qualidade, porque os critérios para a primeira associação de qualidade são mais específicos em relação ao grupo *Impedância*.
- Há uma ordem de qualidade da quinta associação de qualidade para o grupo de teste *Cone*. A quantidade é 1.

Além da criação de uma ordem de qualidade para cada uma das três associações de qualidade, também é criado o trabalho de amostragem de item de qualidade. A quantidade registrada é de apenas 10. Entretanto, dada a configuração da amostragem de item, a soma das quantidades de ordem de qualidade criadas para o tipo de depósito aplicável *Gestão de qualidade somente para processos de depósito* é 16, que excede a quantidade física registrada de 10. Portanto, o trabalho não será criado para as quantidades completas de ordens de qualidade (16), porque apenas 10 estão fisicamente disponíveis para movimentação para o local do controle de qualidade. A prioridade usada para criar o trabalho de amostragem de item de qualidade segue a ordem de criação da ordem de qualidade:

- **Primeira ordem de qualidade (quantidade = 5):** o trabalho de amostragem de item de qualidade é criado para 5. Uma quantidade de 5 (10 – 5) agora permanece para a criação subsequente do trabalho de amostragem de item de qualidade.
- **Segunda ordem de qualidade (quantidade = 10):** o trabalho de amostragem de item de qualidade é criado para 5. Uma quantidade de 0 (zero) agora permanece para a criação subsequente do trabalho de amostragem de item de qualidade.
- **Terceira ordem de qualidade (quantidade = 1):** nenhum trabalho de amostragem de item de qualidade é criado.

Como parte do processo de criação das ordens de qualidade, é criado um bloqueio de estoque de uma quantidade de 10. Esse bloqueio de estoque é referenciado em cada uma das três ordens de qualidade. A soma das quantidades da ordem de qualidade é 16.

Quando as ordens de qualidade são validadas, o sistema tenta criar um trabalho de ordem de qualidade para cada ordem de qualidade validada. Como a soma das quantidades de ordens de qualidade excede a quantidade que está realmente bloqueada e, portanto, disponível para criação de trabalho, o trabalho de ordens de qualidade não pode ser criado para as quantidades completas de ordens de qualidade, conforme mostrado aqui. (Este exemplo continua o exemplo anterior.)

1. **Valide a segunda ordem de qualidade criada (quantidade = 10). O trabalho da ordem de qualidade é criado para uma quantidade de 4.**

    A criação do trabalho da ordem de qualidade é acionada por uma alteração na quantidade de bloqueio de estoque. Como a soma das quantidades da ordem de qualidade era 16, a validação de uma quantidade de 10 fará com que as quantidades restantes da ordem de qualidade sejam validadas como iguais a 6. A quantidade de bloqueio de estoque é reduzida de 10 para 6. A quantidade reduzida de 4 é alocada para a criação do trabalho da ordem de qualidade.

2. **Valide a primeira ordem de qualidade criada (quantidade = 5). O trabalho da ordem de qualidade é criado para uma quantidade de 5.**

    A criação do trabalho da ordem de qualidade é acionada por uma alteração na quantidade de bloqueio de estoque. Como a soma das quantidades da ordem de qualidade era 6, a validação de uma quantidade de 5 fará com que as quantidades restantes da ordem de qualidade sejam validadas como iguais a 1. A quantidade de bloqueio de estoque é reduzida de 6 para 1. A quantidade reduzida de 5 é alocada para a criação do trabalho da ordem de qualidade.

3. **Valide a terceira ordem de qualidade criada (quantidade = 1). O trabalho da ordem de qualidade é criado para uma quantidade de 1.**

    A criação do trabalho da ordem de qualidade é acionada por uma alteração na quantidade de bloqueio de estoque. Como a soma das quantidades da ordem de qualidade era 1, a validação de uma quantidade de 1 fará com que as quantidades restantes da ordem de qualidade sejam validadas como iguais a 0 (zero). O bloqueio de estoque é removido (ou seja, a quantidade de bloqueio de estoque é reduzida de 1 para 0). A quantidade reduzida de 1 é alocada para a criação do trabalho da ordem de qualidade.

> [!NOTE]
> A criação do trabalho da ordem de qualidade depende da quantidade de bloqueio de estoque referenciada em uma ou mais ordens de qualidade. Se a soma das quantidades da ordem de qualidade exceder a quantidade de bloqueio de estoque referenciada, a ordem na qual as ordens de qualidade são validadas determina a criação do trabalho da ordem de qualidade.

## <a name="canceling-quality-item-sampling-work"></a>Cancelamento do trabalho de amostragem de item de qualidade

Você pode cancelar o trabalho criado para a amostragem de item de qualidade. Para controlar o que ocorre quando esse trabalho é cancelado, siga as etapas a seguir.

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral**, na FastTab **Trabalho**, defina a opção **Cancelar registro do recebimento ao cancelar o trabalho** para um dos seguintes valores:

    - **Sim** – Quando o trabalho de amostragem de item de qualidade é cancelado, a ordem de qualidade associada é excluída e o estoque não é registrado.
    - **Não** – Quando o trabalho de amostragem de item de qualidade não é cancelado, a ordem de qualidade associada não é excluída e o estoque não é registrado.

## <a name="cross-docking"></a>Distribuição integrada

Você pode ter uma configuração de associação de qualidade que crie um trabalho de amostragem de item. No entanto, quando existe distribuição integrada em paralelo com uma associação de qualidade que cria um trabalho de amostragem de item de qualidade, se houver quantidade suficiente para satisfazer a distribuição integrada, apenas o trabalho de amostragem de item é criado. Nos casos em que a opção **Habilitar ordem de qualidade para processos de depósito** for configurada como _Sim_ para o depósito de recebimento e o **Tipo de depósito aplicável** é definido como _Gestão de qualidade somente para processos de depósito_ para uma associação de qualidade, a criação do trabalho de amostragem de item de qualidade tem precedência em relação à criação do trabalho de distribuição integrada. Se a quantidade exceder a necessidade de distribuição integrada, o sistema ainda criará apenas o trabalho de amostragem de item.

## <a name="destructive-testing"></a>Teste destrutivo

Você pode definir um grupo de teste que executa testes destrutivos. No caso de um teste destrutivo, a suposição é que, independentemente do resultado do teste, a quantidade do item testado será destruída como parte do teste. A maneira como o recurso _Gestão de qualidade para processos de depósito_ oferece suporte a testes destrutivos se assemelha àquela como o gerenciamento de qualidade oferece suporte a esse teste quando o recurso não está ativado. Antes que a ordem de qualidade possa ser validada, o controlador de qualidade deve especificar o local de retirada para a quantidade que foi destruída. Você pode registrar a seleção na página de ordens de qualidade, selecionando **Estoque \> Separar** no Painel de Ação. Após o registro da seleção da quantidade da ordem de qualidade, a validação pode ser concluída.

## <a name="example-scenario"></a>Cenário de exemplo

### <a name="prepare-the-scenario"></a>Preparar o cenário

Para solucionar esse cenário, você deve preparar seu sistema da seguinte maneira:

- Verifique se os dados de demonstração estão instalados no sistema e selecione a entidade legal **USMF**.
- Ativar o recurso _Gestão de qualidade para processos de depósito_ no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Configure o depósito 51 para usar o recurso _Gestão de qualidade para processos de depósito_ seguindo estas etapas:

    1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
    1. Selecione depósito 51.
    1. Na FastTab **Depósito**, defina a opção **Habilitar ordem de qualidade para processos de depósito** como *Sim*.

### <a name="quality-in-setup--move-to-the-quality-control-location"></a>Configuração na qualidade: acesse a localização de controle de qualidade

Agora você deve preparar uma configuração básica que permita a seu sistema oferecer suporte ao recurso _Gestão de qualidade para processos de depósito_ para o depósito 51. (Os dados da demonstração definem um local de gerenciamento da qualidade chamado *QMS*. Esse local é mencionado várias vezes neste cenário.) Você preparará os seguintes elementos, conforme descrito nas subseções desta seção:

- Classe de trabalho
- Modelo do trabalho
- Diretiva de localização
- Amostragem de item
- Associação de qualidade
- Itens de menu do dispositivo móvel

#### <a name="work-class-for-quality-in"></a>Classe de trabalho dentro da qualidade

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. Crie uma classe de trabalho e defina os seguintes valores:

    - **ID da classe de trabalho:** _QualityIn_
    - **Descrição:** _Amostragem de item de qualidade_
    - **Tipo de ordem de serviço:** _Amostragem de item de qualidade_

#### <a name="work-template"></a>Modelo do trabalho

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Defina o campo **Tipo de ordem de serviço** como _Amostragem de item de qualidade_.
1. Crie um modelo de trabalho e defina os seguintes valores:

    - **Modelo de trabalho:** _51 qualidade_
    - **Descrição do modelo de trabalho:** _51 qualidade_

1. Adicione uma linha ao modelo de trabalho e defina os seguintes valores:

    - **Tipo de trabalho:** _Separar_
    - **ID da classe de trabalho:** _QualityIn_

1. Adicione uma segunda linha ao modelo de trabalho e defina os seguintes valores:

    - **Tipo de trabalho:** _Colocar_
    - **ID da classe de trabalho:** _QualityIn_

#### <a name="location-directive"></a>Diretiva de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. Defina o campo **Tipo de ordem de serviço** como _Amostragem de item de qualidade_.
1. Crie uma diretiva de localização e defina os seguintes valores:

    - **Nome:** _51 para qualidade_
    - **Tipo de trabalho:** _Colocar_
    - **Local:** 5
    - **Depósito:** _51_

1. Adicione uma linha para a diretiva de localização e defina os seguintes valores:

    - **Quantidade inicial:** _1_
    - **Quantidade final:** _1000000_

1. Crie uma ação de diretiva de localização e defina o seguinte valor:

    - **Nome:** _Qualidade_

1. Para a nova ação da diretiva de localização, selecione **Editar consulta** e especifique um registro **Intervalo** com os seguintes valores:

    - **Tabela:** *Localizações*
    - **Campo:** _ID de perfil da localização_
    - **Critérios:** *QMS*

1. Selecione **OK** para salvar a consulta e salve a nova diretiva de localização.

Em seguida, você deve alterar a sequência das diretivas de localização de ordens de compra existentes para o depósito 51. Os dados da demonstração incluem duas diretivas de localização que possuem um valor **Tipo de ordem de serviço** de _Compra_: uma é chamada de _51 QMS_ e a outra é chamada de _51 PO Direct_. Para garantir que o recurso *Gestão de qualidade para processos de depósito* seja aplicado ao depósito 51, verifique se a diretiva de localização _51 QMS_ não é aplicada. Contudo, em vez de excluir essa diretiva de localização (porque você pode querer usá-la no futuro), basta alterar a sequência.

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. Defina o campo **Tipo de ordem de serviço** como _Ordem de serviço_.
1. Na lista de sequências, selecione o número de sequência 5, para a diretiva de localização _51 PO Direct_.
1. Mova a sequência selecionada para o número de sequência 4.
1. Verifique se o número de sequência da diretiva de localização _51 QMS_ agora é pelo menos 5.

#### <a name="item-sampling"></a>Amostragem de item

O recurso _Gestão de qualidade para processos de depósito_ adiciona alguns novos recursos de amostragem de item. Agora o valor **Escopo de amostragem** pode ser _Ordem_, _Remessa_ ou _Carga_, e agora o valor **Quantidade de amostragem** pode ser _Placa de licença completa_.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Amostragem de item**.
1. Crie um registro de amostra do item e defina os seguintes valores:

    - **Amostragem de item:** _3ª PL_
    - **Descrição:** _Cada terceira placa de licença_
    - **Escopo de amostragem:** _Ordem_

1. Na FastTab **Quantidade de amostragem**, defina o campo **Especificação da quantidade** como _Placa de licença completa_.
1. Na FastTab **Processo**, defina o campo **Por enésima placa de licença** como _3_.
1. Na seção **Por dimensão de armazenamento**, habilite **Depósito** e **Status do estoque**.

#### <a name="quality-associations"></a>Associações de qualidade

Crie uma associação de qualidade que usará a nova amostragem de item.

1. Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Associações de qualidade**.
1. Crie um registro de associação de qualidade e defina os seguintes valores:

    - **Tipo de referência:** _Compra_
    - **Código do item:** _Tabela_
    - **Item:** _M9201_
    - **Local:** _5_

1. Na FastTab **Processo**, defina o campo **Tipo de evento** como *Registro*.
1. Na FastTab **Condições**, defina o campo **Tipo de depósito aplicável** como *Gestão de qualidade somente para processos de depósito*.
1. Na FastTab **Processo de ordem de qualidade**, defina o campo **Política de processamento de qualidade** como _Criar ordem de qualidade_.
1. Na FastTab **Especificações**, clique com o botão direito do mouse no campo **Grupo de teste** e depois selecione **Exibir detalhes** para abrir a página **Grupos de teste**.
1. Na página **Grupos de teste**, na guia **Visão geral** da grade superior, crie um grupo de teste e defina os seguintes valores:

    - **Grupo de teste:** _QMS_
    - **Descrição:** _QMS test_
    - **Quantidade aceitável:** _100_
    - **Amostragem de item:** _3ª PL_ (Selecionar)

1. Na guia **Visão geral** da grade inferior, adicione um registro para um teste e defina os seguintes valores:

    - **Sequência:** *1*
    - **Teste:** *Medição de anexo*

1. Na guia **Teste** da grade inferior, defina os seguintes valores:

    - **Teste de variáveis:** *Aprovado/Reprovado*
    - **Resultado padrão:** *Aprovado*

1. Salve o novo grupo de teste e feche a página **Grupos de teste**.
1. Novamente na página **Associações de qualidade**, no campo **Grupo de teste**, selecione **QMS**.
1. Salve o registro.

#### <a name="mobile-device-menu-items-for-quality-in"></a>Itens de menu do dispositivo móvel dentro da qualidade

Para concluir a configuração para mover mercadorias para o local de controle de qualidade, você deve disponibilizar a amostragem de item de qualidade em um item de menu do dispositivo móvel.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione o item de menu do dispositivo móvel **Armazenamento de compra**.
1. Na FastTab **Classes de trabalho**, adicione a ID da classe de trabalho *QualityIn*.

#### <a name="summary-your-setup-to-move-goods-to-quality-control"></a>Resumo: sua configuração para mover mercadorias para o controle de qualidade

Agora você definiu uma associação de qualidade que usa o recurso *Gestão de qualidade para processos de depósito* para acionar a criação de uma ordem de qualidade. Você configurou os dados de trabalho e localização do depósito 51 para garantir que um trabalho específico seja criado quando o registro de compra for feito para o item M9201. Essa configuração garante que todas as terceiras placas de licença registradas sejam movidas para um local de qualidade (_QMS_) e que seja criada uma ordem de qualidade para a quantidade de placas de licença. Todo o resto será movido para armazenamento em vez do local de controle de qualidade.

### <a name="process-quality-management-work"></a>Trabalho de gerenciamento da qualidade do processo

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Crie uma ordem e defina os seguintes valores:

    - **Especificar conta do fornecedor:** *104*
    - **Depósito:** *51*

1. Adicione uma linha de ordem de compra e defina os seguintes valores:

    - **Item:** *M9201*
    - **Quantidade:** *20*
    - **UoM:** *ea*
    - **Depósito:** *51*

1. Anote o número da ordem de compra para que você possa usá-lo mais tarde.
1. Acesse um dispositivo móvel ou emulador que esteja executando o aplicativo móvel do Gerenciamento de Depósito e entre no depósito 51 usando *51* como a ID de usuário e *1* como a senha.
1. Acesse **Entrada \> Recebimento de compra** e digite os seguintes valores:

    - **NúmOrdemDeCompra:** o número da ordem de compra que você acabou de criar
    - **Qtd:** *5*
    - **Unidade:** *ea*

1. Continue a receber na linha, *5 ea* por vez, até que a linha seja totalmente recebida. (Um total de quatro placas será criado.)
1. Saia do aplicativo móvel de Gerenciamento de depósito.
1. Novamente no cliente Web, acesse **Compras e fornecimento \> Ordens de compra \> Todas as ordens de compra**.
1. Encontre e abra sua ordem de compra.
1. Na seção **Linhas de ordem de compra**, selecione a linha para o número do item *M9201* e depois selecione **Linhas de ordem de compra \> Detalhes do trabalho**.
1. Observe que o segundo e o terceiro cabeçalhos de trabalho criados são um trabalho de armazenamento regular, enquanto o primeiro e o quarto cabeçalhos de trabalho são um trabalho de amostragem de item de qualidade. Esse resultado é consistente com a configuração de amostragem de item, configurada para obter amostras de todas as terceiras placas de licença.

#### <a name="move-to-the-quality-control-location"></a>Mover para o local do controle de qualidade

Você agora moverá as placas de licença para os locais designados. A primeira e a quarta placas de licença são movidas para o local de controle de qualidade, enquanto a segunda e a terceira matrículas são movidas diretamente para o armazenamento.

1. Acesse um dispositivo móvel ou emulador que esteja executando o aplicativo móvel do Gerenciamento de Depósito e entre no depósito 51 usando *51* como a ID de usuário e *1* como a senha.
1. Acesse **Entrada \> Armazenamento de compra** e armazene cada placa de licença do procedimento anterior até que você feche todo o trabalho.

#### <a name="summary-process-quality-management-work"></a>Resumo: trabalho de gerenciamento da qualidade do processo

Agora você executou o trabalho de amostragem de item de qualidade para a primeira e a quarta placas de licença movendo-as para o local do controle de qualidade. Você também guardou a segunda e a terceira placas de licença. A próxima etapa é fazer o teste e o controle da ordem da qualidade.

### <a name="quality-out-setup-move-from-the-quality-control-location-to-storage-or-return"></a>Configuração fora da qualidade: mude do local do controle de qualidade para o armazenamento ou a devolução

Quando os trabalhadores relatam resultados de ordens de qualidade, o sistema gera automaticamente trabalho.

Agora você continuará com a configuração básica necessária da classe de trabalho, modelo de trabalho e diretiva de localização para permitir o gerenciamento da qualidade dos processos do depósito, para que o trabalho necessário possa ser criado para mover a quantidade da ordem de qualidade do local de controle de qualidade para um local de depósito designado.

#### <a name="work-class-for-quality-out"></a>Classe de trabalho fora da qualidade

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. Crie uma classe de trabalho e defina os seguintes valores:

    - **ID da classe de trabalho:** *QualityOut*
    - **Descrição:** *Fora de qualidade*
    - **Tipo de ordem de serviço:** *Ordem de qualidade*

#### <a name="work-templates"></a>Modelos do trabalho

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Altere o valor **Tipo de ordem de serviço** para a *Ordem de qualidade*.
1. Crie um modelo de trabalho e defina os seguintes valores:

    - **Modelo de trabalho:** *51 fora da qualidade*
    - **Descrição do modelo de trabalho:** *51 fora da qualidade*

1. Adicione uma linha e defina os seguintes valores:

    - **Tipo de trabalho:** *Separar*
    - **ID da classe de trabalho:** **QualityOut**

1. Adicione uma segunda linha e defina os seguintes valores:

    - **Tipo de trabalho:** *Colocar*
    - **ID da classe de trabalho:** *QualityOut*

#### <a name="location-directives"></a>Diretivas de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. Altere o valor **Tipo de ordem de serviço** para a *Ordem de qualidade*.
1. Crie uma diretiva de localização e defina os seguintes valores:

    - **Nome:** *51 Aprovado*
    - **Tipo de trabalho:** *Colocar*
    - **Local:** *5*
    - **Depósito:** *51*

1. No Painel de ações, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas.
1. Na guia **Intervalo**, defina os seguintes valores:

    - **Tabela:** *Ordens de qualidade*
    - **Campo:** *Status*
    - **Critérios:** *Aprovado*

1. Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.
1. Na FastTab **Linhas**, adicione uma linha e defina os seguintes valores:

    - **Quantidade inicial:** *1*
    - **Quantidade final:** *1000000*

1. Na FastTab **Ações de diretiva de localização**, adicione uma linha e defina o seguinte valor:

    - **Nome:** *Aprovado*

1. Na FastTab **Ações de diretiva de localização**, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas.
1. Na guia **Intervalo**, defina os seguintes valores:

    - **Tabela:** *Localizações*
    - **Campo:** *ID da zona*
    - **Critérios:** *Massa*

1. Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.
1. No Painel de ações, selecione **Salvar** para salvar a nova diretiva de localização.
1. Crie uma segunda diretiva de localização e defina os seguintes valores:

    - **Nome:** *51 Reprovado*
    - **Tipo de trabalho:** *Colocar*
    - **Local:** *5*
    - **Depósito:** *51*

1. No Painel de ações, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas.
1. Na guia **Intervalo**, defina os seguintes valores:

    - **Tabela:** *Ordens de qualidade*
    - **Campo:** *Status*
    - **Critérios:** *Reprovado*

1. Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.
1. Na FastTab **Linhas**, adicione uma linha e defina os seguintes valores:

    - **Quantidade inicial:** *1*
    - **Quantidade final:** *1000000*

1. Na FastTab **Ações de diretiva de localização**, adicione uma linha e defina o seguinte valor:

    - **Nome:** *Reprovado*

1. Na FastTab **Ações de diretiva de localização**, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas.
1. Na guia **Intervalo**, defina os seguintes valores:

    - **Tabela:** *Localizações*
    - **Campo:** *ID da zona*
    - **Critérios:** *Devolução*

1. Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.
1. No Painel de ações, selecione **Salvar** para salvar a nova diretiva de localização.

#### <a name="mobile-device-menu-items-for-quality-out"></a>Itens de menu do dispositivo móvel fora da qualidade

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Selecione o item de menu do dispositivo móvel **Armazenamento de QMS**.
1. Na FastTab **Classes de trabalho**, adicione a ID da classe de trabalho *QualityPut*.

Agora os funcionários do depósito poderão selecionar ordens de qualidade usando o item de menu **Armazenamento de QMS**. As mercadorias que falharam no controle de qualidade podem ser colocadas em um local de devolução e as mercadorias que passaram podem ser colocadas na localização massa-001.

#### <a name="summary-your-setup-to-move-goods-from-quality-control"></a>Resumo: sua configuração para mover mercadorias do controle de qualidade

Você configurou os dados de trabalho e localização para o depósito 51, para garantir que o trabalho seja criado automaticamente quando as ordens de qualidade forem concluídas. Essa configuração garante que cada placa de controle de qualidade seja movida para um local em massa ou um local de devolução.

### <a name="process-quality-management-work"></a>Trabalho de gerenciamento da qualidade do processo

1. Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione a primeira ordem de qualidade para as quantidades que foram registradas.
1. Selecione **Validar**. O status do teste é atualizado para *Reprovado*.
1. Acesse **Gerenciamento de depósito \> Todos os trabalhos**.
1. Abra o trabalho que você acabou de criar e observe que o valor **Tipo de ordem de serviço** é *Ordem de qualidade*. O trabalho inclui uma linha em que a localização de armazenamento é *Devolução* e o status é *Reprovado*. (Se o status da ordem de qualidade fosse *Aprovado*, o local da venda seria *Massa* em vez disso.)
1. Retorne para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione a segunda ordem de qualidade para os itens que foram registrados.
1. Selecione **Resultados** acima da grade inferior. Atualize o valor **Quantidade do resultado** para *5* e verifique se o valor **Resultado do teste** é alterado para uma marca de seleção.
1. Selecione **Validar** e feche a página.
1. Novamente na página **Ordens de qualidade**, selecione **Validar** e realize a validação. O status é atualizado para *Aprovado*.

    > [!NOTE]
    > O evento de validação aciona a criação do trabalho da ordem de qualidade para mover a quantidade do local do controle de qualidade para um novo local.

1. Acesse **Gerenciamento de depósito \> Todos os trabalhos**.
1. Selecione o trabalho que acabou de ser criado e observe que um cabeçalho de trabalho da segunda ordem de qualidade foi criado, em que a localização de armazenamento é *MASSA-001*.
1. Acesse um dispositivo móvel ou emulador que esteja executando o aplicativo móvel do Gerenciamento de Depósito e entre no depósito 51 usando *51* como a ID de usuário e *1* como a senha.
1. Acesse **Qualidade \> Armazenamento de QMS** e processe cada uma das duas placas de licença relacionadas aos dois trabalhos para que todo o trabalho seja fechado.

> [!NOTE]
> Considere adicionar a entrada fora da qualidade a um item de menu do dispositivo móvel em que o código de atividade é *Exibir lista de trabalhos abertos*. Por exemplo, consulte o item de menu do dispositivo móvel chamado **Lista de trabalho** nos dados de demonstração. Primeiro, adicione a classe de trabalho *Ordem de qualidade* a um item de menu direcionado ao usuário, porque essa classe de trabalho é necessária para que o trabalho seja mostrado na lista de trabalho. Em seguida, adicione a classe de trabalho *Ordem de qualidade* ao item de menu **Lista de trabalho**. Os usuários que têm acesso à lista de trabalho poderão escolher e processar o trabalho gerado automaticamente pela validação da ordem de qualidade.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade e não conformidade](quality-management-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]